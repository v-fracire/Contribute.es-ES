---
title: Configuración local de un repositorio de Git
description: Este artículo le servirá de guía para crear un repositorio local de Git y contribuir a la documentación. Se incluye el proceso de bifurcación y clonación.
author: jasonwhowell
ms.author: jasonh
ms.date: 01/18/2018
ms.openlocfilehash: 895c0fb0d64708e8e3d0f632c10a060791d15b65
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805686"
---
# <a name="set-up-git-repository-locally-for-documentation"></a>Configuración local del repositorio de Git para documentación

En este artículo se detallan los pasos para configurar un repositorio de Git en el equipo local, con el propósito de contribuir a la documentación de Microsoft. Los colaboradores pueden usar un repositorio clonado localmente para agregar nuevos artículos, realizar ediciones importantes en los artículos existentes o cambiar las ilustraciones.

Ejecute estas actividades de instalación única para comenzar a contribuir:
> [!div class="checklist"]
> * Determinar el repositorio adecuado
> * Bifurcar el repositorio a su cuenta de GitHub
> * Elegir una carpeta local para los archivos clonados
> * Clonar el repositorio en el equipo local
> * Configurar el valor remoto ascendente

> [!IMPORTANT]
> Si solo va a realizar cambios de menor importancia en un artículo, *no* necesita realizar los pasos de este artículo. Puede continuar directamente con el [flujo de trabajo para cambios rápidos](index.md#quick-edits-to-existing-documents).
>

## <a name="overview"></a>Información general

Para contribuir al sitio de documentación de Microsoft, puede crear y editar archivos de Markdown localmente clonando el repositorio de documentación correspondiente. Microsoft requiere que bifurque el repositorio adecuado en su propia cuenta de GitHub, de manera que tenga permisos de lectura y escritura en ella para almacenar los cambios propuestos. A continuación, use las solicitudes de incorporación de cambios para combinar los cambios en el repositorio central compartido de solo lectura.

![Triángulo de GitHub](./media/git-and-github-initial-setup.png)

Si es la primera vez que usa GitHub, vea el vídeo siguiente para obtener información general de carácter conceptual sobre el proceso de bifurcación y clonación:

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a>Determinar el repositorio

La documentación hospedada en [docs.microsoft.com](https://docs.microsoft.com) reside en varios repositorios diferentes de [github.com](https://www.github.com).

1. Si no está seguro de qué repositorio debe usar, visite el artículo en docs.microsoft.com mediante el explorador web. Seleccione el vínculo **Editar** (icono de lápiz) de la esquina superior derecha del artículo.

   ![Haga clic en Editar para determinar la ubicación del repositorio y el archivo.](media/index/edit-article.png)

2. Este vínculo le lleva a la ubicación de github.com del archivo de Markdown correspondiente en el repositorio adecuado. Anote la dirección URL para ver el nombre del repositorio.

   ![Observe la dirección URL para determinar la ubicación del repositorio.](media/public-repo.png)

   Por ejemplo, estos repositorios populares están disponibles para realizar contribuciones públicas:
   - Documentación de Azure [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)
   - Documentación de SQL Server [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)
   - Documentación de Visual Studio [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)
   - Documentación de .NET [https://github.com/dotnet/docs](https://github.com/dotnet/docs)
   - Documentación de Azure SDK para .NET [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)

## <a name="fork-the-repository"></a>Bifurcar el repositorio
A través del sitio web de GitHub, cree una bifurcación del repositorio apropiado en su propia cuenta de GitHub.

Se requiere una bifurcación personal, dado que todos los repositorios de documentación principales proporcionan acceso de solo lectura. Para poder realizar cambios, debe enviar una [solicitud de incorporación de cambios](git-github-fundamentals.md#pull-requests) desde su bifurcación al repositorio principal. Para facilitar este proceso, primero necesita su copia del repositorio, sobre la que tendrá acceso de escritura. Una *bifurcación* de GitHub sirve para este propósito

1. Vaya a la página del repositorio principal de GitHub y haga clic en el botón **Bifurcar** en la parte superior derecha.

   ![Ejemplo de perfil de GitHub](./media/contribute-get-started-setup-local/fork.png)

2. Si se le solicita, seleccione el icono de la cuenta de GitHub como destino en el que se creará la bifurcación. De esta forma, se crea una copia del repositorio en su cuenta de GitHub. Esta copia se denomina bifurcación.

## <a name="choose-a-local-folder"></a>Seleccionar una carpeta local
La copia del repositorio debe alojarse en una carpeta local. Algunos repositorios pueden tener un gran tamaño, por ejemplo de hasta 5 GB en el caso de documentos de Azure. Por tanto, seleccione una ubicación con suficiente espacio en disco disponible.

1. Elija un nombre de carpeta que le resulte fácil de recordar y escríbalo. Por ejemplo, puede elegir una carpeta raíz `C:\docs\` o una carpeta en su directorio de perfil de usuario `~/Documents/docs/`.

   > [!IMPORTANT]
   > Procure no seleccionar una ruta de carpeta local que esté anidada dentro de otra carpeta ubicada en el repositorio de Git. Si bien es posible almacenar de manera adyacente carpetas de Git clonadas, la anidación entre sí de carpetas de Git causa errores en el seguimiento de archivos.

2. Iniciar Git Bash

   ![Iniciar Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   La ubicación predeterminada desde la que se inicia Git Bash suele ser el directorio principal (~) o `/c/users/<Windows-user-account>/` en el sistema operativo Windows.

   Para determinar el directorio actual, escriba `pwd` en la línea de comandos $. 

3. Cambie el directorio (cd) a la carpeta que ha creado para hospedar localmente el repositorio. Observe que, en las rutas de acceso de las carpetas, Git Bash sigue la convención de Linux y usa la barra diagonal en lugar de la barra diagonal inversa.

   Por ejemplo, `cd /c/docs/ ` o `cd ~/Documents/docs/`.

## <a name="create-a-local-clone"></a>Crear un clon local

Utilizando Git Bash, prepárese para ejecutar el comando **clone** con el fin de incorporar una copia de un repositorio (su bifurcación) a su dispositivo en el directorio actual. 

### <a name="authenticate-by-using-git-credential-manager"></a>Autenticación con el administrador de credenciales de Git
Si ha instalado la última versión de Git para Windows y ha aceptado la instalación predeterminada, el administrador de credenciales de Git está habilitado de forma predeterminada. El administrador de credenciales de Git facilita bastante el proceso de autenticación, ya que no es necesario volver a llamar al token de acceso personal para restablecer las conexiones autenticadas o remotas con GitHub.

1. Ejecute el comando **clone** con el nombre del repositorio. La operación de clonación descarga (clona) el repositorio bifurcado en su equipo local. 

    > [!Tip]
    > Puede obtener la dirección URL de GitHub de la bifurcación para el comando de clonación mediante el botón **Clonar o descargar** de la interfaz de usuario de GitHub:
    >
    > ![Clonar o descargar](./media/contribute-get-started-setup-local/clone-or-download.png)

    Asegúrese de especificar la ruta de acceso a *su bifurcación* durante el proceso de clonación, y no al repositorio principal desde el que ha creado la bifurcación. De lo contrario, no podrá contribuir con sus cambios. Para hacer referencia a la bifurcación, se usa la cuenta de usuario personal de GitHub, cuyo formato es `github.com/<github-username>/<repo>`.

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    El comando de clonación debe presentar un aspecto similar al de este ejemplo:

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. Cuando se le solicite, escriba las credenciales de GitHub.

    ![Inicio de sesión en GitHub](./media/contribute-get-started-setup-local/github-login.png)

3. Cuando se le solicite, escriba el código de autenticación en dos fases.

    ![Autenticación en dos fases de GitHub](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > Las credenciales se almacenarán y se usarán para autenticar futuras solicitudes de GitHub. Solo tiene que realizar la autenticación una vez en cada equipo. 

4. El comando de clonación ejecuta y descarga una copia de los archivos del repositorio desde su bifurcación a una carpeta nueva ubicada en el disco local. Dentro de la carpeta actual, se crea una carpeta nueva. En función del tamaño del repositorio, la operación puede tardar varios minutos. Una vez creada la carpeta, puede explorarla para ver su estructura.

## <a name="configure-remote-upstream"></a>Configuración de ascendente remoto
Tras clonar el repositorio, configure una conexión remota de solo lectura al repositorio principal llamada **upstream** (ascendente). Esta URL ascendente se utiliza para mantener el repositorio local sincronizado con los últimos cambios que realicen otros usuarios. El comando **git remote** se utiliza para establecer el valor de configuración. El comando **fetch** se usa para actualizar la información de la rama desde el repositorio ascendente.

1. Si va a utilizar el **administrador de credenciales de Git**, use los comandos siguientes. Reemplace los marcadores de posición \<repo\> y \<organization\>.
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. Observe los valores configurados y confirme que las direcciones URL son correctas. Las direcciones URL de origen (**origin**) deben apuntar a su bifurcación personal. Las direcciones URL ascendentes (**upstream**) deben apuntar al repositorio principal, como MicrosoftDocs o Azure. 
   ```bash
   git remote -v 
   ```

   Se muestra una salida remota de ejemplo. Se configura una cuenta ficticia de Git llamada MyGitAccount con un token de acceso personal para acceder al repositorio azure-docs:
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. Si ha cometido algún error, puede quitar el valor remoto. Para quitar el valor ascendente, ejecute el comando `git remote remove upstream`.

## <a name="next-steps"></a>Pasos siguientes
- Para obtener más información sobre la incorporación y actualización de contenido, continúe con el [flujo de trabajo de colaboración de GitHub](how-to-write-workflows-major.md).
