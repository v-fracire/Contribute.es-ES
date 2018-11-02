---
title: 'Inicio rápido: Establecimiento y recuperación de un secreto desde Azure Key Vault | Microsoft Docs'
description: 'Inicio rápido: Establecimiento y recuperación de un secreto desde Azure Key Vault'
services: key-vault
author: syntaxc4
manager: erifkin
ms.date: 07/24/2018
ms.author: cfowler
zone_pivot_groups: keyvault-languages
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 497631fe46ac4e2c9c495a609547753a84d662bf
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805755"
---
# <a name="quickstart-set-and-retrieve-a-secret-from-azure-key-vault"></a><span data-ttu-id="83543-103">Inicio rápido: Establecimiento y recuperación de un secreto desde Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="83543-103">Quickstart: Set and retrieve a secret from Azure Key Vault</span></span>

<span data-ttu-id="83543-104">En esta guía de inicio rápido se muestra cómo almacenar un secreto en Key Vault y cómo recuperarlo mediante una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="83543-104">This quickstart shows you how to store a secret in Key Vault and how to retrieve it using a Web app.</span></span> <span data-ttu-id="83543-105">Para ver el valor del secreto, tendría que ejecutar esto en Azure.</span><span class="sxs-lookup"><span data-stu-id="83543-105">To see the secret value you would have to run this on Azure.</span></span> <span data-ttu-id="83543-106">En la guía de inicio rápido se usa Node.js e identidades de Managed Service Identity (MSI).</span><span class="sxs-lookup"><span data-stu-id="83543-106">The quickstart uses Node.js and Managed service identities (MSIs).</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="83543-107">Crear un almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="83543-107">Create a Key Vault.</span></span>
> * <span data-ttu-id="83543-108">Almacenar un secreto en el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="83543-108">Store a secret in the Key Vault.</span></span>
> * <span data-ttu-id="83543-109">Recuperar un secreto del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="83543-109">Retrieve a secret from Key Vault.</span></span>
> * <span data-ttu-id="83543-110">Crear una aplicación web de Azure.</span><span class="sxs-lookup"><span data-stu-id="83543-110">Create an Azure Web Application.</span></span>
> * <span data-ttu-id="83543-111">[Habilitar identidades de servicio administradas](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span><span class="sxs-lookup"><span data-stu-id="83543-111">[Enable managed service identities](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview).</span></span>
> * <span data-ttu-id="83543-112">Conceder los permisos necesarios para que la aplicación web lea datos del almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="83543-112">Grant the required permissions for the web application to read data from Key vault.</span></span>

<span data-ttu-id="83543-113">Antes de continuar, asegúrese de que está familiarizado con los [conceptos básicos](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span><span class="sxs-lookup"><span data-stu-id="83543-113">Before you proceed make sure that you are familiar with the [basic concepts](https://docs.microsoft.com/azure/key-vault/key-vault-whatis#basic-concepts).</span></span>

> [!NOTE]
> <span data-ttu-id="83543-114">Para entender por qué el siguiente tutorial es un procedimiento recomendado, es necesario comprender varios conceptos.</span><span class="sxs-lookup"><span data-stu-id="83543-114">To understand why the below tutorial is the best practice we need to understand a few concepts.</span></span> <span data-ttu-id="83543-115">Key Vault es un repositorio central para almacenar secretos mediante programación.</span><span class="sxs-lookup"><span data-stu-id="83543-115">Key Vault is a central repository to store secrets programmatically.</span></span> <span data-ttu-id="83543-116">Pero para poder hacer esto, las aplicaciones y los usuarios tienen primero que autenticarse en Key Vault, es decir, presentar un secreto.</span><span class="sxs-lookup"><span data-stu-id="83543-116">But to do so applications / users need to first authenticate to Key Vault i.e. present a secret.</span></span> <span data-ttu-id="83543-117">Para seguir los procedimientos recomendados de seguridad debe cambiar este secreto periódicamente.</span><span class="sxs-lookup"><span data-stu-id="83543-117">To follow security best practices this first secret needs to be rotated periodically as well.</span></span> <span data-ttu-id="83543-118">Pero con [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview), a las aplicaciones que se ejecutan en Azure se les da una identidad que Azure administra de forma automática.</span><span class="sxs-lookup"><span data-stu-id="83543-118">But with [Managed Service Identity](https://docs.microsoft.com/azure/active-directory/managed-service-identity/overview), applications that run in Azure are given an identity which is automatically managed by Azure.</span></span> <span data-ttu-id="83543-119">Esto ayuda a solucionar el **problema de introducción de secretos** por el que los usuarios o aplicaciones pueden seguir procedimientos recomendados y no tener que preocuparse por el cambio del primer secreto</span><span class="sxs-lookup"><span data-stu-id="83543-119">This helps solve the **Secret Introduction Problem** where users / applications can follow best practices and not have to worry about rotating the first secret</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83543-120">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="83543-120">Prerequisites</span></span>

::: zone pivot="nodejs"
* [<span data-ttu-id="83543-121">Node JS</span><span class="sxs-lookup"><span data-stu-id="83543-121">Node JS</span></span>](https://nodejs.org/en/)
::: zone-end
::: zone pivot="dotnet"
* <span data-ttu-id="83543-122">[Visual Studio 2017, versión 15.7.3 o posterior,](https://www.microsoft.com/net/download/windows) con las siguientes cargas de trabajo:</span><span class="sxs-lookup"><span data-stu-id="83543-122">[Visual Studio 2017 version 15.7.3 or later](https://www.microsoft.com/net/download/windows) with the following workloads:</span></span>
  * <span data-ttu-id="83543-123">ASP.NET y desarrollo web</span><span class="sxs-lookup"><span data-stu-id="83543-123">ASP.NET and web development</span></span>
  * <span data-ttu-id="83543-124">Desarrollo multiplataforma de .NET Core</span><span class="sxs-lookup"><span data-stu-id="83543-124">.NET Core cross-platform development</span></span>
* [<span data-ttu-id="83543-125">SDK de .NET Core 2.1 o posterior</span><span class="sxs-lookup"><span data-stu-id="83543-125">.NET Core 2.1 SDK or later</span></span>](https://www.microsoft.com/net/download/windows)
::: zone-end
* <span data-ttu-id="83543-126">Git ([descargar](https://git-scm.com/downloads)).</span><span class="sxs-lookup"><span data-stu-id="83543-126">Git ([download](https://git-scm.com/downloads)).</span></span>
* <span data-ttu-id="83543-127">Una suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="83543-127">An Azure subscription.</span></span> <span data-ttu-id="83543-128">Si no tiene una suscripción a Azure, cree una [cuenta gratuita](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) antes de empezar.</span><span class="sxs-lookup"><span data-stu-id="83543-128">If you don't have an Azure subscription, create a [free account](https://azure.microsoft.com/free/?WT.mc_id=A261C142F) before you begin.</span></span>
* <span data-ttu-id="83543-129">[CLI de Azure](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) versión 2.0.4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="83543-129">[Azure CLI](https://docs.microsoft.com/cli/azure/install-azure-cli?view=azure-cli-latest) version 2.0.4 or later.</span></span> <span data-ttu-id="83543-130">Está disponible para Windows, Mac y Linux.</span><span class="sxs-lookup"><span data-stu-id="83543-130">This is available for Windows, Mac, and Linux.</span></span>

## <a name="login-to-azure"></a><span data-ttu-id="83543-131">Inicio de sesión en Azure</span><span class="sxs-lookup"><span data-stu-id="83543-131">Login to Azure</span></span>

<span data-ttu-id="83543-132">Para iniciar sesión en Azure mediante la CLI puede escribir:</span><span class="sxs-lookup"><span data-stu-id="83543-132">To log in to Azure using the CLI, you can type:</span></span>

```azurecli
az login
```

## <a name="create-resource-group"></a><span data-ttu-id="83543-133">Creación de un grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="83543-133">Create resource group</span></span>

<span data-ttu-id="83543-134">Cree un grupo de recursos con el comando [az group create](/cli/azure/group#az-group-create).</span><span class="sxs-lookup"><span data-stu-id="83543-134">Create a resource group with the [az group create](/cli/azure/group#az-group-create) command.</span></span> <span data-ttu-id="83543-135">Un grupo de recursos de Azure es un contenedor lógico donde se implementan y administran recursos de Azure.</span><span class="sxs-lookup"><span data-stu-id="83543-135">An Azure resource group is a logical container into which Azure resources are deployed and managed.</span></span>

<span data-ttu-id="83543-136">Seleccione el nombre del grupo de recursos y rellene el marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="83543-136">Please select a Resource Group name and fill in the placeholder.</span></span>
<span data-ttu-id="83543-137">En el ejemplo siguiente se crea un grupo de recursos llamado *<YourResourceGroupName>* en la ubicación *eastus*.</span><span class="sxs-lookup"><span data-stu-id="83543-137">The following example creates a resource group named *<YourResourceGroupName>* in the *eastus* location.</span></span>

```azurecli
# To list locations: az account list-locations --output table
az group create --name "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="83543-138">El grupo de recursos que acaba de crear se utiliza a lo largo de este tutorial.</span><span class="sxs-lookup"><span data-stu-id="83543-138">The resource group you just created is used throughout this tutorial.</span></span>

## <a name="create-an-azure-key-vault"></a><span data-ttu-id="83543-139">Creación de una instancia de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="83543-139">Create an Azure Key Vault</span></span>

<span data-ttu-id="83543-140">A continuación, creará una instancia de Key Vault en el grupo de recursos creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="83543-140">Next you create a Key Vault using the resource group created in the previous step.</span></span> <span data-ttu-id="83543-141">Aunque "ContosoKeyVault" se utiliza como nombre de la instancia de Key Vault a lo largo de este artículo, tiene que usar un nombre único.</span><span class="sxs-lookup"><span data-stu-id="83543-141">Although “ContosoKeyVault” is used as the name for the Key Vault throughout this article, you have to use a unique name.</span></span> <span data-ttu-id="83543-142">Proporcione la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="83543-142">Provide the following information:</span></span>

* <span data-ttu-id="83543-143">Nombre del almacén: **seleccione aquí el nombre de la instancia de Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="83543-143">Vault name - **Select a Key Vault Name here**.</span></span>
* <span data-ttu-id="83543-144">Nombre del grupo de recursos: **seleccione aquí el nombre del grupo de recursos**.</span><span class="sxs-lookup"><span data-stu-id="83543-144">Resource group name - **Select a Resource Group Name here**.</span></span>
* <span data-ttu-id="83543-145">Ubicación: **Este de EE. UU**.</span><span class="sxs-lookup"><span data-stu-id="83543-145">The location - **East US**.</span></span>

```azurecli
az keyvault create --name "<YourKeyVaultName>" --resource-group "<YourResourceGroupName>" --location "East US"
```

<span data-ttu-id="83543-146">En este momento, su cuenta de Azure es la única autorizada para realizar operaciones en este nuevo almacén.</span><span class="sxs-lookup"><span data-stu-id="83543-146">At this point, your Azure account is the only one authorized to perform any operations on this new vault.</span></span>

## <a name="add-a-secret-to-key-vault"></a><span data-ttu-id="83543-147">Adición de un secreto a Key Vault</span><span class="sxs-lookup"><span data-stu-id="83543-147">Add a secret to key vault</span></span>

<span data-ttu-id="83543-148">Vamos a agregar un secreto para ayudar a ilustrar cómo funciona.</span><span class="sxs-lookup"><span data-stu-id="83543-148">We're adding a secret to help illustrate how this works.</span></span> <span data-ttu-id="83543-149">Se puede almacenar una cadena de conexión de SQL o cualquier otra información que necesite guardar de forma segura, pero que esté disponibles para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="83543-149">You could be storing a SQL connection string or any other information that you need to keep securely but make available to your application.</span></span> <span data-ttu-id="83543-150">En este tutorial, la contraseña se llamará **AppSecret** y almacenará el valor de **MySecret**.</span><span class="sxs-lookup"><span data-stu-id="83543-150">In this tutorial, the password will be called **AppSecret** and will store the value of **MySecret** in it.</span></span>

<span data-ttu-id="83543-151">Escriba los siguientes comandos para crear un secreto en Key Vault denominado **AppSecret** que almacene el valor **MySecret**:</span><span class="sxs-lookup"><span data-stu-id="83543-151">Type the commands below to create a secret in Key Vault called **AppSecret** that will store the value **MySecret**:</span></span>

```azurecli
az keyvault secret set --vault-name "<YourKeyVaultName>" --name "AppSecret" --value "MySecret"
```

<span data-ttu-id="83543-152">Para ver el valor contenido en el secreto como texto sin formato:</span><span class="sxs-lookup"><span data-stu-id="83543-152">To view the value contained in the secret as plain text:</span></span>

```azurecli
az keyvault secret show --name "AppSecret" --vault-name "<YourKeyVaultName>"
```

<span data-ttu-id="83543-153">Este comando muestra la información secreta, URI incluido.</span><span class="sxs-lookup"><span data-stu-id="83543-153">This command shows the secret information including the URI.</span></span> <span data-ttu-id="83543-154">Después de completar estos pasos, debe tener un identificador URI para un secreto en una instancia de Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="83543-154">After completing these steps, you should have a URI to a secret in an Azure Key Vault.</span></span> <span data-ttu-id="83543-155">Anote esta información.</span><span class="sxs-lookup"><span data-stu-id="83543-155">Write this information down.</span></span> <span data-ttu-id="83543-156">La necesitará en otro paso más adelante.</span><span class="sxs-lookup"><span data-stu-id="83543-156">You need it in a later step.</span></span>

## <a name="clone-the-repo"></a><span data-ttu-id="83543-157">Clonación del repositorio</span><span class="sxs-lookup"><span data-stu-id="83543-157">Clone the Repo</span></span>

<span data-ttu-id="83543-158">Clone el repositorio con el fin de realizar una copia local para editar el origen; para ello, debe ejecutar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="83543-158">Clone the repo in order to make a local copy for you to edit the source by running the following command:</span></span>

```bash
git clone https://github.com/Azure-Samples/key-vault-node-quickstart.git
```

::: zone pivot="nodejs"

## <a name="install-dependencies"></a><span data-ttu-id="83543-159">Instalación de dependencias</span><span class="sxs-lookup"><span data-stu-id="83543-159">Install dependencies</span></span>

<span data-ttu-id="83543-160">Aquí se instalan las dependencias.</span><span class="sxs-lookup"><span data-stu-id="83543-160">Here we install the dependencies.</span></span> <span data-ttu-id="83543-161">Ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="83543-161">Run the following commands:</span></span>

    cd key-vault-node-quickstart
    npm install

<span data-ttu-id="83543-162">Este proyecto utiliza 2 módulos de Node:</span><span class="sxs-lookup"><span data-stu-id="83543-162">This project used 2 node modules:</span></span>

* [<span data-ttu-id="83543-163">ms-rest-azure</span><span class="sxs-lookup"><span data-stu-id="83543-163">ms-rest-azure</span></span>](https://www.npmjs.com/package/ms-rest-azure) 
* [<span data-ttu-id="83543-164">azure-keyvault</span><span class="sxs-lookup"><span data-stu-id="83543-164">azure-keyvault</span></span>](https://www.npmjs.com/package/azure-keyvault)

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="83543-165">Publicación de la aplicación web en Azure</span><span class="sxs-lookup"><span data-stu-id="83543-165">Publish the web application to Azure</span></span>

<span data-ttu-id="83543-166">A continuación se muestran los pasos que se deben seguir para publicar la aplicación en Azure.</span><span class="sxs-lookup"><span data-stu-id="83543-166">Below are the few steps we need to do to publish the application to Azure.</span></span>

* <span data-ttu-id="83543-167">El primer paso consiste en crear un plan de [Azure App Service](https://azure.microsoft.com/services/app-service/).</span><span class="sxs-lookup"><span data-stu-id="83543-167">The 1st step is to create a [Azure App Service](https://azure.microsoft.com/services/app-service/) Plan.</span></span> <span data-ttu-id="83543-168">Puede almacenar varias aplicaciones web en este plan.</span><span class="sxs-lookup"><span data-stu-id="83543-168">You can store multiple web apps in this plan.</span></span>

    ```azurecli
    az appservice plan create --name myAppServicePlan --resource-group myResourceGroup
    ```
* <span data-ttu-id="83543-169">A continuación, se crea una aplicación web.</span><span class="sxs-lookup"><span data-stu-id="83543-169">Next we create a web app.</span></span> <span data-ttu-id="83543-170">En el siguiente ejemplo, reemplace <app_name> por un nombre único global de aplicación (los caracteres válidos son a-z, 0-9 y -).</span><span class="sxs-lookup"><span data-stu-id="83543-170">In the following example, replace <app_name> with a globally unique app name (valid characters are a-z, 0-9, and -).</span></span> <span data-ttu-id="83543-171">El tiempo de ejecución se establece en NODE|6.9.</span><span class="sxs-lookup"><span data-stu-id="83543-171">The runtime is set to NODE|6.9.</span></span> <span data-ttu-id="83543-172">Para ver todos los entornos de ejecución admitidos, ejecute `az webapp list-runtimes`.</span><span class="sxs-lookup"><span data-stu-id="83543-172">To see all supported runtimes, run `az webapp list-runtimes`</span></span>

    ```azurecli
    az webapp create --resource-group myResourceGroup --plan myAppServicePlan --name <app_name> --runtime "NODE|6.9" --deployment-local-git
    ```

    <span data-ttu-id="83543-173">Cuando se haya creado la aplicación web, la CLI de Azure mostrará información similar a la del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="83543-173">When the web app has been created, the Azure CLI shows output similar to the following example:</span></span>

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
    <span data-ttu-id="83543-174">Vaya a la aplicación web recién creada y ya debería ver una aplicación web en funcionamiento.</span><span class="sxs-lookup"><span data-stu-id="83543-174">Browse to your newly created web app and you should see a functioning web app.</span></span> <span data-ttu-id="83543-175">Reemplace <app_name> por un nombre de aplicación único.</span><span class="sxs-lookup"><span data-stu-id="83543-175">Replace <app_name> with a unique app name.</span></span>

    ```text
    http://<app name>.azurewebsites.net
    ```
    <span data-ttu-id="83543-176">El comando anterior crea también una aplicación habilitada para Git que le permite implementar en Azure desde el repositorio de Git local.</span><span class="sxs-lookup"><span data-stu-id="83543-176">The above command also creates a Git-enabled app which allows you to deploy to azure from your local git.</span></span> 
    <span data-ttu-id="83543-177">El repositorio de Git local está configurado con la dirección url "https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git".</span><span class="sxs-lookup"><span data-stu-id="83543-177">Local git is configured with url of 'https://<username>@<app_name>.scm.azurewebsites.net/<app_name>.git'</span></span>

* <span data-ttu-id="83543-178">Cree un usuario de implementación. Una vez completado el comando anterior puede agregar una instancia remota de Azure en el repositorio de Git local.</span><span class="sxs-lookup"><span data-stu-id="83543-178">Create a deployment user After the previous command is completed you can add add an Azure remote to your local Git repository.</span></span> <span data-ttu-id="83543-179">Reemplace <url> por la dirección URL del Git remoto que obtuvo en Habilitación de Git para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="83543-179">Replace <url> with the URL of the Git remote that you got from Enable Git for your app.</span></span>

    ```bash
    git remote add azure <url>
    ```
    
::: zone-end

::: zone pivot="dotnet"
## <a name="open-and-edit-the-solution"></a><span data-ttu-id="83543-180">Apertura y edición de la solución</span><span class="sxs-lookup"><span data-stu-id="83543-180">Open and edit the solution</span></span>

<span data-ttu-id="83543-181">Edite el archivo program.cs para ejecutar el ejemplo con su nombre del almacén de claves específico:</span><span class="sxs-lookup"><span data-stu-id="83543-181">Edit the program.cs file to run the sample with your specific key vault name:</span></span>

1. <span data-ttu-id="83543-182">Vaya a la carpeta key-vault-dotnet-core-quickstart.</span><span class="sxs-lookup"><span data-stu-id="83543-182">Browse to the folder key-vault-dotnet-core-quickstart.</span></span>
2. <span data-ttu-id="83543-183">Abra el archivo key-vault-dotnet-core-quickstart.sln en Visual Studio 2017.</span><span class="sxs-lookup"><span data-stu-id="83543-183">Open the key-vault-dotnet-core-quickstart.sln file in Visual Studio 2017.</span></span>
3. <span data-ttu-id="83543-184">Abra el archivo Program.cs y actualice el marcador de posición *YourKeyVaultName* con el nombre del almacén de claves que creó anteriormente.</span><span class="sxs-lookup"><span data-stu-id="83543-184">Open the Program.cs file and update the placeholder *YourKeyVaultName* with the name of your key vault that you created earlier.</span></span>

<span data-ttu-id="83543-185">Esta solución usa las bibliotecas de NuGet [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) y [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault).</span><span class="sxs-lookup"><span data-stu-id="83543-185">This solution uses [AppAuthentication](https://www.nuget.org/packages/Microsoft.Azure.Services.AppAuthentication) and [KeyVault](https://www.nuget.org/packages/Microsoft.Azure.KeyVault) NuGet libraries.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="83543-186">Ejecución de la aplicación</span><span class="sxs-lookup"><span data-stu-id="83543-186">Run the app</span></span>

<span data-ttu-id="83543-187">En el menú principal de Visual Studio 2017, elija **Depurar** > **Iniciar** sin depurar.</span><span class="sxs-lookup"><span data-stu-id="83543-187">From the main menu of Visual Studio 2017, select **Debug** > **Start** without debugging.</span></span> <span data-ttu-id="83543-188">Cuando aparezca el explorador, vaya a la página **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="83543-188">When the browser appears, go to the **About** page.</span></span> <span data-ttu-id="83543-189">Aparecerá el valor de **AppSecret**.</span><span class="sxs-lookup"><span data-stu-id="83543-189">The value for **AppSecret** is displayed.</span></span>

## <a name="publish-the-web-application-to-azure"></a><span data-ttu-id="83543-190">Publicación de la aplicación web en Azure</span><span class="sxs-lookup"><span data-stu-id="83543-190">Publish the web application to Azure</span></span>

<span data-ttu-id="83543-191">Publique esta aplicación en Azure para verla en vivo como una aplicación web y para ver también que puede capturar el valor del secreto:</span><span class="sxs-lookup"><span data-stu-id="83543-191">Publish this app to Azure to see it live as a web app, and to see that you can fetch the secret value:</span></span>

1. <span data-ttu-id="83543-192">En Visual Studio, seleccione el proyecto **key-vault-dotnet-core-quickstart**.</span><span class="sxs-lookup"><span data-stu-id="83543-192">In Visual Studio, select the **key-vault-dotnet-core-quickstart** project.</span></span>
2. <span data-ttu-id="83543-193">Seleccione **Publicar** > **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="83543-193">Select **Publish** > **Start**.</span></span>
3. <span data-ttu-id="83543-194">Cree una nueva instancia de **App Service** y seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="83543-194">Create a new **App Service**, and then select **Publish**.</span></span>
4. <span data-ttu-id="83543-195">Cambie el nombre de la aplicación a **keyvaultdotnetcorequickstart**.</span><span class="sxs-lookup"><span data-stu-id="83543-195">Change the app name to **keyvaultdotnetcorequickstart**.</span></span>
5. <span data-ttu-id="83543-196">Seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="83543-196">Select **Create**.</span></span>

>[!VIDEO https://sec.ch9.ms/ch9/e93d/a6ac417f-2e63-4125-a37a-8f34bf0fe93d/KeyVault_high.mp4]
::: zone-end

## <a name="enable-managed-service-identities"></a><span data-ttu-id="83543-197">Habilitación de las identidades de servicio administradas</span><span class="sxs-lookup"><span data-stu-id="83543-197">Enable managed service identities</span></span>

<span data-ttu-id="83543-198">Azure Key Vault proporciona una forma de almacenar de forma segura credenciales y otras claves y secretos, pero el código tiene que autenticarse en Azure Key Vault para recuperarlos.</span><span class="sxs-lookup"><span data-stu-id="83543-198">Azure Key Vault provides a way to securely store credentials and other keys and secrets, but your code needs to authenticate to Azure Key Vault to retrieve them.</span></span> <span data-ttu-id="83543-199">Managed Service Identity facilita esta labor, ya que proporciona a los servicios de Azure una identidad administrada automáticamente en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="83543-199">Managed Service Identity makes this easier by giving Azure services an automatically managed identity in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="83543-200">Puede usar esta identidad para autenticar cualquier servicio que admita la autenticación de Azure AD, incluido Key Vault, sin necesidad de tener credenciales en el código.</span><span class="sxs-lookup"><span data-stu-id="83543-200">You can use this identity to authenticate to any service that supports Azure AD authentication, including Key Vault, without having any credentials in your code.</span></span>

1. <span data-ttu-id="83543-201">Vuelva a la CLI de Azure.</span><span class="sxs-lookup"><span data-stu-id="83543-201">Return to the Azure CLI.</span></span>
2. <span data-ttu-id="83543-202">Ejecute el comando assign-identity para crear la identidad de esta aplicación:</span><span class="sxs-lookup"><span data-stu-id="83543-202">Run the assign-identity command to create the identity for this application:</span></span>

   ```azurecli
   az webapp identity assign --name "keyvaultdotnetcorequickstart" --resource-group "<YourResourceGroupName>"
   ```

>[!NOTE]
><span data-ttu-id="83543-203">Este comando es el equivalente de ir al portal y cambiar la **Identidad de servicio administrada** a **Activado** en las propiedades de la aplicación web.</span><span class="sxs-lookup"><span data-stu-id="83543-203">The command in this procedure is the equivalent of going to the portal and switching **Managed service identity** to **On** in the web application properties.</span></span>

## <a name="assign-permissions-to-your-application-to-read-secrets-from-key-vault"></a><span data-ttu-id="83543-204">Asignación de permisos a una aplicación para leer secretos de Key Vault</span><span class="sxs-lookup"><span data-stu-id="83543-204">Assign permissions to your application to read secrets from Key Vault</span></span>

<span data-ttu-id="83543-205">Tome nota de la salida cuando publique la aplicación en Azure.</span><span class="sxs-lookup"><span data-stu-id="83543-205">Make a note of the output when you publish the application to Azure.</span></span> <span data-ttu-id="83543-206">Debe tener el formato:</span><span class="sxs-lookup"><span data-stu-id="83543-206">It should be of the format:</span></span>

```json
        {
          "principalId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
          "type": "SystemAssigned"
        }
```

<span data-ttu-id="83543-207">Luego, ejecute este comando con el nombre del almacén de claves y el valor de **PrincipalId**:</span><span class="sxs-lookup"><span data-stu-id="83543-207">Then, run this command by using the name of your key vault and the value of **PrincipalId**:</span></span>

```azurecli
az keyvault set-policy --name '<YourKeyVaultName>' --object-id <PrincipalId> --secret-permissions get
```

::: zone pivot="nodejs"
## <a name="deploy-the-node-app-to-azure-and-retrieve-the-secret-value"></a><span data-ttu-id="83543-208">Implementación de la aplicación de Node en Azure y recuperación del valor del secreto</span><span class="sxs-lookup"><span data-stu-id="83543-208">Deploy the Node App to Azure and retrieve the secret value</span></span>

<span data-ttu-id="83543-209">Ahora que ya está todo establecido,</span><span class="sxs-lookup"><span data-stu-id="83543-209">Now that everything is set.</span></span> <span data-ttu-id="83543-210">ejecute el siguiente comando para implementar la aplicación en Azure.</span><span class="sxs-lookup"><span data-stu-id="83543-210">Run the following command to deploy the app to Azure</span></span>

```bash
git push azure master
```

<span data-ttu-id="83543-211">Después de esto, si navega a https://<app_name>.azurewebsites.net podrá ver el valor del secreto.</span><span class="sxs-lookup"><span data-stu-id="83543-211">After this when you browse https://<app_name>.azurewebsites.net you can see the secret value.</span></span>
<span data-ttu-id="83543-212">Asegúrese de reemplazar el nombre <YourKeyVaultName> por el nombre de su almacén</span><span class="sxs-lookup"><span data-stu-id="83543-212">Make sure that you replaced the name <YourKeyVaultName> with your vault name</span></span>

::: zone-end

::: zone pivot="dotnet"
<span data-ttu-id="83543-213">Ahora, cuando ejecute la aplicación, debería ver el valor del secreto recuperado.</span><span class="sxs-lookup"><span data-stu-id="83543-213">Now when you run the application, you should see your secret value retrieved.</span></span>
::: zone-end

## <a name="next-steps"></a><span data-ttu-id="83543-214">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="83543-214">Next steps</span></span>

::: zone pivot="nodejs"
* [<span data-ttu-id="83543-215">Página principal de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="83543-215">Azure Key Vault Home Page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="83543-216">Documentación de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="83543-216">Azure Key Vault Documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* <span data-ttu-id="83543-217">[Azure SDK For Node](https://docs.microsoft.com/javascript/api/overview/azure/key-vault) (SDK de Azure para Node)</span><span class="sxs-lookup"><span data-stu-id="83543-217">[Azure SDK For Node](https://docs.microsoft.com/javascript/api/overview/azure/key-vault)</span></span>
* [<span data-ttu-id="83543-218">Referencia de API REST en Azure</span><span class="sxs-lookup"><span data-stu-id="83543-218">Azure REST API Reference</span></span>](https://docs.microsoft.com/rest/api/keyvault/)
::: zone-end

::: zone pivot="dotnet"
* [<span data-ttu-id="83543-219">Página principal de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="83543-219">Azure Key Vault home page</span></span>](https://azure.microsoft.com/services/key-vault/)
* [<span data-ttu-id="83543-220">Documentación de Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="83543-220">Azure Key Vault documentation</span></span>](https://docs.microsoft.com/azure/key-vault/)
* [<span data-ttu-id="83543-221">SDK de Azure para .NET</span><span class="sxs-lookup"><span data-stu-id="83543-221">Azure SDK For .NET</span></span>](https://github.com/Azure/azure-sdk-for-net)
* [<span data-ttu-id="83543-222">Referencia de API REST en Azure</span><span class="sxs-lookup"><span data-stu-id="83543-222">Azure REST API reference</span></span>](https://docs.microsoft.com/rest/api/keyvault/)
::: zone-end
