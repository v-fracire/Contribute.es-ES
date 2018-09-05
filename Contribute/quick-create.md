---
title: 'Inicio rápido: Establecimiento y recuperación de un secreto desde Azure Key Vault | Microsoft Docs'
description: 'Inicio rápido: Establecimiento y recuperación de un secreto desde Azure Key Vault'
services: key-vault
author: syntaxc4
manager: erifkin
ms.date: 07/24/2018
ms.author: cfowler
zone_pivot_groups: keyvault-languages, keyvault-platforms
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 8b758274203748bb6e04c03dec5de38fb77947b4
ms.sourcegitcommit: b0105f322f91bb4dbde47f6da35b3c12271d5b03
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/29/2018
ms.locfileid: "43239538"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a>Inicio rápido: Establecimiento y recuperación de un secreto desde Azure Key Vault

En esta guía de inicio rápido se muestra cómo almacenar un secreto en Key Vault y cómo recuperarlo mediante una aplicación web. Para ver el valor del secreto, tendría que ejecutar esto en Azure. La guía de inicio rápido usa Node.js e identidades de Managed Service Identity (MSI)

> [!div class="checklist"]
> * Crear un almacén de claves.
> * Almacenar un secreto en el almacén de claves.
> * Recuperar un secreto del almacén de claves.
> * Crear una aplicación web de Azure.
> * [Habilitar identidades de servicio administradas](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).
> * Conceder los permisos necesarios para que la aplicación web lea datos del almacén de claves.

Antes de continuar, asegúrese de que está familiarizado con los [conceptos básicos](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).

>[!NOTE]
Para entender por qué el siguiente tutorial es un procedimiento recomendado, es necesario comprender varios conceptos. Key Vault es un repositorio central para almacenar secretos mediante programación. Pero para poder hacer esto, las aplicaciones y los usuarios tienen primero que autenticarse en Key Vault, es decir, presentar un secreto. Para seguir los procedimientos recomendados de seguridad debe cambiar este secreto periódicamente. Pero con [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview) a las aplicaciones que se ejecutan en Azure se les da una identidad que Azure administra automáticamente. Esto ayuda a solucionar el **problema de introducción de secretos** por el que los usuarios o aplicaciones pueden seguir procedimientos recomendados y no tener que preocuparse por el cambio del primer secreto

## <a name="prerequisites"></a>Requisitos previos

