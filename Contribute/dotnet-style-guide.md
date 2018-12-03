---
title: Plantilla y hoja de referencia para los artículos de .NET
description: Este artículo contiene una plantilla muy útil que se puede usar para crear artículos para los repositorios de documentación de .NET.
ms.date: 11/07/2018
ms.openlocfilehash: 15f64ec86c475e2da2f6539c8f388d076389c4e0
ms.sourcegitcommit: 68d81b61ffa60aba16acfed023760449e16de91b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2018
ms.locfileid: "52299669"
---
# <a name="metadata-and-markdown-template-for-net-docs"></a><span data-ttu-id="5c10b-103">Metadatos y plantilla de Markdown para la documentación de .NET</span><span class="sxs-lookup"><span data-stu-id="5c10b-103">Metadata and Markdown template for .NET docs</span></span>

<span data-ttu-id="5c10b-104">Esta plantilla de dotnet/docs contiene ejemplos de sintaxis de Markdown, además de instrucciones sobre cómo establecer los metadatos.</span><span class="sxs-lookup"><span data-stu-id="5c10b-104">This dotnet/docs template contains examples of Markdown syntax, as well as guidance on setting the metadata.</span></span>

<span data-ttu-id="5c10b-105">Al crear un archivo Markdown, debe copiar la plantilla incluida en un archivo nuevo, completar los metadatos como se especifica a continuación y establecer el encabezado H1 anterior en el título del artículo.</span><span class="sxs-lookup"><span data-stu-id="5c10b-105">When creating a Markdown file, you should copy the included template to a new file, fill out the metadata as specified below, and set the H1 heading above to the title of the article.</span></span>

## <a name="metadata"></a><span data-ttu-id="5c10b-106">Metadatos</span><span class="sxs-lookup"><span data-stu-id="5c10b-106">Metadata</span></span>

