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
# <a name="set-up-git-repository-locally-for-documentation"></a><span data-ttu-id="63432-103">Configuración local del repositorio de Git para documentación</span><span class="sxs-lookup"><span data-stu-id="63432-103">Set up Git repository locally for documentation</span></span>

<span data-ttu-id="63432-104">En este artículo se detallan los pasos para configurar un repositorio de Git en el equipo local, con el propósito de contribuir a la documentación de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="63432-104">This article describes the steps to set up a git repository on your local machine, with the intent to contribute to Microsoft documentation.</span></span> <span data-ttu-id="63432-105">Los colaboradores pueden usar un repositorio clonado localmente para agregar nuevos artículos, realizar ediciones importantes en los artículos existentes o cambiar las ilustraciones.</span><span class="sxs-lookup"><span data-stu-id="63432-105">Contributors may use a locally cloned repository to add new articles, do major edits on existing articles, or change artwork.</span></span>

<span data-ttu-id="63432-106">Ejecute estas actividades de instalación única para comenzar a contribuir:</span><span class="sxs-lookup"><span data-stu-id="63432-106">You run these one-time setup activities to get started contributing:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="63432-107">Determinar el repositorio adecuado</span><span class="sxs-lookup"><span data-stu-id="63432-107">Determine the appropriate repository</span></span>
> * <span data-ttu-id="63432-108">Bifurcar el repositorio a su cuenta de GitHub</span><span class="sxs-lookup"><span data-stu-id="63432-108">Fork the repository to your GitHub account</span></span>
> * <span data-ttu-id="63432-109">Elegir una carpeta local para los archivos clonados</span><span class="sxs-lookup"><span data-stu-id="63432-109">Choose a local folder for the cloned files</span></span>
> * <span data-ttu-id="63432-110">Clonar el repositorio en el equipo local</span><span class="sxs-lookup"><span data-stu-id="63432-110">Clone the repository to your local machine</span></span>
> * <span data-ttu-id="63432-111">Configurar el valor remoto ascendente</span><span class="sxs-lookup"><span data-stu-id="63432-111">Configure the upstream remote value</span></span>

> [!IMPORTANT]
> <span data-ttu-id="63432-112">Si solo va a realizar cambios de menor importancia en un artículo, *no* necesita realizar los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="63432-112">If you're making only minor changes to an article, you *do not* need to complete the steps in this article.</span></span> <span data-ttu-id="63432-113">Puede continuar directamente con el [flujo de trabajo para cambios rápidos](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="63432-113">You can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>

## <a name="overview"></a><span data-ttu-id="63432-114">Información general</span><span class="sxs-lookup"><span data-stu-id="63432-114">Overview</span></span>

<span data-ttu-id="63432-115">Para contribuir al sitio de documentación de Microsoft, puede crear y editar archivos de Markdown localmente clonando el repositorio de documentación correspondiente.</span><span class="sxs-lookup"><span data-stu-id="63432-115">To contribute to Microsoft's documentation site, you can make and edit Markdown files locally by cloning the corresponding documentation repository.</span></span> <span data-ttu-id="63432-116">Microsoft requiere que bifurque el repositorio adecuado en su propia cuenta de GitHub, de manera que tenga permisos de lectura y escritura en ella para almacenar los cambios propuestos.</span><span class="sxs-lookup"><span data-stu-id="63432-116">Microsoft requires you to fork the appropriate repository into your own GitHub account, so that you have read/write permissions there to store your proposed changes.</span></span> <span data-ttu-id="63432-117">A continuación, use las solicitudes de incorporación de cambios para combinar los cambios en el repositorio central compartido de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="63432-117">Then you use pull requests to merge changes into the read-only central shared repository.</span></span>

![Triángulo de GitHub](./media/git-and-github-initial-setup.png)

<span data-ttu-id="63432-119">Si es la primera vez que usa GitHub, vea el vídeo siguiente para obtener información general de carácter conceptual sobre el proceso de bifurcación y clonación:</span><span class="sxs-lookup"><span data-stu-id="63432-119">If you're new to GitHub, watch the following video for a conceptual overview of the forking and cloning process:</span></span>