::: zone pivot="nodejs"
* [Node JS](https://nodejs.org/en/) ::: zone-end

::: zone pivot="dotnet, windows"
* [Visual Studio 2017, versión 15.7.3 o posterior,](https://www.microsoft.com/net/download/windows) con las siguientes cargas de trabajo:
  * ASP.NET y desarrollo web
  * Desarrollo multiplataforma de .NET Core
* [SDK de .NET Core 2.1 o posterior](https://www.microsoft.com/net/download/windows) :::zone-end

::: zone pivot="dotnet, mac"
* Consulte las [novedades de Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/).
:::zone-end

* Git ([descargar](https://git-scm.com/downloads)).
* Una suscripción de Azure. Si no tiene una suscripción a Azure, cree una [cuenta gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) antes de empezar.
* [CLI de Azure](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) versión 2.0.4 o posterior. Está disponible para Windows, Mac y Linux.

## <a name="login-to-azure"></a>Inicio de sesión en Azure

Para iniciar sesión en Azure mediante la CLI puede escribir:

```azurecli
az login
```

## <a name="create-resource-group"></a>Creación de un grupo de recursos

Cree un grupo de recursos con el comando [az group create](/cli/azure/group#az-group-create). Un grupo de recursos de Azure es un contenedor lógico donde se implementan y administran recursos de Azure.

Seleccione el nombre del grupo de recursos y rellene el marcador de posición.
En el ejemplo siguiente se crea un grupo de recursos llamado *<YourResourceGroupName>* en la ubicación *eastus*.

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

El grupo de recursos que acaba de crear se utiliza a lo largo de este tutorial.

## <a name="create-an-azure-key-vault"></a>Creación de una instancia de Azure Key Vault

A continuación, creará una instancia de Key Vault en el grupo de recursos creado en el paso anterior. Aunque "ContosoKeyVault" se utiliza como nombre de la instancia de Key Vault a lo largo de este artículo, tiene que usar un nombre único. Proporcione la siguiente información:

* Nombre del almacén: **seleccione aquí el nombre de la instancia de Key Vault**.
* Nombre del grupo de recursos: **seleccione aquí el nombre del grupo de recursos**.
* Ubicación: **Este de EE. UU**.

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

En este momento, su cuenta de Azure es la única autorizada para realizar operaciones en este nuevo almacén.

## <a name="add-a-secret-to-key-vault"></a>Adición de un secreto a Key Vault

Vamos a agregar un secreto para ayudar a ilustrar cómo funciona. Se puede almacenar una cadena de conexión de SQL o cualquier otra información que necesite guardar de forma segura, pero que esté disponibles para la aplicación. En este tutorial, la contraseña se llamará **AppSecret** y almacenará el valor de **MySecret**.

Escriba los siguientes comandos para crear un secreto en Key Vault denominado **AppSecret** que almacene el valor **MySecret**:

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

Para ver el valor contenido en el secreto como texto sin formato:

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

Este comando muestra la información secreta, URI incluido. Después de completar estos pasos, debe tener un identificador URI para un secreto en una instancia de Azure Key Vault. Anote esta información. La necesitará en otro paso más adelante.

## <a name="clone-the-repo"></a>Clonación del repositorio

Clone el repositorio con el fin de realizar una copia local para editar el origen; para ello, debe ejecutar el comando siguiente:

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

::: zone pivot="nodejs"

## <a name="install-dependencies"></a>Instalación de dependencias

Aquí se instalan las dependencias. Ejecute los siguientes comandos cd key-vault-node-quickstart npm install

Este proyecto utiliza 2 módulos de Node:

* [ms-rest-azure](https://www.npmjs.com/package/ms-rest-azure) 
* [azure-keyvault](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a>Publicación de la aplicación web en Azure

A continuación se muestran los pasos que deberá seguir:

* El primer paso consiste en crear un plan de [Azure App Service](https://azure.microsoft.com/services/app-service/). Puede almacenar varias aplicaciones web en este plan.

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* A continuación, se crea una aplicación web. En el siguiente ejemplo, reemplace <app_name> por un nombre único global de aplicación (los caracteres válidos son a-z, 0-9 y -). El tiempo de ejecución se establece en NODE|6.9. Para ver todos los entornos de tiempo de ejecución admitidos, ejecute az webapp list-runtimes.

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    Cuando se haya creado la aplicación web, la CLI de Azure mostrará información similar a la del ejemplo siguiente:

    ```json
    {
      "availabilityState": "Normal",
      "clientAffinityEnabled": true,
      "clientCertEnabled": false,
      "cloningInfo": null,
      "containerSize": 0,
      "dailyMemoryTimeQuota": 0,
      "defaultHostName": "<app_name>.azurewebsites.net",
      "enabled": true,
      "deploymentLocalGitUrl": "https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git"
      < JSON data removed for brevity. >
    }
    ```
    Vaya a la aplicación web recién creada y ya debería ver una aplicación web en funcionamiento. Reemplace <app_name> por un nombre de aplicación único.

    ```text
    http://<app name>.azurewebsites.net
    ```
    El comando anterior crea también una aplicación habilitada para Git que le permite implementar en Azure desde el repositorio de Git local. 
    El repositorio de Git local está configurado con la dirección url "https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git".

* Cree un usuario de implementación. Una vez completado el comando anterior puede agregar una instancia remota de Azure en el repositorio de Git local. Reemplace <url> por la dirección URL del Git remoto que obtuvo en Habilitación de Git para la aplicación.

    ```bash
    git remote add azure <url>
    ```
::: zone-end

::: zone pivot="dotnet"

## <a name="open-and-edit-the-solution"></a>Apertura y edición de la solución

Edite el archivo program.cs para ejecutar el ejemplo con su nombre del almacén de claves específico:

1. Vaya a la carpeta key-vault-dotnet-core-quickstart.
2. Abra el archivo key-vault-dotnet-core-quickstart.sln en Visual Studio 2017.
3. Abra el archivo Program.cs y actualice el marcador de posición *YourKeyVaultName* con el nombre del almacén de claves que creó anteriormente.

Esta solución usa las bibliotecas de NuGet [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) y [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault).

## <a name="run-the-app"></a>Ejecución de la aplicación

En el menú principal de Visual Studio 2017, elija **Depurar** > **Iniciar** sin depurar. Cuando aparezca el explorador, vaya a la página **Acerca de**. Aparecerá el valor de **AppSecret**.

## <a name="publish-the-web-application-to-azure"></a>Publicación de la aplicación web en Azure

Publique esta aplicación en Azure para verla en vivo como una aplicación web y para ver también que puede capturar el valor del secreto:

1. En Visual Studio, seleccione el proyecto **key-vault-dotnet-core-quickstart**.
2. Seleccione **Publicar** > **Iniciar**.
3. Cree una nueva instancia de **App Service** y seleccione **Publicar**.
4. Cambie el nombre de la aplicación a **keyvaultdotnetcorequickstart**.
5. Seleccione **Crear**.

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]

::: zone-end

## <a name="enable-managed-service-identities"></a>Habilitación de las identidades de servicio administradas

Azure Key Vault proporciona una forma de almacenar de forma segura credenciales y otras claves y secretos, pero el código tiene que autenticarse en Azure Key Vault para recuperarlos. Managed Service Identity facilita esta labor, ya que proporciona a los servicios de Azure una identidad administrada automáticamente en Azure Active Directory (Azure AD). Puede usar esta identidad para autenticar cualquier servicio que admita la autenticación de Azure AD, incluido Key Vault, sin necesidad de tener credenciales en el código.

1. Vuelva a la CLI de Azure.
2. Ejecute el comando assign-identity para crear la identidad de esta aplicación:

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
>Este comando es el equivalente de ir al portal y cambiar la **Identidad de servicio administrada** a **Activado** en las propiedades de la aplicación web.

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a>Asignación de permisos a una aplicación para leer secretos de Key Vault

Tome nota de la salida cuando publique la aplicación en Azure. Debe tener el formato:

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

Luego, ejecute este comando con el nombre del almacén de claves y el valor de **PrincipalId**:

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

::: zone pivot="nodejs"
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a>Implementación de la aplicación de Node en Azure y recuperación del valor del secreto

Ahora que ya está todo establecido, ejecute el siguiente comando para implementar la aplicación en Azure.

```bash
git push azure master
```

Después de esto, si navega a https://<app_name>.azurewebsites.net podrá ver el valor del secreto.
Asegúrese de reemplazar el nombre <YourKeyVaultName> por el nombre de su almacén

::: zone pivot="dotnet" Ahora, cuando ejecute la aplicación debería ver el valor del secreto recuperado.
::: zone-end

## <a name="next-steps"></a>Pasos siguientes

::: zone pivot="nodejs"
* [Página principal de Azure Key Vault](https://azure.microsoft.com/services/key-vault/)
* [Documentación de Azure Key Vault](https://docs.microsoft.com/azure/key-vault/)
* [Azure SDK For Node](https://docs.microsoft.com/javascript/api/overview/azure/key-vault) (SDK de Azure para Node)
* [Azure REST API Reference](https://docs.microsoft.com/rest/api/keyvault/) (Referencia de API REST en Azure) ::: zone-end

::: zone pivot="dotnet"
* [Página principal de Azure Key Vault](https://azure.microsoft.com/services/key-vault/)
* [Documentación de Azure Key Vault](https://docs.microsoft.com/azure/key-vault/)
* [SDK de Azure para .NET](https://github.com/Azure/azure-sdk-for-net)
* [Azure REST API Reference](https://docs.microsoft.com/rest/api/keyvault/) (Referencia de API REST en Azure) ::: zone-end