<span data-ttu-id="5c10b-107">El bloque de metadatos necesario está en el siguiente bloque de metadatos de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5c10b-107">The required metadata block is in the following sample metadata block:</span></span>

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- <span data-ttu-id="5c10b-108">**Debe** haber un espacio entre los dos puntos (:) y el valor de un elemento de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5c10b-108">You **must** have a space between the colon (:) and the value for a metadata element.</span></span>
- <span data-ttu-id="5c10b-109">En un valor (por ejemplo en un título) los dos puntos interrumpen al analizador de metadatos.</span><span class="sxs-lookup"><span data-stu-id="5c10b-109">Colons in a value (for example, a title) break the metadata parser.</span></span> <span data-ttu-id="5c10b-110">En este caso, incluya el título entre comillas dobles (por ejemplo, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span><span class="sxs-lookup"><span data-stu-id="5c10b-110">In this case, surround the title with double quotes (for example, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).</span></span>
- <span data-ttu-id="5c10b-111">**title**: aparece en los resultados de los motores de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5c10b-111">**title**: Appears in search engine results.</span></span> <span data-ttu-id="5c10b-112">El título no debe ser idéntico al del encabezado H1, y debe contener 60 caracteres o menos.</span><span class="sxs-lookup"><span data-stu-id="5c10b-112">The title shouldn't be identical to the title in your H1 heading, and it should contain 60 characters or less.</span></span>
- <span data-ttu-id="5c10b-113">**description**: resume el contenido del artículo.</span><span class="sxs-lookup"><span data-stu-id="5c10b-113">**description**: Summarizes the content of the article.</span></span> <span data-ttu-id="5c10b-114">Se suele mostrar en la página de resultados de la búsqueda, pero no se usa para la clasificación de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="5c10b-114">It's usually shown in the search results page, but it isn't used for search ranking.</span></span> <span data-ttu-id="5c10b-115">La longitud debe ser de 115-145 caracteres (espacios incluidos).</span><span class="sxs-lookup"><span data-stu-id="5c10b-115">Its length should be 115-145 characters including spaces.</span></span>
- <span data-ttu-id="5c10b-116">**author**: el campo del autor debe contener el **nombre de usuario de GitHub** del autor.</span><span class="sxs-lookup"><span data-stu-id="5c10b-116">**author**: The author field should contain the **GitHub username** of the author.</span></span>
- <span data-ttu-id="5c10b-117">**ms.date**: la fecha de la última actualización importante.</span><span class="sxs-lookup"><span data-stu-id="5c10b-117">**ms.date**: The date of the last significant update.</span></span> <span data-ttu-id="5c10b-118">Actualice este valor en los artículos existentes si ha revisado y actualizado el artículo completo.</span><span class="sxs-lookup"><span data-stu-id="5c10b-118">Update this on existing articles if you reviewed and updated the entire article.</span></span> <span data-ttu-id="5c10b-119">Las correcciones menores, como los errores tipográficos y similares, no merecen una actualización.</span><span class="sxs-lookup"><span data-stu-id="5c10b-119">Small fixes, such as typos or similar do not warrant an update.</span></span>

<span data-ttu-id="5c10b-120">A los artículos se anexan otros metadatos, pero por lo general la mayoría se aplican en el nivel de carpeta, y se especifican en **docfx.json**.</span><span class="sxs-lookup"><span data-stu-id="5c10b-120">Other metadata is attached to each article, but we typically apply most metadata values at the folder level, specified in **docfx.json**.</span></span>

## <a name="basic-markdown-gfm-and-special-characters"></a><span data-ttu-id="5c10b-121">Markdown básico, GFM y caracteres especiales</span><span class="sxs-lookup"><span data-stu-id="5c10b-121">Basic Markdown, GFM, and special characters</span></span>

<span data-ttu-id="5c10b-122">Puede obtener información sobre los conceptos básicos de Markdown, GitHub Flavored Markdown (GFM) y extensiones específicas de OPS en los artículos generales de [Markdown](how-to-write-use-markdown.md) y [Referencia de Markdown](markdown-reference.md).</span><span class="sxs-lookup"><span data-stu-id="5c10b-122">You can learn the basics of Markdown, GitHub Flavored Markdown (GFM), and OPS specific extensions in the general articles on [Markdown](how-to-write-use-markdown.md) and [Markdown reference](markdown-reference.md).</span></span>

<span data-ttu-id="5c10b-123">En Markdown se usan caracteres especiales como \*, \` y \# para el formato.</span><span class="sxs-lookup"><span data-stu-id="5c10b-123">Markdown uses special characters such as \*, \`, and \# for formatting.</span></span> <span data-ttu-id="5c10b-124">Si quiere incluir uno de estos caracteres en el contenido, debe realizar una de estas dos cosas:</span><span class="sxs-lookup"><span data-stu-id="5c10b-124">If you wish to include one of these characters in your content, you must do one of two things:</span></span>

- <span data-ttu-id="5c10b-125">Colocar una barra diagonal inversa delante del carácter especial para aplicarle el "escape" (por ejemplo, `\*` para \*)</span><span class="sxs-lookup"><span data-stu-id="5c10b-125">Put a backslash before the special character to "escape" it (for example, `\*` for a \*)</span></span>
- <span data-ttu-id="5c10b-126">Usar el [código de entidad HTML](http://www.ascii.cl/htmlcodes.htm) para el carácter (por ejemplo, `&#42;` para &#42;).</span><span class="sxs-lookup"><span data-stu-id="5c10b-126">Use the [HTML entity code](http://www.ascii.cl/htmlcodes.htm) for the character (for example, `&#42;` for a &#42;).</span></span>

## <a name="file-names"></a><span data-ttu-id="5c10b-127">Nombres de archivo</span><span class="sxs-lookup"><span data-stu-id="5c10b-127">File names</span></span>

<span data-ttu-id="5c10b-128">En los nombres de archivo se usan las reglas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c10b-128">File names use the following rules:</span></span>

* <span data-ttu-id="5c10b-129">Solo pueden contener letras minúsculas, números y guiones.</span><span class="sxs-lookup"><span data-stu-id="5c10b-129">Contain only lowercase letters, numbers, and hyphens.</span></span>
* <span data-ttu-id="5c10b-130">No pueden contener espacios ni caracteres de puntuación.</span><span class="sxs-lookup"><span data-stu-id="5c10b-130">No spaces or punctuation characters.</span></span> <span data-ttu-id="5c10b-131">Use guiones para separar palabras y números en el nombre de archivo.</span><span class="sxs-lookup"><span data-stu-id="5c10b-131">Use the hyphens to separate words and numbers in the file name.</span></span>
* <span data-ttu-id="5c10b-132">Use verbos de acción que sean específicos, como "desarrollar", "comprar", "compilar" o "solucionar problemas".</span><span class="sxs-lookup"><span data-stu-id="5c10b-132">Use action verbs that are specific, such as develop, buy, build, troubleshoot.</span></span> <span data-ttu-id="5c10b-133">No use gerundios.</span><span class="sxs-lookup"><span data-stu-id="5c10b-133">No -ing words.</span></span>
* <span data-ttu-id="5c10b-134">No use palabras cortas ni incluya "un", "y", "el", "en", "o", etc.</span><span class="sxs-lookup"><span data-stu-id="5c10b-134">No small words - don't include a, and, the, in, or, etc.</span></span>
* <span data-ttu-id="5c10b-135">Deben estar en Markdown y usar la extensión de archivo .md.</span><span class="sxs-lookup"><span data-stu-id="5c10b-135">Must be in Markdown and use the .md file extension.</span></span>
* <span data-ttu-id="5c10b-136">Use nombres de archivo relativamente cortos.</span><span class="sxs-lookup"><span data-stu-id="5c10b-136">Keep file names reasonably short.</span></span> <span data-ttu-id="5c10b-137">Forman parte de la dirección URL de los artículos.</span><span class="sxs-lookup"><span data-stu-id="5c10b-137">They are part of the URL for your articles.</span></span>

## <a name="headings"></a><span data-ttu-id="5c10b-138">Encabezados</span><span class="sxs-lookup"><span data-stu-id="5c10b-138">Headings</span></span>

<span data-ttu-id="5c10b-139">Use mayúsculas de estilo de frase.</span><span class="sxs-lookup"><span data-stu-id="5c10b-139">Use sentence-style capitalization.</span></span> <span data-ttu-id="5c10b-140">Siempre debe poner en mayúscula la primera palabra de un título.</span><span class="sxs-lookup"><span data-stu-id="5c10b-140">Always capitalize the first word of a heading.</span></span>

## <a name="text-styling"></a><span data-ttu-id="5c10b-141">Estilo de texto</span><span class="sxs-lookup"><span data-stu-id="5c10b-141">Text styling</span></span>

<span data-ttu-id="5c10b-142">*Cursiva* Se usa para archivos, carpetas, rutas de acceso (para elementos largos, divididos en su propia línea), términos nuevos.</span><span class="sxs-lookup"><span data-stu-id="5c10b-142">*Italics* Use for files, folders, paths (for long items, split onto their own line), new terms.</span></span>

<span data-ttu-id="5c10b-143">**Negrita** Se usa para los elementos de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="5c10b-143">**Bold** Use for UI elements.</span></span>

<span data-ttu-id="5c10b-144">`Code` Se usa para código insertado, palabras clave del lenguaje, nombres de paquetes NuGet, comandos de la línea de comandos, nombres de tablas y columnas de bases de datos y direcciones URL en las que no quiera que se pueda hacer clic.</span><span class="sxs-lookup"><span data-stu-id="5c10b-144">`Code` Use for inline code, language keywords, NuGet package names, command-line commands, database table and column names, and URLs that you don't want to be clickable.</span></span>

## <a name="links"></a><span data-ttu-id="5c10b-145">Vínculos</span><span class="sxs-lookup"><span data-stu-id="5c10b-145">Links</span></span>

<span data-ttu-id="5c10b-146">Vea el artículo general sobre [Vínculos](how-to-write-links.md) para obtener información sobre delimitadores, vínculos internos, vínculos a otros documentos, archivos de inclusión de código y vínculos externos.</span><span class="sxs-lookup"><span data-stu-id="5c10b-146">See the general article on [Links](how-to-write-links.md) for information about anchors, internal links, links to other documents, code includes, and external links.</span></span>

<span data-ttu-id="5c10b-147">El equipo de documentación de .NET usa las convenciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c10b-147">The .NET docs team uses the following conventions:</span></span>

- <span data-ttu-id="5c10b-148">En la mayoría de los casos, se usan los vínculos relativos y se desaconseja el uso de `~/` en los vínculos, ya que los vínculos relativos se resuelven en el origen en GitHub.</span><span class="sxs-lookup"><span data-stu-id="5c10b-148">In most cases, we use the relative links and discourage the use of `~/` in links because relative links resolve in the source on GitHub.</span></span> <span data-ttu-id="5c10b-149">Pero siempre que se vincula a un archivo en un repositorio dependiente, se usará el carácter `~/` para proporcionar la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="5c10b-149">However, whenever we link to a file in a dependent repo, we'll use the `~/` character to provide the path.</span></span> <span data-ttu-id="5c10b-150">Como los archivos del repositorio dependiente están en otra ubicación de GitHub, los vínculos no se resolverán de forma correcta con vínculos relativos con independencia de cómo se hayan escrito.</span><span class="sxs-lookup"><span data-stu-id="5c10b-150">Because the files in the dependent repo are in a different location in GitHub the links won't resolve correctly with relative links regardless of how they were written.</span></span>
- <span data-ttu-id="5c10b-151">La especificación de los lenguajes C# y Visual Basic se incluye en la documentación de .NET mediante la inclusión del origen de los repositorios de lenguaje.</span><span class="sxs-lookup"><span data-stu-id="5c10b-151">The C# language specification and the Visual Basic language specification are included in the .NET docs by including the source from the language repositories.</span></span> <span data-ttu-id="5c10b-152">Los orígenes de Markdown se administran en los repositorios [csharplang](https://github.com/dotnet/csharplang) y [vblang](https://github.com/dotnet/vblang).</span><span class="sxs-lookup"><span data-stu-id="5c10b-152">The markdown sources are managed in the [csharplang](https://github.com/dotnet/csharplang) and [vblang](https://github.com/dotnet/vblang) repositories.</span></span>

<span data-ttu-id="5c10b-153">Los vínculos a la especificación deben apuntar a los directorios de origen en los que se incluyen esas especificaciones.</span><span class="sxs-lookup"><span data-stu-id="5c10b-153">Links to the spec must point to the source directories where those specs are included.</span></span> <span data-ttu-id="5c10b-154">Para C#, es **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**, como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c10b-154">For C#, it's **~/_csharplang/spec** and for VB, it's **~/_vblang/spec**, as in the following example:</span></span>

```markdown
[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)
```

### <a name="links-to-apis"></a><span data-ttu-id="5c10b-155">Vínculos a las API</span><span class="sxs-lookup"><span data-stu-id="5c10b-155">Links to APIs</span></span>

<span data-ttu-id="5c10b-156">El sistema de compilación tiene algunas extensiones que nos permiten vincular a las API de .NET sin tener que usar vínculos externos.</span><span class="sxs-lookup"><span data-stu-id="5c10b-156">The build system has some extensions that allow us to link to .NET APIs without having to use external links.</span></span> <span data-ttu-id="5c10b-157">Se usa una de las sintaxis siguientes:</span><span class="sxs-lookup"><span data-stu-id="5c10b-157">You use one of the following syntax:</span></span>

1. <span data-ttu-id="5c10b-158">Vinculación automática: `<xref:UID>` o `<xref:UID?displayProperty=nameWithType>`</span><span class="sxs-lookup"><span data-stu-id="5c10b-158">Auto-link: `<xref:UID>` or `<xref:UID?displayProperty=nameWithType>`</span></span>

   <span data-ttu-id="5c10b-159">El parámetro de consulta `displayProperty` produce un texto de vínculo completo.</span><span class="sxs-lookup"><span data-stu-id="5c10b-159">The `displayProperty` query parameter produces a fully qualified link text.</span></span> <span data-ttu-id="5c10b-160">De forma predeterminada, el texto del vínculo muestra solo el nombre de miembro o tipo.</span><span class="sxs-lookup"><span data-stu-id="5c10b-160">By default, link text shows only the member or type name.</span></span>

2. <span data-ttu-id="5c10b-161">Vínculo de Markdown: `[link text](xref:UID)`</span><span class="sxs-lookup"><span data-stu-id="5c10b-161">Markdown link: `[link text](xref:UID)`</span></span>

   <span data-ttu-id="5c10b-162">Se utiliza cuando se desea personalizar el texto del vínculo mostrado.</span><span class="sxs-lookup"><span data-stu-id="5c10b-162">Use when you want to customize the link text displayed.</span></span>

<span data-ttu-id="5c10b-163">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="5c10b-163">Examples:</span></span>

- <span data-ttu-id="5c10b-164">`<xref:System.String>` se representa como [String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="5c10b-164">`<xref:System.String>` renders as [String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="5c10b-165">`<xref:System.String?displayProperty=nameWithType>` se representa como [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="5c10b-165">`<xref:System.String?displayProperty=nameWithType>` renders as [System.String](https://docs.microsoft.com/dotnet/api/system.string)</span></span>
- <span data-ttu-id="5c10b-166">`[String class](xref:System.String)` se representa como [String class](https://docs.microsoft.com/dotnet/api/system.string)</span><span class="sxs-lookup"><span data-stu-id="5c10b-166">`[String class](xref:System.String)` renders as [String class](https://docs.microsoft.com/dotnet/api/system.string)</span></span>

<span data-ttu-id="5c10b-167">Para obtener más información acerca de cómo utilizar esta notación, consulte [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference) (Uso de referencia cruzada).</span><span class="sxs-lookup"><span data-stu-id="5c10b-167">For more information about using this notation, see [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference).</span></span>

<span data-ttu-id="5c10b-168">Cuando algunos UID contienen los caracteres especiales \`, \# o \*, el valor de UID se debe codificar en HTML como `%60`, `%23` y `%2A`, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="5c10b-168">Some UIDs contain the special characters \`, \# or \*, the UID value needs to be HTML encoded as `%60`, `%23` and `%2A` respectively.</span></span> <span data-ttu-id="5c10b-169">En ocasiones verá paréntesis codificados, pero no es un requisito.</span><span class="sxs-lookup"><span data-stu-id="5c10b-169">You'll sometimes see parentheses encoded but it's not a requirement.</span></span>

<span data-ttu-id="5c10b-170">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="5c10b-170">Examples:</span></span>

- <span data-ttu-id="5c10b-171">System.Threading.Tasks.Task\`1 se convierte en `System.Threading.Tasks.Task%601`</span><span class="sxs-lookup"><span data-stu-id="5c10b-171">System.Threading.Tasks.Task\`1 becomes `System.Threading.Tasks.Task%601`</span></span>
- <span data-ttu-id="5c10b-172">System.Exception.\#ctor se convierte en `System.Exception.%23ctor`</span><span class="sxs-lookup"><span data-stu-id="5c10b-172">System.Exception.\#ctor becomes `System.Exception.%23ctor`</span></span>
- <span data-ttu-id="5c10b-173">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se convierte en `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span><span class="sxs-lookup"><span data-stu-id="5c10b-173">System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) becomes  `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`</span></span>

<span data-ttu-id="5c10b-174">Puede encontrar los UID de tipos, una lista de sobrecargas de miembros, o bien un miembro de sobrecarga concreto, en `https://xref.docs.microsoft.com/autocomplete`.</span><span class="sxs-lookup"><span data-stu-id="5c10b-174">You can find the UIDs of types, a member overload list, or a particular overloaded member from `https://xref.docs.microsoft.com/autocomplete`.</span></span> <span data-ttu-id="5c10b-175">La cadena de consulta `?text=*\<type-member-name>*` identifica el tipo o miembro cuyos UID quiere ver.</span><span class="sxs-lookup"><span data-stu-id="5c10b-175">The query string `?text=*\<type-member-name>*` identifies the type or member whose UIDs you'd like to see.</span></span> <span data-ttu-id="5c10b-176">Por ejemplo, `https://xref.docs.microsoft.com/autocomplete?text=string.format` recupera las sobrecargas de [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format).</span><span class="sxs-lookup"><span data-stu-id="5c10b-176">For example, `https://xref.docs.microsoft.com/autocomplete?text=string.format` retrieves the [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format) overloads.</span></span> <span data-ttu-id="5c10b-177">La herramienta busca el parámetro de consulta `text` proporcionado en cualquier parte del UID.</span><span class="sxs-lookup"><span data-stu-id="5c10b-177">The tool searches for the provided `text` query parameter in any part of the UID.</span></span> <span data-ttu-id="5c10b-178">Por ejemplo, puede buscar por nombre de miembro (ToString), nombre de miembro parcial (ToStri), nombre de miembro y tipo (Double.ToString), etc.</span><span class="sxs-lookup"><span data-stu-id="5c10b-178">For example, you can search for member name (ToString), partial member name (ToStri), type and member name (Double.ToString), etc.</span></span>

<span data-ttu-id="5c10b-179">Si agrega \* (o `%2A`) después del UID, el vínculo representará la página de sobrecarga y no una API específica.</span><span class="sxs-lookup"><span data-stu-id="5c10b-179">If you add a \* (or `%2A`) after the UID, the link then represents the overload page and not a specific API.</span></span> <span data-ttu-id="5c10b-180">Por ejemplo, puede usarlo si desea vincular a la página [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) de forma genérica en lugar de a una sobrecarga específica como [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span><span class="sxs-lookup"><span data-stu-id="5c10b-180">For example, you can use that when you want to link to the [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) page in a generic way instead of a specific overload such as [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_).</span></span> <span data-ttu-id="5c10b-181">También puede usar \* para vincular a la página de un miembro cuando el miembro no está sobrecargado; esto evita tener que incluir la lista de parámetros en el UID.</span><span class="sxs-lookup"><span data-stu-id="5c10b-181">You can also use \* to link to a member page when the member is not overloaded; this saves you from having to include the parameter list in the UID.</span></span>

<span data-ttu-id="5c10b-182">Para vincular a una sobrecarga de método concreta, debe incluir el nombre de tipo completo de todos los parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="5c10b-182">To link to a specific method overload, you must include the fully qualified type name of each of the method's parameters.</span></span> <span data-ttu-id="5c10b-183">Por ejemplo, \<xref:System.DateTime.ToString> vincula al método [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) sin parámetros, mientras que \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> vincula al método [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).</span><span class="sxs-lookup"><span data-stu-id="5c10b-183">For example, \<xref:System.DateTime.ToString> links to the parameterless [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) method, while \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> links to the  [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_) method.</span></span>

<span data-ttu-id="5c10b-184">Para vincular a un tipo genérico, como [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), se usa el carácter \` (`%60`) seguido del número de parámetros de tipo genérico.</span><span class="sxs-lookup"><span data-stu-id="5c10b-184">To link to a generic type, such as [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), you use the \` (`%60`) character followed by the number of generic type parameters.</span></span> <span data-ttu-id="5c10b-185">Por ejemplo, `<xref:System.Nullable%601>` vincula al tipo [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), mientras que `<xref:System.Func%602>` vincula al delegado [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).</span><span class="sxs-lookup"><span data-stu-id="5c10b-185">For example, `<xref:System.Nullable%601>` links to the [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1) type, while `<xref:System.Func%602>` links to the [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2) delegate.</span></span>

## <a name="code"></a><span data-ttu-id="5c10b-186">Código</span><span class="sxs-lookup"><span data-stu-id="5c10b-186">Code</span></span>

<span data-ttu-id="5c10b-187">La mejor forma de incluir código consiste en incluir fragmentos de código de un ejemplo que funcione.</span><span class="sxs-lookup"><span data-stu-id="5c10b-187">The best way to include code is to include snippets from a working sample.</span></span> <span data-ttu-id="5c10b-188">Para crear el ejemplo, siga las instrucciones del artículo [Contribuciones a .NET](dotnet-contribute-process.md#contributing-to-samples).</span><span class="sxs-lookup"><span data-stu-id="5c10b-188">Create your sample following the instructions in the [contributing to .NET](dotnet-contribute-process.md#contributing-to-samples) article.</span></span> <span data-ttu-id="5c10b-189">Las reglas básicas para incluir código se encuentran en las instrucciones generales sobre [código](how-to-write-use-markdown.md#code-includes).</span><span class="sxs-lookup"><span data-stu-id="5c10b-189">The basic rules for including code are located in the general guidance on [code](how-to-write-use-markdown.md#code-includes).</span></span>

<span data-ttu-id="5c10b-190">Puede incluir el código mediante la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c10b-190">You can include the code using the following syntax:</span></span>

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* <span data-ttu-id="5c10b-191">`-<language>` (*opcional* pero *recomendado*)</span><span class="sxs-lookup"><span data-stu-id="5c10b-191">`-<language>` (*optional* but *recommended*)</span></span>
  * <span data-ttu-id="5c10b-192">Lenguaje del fragmento de código al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="5c10b-192">Language of the code snippet being referenced.</span></span> <span data-ttu-id="5c10b-193">Para obtener una lista de los valores admitidos, vea [Lenguajes admitidos](#supported-languages).</span><span class="sxs-lookup"><span data-stu-id="5c10b-193">For a list of supported values, see [Supported languages](#supported-languages).</span></span>

* <span data-ttu-id="5c10b-194">`<name>` (*opcional*)</span><span class="sxs-lookup"><span data-stu-id="5c10b-194">`<name>` (*optional*)</span></span>
  * <span data-ttu-id="5c10b-195">Nombre del fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="5c10b-195">Name for the code snippet.</span></span> <span data-ttu-id="5c10b-196">No tiene ningún impacto en el HTML de salida, pero puede usarlo para mejorar la legibilidad del código fuente de Markdown.</span><span class="sxs-lookup"><span data-stu-id="5c10b-196">It doesn’t have any impact on the output HTML, but you can use it to improve the readability of your Markdown source.</span></span>

* <span data-ttu-id="5c10b-197">`<pathToFile>` (*obligatorio*)</span><span class="sxs-lookup"><span data-stu-id="5c10b-197">`<pathToFile>` (*mandatory*)</span></span>
  * <span data-ttu-id="5c10b-198">Ruta de acceso relativa del sistema de archivos que indica el archivo del fragmento de código al que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="5c10b-198">Relative path in the file system that indicates the code snippet file to reference.</span></span> <span data-ttu-id="5c10b-199">Esto lo pueden complicar los diferentes repositorios que forman el conjunto de documentación de .NET.</span><span class="sxs-lookup"><span data-stu-id="5c10b-199">This can be complicated by the different repos that make up the .NET doc set.</span></span> <span data-ttu-id="5c10b-200">Los ejemplos de .NET están en el repositorio dotnet/samples.</span><span class="sxs-lookup"><span data-stu-id="5c10b-200">The .NET samples are in the dotnet/samples repo.</span></span> <span data-ttu-id="5c10b-201">Las rutas de acceso de todos los fragmentos de código deben empezar por `~/samples`, y el resto es la ruta de acceso al origen desde la raíz de ese repositorio.</span><span class="sxs-lookup"><span data-stu-id="5c10b-201">All snippet paths would start with `~/samples`, the rest of the path being the path to the source from the root of that repo.</span></span>

* <span data-ttu-id="5c10b-202">`<queryoption>` (*opcional*)</span><span class="sxs-lookup"><span data-stu-id="5c10b-202">`<queryoption>` (*optional*)</span></span>
  * <span data-ttu-id="5c10b-203">Se usa para especificar cómo se debe recuperar el código del archivo:</span><span class="sxs-lookup"><span data-stu-id="5c10b-203">Used to specify how the code should be retrieved from the file:</span></span>
    * <span data-ttu-id="5c10b-204">`#`: `#{tagname}` (nombre de etiqueta) *o* `#L{startlinenumber}-L{endlinenumber}` (intervalo de líneas).</span><span class="sxs-lookup"><span data-stu-id="5c10b-204">`#`:  `#{tagname}` (tag name) *or* `#L{startlinenumber}-L{endlinenumber}` (line range).</span></span>
    <span data-ttu-id="5c10b-205">No se recomienda el uso de números de línea porque son muy frágiles.</span><span class="sxs-lookup"><span data-stu-id="5c10b-205">We discourage the use of line numbers because they are very brittle.</span></span> <span data-ttu-id="5c10b-206">El nombre de etiqueta es la forma preferida de hacer referencia a los fragmentos de código.</span><span class="sxs-lookup"><span data-stu-id="5c10b-206">Tag name is the preferred way of referencing code snippets.</span></span> <span data-ttu-id="5c10b-207">Use nombres de etiqueta descriptivos.</span><span class="sxs-lookup"><span data-stu-id="5c10b-207">Use meaningful tag names.</span></span> <span data-ttu-id="5c10b-208">Muchos fragmentos de código se han migrado de una plataforma anterior y las etiquetas tienen nombres como `Snippet1` y `Snippet2`, entre otros. Esa práctica es mucho más difícil de mantener).</span><span class="sxs-lookup"><span data-stu-id="5c10b-208">(Many snippets were migrated from a previous platform and the tags have names such as `Snippet1`, `Snippet2` etc. That practice is much harder to maintain.)</span></span>
    * <span data-ttu-id="5c10b-209">`range`: `?range=1,3-5` Un intervalo de líneas.</span><span class="sxs-lookup"><span data-stu-id="5c10b-209">`range`: `?range=1,3-5` A range of lines.</span></span> <span data-ttu-id="5c10b-210">Este ejemplo incluye las líneas 1, 3, 4 y 5.</span><span class="sxs-lookup"><span data-stu-id="5c10b-210">This example includes lines 1, 3, 4, and 5.</span></span>

<span data-ttu-id="5c10b-211">Se recomienda usar la opción del nombre de etiqueta siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="5c10b-211">We recommend using the tag name option whenever possible.</span></span> <span data-ttu-id="5c10b-212">El nombre de etiqueta es el nombre de una región o un comentario de código con el formato `Snippettagname` presente en el código fuente.</span><span class="sxs-lookup"><span data-stu-id="5c10b-212">The tag name is the name of a region or of a code comment in the format of `Snippettagname` present in the source code.</span></span> <span data-ttu-id="5c10b-213">En el ejemplo siguiente se muestra cómo hacer referencia al nombre de etiqueta `BasicThrow`:</span><span class="sxs-lookup"><span data-stu-id="5c10b-213">The following example shows how to refer to the tag name `BasicThrow`:</span></span>

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

<span data-ttu-id="5c10b-214">La ruta de acceso relativa al origen en el repositorio **dotnet/samples** sigue la ruta de acceso `~/samples`.</span><span class="sxs-lookup"><span data-stu-id="5c10b-214">The relative path to the source in the **dotnet/samples** repo follows the `~/samples` path.</span></span>

<span data-ttu-id="5c10b-215">Y en [este archivo de código fuente](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs) puede ver la estructura de las etiquetas de fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="5c10b-215">And you can see how the snippet tags are structured in [this source file](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs).</span></span> <span data-ttu-id="5c10b-216">Para obtener más información sobre la presentación en archivos de origen de fragmento de código por idioma, vea las [directrices de DocFX ](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span><span class="sxs-lookup"><span data-stu-id="5c10b-216">For details about tag name representation in code snippet source files by language, see the [DocFX guidelines](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).</span></span>

<span data-ttu-id="5c10b-217">En el ejemplo siguiente se muestra el código incluido en los tres lenguajes de .NET:</span><span class="sxs-lookup"><span data-stu-id="5c10b-217">The following example shows code included in all three .NET languages:</span></span>

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

<span data-ttu-id="5c10b-218">La inclusión de fragmentos de código desde programas completos garantiza que todo el código se ejecuta a través de nuestro sistema de Integración continua (CI).</span><span class="sxs-lookup"><span data-stu-id="5c10b-218">Including snippets from full programs ensures that all code runs through our Continuous Integration (CI) system.</span></span> <span data-ttu-id="5c10b-219">Pero si tiene que mostrar algo que produce errores en tiempo de compilación o ejecución, puede usar bloques de código insertado.</span><span class="sxs-lookup"><span data-stu-id="5c10b-219">However, if you need to show something that causes compile time or runtime errors, you can use inline code blocks.</span></span>

## <a name="images"></a><span data-ttu-id="5c10b-220">Imágenes</span><span class="sxs-lookup"><span data-stu-id="5c10b-220">Images</span></span>

### <a name="static-image-or-animated-gif"></a><span data-ttu-id="5c10b-221">Imagen estática o GIF animado</span><span class="sxs-lookup"><span data-stu-id="5c10b-221">Static image or animated GIF</span></span>

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a><span data-ttu-id="5c10b-222">Imagen vinculada</span><span class="sxs-lookup"><span data-stu-id="5c10b-222">Linked image</span></span>

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a><span data-ttu-id="5c10b-223">Vídeos</span><span class="sxs-lookup"><span data-stu-id="5c10b-223">Videos</span></span>

<span data-ttu-id="5c10b-224">En la actualidad, puede insertar vídeos de Channel 9 y YouTube con la sintaxis siguiente:</span><span class="sxs-lookup"><span data-stu-id="5c10b-224">Currently, you can embed both Channel 9 and YouTube videos with the following syntax:</span></span>

### <a name="channel-9"></a><span data-ttu-id="5c10b-225">Channel 9</span><span class="sxs-lookup"><span data-stu-id="5c10b-225">Channel 9</span></span>

```markdown
> [!VIDEO <channel9_video_link>]
```

<span data-ttu-id="5c10b-226">Para obtener la dirección URL correcta del vídeo, haga clic en la pestaña **Insertar** situada debajo del marco del vídeo y copie la dirección URL del elemento `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="5c10b-226">To get the video's correct URL, select the **Embed** tab below the video frame, and copy the URL from the `<iframe>` element.</span></span> <span data-ttu-id="5c10b-227">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5c10b-227">For example:</span></span>

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a><span data-ttu-id="5c10b-228">YouTube</span><span class="sxs-lookup"><span data-stu-id="5c10b-228">YouTube</span></span>

<span data-ttu-id="5c10b-229">Para obtener la dirección URL correcta del vídeo, haga clic con el botón derecho en el vídeo, seleccione **Copiar código para insertar**, y copie la dirección URL del elemento `<iframe>`.</span><span class="sxs-lookup"><span data-stu-id="5c10b-229">To get the video's correct URL, right-click on the video, select **Copy Embed Code**, and copy the URL from the `<iframe>` element.</span></span>

```markdown
> [!VIDEO <youtube_video_link>]
```

<span data-ttu-id="5c10b-230">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5c10b-230">For example:</span></span>

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a><span data-ttu-id="5c10b-231">Extensiones de docs.microsoft</span><span class="sxs-lookup"><span data-stu-id="5c10b-231">docs.microsoft extensions</span></span>

<span data-ttu-id="5c10b-232">En docs.microsoft se proporcionan varias extensiones adicionales para GitHub Flavored Markdown.</span><span class="sxs-lookup"><span data-stu-id="5c10b-232">docs.microsoft provides a few additional extensions to GitHub Flavored Markdown.</span></span>

### <a name="checked-lists"></a><span data-ttu-id="5c10b-233">Listas de comprobación probadas</span><span class="sxs-lookup"><span data-stu-id="5c10b-233">Checked lists</span></span>

<span data-ttu-id="5c10b-234">Hay disponible un estilo personalizado para las listas.</span><span class="sxs-lookup"><span data-stu-id="5c10b-234">A custom style is available for lists.</span></span> <span data-ttu-id="5c10b-235">Puede representar listas con marcas de verificación verdes.</span><span class="sxs-lookup"><span data-stu-id="5c10b-235">You can render lists with green check marks.</span></span>

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

<span data-ttu-id="5c10b-236">Esto se representa como:</span><span class="sxs-lookup"><span data-stu-id="5c10b-236">This renders as:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="5c10b-237">Cómo crear una aplicación .NET Core</span><span class="sxs-lookup"><span data-stu-id="5c10b-237">How to create a .NET Core app</span></span>
> * <span data-ttu-id="5c10b-238">Cómo agregar una referencia al paquete Microsoft.XmlSerializer.Generator</span><span class="sxs-lookup"><span data-stu-id="5c10b-238">How to add a reference to the Microsoft.XmlSerializer.Generator package</span></span>
> * <span data-ttu-id="5c10b-239">Cómo editar el archivo MyApp.csproj para agregar dependencias</span><span class="sxs-lookup"><span data-stu-id="5c10b-239">How to edit your MyApp.csproj to add dependencies</span></span>
> * <span data-ttu-id="5c10b-240">Cómo agregar una clase y un XmlSerializer</span><span class="sxs-lookup"><span data-stu-id="5c10b-240">How to add a class and an XmlSerializer</span></span>
> * <span data-ttu-id="5c10b-241">Cómo compilar y ejecutar la aplicación</span><span class="sxs-lookup"><span data-stu-id="5c10b-241">How to build and run the application</span></span>

<span data-ttu-id="5c10b-242">Puede ver un ejemplo de listas de comprobación en acción en la [documentación de .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span><span class="sxs-lookup"><span data-stu-id="5c10b-242">You can see an example of checked lists in action in the [.NET Core docs](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).</span></span>

### <a name="buttons"></a><span data-ttu-id="5c10b-243">Botones</span><span class="sxs-lookup"><span data-stu-id="5c10b-243">Buttons</span></span>

<span data-ttu-id="5c10b-244">Vínculos de botón:</span><span class="sxs-lookup"><span data-stu-id="5c10b-244">Button links:</span></span>

```markdown
> [!div class="button"]
[button links](dotnet-contribute.md)
```

<span data-ttu-id="5c10b-245">Esto se representa como:</span><span class="sxs-lookup"><span data-stu-id="5c10b-245">This renders as:</span></span>

> [!div class="button"]
[<span data-ttu-id="5c10b-246">Vínculos de botón</span><span class="sxs-lookup"><span data-stu-id="5c10b-246">button links</span></span>](dotnet-contribute.md)

<span data-ttu-id="5c10b-247">Puede ver un ejemplo de botones en acción en la [documentación de Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="5c10b-247">You can see an example of buttons in action in the [Visual Studio docs](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).</span></span>

### <a name="step-by-steps"></a><span data-ttu-id="5c10b-248">Guías paso a paso</span><span class="sxs-lookup"><span data-stu-id="5c10b-248">Step-by-steps</span></span>

```markdown
>[!div class="step-by-step"]
[Pre](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)
```

<span data-ttu-id="5c10b-249">Puede ver un ejemplo de guía paso a paso en acción en la [guía de C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span><span class="sxs-lookup"><span data-stu-id="5c10b-249">You can see an example of step-by-steps in action at the [C# Guide](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).</span></span>