>[!VIDEO https://channel9.msdn.com/Blogs/CoolMoose/Git-Repository-Setup/player]

## <a name="determine-the-repository"></a><span data-ttu-id="63432-120">Determinar el repositorio</span><span class="sxs-lookup"><span data-stu-id="63432-120">Determine the repository</span></span>

<span data-ttu-id="63432-121">La documentación hospedada en [docs.microsoft.com](https://docs.microsoft.com) reside en varios repositorios diferentes de [github.com](https://www.github.com).</span><span class="sxs-lookup"><span data-stu-id="63432-121">Documentation hosted at [docs.microsoft.com](https://docs.microsoft.com) resides in several different repositories at [github.com](https://www.github.com).</span></span>

1. <span data-ttu-id="63432-122">Si no está seguro de qué repositorio debe usar, visite el artículo en docs.microsoft.com mediante el explorador web.</span><span class="sxs-lookup"><span data-stu-id="63432-122">If you are unsure of which repository to use, then visit the article on docs.microsoft.com using your web browser.</span></span> <span data-ttu-id="63432-123">Seleccione el vínculo **Editar** (icono de lápiz) de la esquina superior derecha del artículo.</span><span class="sxs-lookup"><span data-stu-id="63432-123">Select the **Edit** link (pencil icon) on the upper right of the article.</span></span>

   ![Haga clic en Editar para determinar la ubicación del repositorio y el archivo.](media/index/edit-article.png)

2. <span data-ttu-id="63432-125">Este vínculo le lleva a la ubicación de github.com del archivo de Markdown correspondiente en el repositorio adecuado.</span><span class="sxs-lookup"><span data-stu-id="63432-125">That link takes you to github.com location for the corresponding Markdown file in the appropriate repository.</span></span> <span data-ttu-id="63432-126">Anote la dirección URL para ver el nombre del repositorio.</span><span class="sxs-lookup"><span data-stu-id="63432-126">Note the URL to view the repository name.</span></span>

   ![Observe la dirección URL para determinar la ubicación del repositorio.](media/public-repo.png)

   <span data-ttu-id="63432-128">Por ejemplo, estos repositorios populares están disponibles para realizar contribuciones públicas:</span><span class="sxs-lookup"><span data-stu-id="63432-128">For example, these popular repositories are available for public contributions:</span></span>
   - <span data-ttu-id="63432-129">Documentación de Azure [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span><span class="sxs-lookup"><span data-stu-id="63432-129">Azure documentation [https://github.com/MicrosoftDocs/azure-docs](https://github.com/MicrosoftDocs/azure-docs)</span></span>
   - <span data-ttu-id="63432-130">Documentación de SQL Server [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span><span class="sxs-lookup"><span data-stu-id="63432-130">SQL Server documentation [https://github.com/MicrosoftDocs/sql-docs](https://github.com/MicrosoftDocs/sql-docs)</span></span>
   - <span data-ttu-id="63432-131">Documentación de Visual Studio [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span><span class="sxs-lookup"><span data-stu-id="63432-131">Visual Studio documentation [https://github.com/MicrosoftDocs/visualstudio-docs](https://github.com/MicrosoftDocs/visualstudio-docs)</span></span>
   - <span data-ttu-id="63432-132">Documentación de .NET [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span><span class="sxs-lookup"><span data-stu-id="63432-132">.NET Documentation [https://github.com/dotnet/docs](https://github.com/dotnet/docs)</span></span>
   - <span data-ttu-id="63432-133">Documentación de Azure SDK para .NET [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span><span class="sxs-lookup"><span data-stu-id="63432-133">Azure .Net SDK documentation [https://github.com/azure/azure-docs-sdk-dotnet](https://github.com/azure/azure-docs-sdk-dotnet)</span></span>

## <a name="fork-the-repository"></a><span data-ttu-id="63432-134">Bifurcar el repositorio</span><span class="sxs-lookup"><span data-stu-id="63432-134">Fork the repository</span></span>
<span data-ttu-id="63432-135">A través del sitio web de GitHub, cree una bifurcación del repositorio apropiado en su propia cuenta de GitHub.</span><span class="sxs-lookup"><span data-stu-id="63432-135">Using the appropriate repository, create a fork of the repository into your own GitHub account by using the GitHub website.</span></span>

<span data-ttu-id="63432-136">Se requiere una bifurcación personal, dado que todos los repositorios de documentación principales proporcionan acceso de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="63432-136">A personal fork is required since all main documentation repositories provide read-only access.</span></span> <span data-ttu-id="63432-137">Para poder realizar cambios, debe enviar una [solicitud de incorporación de cambios](git-github-fundamentals.md#pull-requests) desde su bifurcación al repositorio principal.</span><span class="sxs-lookup"><span data-stu-id="63432-137">To make changes, you must submit a [pull request](git-github-fundamentals.md#pull-requests) from your fork into the main repository.</span></span> <span data-ttu-id="63432-138">Para facilitar este proceso, primero necesita su copia del repositorio, sobre la que tendrá acceso de escritura.</span><span class="sxs-lookup"><span data-stu-id="63432-138">To facilitate this process, you first need your own copy of the repository, in which you have write access.</span></span> <span data-ttu-id="63432-139">Una *bifurcación* de GitHub sirve para este propósito</span><span class="sxs-lookup"><span data-stu-id="63432-139">A GitHub *fork* serves that purpose.</span></span>

1. <span data-ttu-id="63432-140">Vaya a la página del repositorio principal de GitHub y haga clic en el botón **Bifurcar** en la parte superior derecha.</span><span class="sxs-lookup"><span data-stu-id="63432-140">Go to the main repository's GitHub page and click the **Fork** button on the upper right.</span></span>

   ![Ejemplo de perfil de GitHub](./media/contribute-get-started-setup-local/fork.png)

2. <span data-ttu-id="63432-142">Si se le solicita, seleccione el icono de la cuenta de GitHub como destino en el que se creará la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="63432-142">If you are prompted, select your GitHub account tile as the destination where the fork should be created.</span></span> <span data-ttu-id="63432-143">De esta forma, se crea una copia del repositorio en su cuenta de GitHub. Esta copia se denomina bifurcación.</span><span class="sxs-lookup"><span data-stu-id="63432-143">This prompt creates a copy of the repository within your GitHub account, known as a fork.</span></span>

## <a name="choose-a-local-folder"></a><span data-ttu-id="63432-144">Seleccionar una carpeta local</span><span class="sxs-lookup"><span data-stu-id="63432-144">Choose a local folder</span></span>
<span data-ttu-id="63432-145">La copia del repositorio debe alojarse en una carpeta local.</span><span class="sxs-lookup"><span data-stu-id="63432-145">Make a local folder to hold a copy of the repository locally.</span></span> <span data-ttu-id="63432-146">Algunos repositorios pueden tener un gran tamaño, por ejemplo de hasta 5 GB en el caso de documentos de Azure.</span><span class="sxs-lookup"><span data-stu-id="63432-146">Some of the repositories can be large; up to 5 GB for azure-docs for example.</span></span> <span data-ttu-id="63432-147">Por tanto, seleccione una ubicación con suficiente espacio en disco disponible.</span><span class="sxs-lookup"><span data-stu-id="63432-147">Choose a location with available disk space.</span></span>

1. <span data-ttu-id="63432-148">Elija un nombre de carpeta que le resulte fácil de recordar y escríbalo.</span><span class="sxs-lookup"><span data-stu-id="63432-148">Choose a folder name should be easy for you to remember and type.</span></span> <span data-ttu-id="63432-149">Por ejemplo, puede elegir una carpeta raíz `C:\docs\` o una carpeta en su directorio de perfil de usuario `~/Documents/docs/`.</span><span class="sxs-lookup"><span data-stu-id="63432-149">For example, consider a root folder `C:\docs\` or make a folder in your user profile directory `~/Documents/docs/`</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="63432-150">Procure no seleccionar una ruta de carpeta local que esté anidada dentro de otra carpeta ubicada en el repositorio de Git.</span><span class="sxs-lookup"><span data-stu-id="63432-150">Avoid choosing a local folder path that is nested inside of another git repository folder location.</span></span> <span data-ttu-id="63432-151">Si bien es posible almacenar de manera adyacente carpetas de Git clonadas, la anidación entre sí de carpetas de Git causa errores en el seguimiento de archivos.</span><span class="sxs-lookup"><span data-stu-id="63432-151">While it is acceptable to store the git cloned folders adjacent to each other, nesting git folders inside one another causes errors for the file tracking.</span></span>

2. <span data-ttu-id="63432-152">Iniciar Git Bash</span><span class="sxs-lookup"><span data-stu-id="63432-152">Launch Git Bash</span></span>

   ![Iniciar Git Bash](./media/contribute-get-started-setup-local/gitbash-start.png)

   <span data-ttu-id="63432-154">La ubicación predeterminada desde la que se inicia Git Bash suele ser el directorio principal (~) o `/c/users/<Windows-user-account>/` en el sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="63432-154">The default location that Git Bash starts in is typically the home directory (~) or `/c/users/<Windows-user-account>/` on Windows OS.</span></span>

   <span data-ttu-id="63432-155">Para determinar el directorio actual, escriba `pwd` en la línea de comandos $.</span><span class="sxs-lookup"><span data-stu-id="63432-155">To determine the current directory, type `pwd` at the $ prompt.</span></span> 

3. <span data-ttu-id="63432-156">Cambie el directorio (cd) a la carpeta que ha creado para hospedar localmente el repositorio.</span><span class="sxs-lookup"><span data-stu-id="63432-156">Change directory (cd) into the folder that you created for hosting the repository locally.</span></span> <span data-ttu-id="63432-157">Observe que, en las rutas de acceso de las carpetas, Git Bash sigue la convención de Linux y usa la barra diagonal en lugar de la barra diagonal inversa.</span><span class="sxs-lookup"><span data-stu-id="63432-157">Note that Git Bash uses the Linux convention of forward-slashes instead of back-slashes for folder paths.</span></span>

   <span data-ttu-id="63432-158">Por ejemplo, `cd /c/docs/ ` o `cd ~/Documents/docs/`.</span><span class="sxs-lookup"><span data-stu-id="63432-158">For example, `cd /c/docs/ ` or `cd ~/Documents/docs/`</span></span>

## <a name="create-a-local-clone"></a><span data-ttu-id="63432-159">Crear un clon local</span><span class="sxs-lookup"><span data-stu-id="63432-159">Create a local clone</span></span>

<span data-ttu-id="63432-160">Utilizando Git Bash, prepárese para ejecutar el comando **clone** con el fin de incorporar una copia de un repositorio (su bifurcación) a su dispositivo en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="63432-160">Using Git Bash, prepare to run the **clone** command to pull a copy of a repository (your fork) down to your device on the current directory.</span></span> 

### <a name="authenticate-by-using-git-credential-manager"></a><span data-ttu-id="63432-161">Autenticación con el administrador de credenciales de Git</span><span class="sxs-lookup"><span data-stu-id="63432-161">Authenticate by using Git Credential Manager</span></span>
<span data-ttu-id="63432-162">Si ha instalado la última versión de Git para Windows y ha aceptado la instalación predeterminada, el administrador de credenciales de Git está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="63432-162">If you installed the latest version of Git for Windows and accepted the default installation, Git Credential Manager is enabled by default.</span></span> <span data-ttu-id="63432-163">El administrador de credenciales de Git facilita bastante el proceso de autenticación, ya que no es necesario volver a llamar al token de acceso personal para restablecer las conexiones autenticadas o remotas con GitHub.</span><span class="sxs-lookup"><span data-stu-id="63432-163">Git Credential Manager makes authentication much easier, because you don't need to recall your personal access token when re-establishing authenticated connections and remotes with GitHub.</span></span>

1. <span data-ttu-id="63432-164">Ejecute el comando **clone** con el nombre del repositorio.</span><span class="sxs-lookup"><span data-stu-id="63432-164">Run the **clone** command, by providing the repository name.</span></span> <span data-ttu-id="63432-165">La operación de clonación descarga (clona) el repositorio bifurcado en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="63432-165">Cloning downloads (clone) the forked repository on your local computer.</span></span> 

    > [!Tip]
    > <span data-ttu-id="63432-166">Puede obtener la dirección URL de GitHub de la bifurcación para el comando de clonación mediante el botón **Clonar o descargar** de la interfaz de usuario de GitHub:</span><span class="sxs-lookup"><span data-stu-id="63432-166">You can get your fork's GitHub URL for the clone command from the **Clone or download** button in the GitHub UI:</span></span>
    >
    > ![Clonar o descargar](./media/contribute-get-started-setup-local/clone-or-download.png)

    <span data-ttu-id="63432-168">Asegúrese de especificar la ruta de acceso a *su bifurcación* durante el proceso de clonación, y no al repositorio principal desde el que ha creado la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="63432-168">Be sure to specify the path to *your fork* during the cloning process, not the main repository from which you created the fork.</span></span> <span data-ttu-id="63432-169">De lo contrario, no podrá contribuir con sus cambios.</span><span class="sxs-lookup"><span data-stu-id="63432-169">Otherwise, you cannot contribute changes.</span></span> <span data-ttu-id="63432-170">Para hacer referencia a la bifurcación, se usa la cuenta de usuario personal de GitHub, cuyo formato es `github.com/<github-username>/<repo>`.</span><span class="sxs-lookup"><span data-stu-id="63432-170">Your fork is referenced through your personal GitHub user account, such as `github.com/<github-username>/<repo>`.</span></span>

    ```bash
    git clone https://github.com/<github-username>/<repo>.git
    ```

    <span data-ttu-id="63432-171">El comando de clonación debe presentar un aspecto similar al de este ejemplo:</span><span class="sxs-lookup"><span data-stu-id="63432-171">Your clone command should look similar to this example:</span></span>

    ```bash
    git clone https://github.com/smithj/azure-docs.git
    ```

2. <span data-ttu-id="63432-172">Cuando se le solicite, escriba las credenciales de GitHub.</span><span class="sxs-lookup"><span data-stu-id="63432-172">When you're prompted, enter your GitHub credentials.</span></span>

    ![Inicio de sesión en GitHub](./media/contribute-get-started-setup-local/github-login.png)

3. <span data-ttu-id="63432-174">Cuando se le solicite, escriba el código de autenticación en dos fases.</span><span class="sxs-lookup"><span data-stu-id="63432-174">When you're prompted, enter your two-factor authentication code.</span></span>

    ![Autenticación en dos fases de GitHub](./media/contribute-get-started-setup-local/github-2fa.png)

    > [!Note]
    > <span data-ttu-id="63432-176">Las credenciales se almacenarán y se usarán para autenticar futuras solicitudes de GitHub.</span><span class="sxs-lookup"><span data-stu-id="63432-176">Your credentials will be saved and used to authenticate future GitHub requests.</span></span> <span data-ttu-id="63432-177">Solo tiene que realizar la autenticación una vez en cada equipo.</span><span class="sxs-lookup"><span data-stu-id="63432-177">You only need to do this authentication once per computer.</span></span> 

4. <span data-ttu-id="63432-178">El comando de clonación ejecuta y descarga una copia de los archivos del repositorio desde su bifurcación a una carpeta nueva ubicada en el disco local.</span><span class="sxs-lookup"><span data-stu-id="63432-178">The clone command runs and downloads a copy of the repository files from your fork into a new folder on the local disk.</span></span> <span data-ttu-id="63432-179">Dentro de la carpeta actual, se crea una carpeta nueva.</span><span class="sxs-lookup"><span data-stu-id="63432-179">A new folder is made within the current folder.</span></span> <span data-ttu-id="63432-180">En función del tamaño del repositorio, la operación puede tardar varios minutos.</span><span class="sxs-lookup"><span data-stu-id="63432-180">It may take a few minutes, depending on the repository size.</span></span> <span data-ttu-id="63432-181">Una vez creada la carpeta, puede explorarla para ver su estructura.</span><span class="sxs-lookup"><span data-stu-id="63432-181">You can explore the folder to see the structure once it is finished.</span></span>

## <a name="configure-remote-upstream"></a><span data-ttu-id="63432-182">Configuración de ascendente remoto</span><span class="sxs-lookup"><span data-stu-id="63432-182">Configure remote upstream</span></span>
<span data-ttu-id="63432-183">Tras clonar el repositorio, configure una conexión remota de solo lectura al repositorio principal llamada **upstream** (ascendente).</span><span class="sxs-lookup"><span data-stu-id="63432-183">After cloning the repository, set up a read-only remote connection to the main repository named **upstream**.</span></span> <span data-ttu-id="63432-184">Esta URL ascendente se utiliza para mantener el repositorio local sincronizado con los últimos cambios que realicen otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="63432-184">You use the upstream URL to keep your local repository in sync with the latest changes made by others.</span></span> <span data-ttu-id="63432-185">El comando **git remote** se utiliza para establecer el valor de configuración.</span><span class="sxs-lookup"><span data-stu-id="63432-185">The **git remote** command is used to set the configuration value.</span></span> <span data-ttu-id="63432-186">El comando **fetch** se usa para actualizar la información de la rama desde el repositorio ascendente.</span><span class="sxs-lookup"><span data-stu-id="63432-186">You use the **fetch** command to refresh the branch info from the upstream repository.</span></span>

1. <span data-ttu-id="63432-187">Si va a utilizar el **administrador de credenciales de Git**, use los comandos siguientes.</span><span class="sxs-lookup"><span data-stu-id="63432-187">If you're using **Git Credential Manager**, use the following commands.</span></span> <span data-ttu-id="63432-188">Reemplace los marcadores de posición \<repo\> y \<organization\>.</span><span class="sxs-lookup"><span data-stu-id="63432-188">Replace the \<repo\> and \<organization\> placeholders.</span></span>
   ```bash
   cd <repo>
   git remote add upstream https://github.com/<organization>/<repo>.git
   git fetch upstream
   ```

2. <span data-ttu-id="63432-189">Observe los valores configurados y confirme que las direcciones URL son correctas.</span><span class="sxs-lookup"><span data-stu-id="63432-189">View the configured values and confirm the URLs are correct.</span></span> <span data-ttu-id="63432-190">Las direcciones URL de origen (**origin**) deben apuntar a su bifurcación personal.</span><span class="sxs-lookup"><span data-stu-id="63432-190">Ensure the **origin** URLs point to your personal fork.</span></span> <span data-ttu-id="63432-191">Las direcciones URL ascendentes (**upstream**) deben apuntar al repositorio principal, como MicrosoftDocs o Azure.</span><span class="sxs-lookup"><span data-stu-id="63432-191">Ensure the **upstream** URLs point to the main repository, such as MicrosoftDocs or Azure.</span></span> 
   ```bash
   git remote -v 
   ```

   <span data-ttu-id="63432-192">Se muestra una salida remota de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="63432-192">Example remote output is shown.</span></span> <span data-ttu-id="63432-193">Se configura una cuenta ficticia de Git llamada MyGitAccount con un token de acceso personal para acceder al repositorio azure-docs:</span><span class="sxs-lookup"><span data-stu-id="63432-193">A fictitious git account named MyGitAccount is configured with a personal access token to access the repo azure-docs:</span></span>
   ```output
   origin  https://github.com/MyGitAccount/azure-docs.git (fetch)
   origin  https://github.com/MyGitAccount/azure-docs.git(push)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (fetch)
   upstream        https://github.com/MicrosoftDocs/azure-docs.git (push)
   ```

3. <span data-ttu-id="63432-194">Si ha cometido algún error, puede quitar el valor remoto.</span><span class="sxs-lookup"><span data-stu-id="63432-194">If you made a mistake, you can remove the remote value.</span></span> <span data-ttu-id="63432-195">Para quitar el valor ascendente, ejecute el comando `git remote remove upstream`.</span><span class="sxs-lookup"><span data-stu-id="63432-195">To remove the upstream value, run the command `git remote remove upstream`.</span></span>

## <a name="next-steps"></a><span data-ttu-id="63432-196">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="63432-196">Next steps</span></span>
- <span data-ttu-id="63432-197">Para obtener más información sobre la incorporación y actualización de contenido, continúe con el [flujo de trabajo de colaboración de GitHub](how-to-write-workflows-major.md).</span><span class="sxs-lookup"><span data-stu-id="63432-197">To learn more about adding and updating content, continue to the [GitHub contribution workflow](how-to-write-workflows-major.md).</span></span>
