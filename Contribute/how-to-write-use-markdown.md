---
title: Uso de Markdown para escribir Docs
description: En este artículo se proporciona información básica y de referencia para el lenguaje Markdown que se utiliza para escribir artículos de docs.microsoft.com.
ms.date: 07/13/2017
ms.openlocfilehash: 6bb8a1fa20957512addb07dda0e68abec4b0a83f
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805742"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="f23f7-103">Uso de Markdown para escribir Docs</span><span class="sxs-lookup"><span data-stu-id="f23f7-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="f23f7-104">Los artículos de [docs.microsoft.com](http://docs.microsoft.com) están escritos en un lenguaje de marcado ligero denominado [Markdown](https://daringfireball.net/projects/markdown/), que resulta fácil de leer y de aprender.</span><span class="sxs-lookup"><span data-stu-id="f23f7-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="f23f7-105">Por ello, se ha convertido rápidamente en un estándar del sector.</span><span class="sxs-lookup"><span data-stu-id="f23f7-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="f23f7-106">Como el contenido de Docs se almacena en GitHub, puede usar un superconjunto de Markdown denominado [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), que proporciona una funcionalidad adicional para necesidades comunes de aplicación de formato.</span><span class="sxs-lookup"><span data-stu-id="f23f7-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="f23f7-107">Además, la plataforma de Servicios de publicación abierta (OPS) implementa Markdig Markdown Parser.</span><span class="sxs-lookup"><span data-stu-id="f23f7-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="f23f7-108">Markdig ofrece alta compatibilidad con GFM y agrega funciones para habilitar características específicas de Docs.</span><span class="sxs-lookup"><span data-stu-id="f23f7-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="f23f7-109">Markdig es un procesador de Markdown extensible para .NET rápido, potente y conforme a CommonMark.</span><span class="sxs-lookup"><span data-stu-id="f23f7-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="f23f7-110">Mejor soporte técnico de la comunidad</span><span class="sxs-lookup"><span data-stu-id="f23f7-110">Better community support</span></span>
* <span data-ttu-id="f23f7-111">Mejor soporte técnico para los estándares</span><span class="sxs-lookup"><span data-stu-id="f23f7-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="f23f7-112">Aspectos básicos de Markdown</span><span class="sxs-lookup"><span data-stu-id="f23f7-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="f23f7-113">Encabezados</span><span class="sxs-lookup"><span data-stu-id="f23f7-113">Headings</span></span>

<span data-ttu-id="f23f7-114">Para crear un encabezado, debe usar una marca hash (#) como sigue:</span><span class="sxs-lookup"><span data-stu-id="f23f7-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="f23f7-115">Texto en negrita y cursiva</span><span class="sxs-lookup"><span data-stu-id="f23f7-115">Bold and italic text</span></span>

<span data-ttu-id="f23f7-116">Para aplicar formato de **negrita** al texto, debe encerrarlo entre dos asteriscos:</span><span class="sxs-lookup"><span data-stu-id="f23f7-116">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="f23f7-117">Para aplicar formato de *cursiva* al texto, debe encerrarlo entre un solo asterisco:</span><span class="sxs-lookup"><span data-stu-id="f23f7-117">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="f23f7-118">Para aplicar formato de ***negrita y cursiva*** al texto, debe encerrarlo entre tres asteriscos:</span><span class="sxs-lookup"><span data-stu-id="f23f7-118">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="f23f7-119">Listas</span><span class="sxs-lookup"><span data-stu-id="f23f7-119">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="f23f7-120">Listas sin ordenar</span><span class="sxs-lookup"><span data-stu-id="f23f7-120">Unordered list</span></span>

<span data-ttu-id="f23f7-121">Para aplicar formato a una lista sin ordenar o con viñetas, puede usar asteriscos o guiones.</span><span class="sxs-lookup"><span data-stu-id="f23f7-121">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="f23f7-122">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="f23f7-122">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="f23f7-123">se representará como:</span><span class="sxs-lookup"><span data-stu-id="f23f7-123">will be rendered as:</span></span>

- <span data-ttu-id="f23f7-124">Elemento de lista 1</span><span class="sxs-lookup"><span data-stu-id="f23f7-124">List item 1</span></span>
- <span data-ttu-id="f23f7-125">Elemento de lista 2</span><span class="sxs-lookup"><span data-stu-id="f23f7-125">List item 2</span></span>
- <span data-ttu-id="f23f7-126">Elemento de lista 3</span><span class="sxs-lookup"><span data-stu-id="f23f7-126">List item 3</span></span>

<span data-ttu-id="f23f7-127">Para anidar una lista dentro de otra, tiene que aplicar sangría a los elementos de lista secundarios.</span><span class="sxs-lookup"><span data-stu-id="f23f7-127">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="f23f7-128">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="f23f7-128">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="f23f7-129">se representará como:</span><span class="sxs-lookup"><span data-stu-id="f23f7-129">will be rendered as:</span></span>

- <span data-ttu-id="f23f7-130">Elemento de lista 1</span><span class="sxs-lookup"><span data-stu-id="f23f7-130">List item 1</span></span>
  - <span data-ttu-id="f23f7-131">Elemento de lista A</span><span class="sxs-lookup"><span data-stu-id="f23f7-131">List item A</span></span>
  - <span data-ttu-id="f23f7-132">Elemento de lista B</span><span class="sxs-lookup"><span data-stu-id="f23f7-132">List item B</span></span>
- <span data-ttu-id="f23f7-133">Elemento de lista 2</span><span class="sxs-lookup"><span data-stu-id="f23f7-133">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="f23f7-134">Listas ordenada</span><span class="sxs-lookup"><span data-stu-id="f23f7-134">Ordered list</span></span>

<span data-ttu-id="f23f7-135">Para aplicar formato a una lista ordenada o de pasos, debe usar los números correspondientes.</span><span class="sxs-lookup"><span data-stu-id="f23f7-135">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="f23f7-136">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="f23f7-136">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="f23f7-137">se representará como:</span><span class="sxs-lookup"><span data-stu-id="f23f7-137">will be rendered as:</span></span>

1. <span data-ttu-id="f23f7-138">Primera instrucción</span><span class="sxs-lookup"><span data-stu-id="f23f7-138">First instruction</span></span>
2. <span data-ttu-id="f23f7-139">Segunda instrucción</span><span class="sxs-lookup"><span data-stu-id="f23f7-139">Second instruction</span></span>
3. <span data-ttu-id="f23f7-140">Tercera instrucción</span><span class="sxs-lookup"><span data-stu-id="f23f7-140">Third instruction</span></span>

<span data-ttu-id="f23f7-141">Para anidar una lista dentro de otra, tiene que aplicar sangría a los elementos de lista secundarios.</span><span class="sxs-lookup"><span data-stu-id="f23f7-141">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="f23f7-142">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="f23f7-142">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="f23f7-143">se representará como:</span><span class="sxs-lookup"><span data-stu-id="f23f7-143">will be rendered as:</span></span>

1. <span data-ttu-id="f23f7-144">Primera instrucción</span><span class="sxs-lookup"><span data-stu-id="f23f7-144">First instruction</span></span>
   1. <span data-ttu-id="f23f7-145">Subinstrucción</span><span class="sxs-lookup"><span data-stu-id="f23f7-145">Sub-instruction</span></span>
   2. <span data-ttu-id="f23f7-146">Subinstrucción</span><span class="sxs-lookup"><span data-stu-id="f23f7-146">Sub-instruction</span></span>
2. <span data-ttu-id="f23f7-147">Segunda instrucción</span><span class="sxs-lookup"><span data-stu-id="f23f7-147">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="f23f7-148">Tablas</span><span class="sxs-lookup"><span data-stu-id="f23f7-148">Tables</span></span>

<span data-ttu-id="f23f7-149">Las tablas no forman parte de la especificación principal de Markdown, pero son compatibles con GFM.</span><span class="sxs-lookup"><span data-stu-id="f23f7-149">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="f23f7-150">Puede crear tablas con los caracteres de barra vertical (|) y guion (-).</span><span class="sxs-lookup"><span data-stu-id="f23f7-150">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="f23f7-151">Los guiones crean cada encabezado de columna, mientras que las barras verticales separan cada columna.</span><span class="sxs-lookup"><span data-stu-id="f23f7-151">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="f23f7-152">Incluya una línea en blanco antes de la tabla para que se represente correctamente.</span><span class="sxs-lookup"><span data-stu-id="f23f7-152">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="f23f7-153">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="f23f7-153">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="f23f7-154">se representará como:</span><span class="sxs-lookup"><span data-stu-id="f23f7-154">will be rendered as:</span></span>

| <span data-ttu-id="f23f7-155">Diversión</span><span class="sxs-lookup"><span data-stu-id="f23f7-155">Fun</span></span>                  | <span data-ttu-id="f23f7-156">Con</span><span class="sxs-lookup"><span data-stu-id="f23f7-156">With</span></span>                 | <span data-ttu-id="f23f7-157">Tablas</span><span class="sxs-lookup"><span data-stu-id="f23f7-157">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="f23f7-158">columna alineada a la izquierda</span><span class="sxs-lookup"><span data-stu-id="f23f7-158">left-aligned column</span></span>  | <span data-ttu-id="f23f7-159">columna alineada a la derecha</span><span class="sxs-lookup"><span data-stu-id="f23f7-159">right-aligned column</span></span> | <span data-ttu-id="f23f7-160">columna centrada</span><span class="sxs-lookup"><span data-stu-id="f23f7-160">centered column</span></span> |
| <span data-ttu-id="f23f7-161">100 USD</span><span class="sxs-lookup"><span data-stu-id="f23f7-161">$100</span></span>                 | <span data-ttu-id="f23f7-162">100 USD</span><span class="sxs-lookup"><span data-stu-id="f23f7-162">$100</span></span>                 | <span data-ttu-id="f23f7-163">100 USD</span><span class="sxs-lookup"><span data-stu-id="f23f7-163">$100</span></span>            |
| <span data-ttu-id="f23f7-164">10 USD</span><span class="sxs-lookup"><span data-stu-id="f23f7-164">$10</span></span>                  | <span data-ttu-id="f23f7-165">10 USD</span><span class="sxs-lookup"><span data-stu-id="f23f7-165">$10</span></span>                  | <span data-ttu-id="f23f7-166">10 USD</span><span class="sxs-lookup"><span data-stu-id="f23f7-166">$10</span></span>             |
| <span data-ttu-id="f23f7-167">1 USD</span><span class="sxs-lookup"><span data-stu-id="f23f7-167">$1</span></span>                   | <span data-ttu-id="f23f7-168">1 USD</span><span class="sxs-lookup"><span data-stu-id="f23f7-168">$1</span></span>                   | <span data-ttu-id="f23f7-169">1 USD</span><span class="sxs-lookup"><span data-stu-id="f23f7-169">$1</span></span>              |

<span data-ttu-id="f23f7-170">Para obtener más información sobre la creación de tablas, consulte:</span><span class="sxs-lookup"><span data-stu-id="f23f7-170">For more information on creating tables, see:</span></span>

- <span data-ttu-id="f23f7-171">La [característica de ajuste de tabla](#table-wrapping) de Markdig, que puede ayudar a aplicar formato a las tablas anchas.</span><span class="sxs-lookup"><span data-stu-id="f23f7-171">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="f23f7-172">La [organización de información con tablas](https://help.github.com/articles/organizing-information-with-tables/) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="f23f7-172">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="f23f7-173">Las aplicación web del [generador de tablas de Markdown](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="f23f7-173">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="f23f7-174">La [Hoja de referencia de Adam Pritchard sobre Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span><span class="sxs-lookup"><span data-stu-id="f23f7-174">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="f23f7-175">La [información adicional de Michel Fortin sobre Markdown](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="f23f7-175">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="f23f7-176">[Conversión de tablas HTML en Markdown](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="f23f7-176">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="f23f7-177">Vínculos</span><span class="sxs-lookup"><span data-stu-id="f23f7-177">Links</span></span>

<span data-ttu-id="f23f7-178">La sintaxis de Markdown de un vínculo insertado consta de la parte `[link text]`, que es el texto que se va a enlazar, seguida de la parte `(file-name.md)`, que es la dirección URL o el nombre de archivo a los que se va a realizar la vinculación:</span><span class="sxs-lookup"><span data-stu-id="f23f7-178">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="f23f7-179">Para obtener más información sobre la vinculación, vea:</span><span class="sxs-lookup"><span data-stu-id="f23f7-179">For more information on linking, see:</span></span>

- <span data-ttu-id="f23f7-180">La [guía de sintaxis de Markdown](https://daringfireball.net/projects/markdown/syntax#link) para obtener información detallada sobre la compatibilidad de vínculos base de Markdown.</span><span class="sxs-lookup"><span data-stu-id="f23f7-180">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="f23f7-181">La sección [Vínculos](how-to-write-links.md) de esta guía para obtener información sobre la sintaxis de vinculación adicional proporcionada por Markdig.</span><span class="sxs-lookup"><span data-stu-id="f23f7-181">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="f23f7-182">Fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="f23f7-182">Code snippets</span></span>

<span data-ttu-id="f23f7-183">Markdown admite la inserción de fragmentos de código en una oración y como un bloque "delimitado" independiente entre oraciones.</span><span class="sxs-lookup"><span data-stu-id="f23f7-183">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="f23f7-184">Para obtener información, vea:</span><span class="sxs-lookup"><span data-stu-id="f23f7-184">For details, see:</span></span>

- [<span data-ttu-id="f23f7-185">Compatiblidad nativa de Markdown para bloques de código</span><span class="sxs-lookup"><span data-stu-id="f23f7-185">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="f23f7-186">Compatibilidad de GFM para delimitación de código y resaltado de sintaxis</span><span class="sxs-lookup"><span data-stu-id="f23f7-186">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="f23f7-187">Los bloques de código delimitados son una forma sencilla de habilitar el resaltado de sintaxis de los fragmentos de código.</span><span class="sxs-lookup"><span data-stu-id="f23f7-187">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="f23f7-188">El formato general del bloque de código delimitado es:</span><span class="sxs-lookup"><span data-stu-id="f23f7-188">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="f23f7-189">El alias después de los tres caracteres iniciales de acento grave (\`) define el resaltado de sintaxis que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="f23f7-189">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="f23f7-190">A continuación se muestra una lista de lenguajes de programación de uso común en contenido de Docs y la etiqueta asociada:</span><span class="sxs-lookup"><span data-stu-id="f23f7-190">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="f23f7-191">Estos lenguajes tienen nombres descriptivos y la mayoría de ellos realzan el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="f23f7-191">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="f23f7-192">Nombre</span><span class="sxs-lookup"><span data-stu-id="f23f7-192">Name</span></span>|<span data-ttu-id="f23f7-193">Etiqueta de Markdown</span><span class="sxs-lookup"><span data-stu-id="f23f7-193">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="f23f7-194">.NET Console</span><span class="sxs-lookup"><span data-stu-id="f23f7-194">.NET Console</span></span>|<span data-ttu-id="f23f7-195">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="f23f7-195">dotnetcli</span></span>|
|<span data-ttu-id="f23f7-196">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="f23f7-196">ASP.NET (C#)</span></span>|<span data-ttu-id="f23f7-197">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="f23f7-197">aspx-csharp</span></span>|
|<span data-ttu-id="f23f7-198">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="f23f7-198">ASP.NET (VB)</span></span>|<span data-ttu-id="f23f7-199">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="f23f7-199">aspx-vb</span></span>|
|<span data-ttu-id="f23f7-200">AzCopy</span><span class="sxs-lookup"><span data-stu-id="f23f7-200">AzCopy</span></span>|<span data-ttu-id="f23f7-201">azcopy</span><span class="sxs-lookup"><span data-stu-id="f23f7-201">azcopy</span></span>|
|<span data-ttu-id="f23f7-202">CLI de Azure</span><span class="sxs-lookup"><span data-stu-id="f23f7-202">Azure CLI</span></span>|<span data-ttu-id="f23f7-203">azurecli</span><span class="sxs-lookup"><span data-stu-id="f23f7-203">azurecli</span></span>|
|<span data-ttu-id="f23f7-204">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="f23f7-204">Azure PowerShell</span></span>|<span data-ttu-id="f23f7-205">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="f23f7-205">azurepowershell</span></span>|
|<span data-ttu-id="f23f7-206">C++</span><span class="sxs-lookup"><span data-stu-id="f23f7-206">C++</span></span>|<span data-ttu-id="f23f7-207">cpp</span><span class="sxs-lookup"><span data-stu-id="f23f7-207">cpp</span></span>|
|<span data-ttu-id="f23f7-208">C++/CX</span><span class="sxs-lookup"><span data-stu-id="f23f7-208">C++/CX</span></span>|<span data-ttu-id="f23f7-209">cppcx</span><span class="sxs-lookup"><span data-stu-id="f23f7-209">cppcx</span></span>|
|<span data-ttu-id="f23f7-210">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="f23f7-210">C++/WinRT</span></span>|<span data-ttu-id="f23f7-211">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="f23f7-211">cppwinrt</span></span>|
|<span data-ttu-id="f23f7-212">C#</span><span class="sxs-lookup"><span data-stu-id="f23f7-212">C#</span></span>|<span data-ttu-id="f23f7-213">csharp</span><span class="sxs-lookup"><span data-stu-id="f23f7-213">csharp</span></span>|
|<span data-ttu-id="f23f7-214">CSHTML</span><span class="sxs-lookup"><span data-stu-id="f23f7-214">CSHTML</span></span>|<span data-ttu-id="f23f7-215">cshtml</span><span class="sxs-lookup"><span data-stu-id="f23f7-215">cshtml</span></span>|
|<span data-ttu-id="f23f7-216">DAX</span><span class="sxs-lookup"><span data-stu-id="f23f7-216">DAX</span></span>|<span data-ttu-id="f23f7-217">dax</span><span class="sxs-lookup"><span data-stu-id="f23f7-217">dax</span></span>|
|<span data-ttu-id="f23f7-218">F#</span><span class="sxs-lookup"><span data-stu-id="f23f7-218">F#</span></span>|<span data-ttu-id="f23f7-219">fsharp</span><span class="sxs-lookup"><span data-stu-id="f23f7-219">fsharp</span></span>|
|<span data-ttu-id="f23f7-220">Go</span><span class="sxs-lookup"><span data-stu-id="f23f7-220">Go</span></span>|<span data-ttu-id="f23f7-221">go</span><span class="sxs-lookup"><span data-stu-id="f23f7-221">go</span></span>|
|<span data-ttu-id="f23f7-222">HTML</span><span class="sxs-lookup"><span data-stu-id="f23f7-222">HTML</span></span>|<span data-ttu-id="f23f7-223">html</span><span class="sxs-lookup"><span data-stu-id="f23f7-223">html</span></span>|
|<span data-ttu-id="f23f7-224">HTTP</span><span class="sxs-lookup"><span data-stu-id="f23f7-224">HTTP</span></span>|<span data-ttu-id="f23f7-225">http</span><span class="sxs-lookup"><span data-stu-id="f23f7-225">http</span></span>|
|<span data-ttu-id="f23f7-226">Java</span><span class="sxs-lookup"><span data-stu-id="f23f7-226">Java</span></span>|<span data-ttu-id="f23f7-227">java</span><span class="sxs-lookup"><span data-stu-id="f23f7-227">java</span></span>|
|<span data-ttu-id="f23f7-228">JavaScript</span><span class="sxs-lookup"><span data-stu-id="f23f7-228">JavaScript</span></span>|<span data-ttu-id="f23f7-229">javascript</span><span class="sxs-lookup"><span data-stu-id="f23f7-229">javascript</span></span>|
|<span data-ttu-id="f23f7-230">JSON</span><span class="sxs-lookup"><span data-stu-id="f23f7-230">JSON</span></span>|<span data-ttu-id="f23f7-231">json</span><span class="sxs-lookup"><span data-stu-id="f23f7-231">json</span></span>|
|<span data-ttu-id="f23f7-232">Markdown</span><span class="sxs-lookup"><span data-stu-id="f23f7-232">Markdown</span></span>|<span data-ttu-id="f23f7-233">md</span><span class="sxs-lookup"><span data-stu-id="f23f7-233">md</span></span>|
|<span data-ttu-id="f23f7-234">NodeJS</span><span class="sxs-lookup"><span data-stu-id="f23f7-234">NodeJS</span></span>|<span data-ttu-id="f23f7-235">nodejs</span><span class="sxs-lookup"><span data-stu-id="f23f7-235">nodejs</span></span>|
|<span data-ttu-id="f23f7-236">Objective-C</span><span class="sxs-lookup"><span data-stu-id="f23f7-236">Objective-C</span></span>|<span data-ttu-id="f23f7-237">objc</span><span class="sxs-lookup"><span data-stu-id="f23f7-237">objc</span></span>|
|<span data-ttu-id="f23f7-238">OData</span><span class="sxs-lookup"><span data-stu-id="f23f7-238">OData</span></span>|<span data-ttu-id="f23f7-239">odata</span><span class="sxs-lookup"><span data-stu-id="f23f7-239">odata</span></span>|
|<span data-ttu-id="f23f7-240">PHP</span><span class="sxs-lookup"><span data-stu-id="f23f7-240">PHP</span></span>|<span data-ttu-id="f23f7-241">php</span><span class="sxs-lookup"><span data-stu-id="f23f7-241">php</span></span>|
|<span data-ttu-id="f23f7-242">Power Apps Formula</span><span class="sxs-lookup"><span data-stu-id="f23f7-242">Power Apps Formula</span></span>|<span data-ttu-id="f23f7-243">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="f23f7-243">powerappsfl</span></span>|
|<span data-ttu-id="f23f7-244">PowerShell</span><span class="sxs-lookup"><span data-stu-id="f23f7-244">PowerShell</span></span>|<span data-ttu-id="f23f7-245">powershell</span><span class="sxs-lookup"><span data-stu-id="f23f7-245">powershell</span></span>|
|<span data-ttu-id="f23f7-246">Python</span><span class="sxs-lookup"><span data-stu-id="f23f7-246">Python</span></span>|<span data-ttu-id="f23f7-247">python</span><span class="sxs-lookup"><span data-stu-id="f23f7-247">python</span></span>|
|<span data-ttu-id="f23f7-248">Q#</span><span class="sxs-lookup"><span data-stu-id="f23f7-248">Q#</span></span>|<span data-ttu-id="f23f7-249">qsharp</span><span class="sxs-lookup"><span data-stu-id="f23f7-249">qsharp</span></span>|
|<span data-ttu-id="f23f7-250">R</span><span class="sxs-lookup"><span data-stu-id="f23f7-250">R</span></span>|<span data-ttu-id="f23f7-251">r</span><span class="sxs-lookup"><span data-stu-id="f23f7-251">r</span></span>|
|<span data-ttu-id="f23f7-252">Ruby</span><span class="sxs-lookup"><span data-stu-id="f23f7-252">Ruby</span></span>|<span data-ttu-id="f23f7-253">ruby</span><span class="sxs-lookup"><span data-stu-id="f23f7-253">ruby</span></span>|
|<span data-ttu-id="f23f7-254">SQL</span><span class="sxs-lookup"><span data-stu-id="f23f7-254">SQL</span></span>|<span data-ttu-id="f23f7-255">sql</span><span class="sxs-lookup"><span data-stu-id="f23f7-255">sql</span></span>|
|<span data-ttu-id="f23f7-256">Swift</span><span class="sxs-lookup"><span data-stu-id="f23f7-256">Swift</span></span>|<span data-ttu-id="f23f7-257">swift</span><span class="sxs-lookup"><span data-stu-id="f23f7-257">swift</span></span>|
|<span data-ttu-id="f23f7-258">TypeScript</span><span class="sxs-lookup"><span data-stu-id="f23f7-258">TypeScript</span></span>|<span data-ttu-id="f23f7-259">typescript</span><span class="sxs-lookup"><span data-stu-id="f23f7-259">typescript</span></span>|
|<span data-ttu-id="f23f7-260">VB</span><span class="sxs-lookup"><span data-stu-id="f23f7-260">VB</span></span>|<span data-ttu-id="f23f7-261">vb</span><span class="sxs-lookup"><span data-stu-id="f23f7-261">vb</span></span>|
|<span data-ttu-id="f23f7-262">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="f23f7-262">VSTS CLI</span></span>|<span data-ttu-id="f23f7-263">vstscli</span><span class="sxs-lookup"><span data-stu-id="f23f7-263">vstscli</span></span>|
|<span data-ttu-id="f23f7-264">XAML</span><span class="sxs-lookup"><span data-stu-id="f23f7-264">XAML</span></span>|<span data-ttu-id="f23f7-265">xaml</span><span class="sxs-lookup"><span data-stu-id="f23f7-265">xaml</span></span>|
|<span data-ttu-id="f23f7-266">XML</span><span class="sxs-lookup"><span data-stu-id="f23f7-266">XML</span></span>|<span data-ttu-id="f23f7-267">xml</span><span class="sxs-lookup"><span data-stu-id="f23f7-267">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="f23f7-268">Ejemplo: C\#</span><span class="sxs-lookup"><span data-stu-id="f23f7-268">Example: C\#</span></span>

<span data-ttu-id="f23f7-269">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="f23f7-269">__Markdown__</span></span>

    ```csharp
    // Hello1.cs
    public class Hello1
    {
        public static void Main()
        {
            System.Console.WriteLine("Hello, World!");
        }
    }
    ```

<span data-ttu-id="f23f7-270">__Representación__</span><span class="sxs-lookup"><span data-stu-id="f23f7-270">__Render__</span></span>

```csharp
// Hello1.cs
public class Hello1
{
    public static void Main()
    {
        System.Console.WriteLine("Hello, World!");
    }
}
```

#### <a name="example-sql"></a><span data-ttu-id="f23f7-271">Ejemplo: SQL</span><span class="sxs-lookup"><span data-stu-id="f23f7-271">Example: SQL</span></span>

<span data-ttu-id="f23f7-272">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="f23f7-272">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="f23f7-273">__Representación__</span><span class="sxs-lookup"><span data-stu-id="f23f7-273">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="f23f7-274">Extensiones de Markdown personalizadas para OPS</span><span class="sxs-lookup"><span data-stu-id="f23f7-274">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="f23f7-275">La plataforma de Servicios de publicación abierta (OPS) implementa Markdig Parser para Markdown, que ofrece una alta compatibilidad con GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="f23f7-275">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="f23f7-276">Markdig agrega algunas funcionalidades a través de extensiones de Markdown.</span><span class="sxs-lookup"><span data-stu-id="f23f7-276">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="f23f7-277">Por tanto, determinados artículos de la guía completa de creación de OPS se han incluido en esta guía a efectos de referencia.</span><span class="sxs-lookup"><span data-stu-id="f23f7-277">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="f23f7-278">Por ejemplo, vea "Markdig and Markdown extensions" (Markdig y extensiones de Markdown) y "Code snippets" (Fragmentos de código) en la tabla de contenido.</span><span class="sxs-lookup"><span data-stu-id="f23f7-278">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="f23f7-279">Los artículos de Docs usan GFM para aplicar formato a la mayoría de los artículos, como párrafos, vínculos, listas y encabezados.</span><span class="sxs-lookup"><span data-stu-id="f23f7-279">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="f23f7-280">Para un formato más enriquecido, los artículos pueden usar características de Markdig como:</span><span class="sxs-lookup"><span data-stu-id="f23f7-280">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="f23f7-281">Bloques de notas</span><span class="sxs-lookup"><span data-stu-id="f23f7-281">Note blocks</span></span>
- <span data-ttu-id="f23f7-282">Archivos de inclusión</span><span class="sxs-lookup"><span data-stu-id="f23f7-282">Includes</span></span>
- <span data-ttu-id="f23f7-283">Selectores</span><span class="sxs-lookup"><span data-stu-id="f23f7-283">Selectors</span></span>
- <span data-ttu-id="f23f7-284">Vídeos insertados</span><span class="sxs-lookup"><span data-stu-id="f23f7-284">Embedded videos</span></span>
- <span data-ttu-id="f23f7-285">Ejemplos y fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="f23f7-285">Code snippets/samples</span></span>

<span data-ttu-id="f23f7-286">Para obtener una lista completa, vea "Markdig and Markdown extensions" (Markdig y extensiones de Markdown) y "Code snippets" (Fragmentos de código) en la tabla de contenido.</span><span class="sxs-lookup"><span data-stu-id="f23f7-286">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="f23f7-287">Bloques de notas</span><span class="sxs-lookup"><span data-stu-id="f23f7-287">Note blocks</span></span>

<span data-ttu-id="f23f7-288">Puede elegir entre cuatro tipos de bloques de notas para centrar la atención en contenido específico:</span><span class="sxs-lookup"><span data-stu-id="f23f7-288">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="f23f7-289">NOTA</span><span class="sxs-lookup"><span data-stu-id="f23f7-289">NOTE</span></span>
- <span data-ttu-id="f23f7-290">ADVERTENCIA</span><span class="sxs-lookup"><span data-stu-id="f23f7-290">WARNING</span></span>
- <span data-ttu-id="f23f7-291">SUGERENCIA</span><span class="sxs-lookup"><span data-stu-id="f23f7-291">TIP</span></span>
- <span data-ttu-id="f23f7-292">IMPORTANTE</span><span class="sxs-lookup"><span data-stu-id="f23f7-292">IMPORTANT</span></span>

<span data-ttu-id="f23f7-293">En general, los bloques de notas deben usarse con moderación porque pueden ser problemáticos.</span><span class="sxs-lookup"><span data-stu-id="f23f7-293">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="f23f7-294">Aunque también admiten bloques de código, imágenes, listas y vínculos, trate de mantener los bloques de notas sencillos y directos.</span><span class="sxs-lookup"><span data-stu-id="f23f7-294">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="f23f7-295">Archivos de inclusión</span><span class="sxs-lookup"><span data-stu-id="f23f7-295">Includes</span></span>

<span data-ttu-id="f23f7-296">Si tiene archivos de texto o imagen reutilizables que deben incluirse en archivos de artículos, puede usar una referencia al archivo "de inclusión" a través de la característica de inclusión de archivos de Markdig.</span><span class="sxs-lookup"><span data-stu-id="f23f7-296">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="f23f7-297">Esta característica da la orden a OPS para que incluya el archivo en el archivo del artículo en el momento de la compilación, con lo que se convierte en una parte del artículo publicado.</span><span class="sxs-lookup"><span data-stu-id="f23f7-297">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="f23f7-298">Hay tres tipos de archivos de inclusión disponibles para facilitar la reutilización del contenido:</span><span class="sxs-lookup"><span data-stu-id="f23f7-298">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="f23f7-299">Insertado: reutiliza fragmentos de texto comunes insertados en otra oración.</span><span class="sxs-lookup"><span data-stu-id="f23f7-299">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="f23f7-300">Bloque: reutiliza un archivo Markdown completo como un bloque, anidado en una sección de un artículo.</span><span class="sxs-lookup"><span data-stu-id="f23f7-300">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="f23f7-301">Imágenes: se trata de la forma en que se implementa la inclusión de imágenes estándar en Docs.</span><span class="sxs-lookup"><span data-stu-id="f23f7-301">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="f23f7-302">Los archivos de inclusión insertados y en bloque no son más que un archivo Markdown (.md) sencillo.</span><span class="sxs-lookup"><span data-stu-id="f23f7-302">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="f23f7-303">Pueden contener cualquier archivo Markdown válido.</span><span class="sxs-lookup"><span data-stu-id="f23f7-303">It can contain any valid Markdown.</span></span> <span data-ttu-id="f23f7-304">Todos los archivos de inclusión Markdown deben colocarse en un [subdirectorio `/includes` común](git-github-fundamentals.md#includes-subdirectory), en la raíz del repositorio.</span><span class="sxs-lookup"><span data-stu-id="f23f7-304">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="f23f7-305">Cuando se publica el artículo, el archivo incluido se integra perfectamente en él.</span><span class="sxs-lookup"><span data-stu-id="f23f7-305">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="f23f7-306">A continuación se indican requisitos y consideraciones relacionados con los archivos de inclusión:</span><span class="sxs-lookup"><span data-stu-id="f23f7-306">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="f23f7-307">Use archivos de inclusión siempre que necesite que el mismo texto aparezca en varios artículos.</span><span class="sxs-lookup"><span data-stu-id="f23f7-307">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="f23f7-308">Use archivos de inclusión en bloque con volúmenes grandes de contenido, como un párrafo o dos, un procedimiento compartido o una sección compartida.</span><span class="sxs-lookup"><span data-stu-id="f23f7-308">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="f23f7-309">No los use para una unidad inferior a una oración.</span><span class="sxs-lookup"><span data-stu-id="f23f7-309">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="f23f7-310">Los archivos de inclusión no se representarán en la vista representada del artículo en GitHub, porque se basan en las extensiones de Markdig.</span><span class="sxs-lookup"><span data-stu-id="f23f7-310">Includes won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="f23f7-311">Se representarán después de la publicación.</span><span class="sxs-lookup"><span data-stu-id="f23f7-311">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="f23f7-312">Asegúrese de que todo el texto de un archivo de inclusión se escribe en oraciones o frases completas que no dependen del texto anterior o del texto siguiente del artículo al que hace referencia el archivo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="f23f7-312">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="f23f7-313">Si ignora esta instrucción, se crea una cadena no traducible en el artículo que rompe la experiencia localizada.</span><span class="sxs-lookup"><span data-stu-id="f23f7-313">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="f23f7-314">No inserte archivos de inclusión en otros archivos de inclusión.</span><span class="sxs-lookup"><span data-stu-id="f23f7-314">Don't embed includes within other includes.</span></span> <span data-ttu-id="f23f7-315">No son compatibles.</span><span class="sxs-lookup"><span data-stu-id="f23f7-315">They are not supported.</span></span>
- <span data-ttu-id="f23f7-316">Coloque los archivos multimedia en una carpeta de medios específica del subdirectorio de archivos de inclusión, por ejemplo, la carpeta `<repo>`/includes/media.</span><span class="sxs-lookup"><span data-stu-id="f23f7-316">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="f23f7-317">El directorio multimedia no debe contener ninguna imagen en su raíz.</span><span class="sxs-lookup"><span data-stu-id="f23f7-317">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="f23f7-318">Si el archivo de inclusión no tiene imágenes, no se necesita un directorio multimedia correspondiente.</span><span class="sxs-lookup"><span data-stu-id="f23f7-318">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="f23f7-319">Como sucede con los artículos habituales, no comparta contenido multimedia entre los archivos de inclusión.</span><span class="sxs-lookup"><span data-stu-id="f23f7-319">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="f23f7-320">Use un archivo independiente con un nombre exclusivo para cada archivo de inclusión y cada artículo.</span><span class="sxs-lookup"><span data-stu-id="f23f7-320">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="f23f7-321">Almacene el archivo multimedia en la carpeta de medios asociada con el archivo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="f23f7-321">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="f23f7-322">No use un archivo de inclusión como el único contenido de un artículo.</span><span class="sxs-lookup"><span data-stu-id="f23f7-322">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="f23f7-323">Se supone que los archivos de inclusión deben ser complementarios al contenido del resto del artículo.</span><span class="sxs-lookup"><span data-stu-id="f23f7-323">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="f23f7-324">Selectores</span><span class="sxs-lookup"><span data-stu-id="f23f7-324">Selectors</span></span>

<span data-ttu-id="f23f7-325">Use los selectores en los artículos técnicos cuando cree varias versiones del mismo artículo, a fin de abordar las diferencias de implementación entre tecnologías o plataformas.</span><span class="sxs-lookup"><span data-stu-id="f23f7-325">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="f23f7-326">Esto suele aplicarse sobre todo a nuestro contenido en de plataformas móviles destinado a desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="f23f7-326">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="f23f7-327">Actualmente hay dos tipos diferentes de selectores en Markdig, un selector único y un selector múltiple.</span><span class="sxs-lookup"><span data-stu-id="f23f7-327">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="f23f7-328">Como se coloca el mismo selector de Markdown en cada artículo de la selección, se recomienda colocar el selector del artículo en un archivo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="f23f7-328">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="f23f7-329">Después, puede hacer referencia a dicho archivo de inclusión en todos los artículos que usan el mismo selector.</span><span class="sxs-lookup"><span data-stu-id="f23f7-329">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="f23f7-330">Fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="f23f7-330">Code snippets</span></span>

<span data-ttu-id="f23f7-331">Markdig admite la inclusión avanzada de código en un artículo, a través de su extensión de fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="f23f7-331">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="f23f7-332">Proporciona una representación avanzada basada en las características de GFM, como la selección del lenguaje de programación y el color de sintaxis, además de características útiles como:</span><span class="sxs-lookup"><span data-stu-id="f23f7-332">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="f23f7-333">Inclusión de fragmentos y muestras de código centralizados desde un repositorio externo.</span><span class="sxs-lookup"><span data-stu-id="f23f7-333">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="f23f7-334">Interfaz de usuario con pestañas para mostrar varias versiones de ejemplos de código en diferentes lenguajes.</span><span class="sxs-lookup"><span data-stu-id="f23f7-334">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="f23f7-335">Dificultades y solución de problemas</span><span class="sxs-lookup"><span data-stu-id="f23f7-335">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="f23f7-336">Texto alternativo</span><span class="sxs-lookup"><span data-stu-id="f23f7-336">Alt text</span></span>

<span data-ttu-id="f23f7-337">El texto alternativo que contiene guiones bajos no se procesa correctamente.</span><span class="sxs-lookup"><span data-stu-id="f23f7-337">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="f23f7-338">Por ejemplo, en lugar de usar esto:</span><span class="sxs-lookup"><span data-stu-id="f23f7-338">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="f23f7-339">Incluya una secuencia de escape de guiones bajos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="f23f7-339">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="f23f7-340">Apóstrofos y comillas</span><span class="sxs-lookup"><span data-stu-id="f23f7-340">Apostrophes and quotation marks</span></span>

<span data-ttu-id="f23f7-341">Si copia texto de Word en Markdown editor, el texto debe contener apóstrofos o comillas (inglesas) "inteligentes".</span><span class="sxs-lookup"><span data-stu-id="f23f7-341">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="f23f7-342">Es necesario codificarlos o bien cambiarlos a apóstrofos o comillas básicos.</span><span class="sxs-lookup"><span data-stu-id="f23f7-342">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span>
<span data-ttu-id="f23f7-343">De lo contrario, cuando se publique el archivo, aparecerán cosas como esta: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="f23f7-343">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="f23f7-344">A continuación se especifica la codificación para las versiones "inteligentes" de estos signos de puntuación:</span><span class="sxs-lookup"><span data-stu-id="f23f7-344">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="f23f7-345">Comilla izquierda de apertura: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="f23f7-345">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="f23f7-346">Comilla derecha de cierre: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="f23f7-346">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="f23f7-347">Apóstrofo o comilla simple derecha de cierre: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="f23f7-347">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="f23f7-348">Comilla simple izquierda de apertura (uso poco común): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="f23f7-348">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="f23f7-349">Corchetes angulares</span><span class="sxs-lookup"><span data-stu-id="f23f7-349">Angle brackets</span></span>

<span data-ttu-id="f23f7-350">Es habitual usar corchetes angulares para indicar un marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="f23f7-350">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="f23f7-351">Cuando lo haga en el texto (no en el código), tendrá que codificar los corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="f23f7-351">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="f23f7-352">De lo contrario, Markdown considera que se han insertado como una etiqueta HTML.</span><span class="sxs-lookup"><span data-stu-id="f23f7-352">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="f23f7-353">Por ejemplo, codifique `<script name>` como `&lt;script name&gt;`.</span><span class="sxs-lookup"><span data-stu-id="f23f7-353">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="f23f7-354">Vea también:</span><span class="sxs-lookup"><span data-stu-id="f23f7-354">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="f23f7-355">Recursos de Markdown</span><span class="sxs-lookup"><span data-stu-id="f23f7-355">Markdown resources</span></span>

- [<span data-ttu-id="f23f7-356">Introducción a Markdown</span><span class="sxs-lookup"><span data-stu-id="f23f7-356">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="f23f7-357">Hoja de referencia rápida sobre Markdown para Docs</span><span class="sxs-lookup"><span data-stu-id="f23f7-357">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="f23f7-358">Aspectos básicos de Markdown en GitHub</span><span class="sxs-lookup"><span data-stu-id="f23f7-358">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
- [<span data-ttu-id="f23f7-359">La guía de Markdown</span><span class="sxs-lookup"><span data-stu-id="f23f7-359">The Markdown Guide</span></span>](https://www.markdownguide.org/)
