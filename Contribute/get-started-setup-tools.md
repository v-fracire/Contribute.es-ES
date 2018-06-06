---
title: Instalación de herramientas de creación de contenido
description: Este artículo le ayuda a descargar e instalar las herramientas de cliente que necesitará para Git y la edición de archivos de Markdown.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 04/30/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1011c3fc829202a3df134ddc80eb05b8959b7bf6
ms.sourcegitcommit: 782b689882cce3ce07f5613763322989f2d0d63f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "34469380"
---
# <a name="install-content-authoring-tools"></a><span data-ttu-id="2aac6-103">Instalación de herramientas de creación de contenido</span><span class="sxs-lookup"><span data-stu-id="2aac6-103">Install content authoring tools</span></span>

<span data-ttu-id="2aac6-104">En este artículo se describen los pasos para instalar de forma interactiva herramientas de cliente de Git y Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2aac6-104">This article describes the steps to interactively install Git client tools and Visual Studio Code.</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="2aac6-105">Instalación de [Git para Windows](https://git-scm.com/download/win)</span><span class="sxs-lookup"><span data-stu-id="2aac6-105">Install [Git for Windows](https://git-scm.com/download/win)</span></span>
> * <span data-ttu-id="2aac6-106">Instalación de [Visual Studio Code](https://code.visualstudio.com/)</span><span class="sxs-lookup"><span data-stu-id="2aac6-106">Install [Visual Studio Code](https://code.visualstudio.com/)</span></span>
> * <span data-ttu-id="2aac6-107">Instalación del [paquete de creación de Docs](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)</span><span class="sxs-lookup"><span data-stu-id="2aac6-107">Install [Docs Authoring Pack](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)</span></span>

>[!IMPORTANT]
> <span data-ttu-id="2aac6-108">Si solo va a realizar cambios de menor importancia en un artículo, *no* necesita realizar todos los pasos del artículo y, por tanto, puede continuar directamente con el [flujo de trabajo para cambios rápidos](index.md#quick-edits-to-existing-documents).</span><span class="sxs-lookup"><span data-stu-id="2aac6-108">If you're making only minor changes to an article, you *do not* need to complete the steps in this article and can continue directly to the [quick changes workflow](index.md#quick-edits-to-existing-documents).</span></span>
>
> <span data-ttu-id="2aac6-109">Se pide a los principales colaboradores que completen estos pasos, que le permiten usar el [flujo de trabajo de cambios mayores y de larga duración](how-to-write-workflows-major.md).</span><span class="sxs-lookup"><span data-stu-id="2aac6-109">Major contributors are encouraged to complete these steps, which enable you to use the [major/long-running changes workflow](how-to-write-workflows-major.md).</span></span> <span data-ttu-id="2aac6-110">Aunque disponga de permisos de escritura en el repositorio principal, *se recomienda encarecidamente que bifurque y clone el repositorio (y en esta guía se supone que así lo ha hecho)*, de manera que tendrá permisos de lectura y escritura para almacenar los cambios propuestos en la bifurcación.</span><span class="sxs-lookup"><span data-stu-id="2aac6-110">Even if you have write permissions in the main repository, *we highly recommend (and this guide assumes) that you fork and clone the repository*, so that you have read/write permissions to store your proposed changes in your fork.</span></span>

## <a name="install-git-client-tools-on-windows"></a><span data-ttu-id="2aac6-111">Instalación de las herramientas de cliente para Git en Windows</span><span class="sxs-lookup"><span data-stu-id="2aac6-111">Install Git client tools on Windows</span></span>

 <span data-ttu-id="2aac6-112">Instale la última versión de las [herramientas de cliente para Git de Software Freedom Conservancy](https://git-scm.com/download/).</span><span class="sxs-lookup"><span data-stu-id="2aac6-112">Install the latest version of [Software Freedom Conservancy's Git client tools](https://git-scm.com/download/).</span></span> <span data-ttu-id="2aac6-113">La instalación incluye el sistema de control de versiones de Git y Git Bash, la aplicación de línea de comandos que usa para interactuar con el repositorio de Git local.</span><span class="sxs-lookup"><span data-stu-id="2aac6-113">The install includes the Git version control system and Git Bash, the command-line app that you use to interact with your local Git repository.</span></span>

<span data-ttu-id="2aac6-114">Si prefiere una interfaz gráfica de usuario (GUI) en lugar de una interfaz de la línea de comandos (CLI), vea la [página de clientes de la GUI disponible de Software Freedom Conservancy](https://git-scm.com/downloads/guis), [GitHub Desktop de GitHub](https://desktop.github.com/) o [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) para consultar algunas opciones populares.</span><span class="sxs-lookup"><span data-stu-id="2aac6-114">If you prefer a graphical user interface (GUI) over a command-line interface (CLI), see [Software Freedom Conservancy's available GUI Clients page](https://git-scm.com/downloads/guis), [GitHub's GitHub Desktop](https://desktop.github.com/), or [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) for some popular options.</span></span>

<span data-ttu-id="2aac6-115">Siga las instrucciones de su cliente elegido para la instalación y configuración.</span><span class="sxs-lookup"><span data-stu-id="2aac6-115">Follow the instructions for your chosen client for installation and configuration.</span></span>

<span data-ttu-id="2aac6-116">En el siguiente artículo, podrá [configurar un repositorio de Git local](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="2aac6-116">In the next article, you will [Set up a local Git repository](get-started-setup-local.md).</span></span>

   <span data-ttu-id="2aac6-117">Aquí encontrará recursos adicionales de Git: [Git terminology](https://help.github.com/articles/github-glossary) (Terminología de Git) | [Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) (Conceptos básicos de Git) | [Learning Git and GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/) (Información sobre Git y GitHub)</span><span class="sxs-lookup"><span data-stu-id="2aac6-117">Additional Git resources are available here: [Git terminology](https://help.github.com/articles/github-glossary) | [Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) | [Learning Git and GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/)</span></span>

## <a name="understand-markdown-editors"></a><span data-ttu-id="2aac6-118">Descripción de los editores de Markdown</span><span class="sxs-lookup"><span data-stu-id="2aac6-118">Understand Markdown editors</span></span>

<span data-ttu-id="2aac6-119">Markdown es un lenguaje de marcado ligero fácil de leer y de aprender.</span><span class="sxs-lookup"><span data-stu-id="2aac6-119">Markdown is a lightweight markup language that is both easy to read and easy to learn.</span></span> <span data-ttu-id="2aac6-120">Por ello, se ha convertido rápidamente en un estándar del sector.</span><span class="sxs-lookup"><span data-stu-id="2aac6-120">Therefore, it has rapidly become an industry standard.</span></span> <span data-ttu-id="2aac6-121">Para escribir artículos en Markdown, se recomienda que primero descargue e instale Markdown editor.</span><span class="sxs-lookup"><span data-stu-id="2aac6-121">To write articles in Markdown, we recommend that you first download and install a Markdown editor.</span></span>  <span data-ttu-id="2aac6-122">[Visual Studio Code](https://code.visualstudio.com/) es la herramienta preferida para la edición de Markdown en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2aac6-122">[Visual Studio Code](https://code.visualstudio.com/) is the preferred tool for editing Markdown at Microsoft.</span></span> <span data-ttu-id="2aac6-123">[Atom](https://atom.io) es otra herramienta popular para la edición de Markdown.</span><span class="sxs-lookup"><span data-stu-id="2aac6-123">[Atom](https://atom.io) is another popular tool for editing Markdown.</span></span>

<span data-ttu-id="2aac6-124">El texto de Markdown se guarda en archivos con extensión .md.</span><span class="sxs-lookup"><span data-stu-id="2aac6-124">Markdown text is saved into files with .md extension.</span></span>

<span data-ttu-id="2aac6-125">La información adicional sobre cómo escribir con Markdown, incluidos los aspectos básicos y las características de Markdown compatibles con las extensiones de Markdown personalizadas para OPS, se proporciona más adelante en el artículo [Uso de Markdown](how-to-write-use-markdown.md).</span><span class="sxs-lookup"><span data-stu-id="2aac6-125">Additional details on how to write with Markdown, including Markdown basics and the features supported by OPS custom Markdown extensions, are covered later in the [How to use Markdown](how-to-write-use-markdown.md) article.</span></span>

## <a name="visual-studio-code"></a><span data-ttu-id="2aac6-126">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="2aac6-126">Visual Studio Code</span></span>

<span data-ttu-id="2aac6-127">[Visual Studio Code](https://code.visualstudio.com/), también conocido como VS Code, es un editor ligero que funciona en Windows, Linux y Mac.</span><span class="sxs-lookup"><span data-stu-id="2aac6-127">[Visual Studio Code](https://code.visualstudio.com/), also known as VS Code, is a lightweight editor that works on Windows, Linux, and Mac.</span></span> <span data-ttu-id="2aac6-128">Incluye integración de Git y compatibilidad con las extensiones.</span><span class="sxs-lookup"><span data-stu-id="2aac6-128">It includes git integration, and support for extensions.</span></span>

<span data-ttu-id="2aac6-129">Descargue e instale [VS Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="2aac6-129">Download and install [VS Code](https://code.visualstudio.com/).</span></span> <span data-ttu-id="2aac6-130">La página principal de VS Code debería detectar correctamente el sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="2aac6-130">The VS Code home page should detect your operating system correctly.</span></span>

- [<span data-ttu-id="2aac6-131">Windows</span><span class="sxs-lookup"><span data-stu-id="2aac6-131">Windows</span></span>](https://code.visualstudio.com/docs/setup/windows)
- [<span data-ttu-id="2aac6-132">Mac</span><span class="sxs-lookup"><span data-stu-id="2aac6-132">Mac</span></span>](https://code.visualstudio.com/docs/setup/mac)
- [<span data-ttu-id="2aac6-133">Linux</span><span class="sxs-lookup"><span data-stu-id="2aac6-133">Linux</span></span>](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> <span data-ttu-id="2aac6-134">Para ejecutar VS Code y abrir la carpeta actual, ejecute el comando `code .` en la línea de comandos o el shell de bash.</span><span class="sxs-lookup"><span data-stu-id="2aac6-134">To launch VS Code and open the current folder, run the command `code .` in the command line or bash shell.</span></span> <span data-ttu-id="2aac6-135">Si la carpeta actual forma parte de un repositorio de Git local, la integración de github aparece automáticamente en Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2aac6-135">If the current folder is part of a local git repo, the github integration appears in Visual Studio Code automatically.</span></span>

## <a name="docs-authoring-pack"></a><span data-ttu-id="2aac6-136">Paquete de creación de Docs</span><span class="sxs-lookup"><span data-stu-id="2aac6-136">Docs Authoring Pack</span></span>
<span data-ttu-id="2aac6-137">Instale el paquete de creación de Docs para Visual Studio Code.</span><span class="sxs-lookup"><span data-stu-id="2aac6-137">Install the Docs Authoring Pack for Visual Studio Code.</span></span> <span data-ttu-id="2aac6-138">Este conjunto de extensiones incluye asistencia básica de creación para facilitar la escritura de Markdown, además de una característica de vista previa, para que pueda ver el aspecto de Markdown con el estilo del sitio docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2aac6-138">This set of extensions includes basic authoring assistance for help when writing Markdown, and a preview feature, so that you can see what the Markdown looks like in the style of the docs.microsoft.com site.</span></span>

   <span data-ttu-id="2aac6-139">Visite esta [página de Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) y seleccione **Install** (Instalar) o busque `docsmsft.docs-authoring-pack` en la lista de extensiones en la ventana de VS Code.</span><span class="sxs-lookup"><span data-stu-id="2aac6-139">Visit this [marketplace page](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) and select **Install**, or search for `docsmsft.docs-authoring-pack` in your extensions list in the VS Code window.</span></span> 

   <span data-ttu-id="2aac6-140">Presione Alt+M en VS Code para acceder al paquete de creación de Docs.</span><span class="sxs-lookup"><span data-stu-id="2aac6-140">The Docs Authoring Pack is accessible by pressing Alt+M inside of VS Code.</span></span> <span data-ttu-id="2aac6-141">La barra de herramientas está oculta de forma predeterminada, pero se puede mostrar.</span><span class="sxs-lookup"><span data-stu-id="2aac6-141">The toolbar is hidden by default but can be shown.</span></span> <span data-ttu-id="2aac6-142">Edite la configuración de VS Code (Control+coma) y agregue los ajustes de usuario `"markdown.showToolbar": true` para mostrar la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="2aac6-142">Edit the VS Code settings (Control+comma) and adding user setting `"markdown.showToolbar": true` to show the toolbar.</span></span>

   <span data-ttu-id="2aac6-143">Para más información, vea la página del [paquete de creación de Docs](how-to-write-docs-auth-pack.md).</span><span class="sxs-lookup"><span data-stu-id="2aac6-143">For more information, see the [Docs Authoring Pack](how-to-write-docs-auth-pack.md) page.</span></span>


## <a name="next-steps"></a><span data-ttu-id="2aac6-144">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2aac6-144">Next steps</span></span>

<span data-ttu-id="2aac6-145">Ahora está listo para la [configuración de un repositorio de Git local](get-started-setup-local.md).</span><span class="sxs-lookup"><span data-stu-id="2aac6-145">Now you are ready to [Set up a local Git repository](get-started-setup-local.md).</span></span>
