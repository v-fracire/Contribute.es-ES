---
title: Uso de Markdown para escribir Docs
description: En este artículo se proporciona información básica y de referencia para el lenguaje Markdown que se utiliza para escribir artículos de docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 07/13/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 96d00abc052c3b23ca62201dccdbe590a927e72d
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="d85a3-103">Uso de Markdown para escribir Docs</span><span class="sxs-lookup"><span data-stu-id="d85a3-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="d85a3-104">Los artículos de docs.microsoft.com están escritos en un lenguaje de marcado ligero denominado [Markdown](https://daringfireball.net/projects/markdown/), que resulta fácil de leer y de aprender.</span><span class="sxs-lookup"><span data-stu-id="d85a3-104">Docs.microsoft.com articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="d85a3-105">Por ello, se ha convertido rápidamente en un estándar del sector.</span><span class="sxs-lookup"><span data-stu-id="d85a3-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="d85a3-106">Como el contenido de Docs está almacenado en GitHub, puede usar un superconjunto de Markdown denominado [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), que proporciona una funcionalidad adicional para necesidades comunes de aplicación de formato.</span><span class="sxs-lookup"><span data-stu-id="d85a3-106">Because Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="d85a3-107">Además, la plataforma de Servicios de publicación abierta (OPS) implementa DocFX Flavored Markdown (DFM).</span><span class="sxs-lookup"><span data-stu-id="d85a3-107">Additionally, Open Publishing Services (OPS) implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="d85a3-108">DFM ofrece una alta compatibilidad con GitHub Flavored Markdown (GFM) y agrega una funcionalidad para habilitar características específicas para Docs.</span><span class="sxs-lookup"><span data-stu-id="d85a3-108">DFM is highly compatible with GitHub Flavored Markdown (GFM), adding functionality to enable Docs-specific features.</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="d85a3-109">Aspectos básicos de Markdown</span><span class="sxs-lookup"><span data-stu-id="d85a3-109">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="d85a3-110">Encabezados</span><span class="sxs-lookup"><span data-stu-id="d85a3-110">Headings</span></span>

