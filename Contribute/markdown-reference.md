---
title: Referencia de Markdown para OPS y docs.microsoft.com
description: La guía de la plataforma de OPS para extensiones de Markdown y DocFX Flavored Markdown (DFM).
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 05/18/2018
ms.topic: contributor-guide
ms.prod: non-product-specific
audience: internal,external
ms.openlocfilehash: 64921bacf48e638221048db4b24e1a941f1d2777
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609554"
---
# <a name="markdown-reference-for-ops"></a><span data-ttu-id="4e7bf-103">Referencia de Markdown para OPS</span><span class="sxs-lookup"><span data-stu-id="4e7bf-103">Markdown Reference for OPS</span></span>

<span data-ttu-id="4e7bf-104">Markdown es un lenguaje de marcado ligero con sintaxis de texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-104">Markdown is a lightweight markup language with plain text formatting syntax.</span></span> <span data-ttu-id="4e7bf-105">Servicios de publicación abierta (OPS) admite el estándar CommonMark para Markdown, además de algunas extensiones de Markdown personalizadas diseñadas para proporcionar contenido más enriquecido en docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-105">Open Publishing Services (OPS) supports the CommonMark standard for Markdown, plus some custom Markdown extensions designed to provide richer content on docs.microsoft.com.</span></span> <span data-ttu-id="4e7bf-106">En este artículo se proporciona una referencia alfabética para el uso de Markdown en OPS para docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-106">This article provides an alphabetical reference for using Markdown in OPS for docs.microsoft.com.</span></span>