<span data-ttu-id="d85a3-111">Para crear un encabezado, debe usar una marca hash (#) como sigue:</span><span class="sxs-lookup"><span data-stu-id="d85a3-111">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a><span data-ttu-id="d85a3-112">Texto en negrita y cursiva</span><span class="sxs-lookup"><span data-stu-id="d85a3-112">Bold and italic text</span></span>

<span data-ttu-id="d85a3-113">Para aplicar formato de **negrita** al texto, debe encerrarlo entre dos asteriscos:</span><span class="sxs-lookup"><span data-stu-id="d85a3-113">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
    This text is **bold**.
```

<span data-ttu-id="d85a3-114">Para aplicar formato de *cursiva* al texto, debe encerrarlo entre un solo asterisco:</span><span class="sxs-lookup"><span data-stu-id="d85a3-114">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
    This text is *italic*.
```

<span data-ttu-id="d85a3-115">Para aplicar formato de ***negrita y cursiva*** al texto, debe encerrarlo entre tres asteriscos:</span><span class="sxs-lookup"><span data-stu-id="d85a3-115">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a><span data-ttu-id="d85a3-116">Listas</span><span class="sxs-lookup"><span data-stu-id="d85a3-116">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="d85a3-117">Listas sin ordenar</span><span class="sxs-lookup"><span data-stu-id="d85a3-117">Unordered list</span></span>

<span data-ttu-id="d85a3-118">Para aplicar formato a una lista sin ordenar o con viñetas, puede usar asteriscos o guiones.</span><span class="sxs-lookup"><span data-stu-id="d85a3-118">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="d85a3-119">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="d85a3-119">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="d85a3-120">se representará como:</span><span class="sxs-lookup"><span data-stu-id="d85a3-120">will be rendered as:</span></span>

- <span data-ttu-id="d85a3-121">Elemento de lista 1</span><span class="sxs-lookup"><span data-stu-id="d85a3-121">List item 1</span></span>
- <span data-ttu-id="d85a3-122">Elemento de lista 2</span><span class="sxs-lookup"><span data-stu-id="d85a3-122">List item 2</span></span>
- <span data-ttu-id="d85a3-123">Elemento de lista 3</span><span class="sxs-lookup"><span data-stu-id="d85a3-123">List item 3</span></span>

<span data-ttu-id="d85a3-124">Para anidar una lista dentro de otra, tiene que aplicar sangría a los elementos de lista secundarios.</span><span class="sxs-lookup"><span data-stu-id="d85a3-124">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="d85a3-125">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="d85a3-125">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="d85a3-126">se representará como:</span><span class="sxs-lookup"><span data-stu-id="d85a3-126">will be rendered as:</span></span>

- <span data-ttu-id="d85a3-127">Elemento de lista 1</span><span class="sxs-lookup"><span data-stu-id="d85a3-127">List item 1</span></span>
  - <span data-ttu-id="d85a3-128">Elemento de lista A</span><span class="sxs-lookup"><span data-stu-id="d85a3-128">List item A</span></span>
  - <span data-ttu-id="d85a3-129">Elemento de lista B</span><span class="sxs-lookup"><span data-stu-id="d85a3-129">List item B</span></span>
- <span data-ttu-id="d85a3-130">Elemento de lista 2</span><span class="sxs-lookup"><span data-stu-id="d85a3-130">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="d85a3-131">Listas ordenada</span><span class="sxs-lookup"><span data-stu-id="d85a3-131">Ordered list</span></span>

<span data-ttu-id="d85a3-132">Para aplicar formato a una lista ordenada o de pasos, debe usar los números correspondientes.</span><span class="sxs-lookup"><span data-stu-id="d85a3-132">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="d85a3-133">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="d85a3-133">For example, the following Markdown:</span></span>

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

<span data-ttu-id="d85a3-134">se representará como:</span><span class="sxs-lookup"><span data-stu-id="d85a3-134">will be rendered as:</span></span>

1. <span data-ttu-id="d85a3-135">Primera instrucción</span><span class="sxs-lookup"><span data-stu-id="d85a3-135">First instruction</span></span>
2. <span data-ttu-id="d85a3-136">Segunda instrucción</span><span class="sxs-lookup"><span data-stu-id="d85a3-136">Second instruction</span></span>
3. <span data-ttu-id="d85a3-137">Tercera instrucción</span><span class="sxs-lookup"><span data-stu-id="d85a3-137">Third instruction</span></span>

<span data-ttu-id="d85a3-138">Para anidar una lista dentro de otra, tiene que aplicar sangría a los elementos de lista secundarios.</span><span class="sxs-lookup"><span data-stu-id="d85a3-138">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="d85a3-139">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="d85a3-139">For example, the following Markdown:</span></span>

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

<span data-ttu-id="d85a3-140">se representará como:</span><span class="sxs-lookup"><span data-stu-id="d85a3-140">will be rendered as:</span></span>

1. <span data-ttu-id="d85a3-141">Primera instrucción</span><span class="sxs-lookup"><span data-stu-id="d85a3-141">First instruction</span></span>
    1. <span data-ttu-id="d85a3-142">Subinstrucción</span><span class="sxs-lookup"><span data-stu-id="d85a3-142">Sub-instruction</span></span>
    2. <span data-ttu-id="d85a3-143">Subinstrucción</span><span class="sxs-lookup"><span data-stu-id="d85a3-143">Sub-instruction</span></span>
2. <span data-ttu-id="d85a3-144">Segunda instrucción</span><span class="sxs-lookup"><span data-stu-id="d85a3-144">Second instruction</span></span>

### <a name="tables"></a><span data-ttu-id="d85a3-145">Tablas</span><span class="sxs-lookup"><span data-stu-id="d85a3-145">Tables</span></span>

<span data-ttu-id="d85a3-146">Las tablas no forman parte de la especificación principal de Markdown, pero son compatibles con GFM.</span><span class="sxs-lookup"><span data-stu-id="d85a3-146">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="d85a3-147">Puede crear tablas con los caracteres de barra vertical (|) y guion (-).</span><span class="sxs-lookup"><span data-stu-id="d85a3-147">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="d85a3-148">Los guiones crean cada encabezado de columna, mientras que las barras verticales separan cada columna.</span><span class="sxs-lookup"><span data-stu-id="d85a3-148">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="d85a3-149">Incluya una línea en blanco antes de la tabla para que se represente correctamente.</span><span class="sxs-lookup"><span data-stu-id="d85a3-149">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="d85a3-150">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="d85a3-150">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="d85a3-151">se representará como:</span><span class="sxs-lookup"><span data-stu-id="d85a3-151">will be rendered as:</span></span>

| <span data-ttu-id="d85a3-152">Diversión</span><span class="sxs-lookup"><span data-stu-id="d85a3-152">Fun</span></span>                  | <span data-ttu-id="d85a3-153">Con</span><span class="sxs-lookup"><span data-stu-id="d85a3-153">With</span></span>                 | <span data-ttu-id="d85a3-154">Tablas</span><span class="sxs-lookup"><span data-stu-id="d85a3-154">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="d85a3-155">columna alineada a la izquierda</span><span class="sxs-lookup"><span data-stu-id="d85a3-155">left-aligned column</span></span>  | <span data-ttu-id="d85a3-156">columna alineada a la derecha</span><span class="sxs-lookup"><span data-stu-id="d85a3-156">right-aligned column</span></span> | <span data-ttu-id="d85a3-157">columna centrada</span><span class="sxs-lookup"><span data-stu-id="d85a3-157">centered column</span></span> |
| <span data-ttu-id="d85a3-158">100 USD</span><span class="sxs-lookup"><span data-stu-id="d85a3-158">$100</span></span>                 | <span data-ttu-id="d85a3-159">100 USD</span><span class="sxs-lookup"><span data-stu-id="d85a3-159">$100</span></span>                 | <span data-ttu-id="d85a3-160">100 USD</span><span class="sxs-lookup"><span data-stu-id="d85a3-160">$100</span></span>            |
| <span data-ttu-id="d85a3-161">10 USD</span><span class="sxs-lookup"><span data-stu-id="d85a3-161">$10</span></span>                  | <span data-ttu-id="d85a3-162">10 USD</span><span class="sxs-lookup"><span data-stu-id="d85a3-162">$10</span></span>                  | <span data-ttu-id="d85a3-163">10 USD</span><span class="sxs-lookup"><span data-stu-id="d85a3-163">$10</span></span>             |
| <span data-ttu-id="d85a3-164">1 USD</span><span class="sxs-lookup"><span data-stu-id="d85a3-164">$1</span></span>                   | <span data-ttu-id="d85a3-165">1 USD</span><span class="sxs-lookup"><span data-stu-id="d85a3-165">$1</span></span>                   | <span data-ttu-id="d85a3-166">1 USD</span><span class="sxs-lookup"><span data-stu-id="d85a3-166">$1</span></span>              |

<span data-ttu-id="d85a3-167">Para obtener más información sobre la creación de tablas, consulte:</span><span class="sxs-lookup"><span data-stu-id="d85a3-167">For more information on creating tables, see:</span></span>

- <span data-ttu-id="d85a3-168">La [característica de ajuste de tabla](#table-wrapping) de DFM, que puede ayudar a aplicar formato a las tablas anchas</span><span class="sxs-lookup"><span data-stu-id="d85a3-168">The DFM [table wrapping feature](#table-wrapping), which can help with formatting of wide tables</span></span>
- <span data-ttu-id="d85a3-169">La [organización de información con tablas](https://help.github.com/articles/organizing-information-with-tables/) de GitHub</span><span class="sxs-lookup"><span data-stu-id="d85a3-169">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/)</span></span>
- <span data-ttu-id="d85a3-170">Las aplicación web del [generador de tablas de Markdown](https://www.tablesgenerator.com/markdown_tables)</span><span class="sxs-lookup"><span data-stu-id="d85a3-170">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app</span></span>
- <span data-ttu-id="d85a3-171">La [Hoja de referencia de Adam Pritchard sobre Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)</span><span class="sxs-lookup"><span data-stu-id="d85a3-171">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)</span></span>
- <span data-ttu-id="d85a3-172">La [información adicional de Michel Fortin sobre Markdown](https://michelf.ca/projects/php-markdown/extra/#table)</span><span class="sxs-lookup"><span data-stu-id="d85a3-172">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table)</span></span>
- [<span data-ttu-id="d85a3-173">Conversión de tablas HTML en Markdown</span><span class="sxs-lookup"><span data-stu-id="d85a3-173">Convert HTML tables to Markdown</span></span>](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a><span data-ttu-id="d85a3-174">Vínculos</span><span class="sxs-lookup"><span data-stu-id="d85a3-174">Links</span></span>

<span data-ttu-id="d85a3-175">La sintaxis de Markdown de un vínculo insertado consta de la parte `[link text]`, que es el texto que se va a enlazar, seguida de la parte `(file-name.md)`, que es la dirección URL o el nombre de archivo a los que se va a realizar la vinculación:</span><span class="sxs-lookup"><span data-stu-id="d85a3-175">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="d85a3-176">Para obtener más información sobre la vinculación, vea:</span><span class="sxs-lookup"><span data-stu-id="d85a3-176">For more information on linking, see:</span></span>

- <span data-ttu-id="d85a3-177">La [guía de sintaxis de Markdown](https://daringfireball.net/projects/markdown/syntax#link) para obtener información detallada sobre la compatibilidad de vínculos base de Markdown.</span><span class="sxs-lookup"><span data-stu-id="d85a3-177">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="d85a3-178">La sección [Vínculos](how-to-write-links.md) de esta guía para obtener información sobre la sintaxis de vinculación adicional proporcionada por DFM.</span><span class="sxs-lookup"><span data-stu-id="d85a3-178">The [Links](how-to-write-links.md) section of this guide for details on additional linking syntax that DFM provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="d85a3-179">Fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="d85a3-179">Code snippets</span></span>

<span data-ttu-id="d85a3-180">Markdown admite la inserción de fragmentos de código en una oración y como un bloque "delimitado" independiente entre oraciones.</span><span class="sxs-lookup"><span data-stu-id="d85a3-180">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="d85a3-181">Para obtener información, vea:</span><span class="sxs-lookup"><span data-stu-id="d85a3-181">For details, see:</span></span>

- [<span data-ttu-id="d85a3-182">Compatiblidad nativa de Markdown para bloques de código</span><span class="sxs-lookup"><span data-stu-id="d85a3-182">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="d85a3-183">Compatibilidad de GFM para delimitación de código y resaltado de sintaxis</span><span class="sxs-lookup"><span data-stu-id="d85a3-183">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="d85a3-184">Los bloques de código delimitados son una forma sencilla de habilitar el resaltado de sintaxis de los fragmentos de código.</span><span class="sxs-lookup"><span data-stu-id="d85a3-184">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="d85a3-185">El formato general del bloque de código delimitado es:</span><span class="sxs-lookup"><span data-stu-id="d85a3-185">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="d85a3-186">El alias después de los tres caracteres iniciales de acento grave (\`) define el resaltado de sintaxis que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="d85a3-186">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="d85a3-187">A continuación se muestra una lista de lenguajes de programación de uso común en contenido de Docs y la etiqueta asociada:</span><span class="sxs-lookup"><span data-stu-id="d85a3-187">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="d85a3-188">Estos lenguajes tienen nombres descriptivos y la mayoría de ellos realzan el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="d85a3-188">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="d85a3-189">Nombre</span><span class="sxs-lookup"><span data-stu-id="d85a3-189">Name</span></span>|<span data-ttu-id="d85a3-190">Etiqueta de Markdown</span><span class="sxs-lookup"><span data-stu-id="d85a3-190">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="d85a3-191">.NET Console</span><span class="sxs-lookup"><span data-stu-id="d85a3-191">.NET Console</span></span>|<span data-ttu-id="d85a3-192">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="d85a3-192">dotnetcli</span></span>|
|<span data-ttu-id="d85a3-193">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="d85a3-193">ASP.NET (C#)</span></span>|<span data-ttu-id="d85a3-194">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="d85a3-194">aspx-csharp</span></span>|
|<span data-ttu-id="d85a3-195">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="d85a3-195">ASP.NET (VB)</span></span>|<span data-ttu-id="d85a3-196">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="d85a3-196">aspx-vb</span></span>|
|<span data-ttu-id="d85a3-197">AzCopy</span><span class="sxs-lookup"><span data-stu-id="d85a3-197">AzCopy</span></span>|<span data-ttu-id="d85a3-198">azcopy</span><span class="sxs-lookup"><span data-stu-id="d85a3-198">azcopy</span></span>|
|<span data-ttu-id="d85a3-199">CLI de Azure</span><span class="sxs-lookup"><span data-stu-id="d85a3-199">Azure CLI</span></span>|<span data-ttu-id="d85a3-200">azurecli</span><span class="sxs-lookup"><span data-stu-id="d85a3-200">azurecli</span></span>|
|<span data-ttu-id="d85a3-201">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="d85a3-201">Azure PowerShell</span></span>|<span data-ttu-id="d85a3-202">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="d85a3-202">azurepowershell</span></span>|
|<span data-ttu-id="d85a3-203">C++</span><span class="sxs-lookup"><span data-stu-id="d85a3-203">C++</span></span>|<span data-ttu-id="d85a3-204">cpp</span><span class="sxs-lookup"><span data-stu-id="d85a3-204">cpp</span></span>|
|<span data-ttu-id="d85a3-205">C++/CX</span><span class="sxs-lookup"><span data-stu-id="d85a3-205">C++/CX</span></span>|<span data-ttu-id="d85a3-206">cppcx</span><span class="sxs-lookup"><span data-stu-id="d85a3-206">cppcx</span></span>|
|<span data-ttu-id="d85a3-207">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="d85a3-207">C++/WinRT</span></span>|<span data-ttu-id="d85a3-208">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="d85a3-208">cppwinrt</span></span>|
|<span data-ttu-id="d85a3-209">C#</span><span class="sxs-lookup"><span data-stu-id="d85a3-209">C#</span></span>|<span data-ttu-id="d85a3-210">csharp</span><span class="sxs-lookup"><span data-stu-id="d85a3-210">csharp</span></span>|
|<span data-ttu-id="d85a3-211">CSHTML</span><span class="sxs-lookup"><span data-stu-id="d85a3-211">CSHTML</span></span>|<span data-ttu-id="d85a3-212">cshtml</span><span class="sxs-lookup"><span data-stu-id="d85a3-212">cshtml</span></span>|
|<span data-ttu-id="d85a3-213">DAX</span><span class="sxs-lookup"><span data-stu-id="d85a3-213">DAX</span></span>|<span data-ttu-id="d85a3-214">dax</span><span class="sxs-lookup"><span data-stu-id="d85a3-214">dax</span></span>|
|<span data-ttu-id="d85a3-215">F#</span><span class="sxs-lookup"><span data-stu-id="d85a3-215">F#</span></span>|<span data-ttu-id="d85a3-216">fsharp</span><span class="sxs-lookup"><span data-stu-id="d85a3-216">fsharp</span></span>|
|<span data-ttu-id="d85a3-217">Go</span><span class="sxs-lookup"><span data-stu-id="d85a3-217">Go</span></span>|<span data-ttu-id="d85a3-218">go</span><span class="sxs-lookup"><span data-stu-id="d85a3-218">go</span></span>|
|<span data-ttu-id="d85a3-219">HTML</span><span class="sxs-lookup"><span data-stu-id="d85a3-219">HTML</span></span>|<span data-ttu-id="d85a3-220">html</span><span class="sxs-lookup"><span data-stu-id="d85a3-220">html</span></span>|
|<span data-ttu-id="d85a3-221">HTTP</span><span class="sxs-lookup"><span data-stu-id="d85a3-221">HTTP</span></span>|<span data-ttu-id="d85a3-222">http</span><span class="sxs-lookup"><span data-stu-id="d85a3-222">http</span></span>|
|<span data-ttu-id="d85a3-223">Java</span><span class="sxs-lookup"><span data-stu-id="d85a3-223">Java</span></span>|<span data-ttu-id="d85a3-224">java</span><span class="sxs-lookup"><span data-stu-id="d85a3-224">java</span></span>|
|<span data-ttu-id="d85a3-225">JavaScript</span><span class="sxs-lookup"><span data-stu-id="d85a3-225">JavaScript</span></span>|<span data-ttu-id="d85a3-226">javascript</span><span class="sxs-lookup"><span data-stu-id="d85a3-226">javascript</span></span>|
|<span data-ttu-id="d85a3-227">JSON</span><span class="sxs-lookup"><span data-stu-id="d85a3-227">JSON</span></span>|<span data-ttu-id="d85a3-228">json</span><span class="sxs-lookup"><span data-stu-id="d85a3-228">json</span></span>|
|<span data-ttu-id="d85a3-229">Markdown</span><span class="sxs-lookup"><span data-stu-id="d85a3-229">Markdown</span></span>|<span data-ttu-id="d85a3-230">md</span><span class="sxs-lookup"><span data-stu-id="d85a3-230">md</span></span>|
|<span data-ttu-id="d85a3-231">NodeJS</span><span class="sxs-lookup"><span data-stu-id="d85a3-231">NodeJS</span></span>|<span data-ttu-id="d85a3-232">nodejs</span><span class="sxs-lookup"><span data-stu-id="d85a3-232">nodejs</span></span>|
|<span data-ttu-id="d85a3-233">Objective-C</span><span class="sxs-lookup"><span data-stu-id="d85a3-233">Objective-C</span></span>|<span data-ttu-id="d85a3-234">objc</span><span class="sxs-lookup"><span data-stu-id="d85a3-234">objc</span></span>|
|<span data-ttu-id="d85a3-235">OData</span><span class="sxs-lookup"><span data-stu-id="d85a3-235">OData</span></span>|<span data-ttu-id="d85a3-236">odata</span><span class="sxs-lookup"><span data-stu-id="d85a3-236">odata</span></span>|
|<span data-ttu-id="d85a3-237">PHP</span><span class="sxs-lookup"><span data-stu-id="d85a3-237">PHP</span></span>|<span data-ttu-id="d85a3-238">php</span><span class="sxs-lookup"><span data-stu-id="d85a3-238">php</span></span>|
|<span data-ttu-id="d85a3-239">Power Apps Formula</span><span class="sxs-lookup"><span data-stu-id="d85a3-239">Power Apps Formula</span></span>|<span data-ttu-id="d85a3-240">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="d85a3-240">powerappsfl</span></span>|
|<span data-ttu-id="d85a3-241">PowerShell</span><span class="sxs-lookup"><span data-stu-id="d85a3-241">PowerShell</span></span>|<span data-ttu-id="d85a3-242">powershell</span><span class="sxs-lookup"><span data-stu-id="d85a3-242">powershell</span></span>|
|<span data-ttu-id="d85a3-243">Python</span><span class="sxs-lookup"><span data-stu-id="d85a3-243">Python</span></span>|<span data-ttu-id="d85a3-244">python</span><span class="sxs-lookup"><span data-stu-id="d85a3-244">python</span></span>|
|<span data-ttu-id="d85a3-245">Q#</span><span class="sxs-lookup"><span data-stu-id="d85a3-245">Q#</span></span>|<span data-ttu-id="d85a3-246">qsharp</span><span class="sxs-lookup"><span data-stu-id="d85a3-246">qsharp</span></span>|
|<span data-ttu-id="d85a3-247">Ruby</span><span class="sxs-lookup"><span data-stu-id="d85a3-247">Ruby</span></span>|<span data-ttu-id="d85a3-248">ruby</span><span class="sxs-lookup"><span data-stu-id="d85a3-248">ruby</span></span>|
|<span data-ttu-id="d85a3-249">SQL</span><span class="sxs-lookup"><span data-stu-id="d85a3-249">SQL</span></span>|<span data-ttu-id="d85a3-250">sql</span><span class="sxs-lookup"><span data-stu-id="d85a3-250">sql</span></span>|
|<span data-ttu-id="d85a3-251">Swift</span><span class="sxs-lookup"><span data-stu-id="d85a3-251">Swift</span></span>|<span data-ttu-id="d85a3-252">swift</span><span class="sxs-lookup"><span data-stu-id="d85a3-252">swift</span></span>|
|<span data-ttu-id="d85a3-253">TypeScript</span><span class="sxs-lookup"><span data-stu-id="d85a3-253">TypeScript</span></span>|<span data-ttu-id="d85a3-254">typescript</span><span class="sxs-lookup"><span data-stu-id="d85a3-254">typescript</span></span>|
|<span data-ttu-id="d85a3-255">VB</span><span class="sxs-lookup"><span data-stu-id="d85a3-255">VB</span></span>|<span data-ttu-id="d85a3-256">vb</span><span class="sxs-lookup"><span data-stu-id="d85a3-256">vb</span></span>|
|<span data-ttu-id="d85a3-257">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="d85a3-257">VSTS CLI</span></span>|<span data-ttu-id="d85a3-258">vstscli</span><span class="sxs-lookup"><span data-stu-id="d85a3-258">vstscli</span></span>|
|<span data-ttu-id="d85a3-259">XAML</span><span class="sxs-lookup"><span data-stu-id="d85a3-259">XAML</span></span>|<span data-ttu-id="d85a3-260">xaml</span><span class="sxs-lookup"><span data-stu-id="d85a3-260">xaml</span></span>|
|<span data-ttu-id="d85a3-261">XML</span><span class="sxs-lookup"><span data-stu-id="d85a3-261">XML</span></span>|<span data-ttu-id="d85a3-262">xml</span><span class="sxs-lookup"><span data-stu-id="d85a3-262">xml</span></span>|

#### <a name="example-c"></a><span data-ttu-id="d85a3-263">Ejemplo: C\#</span><span class="sxs-lookup"><span data-stu-id="d85a3-263">Example: C\#</span></span>

<span data-ttu-id="d85a3-264">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="d85a3-264">__Markdown__</span></span>

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

<span data-ttu-id="d85a3-265">__Representación__</span><span class="sxs-lookup"><span data-stu-id="d85a3-265">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="d85a3-266">Ejemplo: SQL</span><span class="sxs-lookup"><span data-stu-id="d85a3-266">Example: SQL</span></span>

<span data-ttu-id="d85a3-267">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="d85a3-267">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="d85a3-268">__Representación__</span><span class="sxs-lookup"><span data-stu-id="d85a3-268">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="d85a3-269">Extensiones de Markdown personalizadas para OPS</span><span class="sxs-lookup"><span data-stu-id="d85a3-269">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="d85a3-270">La plataforma de Servicios de publicación abierta (OPS) implementa DocFX Flavored Markdown (DFM), que ofrece una alta compatibilidad con GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="d85a3-270">Open Publishing Services (OPS) implements DocFX Flavored Markdown (DFM), which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="d85a3-271">DFM agrega algunas funcionalidades a través de extensiones de Markdown.</span><span class="sxs-lookup"><span data-stu-id="d85a3-271">DFM adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="d85a3-272">Por tanto, determinados artículos de la guía completa de creación de OPS se han incluido en esta guía a efectos de referencia.</span><span class="sxs-lookup"><span data-stu-id="d85a3-272">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="d85a3-273">(Por ejemplo, vea "DFM and Markdown extensions" (DFM y extensiones de Markdown) y "Code snippets" (Fragmentos de código) en la tabla de contenido).</span><span class="sxs-lookup"><span data-stu-id="d85a3-273">(For example, see "DFM and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="d85a3-274">Los artículos de Docs usan GFM para aplicar formato a la mayoría de los artículos, como párrafos, vínculos, listas y encabezados.</span><span class="sxs-lookup"><span data-stu-id="d85a3-274">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="d85a3-275">Para un formato más enriquecido, los artículos pueden usar características de DFM como:</span><span class="sxs-lookup"><span data-stu-id="d85a3-275">For richer formatting, articles can use DFM features such as:</span></span>

- <span data-ttu-id="d85a3-276">Bloques de notas</span><span class="sxs-lookup"><span data-stu-id="d85a3-276">Note blocks</span></span>
- <span data-ttu-id="d85a3-277">Archivos de inclusión</span><span class="sxs-lookup"><span data-stu-id="d85a3-277">Includes</span></span>
- <span data-ttu-id="d85a3-278">Selectores</span><span class="sxs-lookup"><span data-stu-id="d85a3-278">Selectors</span></span>
- <span data-ttu-id="d85a3-279">Vídeos insertados</span><span class="sxs-lookup"><span data-stu-id="d85a3-279">Embedded videos</span></span>
- <span data-ttu-id="d85a3-280">Ejemplos y fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="d85a3-280">Code snippets/samples</span></span>

<span data-ttu-id="d85a3-281">Para obtener una lista completa, vea "DFM and Markdown extensions" (DFM y extensiones de Markdown) y "Code snippets" (Fragmentos de código) en la tabla de contenido.</span><span class="sxs-lookup"><span data-stu-id="d85a3-281">For the complete list, refer to "DFM and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="d85a3-282">Bloques de notas</span><span class="sxs-lookup"><span data-stu-id="d85a3-282">Note blocks</span></span>

<span data-ttu-id="d85a3-283">Puede elegir entre cuatro tipos de bloques de notas para centrar la atención en contenido específico:</span><span class="sxs-lookup"><span data-stu-id="d85a3-283">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="d85a3-284">NOTA</span><span class="sxs-lookup"><span data-stu-id="d85a3-284">NOTE</span></span>
- <span data-ttu-id="d85a3-285">ADVERTENCIA</span><span class="sxs-lookup"><span data-stu-id="d85a3-285">WARNING</span></span>
- <span data-ttu-id="d85a3-286">SUGERENCIA</span><span class="sxs-lookup"><span data-stu-id="d85a3-286">TIP</span></span>
- <span data-ttu-id="d85a3-287">IMPORTANTE</span><span class="sxs-lookup"><span data-stu-id="d85a3-287">IMPORTANT</span></span>

<span data-ttu-id="d85a3-288">En general, los bloques de notas deben usarse con moderación porque pueden ser problemáticos.</span><span class="sxs-lookup"><span data-stu-id="d85a3-288">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="d85a3-289">Aunque también admiten bloques de código, imágenes, listas y vínculos, trate de mantener los bloques de notas sencillos y directos.</span><span class="sxs-lookup"><span data-stu-id="d85a3-289">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

### <a name="includes"></a><span data-ttu-id="d85a3-290">Archivos de inclusión</span><span class="sxs-lookup"><span data-stu-id="d85a3-290">Includes</span></span>

<span data-ttu-id="d85a3-291">Si tiene archivos de texto o imagen reutilizables que deben incluirse en archivos de artículos, puede usar una referencia al archivo "de inclusión" a través de la característica de inclusión de archivos de DFM.</span><span class="sxs-lookup"><span data-stu-id="d85a3-291">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the DFM file include feature.</span></span> <span data-ttu-id="d85a3-292">Esta característica da la orden a OPS para que incluya el archivo en el archivo del artículo en el momento de la compilación, con lo que se convierte en una parte del artículo publicado.</span><span class="sxs-lookup"><span data-stu-id="d85a3-292">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="d85a3-293">Hay tres tipos de archivos de inclusión disponibles para facilitar la reutilización del contenido:</span><span class="sxs-lookup"><span data-stu-id="d85a3-293">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="d85a3-294">Insertado: reutiliza fragmentos de texto comunes insertados en otra oración.</span><span class="sxs-lookup"><span data-stu-id="d85a3-294">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="d85a3-295">Bloque: reutiliza un archivo Markdown completo como un bloque, anidado en una sección de un artículo.</span><span class="sxs-lookup"><span data-stu-id="d85a3-295">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="d85a3-296">Imágenes: se trata de la forma en que se implementa la inclusión de imágenes estándar en Docs.</span><span class="sxs-lookup"><span data-stu-id="d85a3-296">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="d85a3-297">Los archivos de inclusión insertados y en bloque no son más que un archivo Markdown (.md) sencillo.</span><span class="sxs-lookup"><span data-stu-id="d85a3-297">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="d85a3-298">Pueden contener cualquier archivo Markdown válido.</span><span class="sxs-lookup"><span data-stu-id="d85a3-298">It can contain any valid Markdown.</span></span> <span data-ttu-id="d85a3-299">Todos los archivos de inclusión Markdown deben colocarse en un [subdirectorio `/includes` común](git-github-fundamentals.md#includes-subdirectory), en la raíz del repositorio.</span><span class="sxs-lookup"><span data-stu-id="d85a3-299">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="d85a3-300">Cuando se publica el artículo, el archivo incluido se integra perfectamente en él.</span><span class="sxs-lookup"><span data-stu-id="d85a3-300">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="d85a3-301">A continuación se indican requisitos y consideraciones relacionados con los archivos de inclusión:</span><span class="sxs-lookup"><span data-stu-id="d85a3-301">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="d85a3-302">Use archivos de inclusión siempre que necesite que el mismo texto aparezca en varios artículos.</span><span class="sxs-lookup"><span data-stu-id="d85a3-302">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="d85a3-303">Use archivos de inclusión en bloque con volúmenes grandes de contenido, como un párrafo o dos, un procedimiento compartido o una sección compartida.</span><span class="sxs-lookup"><span data-stu-id="d85a3-303">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="d85a3-304">No los use para una unidad inferior a una oración.</span><span class="sxs-lookup"><span data-stu-id="d85a3-304">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="d85a3-305">Los archivos de inclusión no se representarán en la vista representada del artículo en GitHub, porque se basan en las extensiones de DFM.</span><span class="sxs-lookup"><span data-stu-id="d85a3-305">Includes won't be rendered in the GitHub rendered view of your article, because they rely on DFM extensions.</span></span> <span data-ttu-id="d85a3-306">Se representarán después de la publicación.</span><span class="sxs-lookup"><span data-stu-id="d85a3-306">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="d85a3-307">Asegúrese de que todo el texto de un archivo de inclusión se escribe en oraciones o frases completas que no dependen del texto anterior o del texto siguiente del artículo al que hace referencia el archivo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="d85a3-307">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="d85a3-308">Si ignora esta instrucción, se crea una cadena no traducible en el artículo que rompe la experiencia localizada.</span><span class="sxs-lookup"><span data-stu-id="d85a3-308">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="d85a3-309">No inserte archivos de inclusión en otros archivos de inclusión.</span><span class="sxs-lookup"><span data-stu-id="d85a3-309">Don't embed includes within other includes.</span></span> <span data-ttu-id="d85a3-310">No son compatibles.</span><span class="sxs-lookup"><span data-stu-id="d85a3-310">They are not supported.</span></span>
- <span data-ttu-id="d85a3-311">Coloque los archivos multimedia en una carpeta de medios específica del subdirectorio de archivos de inclusión, por ejemplo, la carpeta `<repo>`/includes/media.</span><span class="sxs-lookup"><span data-stu-id="d85a3-311">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="d85a3-312">El directorio multimedia no debe contener ninguna imagen en su raíz.</span><span class="sxs-lookup"><span data-stu-id="d85a3-312">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="d85a3-313">Si el archivo de inclusión no tiene imágenes, no se necesita un directorio multimedia correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d85a3-313">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="d85a3-314">Como sucede con los artículos habituales, no comparta contenido multimedia entre los archivos de inclusión.</span><span class="sxs-lookup"><span data-stu-id="d85a3-314">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="d85a3-315">Use un archivo independiente con un nombre exclusivo para cada archivo de inclusión y cada artículo.</span><span class="sxs-lookup"><span data-stu-id="d85a3-315">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="d85a3-316">Almacene el archivo multimedia en la carpeta de medios asociada con el archivo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="d85a3-316">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="d85a3-317">No use un archivo de inclusión como el único contenido de un artículo.</span><span class="sxs-lookup"><span data-stu-id="d85a3-317">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="d85a3-318">Se supone que los archivos de inclusión deben ser complementarios al contenido del resto del artículo.</span><span class="sxs-lookup"><span data-stu-id="d85a3-318">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

### <a name="selectors"></a><span data-ttu-id="d85a3-319">Selectores</span><span class="sxs-lookup"><span data-stu-id="d85a3-319">Selectors</span></span>

<span data-ttu-id="d85a3-320">Use los selectores en los artículos técnicos cuando cree varias versiones del mismo artículo, a fin de abordar las diferencias de implementación entre tecnologías o plataformas.</span><span class="sxs-lookup"><span data-stu-id="d85a3-320">Use selectors in technical articles when you author multiple flavors of the same article, to address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="d85a3-321">Esto suele aplicarse sobre todo a nuestro contenido en de plataformas móviles destinado a desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="d85a3-321">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="d85a3-322">Actualmente hay dos tipos diferentes de selectores en DFM, un selector único y un selector múltiple.</span><span class="sxs-lookup"><span data-stu-id="d85a3-322">There are currently two different types of selectors in DFM, a single selector and a multi-selector.</span></span>

<span data-ttu-id="d85a3-323">Como se coloca el mismo selector de Markdown en cada artículo de la selección, se recomienda colocar el selector del artículo en un archivo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="d85a3-323">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="d85a3-324">Después, puede hacer referencia a dicho archivo de inclusión en todos los artículos que usan el mismo selector.</span><span class="sxs-lookup"><span data-stu-id="d85a3-324">Then you can reference that include in all your articles that use the same selector.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="d85a3-325">Fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="d85a3-325">Code snippets</span></span>

<span data-ttu-id="d85a3-326">DFM admite la inclusión avanzada de código en un artículo, a través de su extensión de fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="d85a3-326">DFM supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="d85a3-327">Proporciona una representación avanzada basada en las características de GFM, como la selección del lenguaje de programación y el color de sintaxis, además de características útiles como:</span><span class="sxs-lookup"><span data-stu-id="d85a3-327">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="d85a3-328">Inclusión de fragmentos y muestras de código centralizados desde un repositorio externo.</span><span class="sxs-lookup"><span data-stu-id="d85a3-328">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="d85a3-329">Interfaz de usuario con pestañas para mostrar varias versiones de ejemplos de código en diferentes lenguajes.</span><span class="sxs-lookup"><span data-stu-id="d85a3-329">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="d85a3-330">Dificultades y solución de problemas</span><span class="sxs-lookup"><span data-stu-id="d85a3-330">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="d85a3-331">Texto alternativo</span><span class="sxs-lookup"><span data-stu-id="d85a3-331">Alt text</span></span>

<span data-ttu-id="d85a3-332">El texto alternativo que contiene guiones bajos no se procesa correctamente.</span><span class="sxs-lookup"><span data-stu-id="d85a3-332">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="d85a3-333">Por ejemplo, en lugar de usar esto:</span><span class="sxs-lookup"><span data-stu-id="d85a3-333">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="d85a3-334">Incluya una secuencia de escape de guiones bajos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="d85a3-334">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="d85a3-335">Apóstrofos y comillas</span><span class="sxs-lookup"><span data-stu-id="d85a3-335">Apostrophes and quotation marks</span></span>

<span data-ttu-id="d85a3-336">Si copia texto de Word en Markdown editor, el texto debe contener apóstrofos o comillas (inglesas) "inteligentes".</span><span class="sxs-lookup"><span data-stu-id="d85a3-336">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="d85a3-337">Es necesario codificarlos o bien cambiarlos a apóstrofos o comillas básicos.</span><span class="sxs-lookup"><span data-stu-id="d85a3-337">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="d85a3-338">De lo contrario, cuando se publique el archivo, aparecerán cosas como esta: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="d85a3-338">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="d85a3-339">A continuación se especifica la codificación para las versiones "inteligentes" de estos signos de puntuación:</span><span class="sxs-lookup"><span data-stu-id="d85a3-339">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="d85a3-340">Comilla izquierda de apertura: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="d85a3-340">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="d85a3-341">Comilla derecha de cierre: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="d85a3-341">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="d85a3-342">Apóstrofo o comilla simple derecha de cierre: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="d85a3-342">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="d85a3-343">Comilla simple izquierda de apertura (uso poco común): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="d85a3-343">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="d85a3-344">Corchetes angulares</span><span class="sxs-lookup"><span data-stu-id="d85a3-344">Angle brackets</span></span>

<span data-ttu-id="d85a3-345">Si usa corchetes angulares en el texto (sin codificar) en el archivo, por ejemplo, para denotar un marcador de posición, debe codificar manualmente los corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="d85a3-345">If you use angle brackets in text (not code) in your file--for example, to denote a placeholder--you need to manually encode the angle brackets.</span></span> <span data-ttu-id="d85a3-346">De lo contrario, Markdown considera que se han insertado como una etiqueta HTML.</span><span class="sxs-lookup"><span data-stu-id="d85a3-346">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="d85a3-347">Por ejemplo, codifique `<script name>` como `&lt;script name&gt;`.</span><span class="sxs-lookup"><span data-stu-id="d85a3-347">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="d85a3-348">Otras referencias</span><span class="sxs-lookup"><span data-stu-id="d85a3-348">See also</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="d85a3-349">Recursos de Markdown</span><span class="sxs-lookup"><span data-stu-id="d85a3-349">Markdown resources</span></span>

- [<span data-ttu-id="d85a3-350">Introducción a Markdown</span><span class="sxs-lookup"><span data-stu-id="d85a3-350">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="d85a3-351">Hoja de referencia rápida sobre Markdown para Docs</span><span class="sxs-lookup"><span data-stu-id="d85a3-351">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="d85a3-352">Aspectos básicos de Markdown en GitHub</span><span class="sxs-lookup"><span data-stu-id="d85a3-352">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