<span data-ttu-id="4e7bf-107">Puede usar cualquier editor de texto para crear contenido de Markdown.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-107">You can use any text editor to author Markdown.</span></span> <span data-ttu-id="4e7bf-108">Como editor que facilita la inserción de la sintaxis estándar de Markdown y extensiones de OPS personalizadas, se recomienda [VS Code](https://code.visualstudio.com/) con el [Paquete de creación de Docs](https://aka.ms/DocsAuthoringPack) instalado.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-108">For an editor that facilitates inserting both standard Markdown syntax and custom OPS extensions, we recommend [VS Code](https://code.visualstudio.com/) with the [Docs Authoring Pack](https://aka.ms/DocsAuthoringPack) installed.</span></span>

<span data-ttu-id="4e7bf-109">En OPS se ha estandarizado Markdig para todos los repositorios nuevos, mientras que los antiguos se están migrando a Markdig.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-109">OPS has standardized on Markdig for all new repos, and older repos are migrating to Markdig.</span></span> <span data-ttu-id="4e7bf-110">Puede probar la representación de Markdown en Markdig frente a otros motores en [https://babelmark.github.io/](https://babelmark.github.io/).</span><span class="sxs-lookup"><span data-stu-id="4e7bf-110">You can test the rendering of Markdown in Markdig vs. other engines at [https://babelmark.github.io/](https://babelmark.github.io/).</span></span>

## <a name="alerts-note-tip-important-caution-warning"></a><span data-ttu-id="4e7bf-111">Alertas (Nota, Sugerencia, Importante, Precaución, Advertencia)</span><span class="sxs-lookup"><span data-stu-id="4e7bf-111">Alerts (Note, Tip, Important, Caution, Warning)</span></span>

<span data-ttu-id="4e7bf-112">Alertas es una extensión de Markdown específica de OPS para crear citas en bloque que se representan en docs.microsoft.com con iconos y colores que indican la importancia del contenido.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-112">Alerts is an OPS-specific Markdown extension to create block quotes that render on docs.microsoft.com with colors and icons that indicate the significance of the content.</span></span> <span data-ttu-id="4e7bf-113">Se admiten los tipos de alerta siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-113">The following alert types are supported:</span></span>

```markdown
> [!NOTE]
> Information the user should notice even if skimming.

> [!TIP]
> Optional information to help a user be more successful.

> [!IMPORTANT]
> Essential information required for user success.

> [!CAUTION]
> Negative potential consequences of an action.

> [!WARNING]
> Dangerous certain consequences of an action.
```

<span data-ttu-id="4e7bf-114">Estas alertas tienen este aspecto en docs.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-114">These alerts look like this on docs.microsoft.com:</span></span>

> [!NOTE]
> <span data-ttu-id="4e7bf-115">Información que el usuario debe apreciar aunque simplemente esté ojeando.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-115">Information the user should notice even if skimming.</span></span>

> [!TIP]
> <span data-ttu-id="4e7bf-116">Información opcional para ayudar al usuario a tener más éxito.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-116">Optional information to help a user be more successful.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e7bf-117">Información esencial requerida para el éxito del usuario.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-117">Essential information required for user success.</span></span>

> [!CAUTION]
> <span data-ttu-id="4e7bf-118">Las posibles consecuencias negativas de una acción.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-118">Negative potential consequences of an action.</span></span>

> [!WARNING]
> <span data-ttu-id="4e7bf-119">Consecuencias peligrosas concretas de una acción.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-119">Dangerous certain consequences of an action.</span></span>

## <a name="code-snippets"></a><span data-ttu-id="4e7bf-120">Fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="4e7bf-120">Code snippets</span></span>

<span data-ttu-id="4e7bf-121">Puede insertar fragmentos de código en los archivos Markdown:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-121">You can embed code snippets in your Markdown files:</span></span>

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a><span data-ttu-id="4e7bf-122">Encabezados</span><span class="sxs-lookup"><span data-stu-id="4e7bf-122">Headings</span></span>

<span data-ttu-id="4e7bf-123">OPS admite seis niveles de título de Markdown:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-123">OPS supports six levels of Markdown headings:</span></span>

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- <span data-ttu-id="4e7bf-124">Debe haber un espacio entre el último `#` y el texto del título.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-124">There must be a space between the last `#` and heading text.</span></span>
- <span data-ttu-id="4e7bf-125">En cada archivo Markdown solo puede haber un título H1.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-125">Each Markdown file must have one and only one H1.</span></span>
- <span data-ttu-id="4e7bf-126">El título H1 debe ser el primer contenido del archivo después del bloque de metadatos YML.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-126">The H1 must be the first content in the file after the YML metadata block.</span></span>
- <span data-ttu-id="4e7bf-127">Los títulos H2 aparecen de forma automáticamente en el menú de navegación de la derecha del archivo publicado.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-127">H2s automatically appear in the right-hand navigating menu of the published file.</span></span> <span data-ttu-id="4e7bf-128">Los títulos de nivel inferior no, por lo que debe usar los títulos H2 de forma estratégica para ayudar a los lectores a desplazarse por el contenido.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-128">Lower-level headings do not, so use H2s strategically to help readers navigate your content.</span></span>
- <span data-ttu-id="4e7bf-129">Los títulos HTML, como `<h1>`, no se recomiendan, y en algunos casos generarán advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-129">HMTL headings, such as `<h1>`, are not recommended and in some cases will cause build warnings.</span></span>
- <span data-ttu-id="4e7bf-130">Puede vincular a los títulos individuales de un archivo mediante [marcadores](#bookmark-links).</span><span class="sxs-lookup"><span data-stu-id="4e7bf-130">You can link to individual headings in a file via [bookmarks](#bookmark-links).</span></span>

## <a name="html"></a><span data-ttu-id="4e7bf-131">HTML</span><span class="sxs-lookup"><span data-stu-id="4e7bf-131">HTML</span></span>

<span data-ttu-id="4e7bf-132">Aunque Markdown admite HTML insertado, no se recomienda HTML para la publicación a través de OPS y, a excepción de una lista limitada de valores, provocará errores o advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-132">Although Markdown supports inline HTML, HTML is not recommended for publishing via OPS, and except for a limited list of values will cause build errors or warnings.</span></span> <!--For more information, see HTML Whitelist. // do we want to add the whitelist? -->

## <a name="images"></a><span data-ttu-id="4e7bf-133">Imágenes</span><span class="sxs-lookup"><span data-stu-id="4e7bf-133">Images</span></span>

<span data-ttu-id="4e7bf-134">La sintaxis para incluir una imagen es:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-134">The syntax to include an image is:</span></span>

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

<span data-ttu-id="4e7bf-135">Donde `alt text` es una breve descripción de la imagen y `<folder path>` es una ruta de acceso relativa a la imagen.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-135">Where `alt text` is a brief description of the image and `<folder path>` is a relative path to the image.</span></span> <span data-ttu-id="4e7bf-136">El texto alternativo es obligatorio para los lectores de pantalla destinados a usuarios con discapacidad visual.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-136">Alternate text is required for screen readers for the visually impaired.</span></span> <span data-ttu-id="4e7bf-137">También es útil si hay un error del sitio donde no se puede representar la imagen.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-137">It is also useful if there is a site bug where the image cannot render.</span></span>

<span data-ttu-id="4e7bf-138">Las imágenes se deben almacenar en una carpeta `/media` dentro del conjunto de documentación.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-138">Images should be stored in a `/media` folder within your doc set.</span></span> <span data-ttu-id="4e7bf-139">De forma predeterminada, se admiten los tipos de archivo siguientes para las imágenes:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-139">The following file types are supported by default for images:</span></span>

- <span data-ttu-id="4e7bf-140">.jpg</span><span class="sxs-lookup"><span data-stu-id="4e7bf-140">.jpg</span></span>
- <span data-ttu-id="4e7bf-141">.png</span><span class="sxs-lookup"><span data-stu-id="4e7bf-141">.png</span></span>

<span data-ttu-id="4e7bf-142">Puede agregar compatibilidad con otros tipos de imagen si los agrega como recursos al archivo docfx.json <!--add link to reference when available--> del conjunto de documentación.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-142">You can add support for other image types by adding them as resources to the docfx.json file<!--add link to reference when available--> for your doc set.</span></span>

## <a name="links"></a><span data-ttu-id="4e7bf-143">Vínculos</span><span class="sxs-lookup"><span data-stu-id="4e7bf-143">Links</span></span>

<span data-ttu-id="4e7bf-144">En la mayoría de los casos, OPS usa vínculos de Markdown estándar a otros archivos y páginas.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-144">In most cases, OPS uses standard Markdown links to other files and pages.</span></span> <span data-ttu-id="4e7bf-145">Los tipos de vínculos se describen en las subsecciones siguientes.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-145">The types of links are described in subsections below.</span></span>

> [!TIP]
> <span data-ttu-id="4e7bf-146">El Paquete de creación de Docs para VS Code puede ayudar a insertar vínculos relativos y marcadores de forma correcta sin la tediosa tarea de tener que determinar las rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-146">The Docs Authoring Pack for VS Code can help insert relative links and bookmarks correctly without the tedium of figuring out the paths!</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e7bf-147">No incluya códigos de configuración regional, como es-ES, en los vínculos a los sitios de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-147">Do not include locale codes, such as en-us, in your links to Microsoft sites.</span></span> <span data-ttu-id="4e7bf-148">Los códigos de configuración regional codificados de forma rígida evitan que se represente el contenido localizado, lo que es una mala experiencia para los usuarios de otras configuraciones regionales e incurre en costes de localización importantes.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-148">Hard-coded locale codes prevent localized content from rendering, which is a bad customer experience for users in other locales and incurs significant localization costs.</span></span> <span data-ttu-id="4e7bf-149">Al copiar una dirección URL de un explorador, el código de configuración regional se incluye de forma predeterminada, por lo que tendrá que eliminarlo manualmente al crear el vínculo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-149">When you copy a URL from a browser, the locale code is included by default, so you need to manually delete it when you create your link.</span></span> <span data-ttu-id="4e7bf-150">Por ejemplo, use:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-150">For example, use:</span></span>
>
> `[Microsoft](https://www.microsoft.com)`
>
> <span data-ttu-id="4e7bf-151">No:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-151">Not:</span></span>
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a><span data-ttu-id="4e7bf-152">Vínculos relativos a archivos del mismo conjunto de documentación</span><span class="sxs-lookup"><span data-stu-id="4e7bf-152">Relative links to files in the same doc set</span></span>

<span data-ttu-id="4e7bf-153">Una ruta de acceso relativa es la ruta de acceso al archivo de destino con respecto al archivo actual.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-153">A relative path is the path to the target file relative to the current file.</span></span> <span data-ttu-id="4e7bf-154">En OPS, se puede usar una ruta de acceso relativa para vincular a otro archivo del mismo conjunto de documentación.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-154">In OPS, you can use a relative path to link to another file within the same doc set.</span></span> <span data-ttu-id="4e7bf-155">La sintaxis para una ruta de acceso relativa es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-155">The syntax for a relative path is as follows:</span></span>

```markdown
[link text](../../folder/filename.md)
```

<span data-ttu-id="4e7bf-156">Donde `../` indica un nivel superior en la jerarquía.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-156">Where `../` indicates one level above in the hierarchy.</span></span>

- <span data-ttu-id="4e7bf-157">La ruta de acceso relativa se resolverá durante la compilación, incluida la eliminación de la extensión .md.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-157">The relative path will be resolved during the build, including removal of the .md extension.</span></span>
- <span data-ttu-id="4e7bf-158">Puede usar "../" para vincular a un archivo de la carpeta principal, pero ese archivo tiene que estar en el mismo conjunto de documentación.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-158">You can use "../" to link to a file in the parent folder, but that file has to be in the same doc set.</span></span> <span data-ttu-id="4e7bf-159">No puede usar "../" para vincular a un archivo en la carpeta de otro conjunto de documentación.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-159">You cannot use "../" to link to a file in another doc set folder.</span></span>
- <span data-ttu-id="4e7bf-160">OPS también admite una forma especial de ruta de acceso relativa que empieza por "~" (por ejemplo, ~/foo/bar.md).</span><span class="sxs-lookup"><span data-stu-id="4e7bf-160">OPS also supports a special form of relative path that starts with "~" (for example, ~/foo/bar.md).</span></span> <span data-ttu-id="4e7bf-161">Esta sintaxis indica un archivo relativo a la carpeta raíz de un conjunto de documentación.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-161">This syntax indicates a file relative to the root folder of a doc set.</span></span> <span data-ttu-id="4e7bf-162">Este tipo de ruta de acceso también se valida y resuelve durante la compilación.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-162">This kind of path is also validated and resolved during the build.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e7bf-163">Incluya la extensión de archivo en la ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-163">Include the file extension in the relative path.</span></span> <span data-ttu-id="4e7bf-164">La compilación valida la existencia del archivo de destino de esa ruta de acceso relativa.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-164">Build validates the existence of the target file of that relative path.</span></span> <span data-ttu-id="4e7bf-165">Si la ruta de acceso relativa no incluye la extensión de archivo, es probable que la compilación notifique una advertencia de vínculo roto.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-165">If relative path does not include file extension, it is likely build will report a warning of broken link.</span></span> <span data-ttu-id="4e7bf-166">Por ejemplo, use:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-166">For example, use:</span></span>
>
> `[link text](../../folder/filename.md)`
>
> <span data-ttu-id="4e7bf-167">No:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-167">Not:</span></span>
>
> `[link text](../../folder/filename)`

### <a name="absolute-links-to-other-files-in-ops"></a><span data-ttu-id="4e7bf-168">Vínculos absolutos a otros archivos en OPS</span><span class="sxs-lookup"><span data-stu-id="4e7bf-168">Absolute links to other files in OPS</span></span>

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

<span data-ttu-id="4e7bf-169">No incluya la extensión de archivo (.md).</span><span class="sxs-lookup"><span data-stu-id="4e7bf-169">Do not include the file extension (.md).</span></span> <span data-ttu-id="4e7bf-170">Esto se vincula al archivo de información general de Linux desde fuera del conjunto de documentación "articles" de Azure.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-170">This links to the Linux overview file from outside the Azure "articles" doc set.</span></span>

### <a name="links-to-external-sites"></a><span data-ttu-id="4e7bf-171">Vínculos a sitios externos</span><span class="sxs-lookup"><span data-stu-id="4e7bf-171">Links to external sites</span></span>

```markdown
[Microsoft](https://www.microsoft.com)
```

<span data-ttu-id="4e7bf-172">Vínculo basado en una dirección URL a otra página web (debe incluir https://).</span><span class="sxs-lookup"><span data-stu-id="4e7bf-172">URL-based link to another web page (must include https://).</span></span>

### <a name="bookmark-links"></a><span data-ttu-id="4e7bf-173">Vínculos de marcador</span><span class="sxs-lookup"><span data-stu-id="4e7bf-173">Bookmark links</span></span>

<span data-ttu-id="4e7bf-174">Vínculo de marcador a un título de otro archivo en el mismo repositorio:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-174">Bookmark link to a heading in another file in the same repo:</span></span>

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

<span data-ttu-id="4e7bf-175">Vínculo de marcador a un título del archivo actual:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-175">Bookmark link to a heading in the current file:</span></span>

```markdown
[Managed Disks](#managed-disks)
```

<span data-ttu-id="4e7bf-176">Use una etiqueta hash seguida de las palabras del título sin puntuación y sustituya los espacios por guiones.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-176">Use a hash tag followed by the words of the heading with punctuation removed and spaces replaced with dashes.</span></span>

### <a name="explicit-anchor-links"></a><span data-ttu-id="4e7bf-177">Vínculos delimitadores explícitos</span><span class="sxs-lookup"><span data-stu-id="4e7bf-177">Explicit anchor links</span></span>

<span data-ttu-id="4e7bf-178">Los vínculos delimitadores explícitos en los que se usa la etiqueta `<a>` de HTML **no son necesarios ni se recomiendan**, excepto en páginas de sitio central o de aterrizaje.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-178">Explicit anchor links using the `<a>` HTML tag are **not required or recommended** except in hub and landing pages.</span></span> <span data-ttu-id="4e7bf-179">Use los marcadores como se describió anteriormente en los archivos Markdown generales.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-179">Use bookmarks as described above in general Markdown files.</span></span> <span data-ttu-id="4e7bf-180">Para las páginas de sitio central o de aterrizaje, use los delimitadores de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-180">For hub and landing pages, use anchors as follows:</span></span>

<span data-ttu-id="4e7bf-181">`## <a id="AnchorText"> </a>Header text` o `## <a name="AnchorText"> </a>Header text`</span><span class="sxs-lookup"><span data-stu-id="4e7bf-181">`## <a id="AnchorText"> </a>Header text` or `## <a name="AnchorText"> </a>Header text`</span></span>

<span data-ttu-id="4e7bf-182">Para vincular a delimitadores explícitos, use la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-182">To link to explicit anchors, use the following syntax:</span></span>

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a><span data-ttu-id="4e7bf-183">Vínculos XREF (de referencia cruzada)</span><span class="sxs-lookup"><span data-stu-id="4e7bf-183">XREF (cross reference) links</span></span>

<span data-ttu-id="4e7bf-184">Para vincular a páginas de referencia de API generadas automáticamente del conjunto de documentación actual o de otros, use vínculos XREF con el identificador único (UID).</span><span class="sxs-lookup"><span data-stu-id="4e7bf-184">To link to auto-generated API references pages in the current doc set or other doc sets, use XREF links with the unique ID (UID).</span></span>

> [!NOTE]
> <span data-ttu-id="4e7bf-185">Para hacer referencia a páginas de referencia de API en otros conjuntos de documentación, tendrá que agregar la configuración `xrefService` en el archivo `docfx.json`.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-185">To reference API reference pages in other doc sets, you need to add `xrefService` configuration in `docfx.json` file.</span></span>
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

<span data-ttu-id="4e7bf-186">El UID equivale al nombre de clase y miembro completo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-186">The UID equates to the fully qualified class and member name.</span></span> <span data-ttu-id="4e7bf-187">Si agrega un \* después del UID, el vínculo representará a la página de sobrecarga y no a una API específica.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-187">If you add a \* after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="4e7bf-188">Por ejemplo, use `List<T>.BinarySearch*` para vincular a la página del método BinarySearch en lugar de vincular a una sobrecarga específica como `List<T>.BinarySearch(T, IComparer<T>)`.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-188">For example, use `List<T>.BinarySearch*` to link to the BinarySearch Method page instead of linking to a specific overload such as `List<T>.BinarySearch(T, IComparer<T>)`.</span></span>

<span data-ttu-id="4e7bf-189">Puede usar una de las sintaxis siguientes:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-189">You can use one of the following syntaxes:</span></span>

- <span data-ttu-id="4e7bf-190">Vinculación automática: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="4e7bf-190">Auto-link: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`</span></span>

  <span data-ttu-id="4e7bf-191">El parámetro de consulta `displayProperty` opcional genera un texto de vínculo completo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-191">The optional `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="4e7bf-192">De forma predeterminada, el texto del vínculo muestra solo el nombre de miembro o tipo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-192">By default, link text shows only the member or type name.</span></span>

- <span data-ttu-id="4e7bf-193">Vínculo de Markdown: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="4e7bf-193">Markdown link: `[link text](xref:UID)`</span></span>
  
  <span data-ttu-id="4e7bf-194">Se utiliza cuando se desea personalizar el texto del vínculo mostrado.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-194">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="4e7bf-195">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-195">Examples:</span></span>

- <span data-ttu-id="4e7bf-196">`<xref:System.String>` se representa como "String".</span><span class="sxs-lookup"><span data-stu-id="4e7bf-196">`<xref:System.String>` renders as "String".</span></span>
- <span data-ttu-id="4e7bf-197">`<xref:System.String?displayProperty=nameWithType>` se representa como "System.String".</span><span class="sxs-lookup"><span data-stu-id="4e7bf-197">`<xref:System.String?displayProperty=nameWithType>` renders as "System.String".</span></span>
- <span data-ttu-id="4e7bf-198">`[String class](xref:System.String)` se representa como "String class".</span><span class="sxs-lookup"><span data-stu-id="4e7bf-198">`[String class](xref:System.String)` renders as "String class".</span></span>

<span data-ttu-id="4e7bf-199">En este momento, no hay manera de encontrar con facilidad los UID.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-199">Right now, there is no easy way to find the UIDs.</span></span> <span data-ttu-id="4e7bf-200"><!-- ? -->La mejor manera de encontrar el UID de una API es ver el origen de la página de API a la que se quiere vincular y buscar el valor ms.assetid.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-200"><!-- ? -->The best way to find the UID for an API is to view the source for the API page you want to link to and find the ms.assetid value.</span></span> <span data-ttu-id="4e7bf-201">No se muestran los valores individuales de sobrecarga en el origen.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-201">Individual overload values are not shown in the source.</span></span> <span data-ttu-id="4e7bf-202">Estamos trabajando para mejorar el sistema próximamente.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-202">We're working on having a better system in the future.</span></span>

<span data-ttu-id="4e7bf-203">Cuando el UID contiene los caracteres especiales \`, \# o \*, el valor de UID debe codificarse en HTML como `%60`, `%23` y `%2A`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-203">When the UID contains the special characters \`, \#, or \*, the UID value needs to be HTML encoded as `%60`, `%23`, and `%2A`, respectively.</span></span> <span data-ttu-id="4e7bf-204">En ocasiones verá paréntesis codificados, pero no es un requisito.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-204">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="4e7bf-205">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-205">Examples:</span></span>

- <span data-ttu-id="4e7bf-206">System.Threading.Tasks.Task\`1 se convierte en `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="4e7bf-206">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="4e7bf-207">System.Exception.\#ctor se convierte en `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="4e7bf-207">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="4e7bf-208">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se convierte en `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="4e7bf-208">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a><span data-ttu-id="4e7bf-209">Listas (Numeradas, Con viñetas, De comprobación)</span><span class="sxs-lookup"><span data-stu-id="4e7bf-209">Lists (Numbered, Bulleted, Checklist)</span></span>

### <a name="numbered-list"></a><span data-ttu-id="4e7bf-210">Lista numerada</span><span class="sxs-lookup"><span data-stu-id="4e7bf-210">Numbered list</span></span>

<span data-ttu-id="4e7bf-211">Para crear una lista numerada, puede usar todo números 1, que se representarán como una lista secuencial cuando se publique.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-211">To create a numbered list, you can use all 1s, which are rendered as a sequential list when published.</span></span> <span data-ttu-id="4e7bf-212">Para mejorar la legibilidad del origen, puede incrementar las listas.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-212">For increased source readability, you can increment your lists.</span></span>

<span data-ttu-id="4e7bf-213">No use letras en las listas, ni siquiera en las anidadas,</span><span class="sxs-lookup"><span data-stu-id="4e7bf-213">Do not use letters in lists, including nested lists.</span></span> <span data-ttu-id="4e7bf-214">dado que no se representan correctamente cuando se publican a través de OPS.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-214">They do not render correctly when published via OPS.</span></span> <span data-ttu-id="4e7bf-215">Las listas anidadas en las que se usan números se representarán como letras en minúscula al publicarse.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-215">Nested lists using numbers will render as lowercase letters when published.</span></span> <span data-ttu-id="4e7bf-216">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-216">For example:</span></span>

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

<span data-ttu-id="4e7bf-217">Esto se representa de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-217">This renders as follows:</span></span>

1. <span data-ttu-id="4e7bf-218">Esto es</span><span class="sxs-lookup"><span data-stu-id="4e7bf-218">This is</span></span>
1. <span data-ttu-id="4e7bf-219">una lista numerada principal</span><span class="sxs-lookup"><span data-stu-id="4e7bf-219">a parent numbered list</span></span>
   1. <span data-ttu-id="4e7bf-220">y esto es</span><span class="sxs-lookup"><span data-stu-id="4e7bf-220">and this is</span></span>
   1. <span data-ttu-id="4e7bf-221">una lista numerada anidada</span><span class="sxs-lookup"><span data-stu-id="4e7bf-221">a nested numbered list</span></span>
1. <span data-ttu-id="4e7bf-222">(fin)</span><span class="sxs-lookup"><span data-stu-id="4e7bf-222">(fin)</span></span>

### <a name="bulleted-list"></a><span data-ttu-id="4e7bf-223">Lista con viñetas</span><span class="sxs-lookup"><span data-stu-id="4e7bf-223">Bulleted list</span></span>

<span data-ttu-id="4e7bf-224">Para crear una lista con viñetas, use `-` seguido de un espacio al principio de cada línea:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-224">To create a bulleted list, use `-` followed by a space at the beginning of each line:</span></span>

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

<span data-ttu-id="4e7bf-225">Esto se representa de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-225">This renders as follows:</span></span>

- <span data-ttu-id="4e7bf-226">Esto es</span><span class="sxs-lookup"><span data-stu-id="4e7bf-226">This is</span></span>
- <span data-ttu-id="4e7bf-227">una lista con viñetas principal</span><span class="sxs-lookup"><span data-stu-id="4e7bf-227">a parent bulleted list</span></span>
  - <span data-ttu-id="4e7bf-228">y esto es</span><span class="sxs-lookup"><span data-stu-id="4e7bf-228">and this is</span></span>
  - <span data-ttu-id="4e7bf-229">una lista con viñetas anidada</span><span class="sxs-lookup"><span data-stu-id="4e7bf-229">a nested bulleted list</span></span>
- <span data-ttu-id="4e7bf-230">Listo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-230">All done!</span></span>

### <a name="checklist"></a><span data-ttu-id="4e7bf-231">Lista de comprobación</span><span class="sxs-lookup"><span data-stu-id="4e7bf-231">Checklist</span></span>

<span data-ttu-id="4e7bf-232">Las listas de comprobación se pueden usar en docs.microsoft.com (solo) a través de una extensión de Markdown personalizada:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-232">Checklists are available for use on docs.microsoft.com (only) via a custom Markdown extension:</span></span>

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

<span data-ttu-id="4e7bf-233">Este ejemplo se representa en docs.microsoft.com de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-233">This example renders on docs.microsoft.com like this:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="4e7bf-234">Elemento de lista 1</span><span class="sxs-lookup"><span data-stu-id="4e7bf-234">List item 1</span></span>
> * <span data-ttu-id="4e7bf-235">Elemento de lista 2</span><span class="sxs-lookup"><span data-stu-id="4e7bf-235">List item 2</span></span>
> * <span data-ttu-id="4e7bf-236">Elemento de lista 3</span><span class="sxs-lookup"><span data-stu-id="4e7bf-236">List item 3</span></span>

<span data-ttu-id="4e7bf-237">Use las listas de comprobación al principio o al final de un artículo para resumir el contenido de tipo "Qué aprenderá" o "Qué ha aprendido".</span><span class="sxs-lookup"><span data-stu-id="4e7bf-237">Use checklists at the beginning or end of an article to summarize "What will you learn" or "What have you learned" content.</span></span> <span data-ttu-id="4e7bf-238">No agregue listas de comprobación aleatorias en los artículos.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-238">Do not add random checklists throughout your articles.</span></span>
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a><span data-ttu-id="4e7bf-239">Acción "Paso siguiente"</span><span class="sxs-lookup"><span data-stu-id="4e7bf-239">Next step action</span></span>

<span data-ttu-id="4e7bf-240">Puede usar una extensión personalizada para agregar un botón de acción "Paso siguiente" a las páginas de docs.microsoft.com (solamente).</span><span class="sxs-lookup"><span data-stu-id="4e7bf-240">You can use a custom extension to add a next step action button to pages on docs.microsoft.com (only).</span></span>

<span data-ttu-id="4e7bf-241">La sintaxis es la siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-241">The syntax is as follows:</span></span>

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

<span data-ttu-id="4e7bf-242">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-242">For example:</span></span>

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

<span data-ttu-id="4e7bf-243">Esto se representa de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-243">This renders as follows:</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4e7bf-244">Más información sobre el estilo básico</span><span class="sxs-lookup"><span data-stu-id="4e7bf-244">Learn about basic style</span></span>](style-quick-start.md)

<span data-ttu-id="4e7bf-245">Puede usar cualquier vínculo compatible en una acción "Paso siguiente", incluido un vínculo de Markdown a otra página web.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-245">You can use any supported link in a next step action, including a Markdown link to another web page.</span></span> <span data-ttu-id="4e7bf-246">En la mayoría de los casos, el vínculo de la acción "Paso siguiente" será relativo a otro archivo del mismo conjunto de documentación.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-246">In most cases, the next action link will be a relative link to another file in the same doc set.</span></span>

## <a name="section-definition"></a><span data-ttu-id="4e7bf-247">Definición de secciones</span><span class="sxs-lookup"><span data-stu-id="4e7bf-247">Section definition</span></span>

<span data-ttu-id="4e7bf-248"><!-- more info about this would be helpful! --> Es posible que necesite definir una sección.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-248"><!-- more info about this would be helpful! --> You might need to define a section.</span></span> <span data-ttu-id="4e7bf-249">Esta sintaxis se suele usar en tablas de código.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-249">This syntax is mostly used for code tables.</span></span>
<span data-ttu-id="4e7bf-250">Vea el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-250">See the following example:</span></span>

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

<span data-ttu-id="4e7bf-251">El texto de Markdown de la cita en bloque anterior se mostrará como:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-251">The preceding blockquote Markdown text will be rendered as:</span></span>
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a><span data-ttu-id="4e7bf-252">Selectores</span><span class="sxs-lookup"><span data-stu-id="4e7bf-252">Selectors</span></span>

<span data-ttu-id="4e7bf-253"><!-- could be more clear! --> Puede usar un selector cuando quiera conectar páginas diferentes del mismo artículo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-253"><!-- could be more clear! --> You can use a selector when you want to connect different pages for the same article.</span></span> <span data-ttu-id="4e7bf-254">Así, los lectores podrán alternar entre esas páginas.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-254">Readers can then switch between those pages.</span></span>

> [!NOTE]
> <span data-ttu-id="4e7bf-255">Esta extensión funciona de forma diferente en docs.microsoft.com y en MSDN.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-255">This extension works differently between docs.microsoft.com and MSDN.</span></span> <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a><span data-ttu-id="4e7bf-256">Selector único</span><span class="sxs-lookup"><span data-stu-id="4e7bf-256">Single selector</span></span>

```
> [!div class="op_single_selector"]
> - [Universal Windows](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)
```

<span data-ttu-id="4e7bf-257">...se mostrará así:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-257">... will be rendered like this:</span></span>

> [!div class="op_single_selector"]
> - [Windows universal](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a><span data-ttu-id="4e7bf-266">Selector múltiple</span><span class="sxs-lookup"><span data-stu-id="4e7bf-266">Multi-selector</span></span>

```
> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)
```

<span data-ttu-id="4e7bf-267">...se mostrará así:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-267">... will be rendered like this:</span></span>

> [!div class="op_multi_selector" title1="Platform" title2="Backend"]
> - [(iOS | .NET)](how-to-write-workflows-major.md)
> - [(iOS | JavaScript)](how-to-write-workflows-major.md)
> - [(Windows universal C# | .NET)](how-to-write-workflows-major.md)
> - [(Windows universal C# | Javascript)](how-to-write-workflows-major.md)
> - [(Windows Phone | .NET)](how-to-write-workflows-major.md)
> - [(Windows Phone | Javascript)](how-to-write-workflows-major.md)
> - [(Android | .NET)](how-to-write-workflows-major.md)
> - [(Android | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin iOS | Javascript)](how-to-write-workflows-major.md)
> - [(Xamarin Android | Javascript)](how-to-write-workflows-major.md)

<!-- uncomment and link when Cory's topic is live
## Tabbed content

Tabs are a Markdown extension for docs.microsoft.com that allow us to present different versions of content, such as procedural steps to accomplish the same task on different platforms, in a tabbed format.

Because the syntax and requirements for tabbed content are fairly complex, they are documented separately in Tabbed Content.
-->

## <a name="tables"></a><span data-ttu-id="4e7bf-278">Tablas</span><span class="sxs-lookup"><span data-stu-id="4e7bf-278">Tables</span></span>

<span data-ttu-id="4e7bf-279">La forma más sencilla de crear una tabla en Markdown es usar barras verticales y líneas.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-279">The simplest way to create a table in Markdown is to use pipes and lines.</span></span> <span data-ttu-id="4e7bf-280">Para crear una tabla estándar con un encabezado, siga la primera línea con una línea discontinua:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-280">To create a standard table with a header, follow the first line with dashed line:</span></span>

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

<span data-ttu-id="4e7bf-281">Esto se representa de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-281">This renders as follows:</span></span>

|<span data-ttu-id="4e7bf-282">Esto es</span><span class="sxs-lookup"><span data-stu-id="4e7bf-282">This is</span></span>   |<span data-ttu-id="4e7bf-283">un sencillo</span><span class="sxs-lookup"><span data-stu-id="4e7bf-283">a simple</span></span>   |<span data-ttu-id="4e7bf-284">encabezado de tabla</span><span class="sxs-lookup"><span data-stu-id="4e7bf-284">table header</span></span>|
|----------|-----------|------------|
|<span data-ttu-id="4e7bf-285">los datos</span><span class="sxs-lookup"><span data-stu-id="4e7bf-285">table</span></span>     |<span data-ttu-id="4e7bf-286">de la tabla</span><span class="sxs-lookup"><span data-stu-id="4e7bf-286">data</span></span>       |<span data-ttu-id="4e7bf-287">aquí</span><span class="sxs-lookup"><span data-stu-id="4e7bf-287">here</span></span>        |
|<span data-ttu-id="4e7bf-288">no es</span><span class="sxs-lookup"><span data-stu-id="4e7bf-288">it doesn't</span></span>|<span data-ttu-id="4e7bf-289">necesario que</span><span class="sxs-lookup"><span data-stu-id="4e7bf-289">actually</span></span>   |<span data-ttu-id="4e7bf-290">se alineen correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-290">have to line up nicely!</span></span>||

<span data-ttu-id="4e7bf-291">También puede crear una tabla sin encabezado.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-291">You can also create a table without a header.</span></span> <span data-ttu-id="4e7bf-292">Por ejemplo, para crear una lista con varias columnas:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-292">For example, to create a multiple-column list:</span></span>

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

<span data-ttu-id="4e7bf-293">Esto se representa de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-293">This renders like this:</span></span>

|   |   |
| - | - |
| <span data-ttu-id="4e7bf-294">Esta</span><span class="sxs-lookup"><span data-stu-id="4e7bf-294">This</span></span> | <span data-ttu-id="4e7bf-295">tabla</span><span class="sxs-lookup"><span data-stu-id="4e7bf-295">table</span></span> |
| <span data-ttu-id="4e7bf-296">no tiene</span><span class="sxs-lookup"><span data-stu-id="4e7bf-296">has no</span></span> | <span data-ttu-id="4e7bf-297">encabezado</span><span class="sxs-lookup"><span data-stu-id="4e7bf-297">header</span></span> |

<span data-ttu-id="4e7bf-298">Las columnas se pueden alinear usando dos puntos:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-298">You can align the columns by using colons:</span></span>

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

<span data-ttu-id="4e7bf-299">Se representa de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-299">Renders as follows:</span></span>

|                  |
|------------------|
|    <span data-ttu-id="4e7bf-300">alineado a la derecha:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-300">right aligned:</span></span>|
|<span data-ttu-id="4e7bf-301">:alineado a la izquierda</span><span class="sxs-lookup"><span data-stu-id="4e7bf-301">:left aligned</span></span>     |
|<span data-ttu-id="4e7bf-302">:centrado        :</span><span class="sxs-lookup"><span data-stu-id="4e7bf-302">:centered        :</span></span>|

> [!TIP]
> La Extensión de creación de Docs para VS Code facilita la adición de tablas de Markdown básicas.
>
> También puede usar un [generador de tablas en línea](http://www.tablesgenerator.com/markdown_tables).

### <a name="mx-tdbreakall"></a><span data-ttu-id="4e7bf-305">mx-tdBreakAll</span><span class="sxs-lookup"><span data-stu-id="4e7bf-305">mx-tdBreakAll</span></span>

> [!IMPORTANT]
> Esto solo funciona en el sitio docs.microsoft.com.

<span data-ttu-id="4e7bf-307">Si crea una tabla en Markdown, podría expandirse hacia el panel de navegación de la derecha y llegar a ser ilegible.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-307">If you create a table in Markdown, the table might expand to the right navigation and become unreadable.</span></span> <span data-ttu-id="4e7bf-308">Este problema se puede solucionar permitiendo que la representación de Docs interrumpa la tabla cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-308">You can solve that by allowing Docs rendering to break the table when needed.</span></span> <span data-ttu-id="4e7bf-309">Basta con ajustar la tabla con la clase personalizada `[!div class="mx-tdBreakAll"]`.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-309">Just wrap up the table with the custom class `[!div class="mx-tdBreakAll"]`.</span></span>

<span data-ttu-id="4e7bf-310">Aquí tiene un código de Markdown de ejemplo de una tabla con tres filas que se ajustará con un elemento `div` con el nombre de clase `mx-tdBreakAll`.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-310">Here is a Markdown sample of a table with three rows that will be wrapped by a `div` with the class name `mx-tdBreakAll`.</span></span>

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

<span data-ttu-id="4e7bf-311">Se mostrará así:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-311">It will be rendered like this:</span></span>

> [!div class="mx-tdBreakAll"]
> |<span data-ttu-id="4e7bf-312">Nombre</span><span class="sxs-lookup"><span data-stu-id="4e7bf-312">Name</span></span>|<span data-ttu-id="4e7bf-313">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e7bf-313">Syntax</span></span>|<span data-ttu-id="4e7bf-314">¿Es obligatorio para la instalación silenciosa?</span><span class="sxs-lookup"><span data-stu-id="4e7bf-314">Mandatory for silent installation?</span></span>|<span data-ttu-id="4e7bf-315">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e7bf-315">Description</span></span>|
> |-------------|----------|---------|---------|
> |<span data-ttu-id="4e7bf-316">Quiet</span><span class="sxs-lookup"><span data-stu-id="4e7bf-316">Quiet</span></span>|<span data-ttu-id="4e7bf-317">/quiet</span><span class="sxs-lookup"><span data-stu-id="4e7bf-317">/quiet</span></span>|<span data-ttu-id="4e7bf-318">Sí</span><span class="sxs-lookup"><span data-stu-id="4e7bf-318">Yes</span></span>|<span data-ttu-id="4e7bf-319">Ejecuta el instalador sin mostrar ni interfaz de usuario ni avisos.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-319">Runs the installer, displaying no UI and no prompts.</span></span>|
> |<span data-ttu-id="4e7bf-320">NoRestart</span><span class="sxs-lookup"><span data-stu-id="4e7bf-320">NoRestart</span></span>|<span data-ttu-id="4e7bf-321">/norestart</span><span class="sxs-lookup"><span data-stu-id="4e7bf-321">/norestart</span></span>|<span data-ttu-id="4e7bf-322">No</span><span class="sxs-lookup"><span data-stu-id="4e7bf-322">No</span></span>|<span data-ttu-id="4e7bf-323">Omite cualquier intento de reinicio.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-323">Suppresses any attempts to restart.</span></span> <span data-ttu-id="4e7bf-324">La interfaz de usuario se mostrará de manera predeterminada después de reiniciar.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-324">By default, the UI will prompt before restart.</span></span>|
> |<span data-ttu-id="4e7bf-325">Help</span><span class="sxs-lookup"><span data-stu-id="4e7bf-325">Help</span></span>|<span data-ttu-id="4e7bf-326">/help</span><span class="sxs-lookup"><span data-stu-id="4e7bf-326">/help</span></span>|<span data-ttu-id="4e7bf-327">No</span><span class="sxs-lookup"><span data-stu-id="4e7bf-327">No</span></span>|<span data-ttu-id="4e7bf-328">Proporciona ayuda y referencia rápida.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-328">Provides help and quick reference.</span></span> <span data-ttu-id="4e7bf-329">Muestra el uso correcto del comando de instalación, incluida una lista de todas las opciones y los comportamientos.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-329">Displays the correct use of the setup command, including a list of all options and behaviors.</span></span>|

### <a name="mx-tdcol2breakall"></a><span data-ttu-id="4e7bf-330">mx-tdCol2BreakAll</span><span class="sxs-lookup"><span data-stu-id="4e7bf-330">mx-tdCol2BreakAll</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e7bf-331">Esto solo funciona en el sitio docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-331">This only works on the docs.microsoft.com site.</span></span>

<span data-ttu-id="4e7bf-332">De vez en cuando, es posible que haya palabras muy largas en la segunda columna de una tabla.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-332">From time to time, you might have very long words in the second column of a table.</span></span> <span data-ttu-id="4e7bf-333">Para asegurarse de que se dividan correctamente, puede aplicar la clase `mx-tdCol2BreakAll` mediante la sintaxis de ajuste `div` mostrada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-333">To ensure they are broken apart nicely, you can apply the class `mx-tdCol2BreakAll` by using the `div` wrapper syntax as shown earlier.</span></span>

### <a name="html-tables"></a><span data-ttu-id="4e7bf-334">Tablas HTML</span><span class="sxs-lookup"><span data-stu-id="4e7bf-334">HTML Tables</span></span>

<span data-ttu-id="4e7bf-335">Las tablas HTML no se recomiendan para docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-335">HTML tables are not recommended for docs.microsoft.com.</span></span> <span data-ttu-id="4e7bf-336">No son lenguaje natural en el código, lo que es un principio clave de Markdown.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-336">They are not human readable in the source - which is a key principle of Markdown.</span></span>

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a><span data-ttu-id="4e7bf-337">Vídeos</span><span class="sxs-lookup"><span data-stu-id="4e7bf-337">Videos</span></span>

### <a name="embedding-videos-into-a-markdown-page"></a><span data-ttu-id="4e7bf-338">Inserción de vídeos en una página de Markdown</span><span class="sxs-lookup"><span data-stu-id="4e7bf-338">Embedding videos into a Markdown page</span></span>

<span data-ttu-id="4e7bf-339">En la actualidad, OPS puede admitir vídeos publicados en una de estas tres ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-339">Currently, OPS can support videos published to one of three locations:</span></span>

- <span data-ttu-id="4e7bf-340">YouTube</span><span class="sxs-lookup"><span data-stu-id="4e7bf-340">YouTube</span></span>
- <span data-ttu-id="4e7bf-341">Channel 9</span><span class="sxs-lookup"><span data-stu-id="4e7bf-341">Channel 9</span></span>
- <span data-ttu-id="4e7bf-342">El sistema "One Player" de Microsoft</span><span class="sxs-lookup"><span data-stu-id="4e7bf-342">Microsoft's own 'One Player' system</span></span>

<span data-ttu-id="4e7bf-343">Así, puede insertar un vídeo usando la siguiente sintaxis y OPS lo mostrará.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-343">You can embed a video with the following syntax, and OPS will render it.</span></span>

```markdown
> [!VIDEO <embedded_video_link>]
```

<span data-ttu-id="4e7bf-344">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-344">Example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

<span data-ttu-id="4e7bf-345">...se representará como:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-345">... will be rendered as:</span></span>

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

<span data-ttu-id="4e7bf-346">Y aparecerá así en las páginas publicadas:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-346">And it will be displayed like this on published pages:</span></span>

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> <span data-ttu-id="4e7bf-347">La dirección URL del vídeo de CH9 debe empezar por `https` y acabar en `/player`.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-347">The CH9 video URL should start with `https` and end with `/player`.</span></span> <span data-ttu-id="4e7bf-348">De lo contrario, se insertará toda la página en lugar de insertarse solo el vídeo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-348">Otherwise, it will embed the whole page instead of the video only.</span></span>

### <a name="uploading-new-videos"></a><span data-ttu-id="4e7bf-349">Carga de vídeos nuevos</span><span class="sxs-lookup"><span data-stu-id="4e7bf-349">Uploading new videos</span></span>

<span data-ttu-id="4e7bf-350">Todos los vídeos nuevos se deben cargar mediante el proceso siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-350">Any new videos should be uploaded using the following process:</span></span>

1. <span data-ttu-id="4e7bf-351">Únase al grupo **docs_video_users** en IDWEB.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-351">Join the **docs_video_users** group on IDWEB.</span></span>
1. <span data-ttu-id="4e7bf-352">Vaya a https://aka.ms/VideoUploadRequest y rellene los detalles del vídeo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-352">Go to https://aka.ms/VideoUploadRequest and fill in the details for your video.</span></span> <span data-ttu-id="4e7bf-353">Necesitará lo siguiente (tenga en cuenta que ninguno de estos elementos será visible para el público):</span><span class="sxs-lookup"><span data-stu-id="4e7bf-353">You will need (note that none of these items will be visible to the public):</span></span>
    1. <span data-ttu-id="4e7bf-354">Un título para el vídeo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-354">A title for your video.</span></span>
    1. <span data-ttu-id="4e7bf-355">Una lista de los productos y servicios con los que está relacionado el vídeo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-355">A list of products/services that your video is related to.</span></span>
    1. <span data-ttu-id="4e7bf-356">La página de destino o, si todavía no la tiene, el conjunto de documentación en el que se va a hospedar el vídeo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-356">The target page or (if you don’t have the page yet) doc set that your video will be hosted on.</span></span>
    1. <span data-ttu-id="4e7bf-357">Un vínculo al archivo MP4 del vídeo (si no tiene una ubicación para colocar el archivo, lo puede colocar aquí de forma temporal: `\\scratch2\scratch\apex`).</span><span class="sxs-lookup"><span data-stu-id="4e7bf-357">A link to the MP4 file for your video (if you don’t have a location to put the file, you can put it here temporarily:   `\\scratch2\scratch\apex`).</span></span> <span data-ttu-id="4e7bf-358">Los archivos MP4 deben tener una resolución de 720p o superior.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-358">MP4 files should be 720p or higher.</span></span>
    1. <span data-ttu-id="4e7bf-359">Una descripción del vídeo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-359">A description of the video.</span></span>
1. <span data-ttu-id="4e7bf-360">Envíe (guarde) ese elemento.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-360">Submit (save) that item.</span></span>
1. <span data-ttu-id="4e7bf-361">El vídeo se cargará en el plazo de dos días laborables.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-361">Within two business days, the video will get uploaded.</span></span> <span data-ttu-id="4e7bf-362">El vínculo que necesita para insertar se colocará en el elemento de trabajo, y se le *devolverá* para resolverlo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-362">The link you need for embedding will be placed into the work item, and it will be resolved *back to you*.</span></span>
1. <span data-ttu-id="4e7bf-363">Una vez que haya obtenido el vínculo del vídeo, cierre el elemento de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4e7bf-363">Once you have grabbed the video link, close the work item.</span></span>
1. <span data-ttu-id="4e7bf-364">Después, puede agregar el vínculo del vídeo a la publicación, mediante esta sintaxis:</span><span class="sxs-lookup"><span data-stu-id="4e7bf-364">The video link can then be added to your post, using this syntax:</span></span>

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
