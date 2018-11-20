---
title: Uso de Markdown para escribir Docs
description: En este artículo se proporciona información básica y de referencia para el lenguaje Markdown que se utiliza para escribir artículos de docs.microsoft.com.
ms.date: 07/13/2017
ms.openlocfilehash: 21194c4bd6020d847b526a4d9544c826aa199e2a
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609531"
---
# <a name="how-to-use-markdown-for-writing-docs"></a><span data-ttu-id="4f60c-103">Uso de Markdown para escribir Docs</span><span class="sxs-lookup"><span data-stu-id="4f60c-103">How to use Markdown for writing Docs</span></span>

<span data-ttu-id="4f60c-104">Los artículos de [docs.microsoft.com](http://docs.microsoft.com) están escritos en un lenguaje de marcado ligero denominado [Markdown](https://daringfireball.net/projects/markdown/), que resulta fácil de leer y de aprender.</span><span class="sxs-lookup"><span data-stu-id="4f60c-104">[Docs.microsoft.com](http://docs.microsoft.com) articles are written in a lightweight markup language called [Markdown](https://daringfireball.net/projects/markdown/), which is both easy to read and easy to learn.</span></span> <span data-ttu-id="4f60c-105">Por ello, se ha convertido rápidamente en un estándar del sector.</span><span class="sxs-lookup"><span data-stu-id="4f60c-105">Because of this, it has quickly become an industry standard.</span></span>

<span data-ttu-id="4f60c-106">Como el contenido de Docs se almacena en GitHub, puede usar un superconjunto de Markdown denominado [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), que proporciona una funcionalidad adicional para necesidades comunes de aplicación de formato.</span><span class="sxs-lookup"><span data-stu-id="4f60c-106">Since Docs content is stored in GitHub, it can use a superset of Markdown called [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), which provides additional functionality for common formatting needs.</span></span> <span data-ttu-id="4f60c-107">Además, la plataforma Servicios de publicación abierta (OPS) implementa Markdig Markdown Parser.</span><span class="sxs-lookup"><span data-stu-id="4f60c-107">Additionally, Open Publishing Services (OPS) implements Markdig Markdown Parser.</span></span> <span data-ttu-id="4f60c-108">Markdig ofrece alta compatibilidad con GFM y agrega funciones para habilitar características específicas de Docs.</span><span class="sxs-lookup"><span data-stu-id="4f60c-108">Markdig is highly compatible with GFM, adding functionality to enable Docs-specific features.</span></span>

* <span data-ttu-id="4f60c-109">Markdig es un procesador de Markdown extensible para .NET rápido, potente y conforme a CommonMark.</span><span class="sxs-lookup"><span data-stu-id="4f60c-109">Markdig is a fast, powerful, CommonMark compliant, extensible Markdown processor for .NET.</span></span>
* https://github.com/lunet-io/markdig
* <span data-ttu-id="4f60c-110">Mejor soporte técnico de la comunidad</span><span class="sxs-lookup"><span data-stu-id="4f60c-110">Better community support</span></span>
* <span data-ttu-id="4f60c-111">Mejor soporte técnico para los estándares</span><span class="sxs-lookup"><span data-stu-id="4f60c-111">Better standards support</span></span>

## <a name="markdown-basics"></a><span data-ttu-id="4f60c-112">Aspectos básicos de Markdown</span><span class="sxs-lookup"><span data-stu-id="4f60c-112">Markdown basics</span></span>

### <a name="headings"></a><span data-ttu-id="4f60c-113">Encabezados</span><span class="sxs-lookup"><span data-stu-id="4f60c-113">Headings</span></span>

<span data-ttu-id="4f60c-114">Para crear un encabezado, debe usar una marca hash (#) como sigue:</span><span class="sxs-lookup"><span data-stu-id="4f60c-114">To create a heading, you use a hash mark (#), as follows:</span></span>

```markdown
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
```

<span data-ttu-id="4f60c-115">Los encabezados se deben expresar en estilo atx, es decir usar de 1 a 6 caracteres de hash (#) al inicio de la línea para indicar un encabezado, lo que se corresponde a los niveles de título HTML de H1 a H6.</span><span class="sxs-lookup"><span data-stu-id="4f60c-115">Headings should be done using atx-style, that is, use 1-6 hash characters (#) at the start of the line to indicate a heading, corresponding to HTML headings levels H1 through H6.</span></span> <span data-ttu-id="4f60c-116">Anteriormente se usan ejemplos de encabezados de nivel 1 a 4.</span><span class="sxs-lookup"><span data-stu-id="4f60c-116">Examples of first- through fourth-level headers are used above.</span></span>

<span data-ttu-id="4f60c-117">Solo **debe** haber un encabezado de primer nivel (H1) en el título, que se mostrará como el título de la página.</span><span class="sxs-lookup"><span data-stu-id="4f60c-117">There **must** be only one first-level heading (H1) in your topic, which will be displayed as the on-page title.</span></span>

<span data-ttu-id="4f60c-118">Si el encabezado termina con un carácter `#`, tendrá que agregar un carácter `#` adicional al final para que el título se represente de forma correcta.</span><span class="sxs-lookup"><span data-stu-id="4f60c-118">If your heading finishes with a `#` character, you need to add an extra `#` character in the end in order for the title to render correctly.</span></span> <span data-ttu-id="4f60c-119">Por ejemplo, `# Async Programming in F# #`.</span><span class="sxs-lookup"><span data-stu-id="4f60c-119">For example, `# Async Programming in F# #`.</span></span>

<span data-ttu-id="4f60c-120">Los encabezados de segundo nivel generarán la tabla de contenido de la página que aparece en la sección "En este artículo" por debajo del título de la página.</span><span class="sxs-lookup"><span data-stu-id="4f60c-120">Second-level headings will generate the on-page TOC that appears in the "In this article" section underneath the on-page title.</span></span>

### <a name="bold-and-italic-text"></a><span data-ttu-id="4f60c-121">Texto en negrita y cursiva</span><span class="sxs-lookup"><span data-stu-id="4f60c-121">Bold and italic text</span></span>

<span data-ttu-id="4f60c-122">Para aplicar formato de **negrita** al texto, debe encerrarlo entre dos asteriscos:</span><span class="sxs-lookup"><span data-stu-id="4f60c-122">To format text as **bold**, you enclose it in two asterisks:</span></span>

```markdown
This text is **bold**.
```

<span data-ttu-id="4f60c-123">Para aplicar formato de *cursiva* al texto, debe encerrarlo entre un solo asterisco:</span><span class="sxs-lookup"><span data-stu-id="4f60c-123">To format text as *italic*, you enclose it in a single asterisk:</span></span>

```markdown
This text is *italic*.
```

<span data-ttu-id="4f60c-124">Para aplicar formato de ***negrita y cursiva*** al texto, debe encerrarlo entre tres asteriscos:</span><span class="sxs-lookup"><span data-stu-id="4f60c-124">To format text as both ***bold and italic***, you enclose it in three asterisks:</span></span>

```markdown
This is text is both ***bold and italic***.
```

### <a name="blockquotes"></a><span data-ttu-id="4f60c-125">Citas en bloque</span><span class="sxs-lookup"><span data-stu-id="4f60c-125">Blockquotes</span></span>

<span data-ttu-id="4f60c-126">Las citas en bloque se crean con el carácter `>`:</span><span class="sxs-lookup"><span data-stu-id="4f60c-126">Blockquotes are created using the `>` character:</span></span>

```markdown
> The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended. Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight. In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.
```

<span data-ttu-id="4f60c-127">El ejemplo anterior se representa de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4f60c-127">The preceding example renders as follows:</span></span>

> <span data-ttu-id="4f60c-128">La sequía duraba ya 10 millones de años, y el reinado de los terribles reptiles había desaparecido hacía tiempo.</span><span class="sxs-lookup"><span data-stu-id="4f60c-128">The drought had lasted now for ten million years, and the reign of the terrible lizards had long since ended.</span></span> <span data-ttu-id="4f60c-129">Aquí en el Ecuador, en el continente que un día sería conocido como África, la batalla por la supervivencia había alcanzado su punto de máxima crueldad, pero no había rastro del vencedor.</span><span class="sxs-lookup"><span data-stu-id="4f60c-129">Here on the Equator, in the continent which would one day be known as Africa, the battle for existence had reached a new climax of ferocity, and the victor was not yet in sight.</span></span> <span data-ttu-id="4f60c-130">En esta tierra yerma y desolada, solo prosperarían los más pequeños, veloces o fieros, los únicos con la esperanza de sobrevivir.</span><span class="sxs-lookup"><span data-stu-id="4f60c-130">In this barren and desiccated land, only the small or the swift or the fierce could flourish, or even hope to survive.</span></span>

### <a name="lists"></a><span data-ttu-id="4f60c-131">Listas</span><span class="sxs-lookup"><span data-stu-id="4f60c-131">Lists</span></span>

#### <a name="unordered-list"></a><span data-ttu-id="4f60c-132">Listas sin ordenar</span><span class="sxs-lookup"><span data-stu-id="4f60c-132">Unordered list</span></span>

<span data-ttu-id="4f60c-133">Para aplicar formato a una lista sin ordenar o con viñetas, puede usar asteriscos o guiones.</span><span class="sxs-lookup"><span data-stu-id="4f60c-133">To format an unordered/bulleted list, you can use either asterisks or dashes.</span></span> <span data-ttu-id="4f60c-134">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="4f60c-134">For example, the following Markdown:</span></span>

```markdown
- List item 1
- List item 2
- List item 3
```

<span data-ttu-id="4f60c-135">se representará como:</span><span class="sxs-lookup"><span data-stu-id="4f60c-135">will be rendered as:</span></span>

- <span data-ttu-id="4f60c-136">Elemento de lista 1</span><span class="sxs-lookup"><span data-stu-id="4f60c-136">List item 1</span></span>
- <span data-ttu-id="4f60c-137">Elemento de lista 2</span><span class="sxs-lookup"><span data-stu-id="4f60c-137">List item 2</span></span>
- <span data-ttu-id="4f60c-138">Elemento de lista 3</span><span class="sxs-lookup"><span data-stu-id="4f60c-138">List item 3</span></span>

<span data-ttu-id="4f60c-139">Para anidar una lista dentro de otra, tiene que aplicar sangría a los elementos de lista secundarios.</span><span class="sxs-lookup"><span data-stu-id="4f60c-139">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="4f60c-140">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="4f60c-140">For example, the following Markdown:</span></span>

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

<span data-ttu-id="4f60c-141">se representará como:</span><span class="sxs-lookup"><span data-stu-id="4f60c-141">will be rendered as:</span></span>

- <span data-ttu-id="4f60c-142">Elemento de lista 1</span><span class="sxs-lookup"><span data-stu-id="4f60c-142">List item 1</span></span>
  - <span data-ttu-id="4f60c-143">Elemento de lista A</span><span class="sxs-lookup"><span data-stu-id="4f60c-143">List item A</span></span>
  - <span data-ttu-id="4f60c-144">Elemento de lista B</span><span class="sxs-lookup"><span data-stu-id="4f60c-144">List item B</span></span>
- <span data-ttu-id="4f60c-145">Elemento de lista 2</span><span class="sxs-lookup"><span data-stu-id="4f60c-145">List item 2</span></span>

#### <a name="ordered-list"></a><span data-ttu-id="4f60c-146">Listas ordenada</span><span class="sxs-lookup"><span data-stu-id="4f60c-146">Ordered list</span></span>

<span data-ttu-id="4f60c-147">Para aplicar formato a una lista ordenada o de pasos, debe usar los números correspondientes.</span><span class="sxs-lookup"><span data-stu-id="4f60c-147">To format an ordered/stepwise list, you use corresponding numbers.</span></span> <span data-ttu-id="4f60c-148">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="4f60c-148">For example, the following Markdown:</span></span>

```markdown
1. First instruction
1. Second instruction
1. Third instruction
```

<span data-ttu-id="4f60c-149">se representará como:</span><span class="sxs-lookup"><span data-stu-id="4f60c-149">will be rendered as:</span></span>

1. <span data-ttu-id="4f60c-150">Primera instrucción</span><span class="sxs-lookup"><span data-stu-id="4f60c-150">First instruction</span></span>
2. <span data-ttu-id="4f60c-151">Segunda instrucción</span><span class="sxs-lookup"><span data-stu-id="4f60c-151">Second instruction</span></span>
3. <span data-ttu-id="4f60c-152">Tercera instrucción</span><span class="sxs-lookup"><span data-stu-id="4f60c-152">Third instruction</span></span>

<span data-ttu-id="4f60c-153">Para anidar una lista dentro de otra, tiene que aplicar sangría a los elementos de lista secundarios.</span><span class="sxs-lookup"><span data-stu-id="4f60c-153">To nest a list within another list, indent the child list items.</span></span> <span data-ttu-id="4f60c-154">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="4f60c-154">For example, the following Markdown:</span></span>

```markdown
1. First instruction
   1. Sub-instruction
   1. Sub-instruction
1. Second instruction
```

<span data-ttu-id="4f60c-155">se representará como:</span><span class="sxs-lookup"><span data-stu-id="4f60c-155">will be rendered as:</span></span>

1. <span data-ttu-id="4f60c-156">Primera instrucción</span><span class="sxs-lookup"><span data-stu-id="4f60c-156">First instruction</span></span>
   1. <span data-ttu-id="4f60c-157">Subinstrucción</span><span class="sxs-lookup"><span data-stu-id="4f60c-157">Sub-instruction</span></span>
   2. <span data-ttu-id="4f60c-158">Subinstrucción</span><span class="sxs-lookup"><span data-stu-id="4f60c-158">Sub-instruction</span></span>
2. <span data-ttu-id="4f60c-159">Segunda instrucción</span><span class="sxs-lookup"><span data-stu-id="4f60c-159">Second instruction</span></span>

<span data-ttu-id="4f60c-160">Observe que se usa "1."</span><span class="sxs-lookup"><span data-stu-id="4f60c-160">Note that we use '1.'</span></span> <span data-ttu-id="4f60c-161">para todas las entradas.</span><span class="sxs-lookup"><span data-stu-id="4f60c-161">for all entries.</span></span> <span data-ttu-id="4f60c-162">Facilita la revisión de las diferencias cuando las actualizaciones posteriores incluyan pasos nuevos o quiten pasos existentes.</span><span class="sxs-lookup"><span data-stu-id="4f60c-162">It makes diffs easier to review when later updates include new steps or remove existing steps.</span></span>

### <a name="tables"></a><span data-ttu-id="4f60c-163">Tablas</span><span class="sxs-lookup"><span data-stu-id="4f60c-163">Tables</span></span>

<span data-ttu-id="4f60c-164">Las tablas no forman parte de la especificación principal de Markdown, pero son compatibles con GFM.</span><span class="sxs-lookup"><span data-stu-id="4f60c-164">Tables are not part of the core Markdown specification, but GFM supports them.</span></span> <span data-ttu-id="4f60c-165">Puede crear tablas con los caracteres de barra vertical (|) y guion (-).</span><span class="sxs-lookup"><span data-stu-id="4f60c-165">You can create tables by using the pipe (|) and hyphen (-) characters.</span></span> <span data-ttu-id="4f60c-166">Los guiones crean cada encabezado de columna, mientras que las barras verticales separan cada columna.</span><span class="sxs-lookup"><span data-stu-id="4f60c-166">Hyphens create each column's header, while pipes separate each column.</span></span> <span data-ttu-id="4f60c-167">Incluya una línea en blanco antes de la tabla para que se represente correctamente.</span><span class="sxs-lookup"><span data-stu-id="4f60c-167">Include a blank line before your table so it's rendered correctly.</span></span>

<span data-ttu-id="4f60c-168">Por ejemplo, el siguiente código Markdown:</span><span class="sxs-lookup"><span data-stu-id="4f60c-168">For example, the following Markdown:</span></span>

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

<span data-ttu-id="4f60c-169">se representará como:</span><span class="sxs-lookup"><span data-stu-id="4f60c-169">will be rendered as:</span></span>

| <span data-ttu-id="4f60c-170">Diversión</span><span class="sxs-lookup"><span data-stu-id="4f60c-170">Fun</span></span>                  | <span data-ttu-id="4f60c-171">Con</span><span class="sxs-lookup"><span data-stu-id="4f60c-171">With</span></span>                 | <span data-ttu-id="4f60c-172">Tablas</span><span class="sxs-lookup"><span data-stu-id="4f60c-172">Tables</span></span>          |
| :------------------- | -------------------: |:---------------:|
| <span data-ttu-id="4f60c-173">columna alineada a la izquierda</span><span class="sxs-lookup"><span data-stu-id="4f60c-173">left-aligned column</span></span>  | <span data-ttu-id="4f60c-174">columna alineada a la derecha</span><span class="sxs-lookup"><span data-stu-id="4f60c-174">right-aligned column</span></span> | <span data-ttu-id="4f60c-175">columna centrada</span><span class="sxs-lookup"><span data-stu-id="4f60c-175">centered column</span></span> |
| <span data-ttu-id="4f60c-176">100 USD</span><span class="sxs-lookup"><span data-stu-id="4f60c-176">$100</span></span>                 | <span data-ttu-id="4f60c-177">100 USD</span><span class="sxs-lookup"><span data-stu-id="4f60c-177">$100</span></span>                 | <span data-ttu-id="4f60c-178">100 USD</span><span class="sxs-lookup"><span data-stu-id="4f60c-178">$100</span></span>            |
| <span data-ttu-id="4f60c-179">10 USD</span><span class="sxs-lookup"><span data-stu-id="4f60c-179">$10</span></span>                  | <span data-ttu-id="4f60c-180">10 USD</span><span class="sxs-lookup"><span data-stu-id="4f60c-180">$10</span></span>                  | <span data-ttu-id="4f60c-181">10 USD</span><span class="sxs-lookup"><span data-stu-id="4f60c-181">$10</span></span>             |
| <span data-ttu-id="4f60c-182">1 USD</span><span class="sxs-lookup"><span data-stu-id="4f60c-182">$1</span></span>                   | <span data-ttu-id="4f60c-183">1 USD</span><span class="sxs-lookup"><span data-stu-id="4f60c-183">$1</span></span>                   | <span data-ttu-id="4f60c-184">1 USD</span><span class="sxs-lookup"><span data-stu-id="4f60c-184">$1</span></span>              |

<span data-ttu-id="4f60c-185">Para obtener más información sobre la creación de tablas, consulte:</span><span class="sxs-lookup"><span data-stu-id="4f60c-185">For more information on creating tables, see:</span></span>

- <span data-ttu-id="4f60c-186">La [característica de ajuste de tabla](#table-wrapping) de Markdig, que puede ayudar a aplicar formato a las tablas anchas.</span><span class="sxs-lookup"><span data-stu-id="4f60c-186">The Markdig [table wrapping feature](#table-wrapping), which can help with formatting of wide tables.</span></span>
- <span data-ttu-id="4f60c-187">La [organización de información con tablas](https://help.github.com/articles/organizing-information-with-tables/) de GitHub.</span><span class="sxs-lookup"><span data-stu-id="4f60c-187">GitHub's [Organizing information with tables](https://help.github.com/articles/organizing-information-with-tables/).</span></span>
- <span data-ttu-id="4f60c-188">Las aplicación web del [generador de tablas de Markdown](https://www.tablesgenerator.com/markdown_tables).</span><span class="sxs-lookup"><span data-stu-id="4f60c-188">The [Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables) web app.</span></span>
- <span data-ttu-id="4f60c-189">La [Hoja de referencia de Adam Pritchard sobre Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span><span class="sxs-lookup"><span data-stu-id="4f60c-189">[Adam Pritchard's Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables).</span></span>
- <span data-ttu-id="4f60c-190">La [información adicional de Michel Fortin sobre Markdown](https://michelf.ca/projects/php-markdown/extra/#table).</span><span class="sxs-lookup"><span data-stu-id="4f60c-190">[Michel Fortin's Markdown Extra](https://michelf.ca/projects/php-markdown/extra/#table).</span></span>
- <span data-ttu-id="4f60c-191">[Conversión de tablas HTML en Markdown](https://jmalarcon.github.io/markdowntables/).</span><span class="sxs-lookup"><span data-stu-id="4f60c-191">[Convert HTML tables to Markdown](https://jmalarcon.github.io/markdowntables/).</span></span>

### <a name="links"></a><span data-ttu-id="4f60c-192">Vínculos</span><span class="sxs-lookup"><span data-stu-id="4f60c-192">Links</span></span>

<span data-ttu-id="4f60c-193">La sintaxis de Markdown de un vínculo insertado consta de la parte `[link text]`, que es el texto que se va a enlazar, seguida de la parte `(file-name.md)`, que es la dirección URL o el nombre de archivo a los que se va a realizar la vinculación:</span><span class="sxs-lookup"><span data-stu-id="4f60c-193">The Markdown syntax for an inline link consists of the `[link text]` portion, which is the text that will be hyperlinked, followed by the `(file-name.md)` portion, which is the URL or file name that's being linked to:</span></span>

 `[link text](file-name.md)`

<span data-ttu-id="4f60c-194">Para obtener más información sobre la vinculación, vea:</span><span class="sxs-lookup"><span data-stu-id="4f60c-194">For more information on linking, see:</span></span>

- <span data-ttu-id="4f60c-195">La [guía de sintaxis de Markdown](https://daringfireball.net/projects/markdown/syntax#link) para obtener información detallada sobre la compatibilidad de vínculos base de Markdown.</span><span class="sxs-lookup"><span data-stu-id="4f60c-195">The [Markdown syntax guide](https://daringfireball.net/projects/markdown/syntax#link) for details on Markdown's base linking support.</span></span>
- <span data-ttu-id="4f60c-196">La sección [Vínculos](how-to-write-links.md) de esta guía para obtener información sobre la sintaxis de vinculación adicional proporcionada por Markdig.</span><span class="sxs-lookup"><span data-stu-id="4f60c-196">The [Links](how-to-write-links.md) section of this guide for details on the additional linking syntax that Markdig provides.</span></span>

### <a name="code-snippets"></a><span data-ttu-id="4f60c-197">Fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="4f60c-197">Code snippets</span></span>

<span data-ttu-id="4f60c-198">Markdown admite la inserción de fragmentos de código en una oración y como un bloque "delimitado" independiente entre oraciones.</span><span class="sxs-lookup"><span data-stu-id="4f60c-198">Markdown supports the placement of code snippets both inline in a sentence and as a separate "fenced" block between sentences.</span></span> <span data-ttu-id="4f60c-199">Para obtener información, vea:</span><span class="sxs-lookup"><span data-stu-id="4f60c-199">For details, see:</span></span>

- [<span data-ttu-id="4f60c-200">Compatiblidad nativa de Markdown para bloques de código</span><span class="sxs-lookup"><span data-stu-id="4f60c-200">Markdown's native support for code blocks</span></span>](https://daringfireball.net/projects/markdown/syntax#precode)
- [<span data-ttu-id="4f60c-201">Compatibilidad de GFM para delimitación de código y resaltado de sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f60c-201">GFM support for code fencing and syntax highlighting</span></span>](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

<span data-ttu-id="4f60c-202">Los bloques de código delimitados son una forma sencilla de habilitar el resaltado de sintaxis de los fragmentos de código.</span><span class="sxs-lookup"><span data-stu-id="4f60c-202">Fenced code blocks are an easy way to enable syntax highlighting for your code snippets.</span></span> <span data-ttu-id="4f60c-203">El formato general del bloque de código delimitado es:</span><span class="sxs-lookup"><span data-stu-id="4f60c-203">The general format for fenced code blocks is:</span></span>

    ```alias
    ...
    your code goes in here
    ...
    ```

<span data-ttu-id="4f60c-204">El alias después de los tres caracteres iniciales de acento grave (\`) define el resaltado de sintaxis que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="4f60c-204">The alias after the initial three backtick (\`) characters defines the syntax highlighting to be used.</span></span> <span data-ttu-id="4f60c-205">A continuación se muestra una lista de lenguajes de programación de uso común en contenido de Docs y la etiqueta asociada:</span><span class="sxs-lookup"><span data-stu-id="4f60c-205">The following is a list of commonly used programming languages in Docs content and the matching label:</span></span>

<span data-ttu-id="4f60c-206">Estos lenguajes tienen nombres descriptivos y la mayoría de ellos realzan el lenguaje.</span><span class="sxs-lookup"><span data-stu-id="4f60c-206">These languages have friendly name support and most have language highlighting.</span></span>

|<span data-ttu-id="4f60c-207">Nombre</span><span class="sxs-lookup"><span data-stu-id="4f60c-207">Name</span></span>|<span data-ttu-id="4f60c-208">Etiqueta de Markdown</span><span class="sxs-lookup"><span data-stu-id="4f60c-208">Markdown Label</span></span>|
|-----|-------|
|<span data-ttu-id="4f60c-209">.NET Console</span><span class="sxs-lookup"><span data-stu-id="4f60c-209">.NET Console</span></span>|<span data-ttu-id="4f60c-210">dotnetcli</span><span class="sxs-lookup"><span data-stu-id="4f60c-210">dotnetcli</span></span>|
|<span data-ttu-id="4f60c-211">ASP.NET (C#)</span><span class="sxs-lookup"><span data-stu-id="4f60c-211">ASP.NET (C#)</span></span>|<span data-ttu-id="4f60c-212">aspx-csharp</span><span class="sxs-lookup"><span data-stu-id="4f60c-212">aspx-csharp</span></span>|
|<span data-ttu-id="4f60c-213">ASP.NET (VB)</span><span class="sxs-lookup"><span data-stu-id="4f60c-213">ASP.NET (VB)</span></span>|<span data-ttu-id="4f60c-214">aspx-vb</span><span class="sxs-lookup"><span data-stu-id="4f60c-214">aspx-vb</span></span>|
|<span data-ttu-id="4f60c-215">AzCopy</span><span class="sxs-lookup"><span data-stu-id="4f60c-215">AzCopy</span></span>|<span data-ttu-id="4f60c-216">azcopy</span><span class="sxs-lookup"><span data-stu-id="4f60c-216">azcopy</span></span>|
|<span data-ttu-id="4f60c-217">CLI de Azure</span><span class="sxs-lookup"><span data-stu-id="4f60c-217">Azure CLI</span></span>|<span data-ttu-id="4f60c-218">azurecli</span><span class="sxs-lookup"><span data-stu-id="4f60c-218">azurecli</span></span>|
|<span data-ttu-id="4f60c-219">Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f60c-219">Azure PowerShell</span></span>|<span data-ttu-id="4f60c-220">azurepowershell</span><span class="sxs-lookup"><span data-stu-id="4f60c-220">azurepowershell</span></span>|
|<span data-ttu-id="4f60c-221">C++</span><span class="sxs-lookup"><span data-stu-id="4f60c-221">C++</span></span>|<span data-ttu-id="4f60c-222">cpp</span><span class="sxs-lookup"><span data-stu-id="4f60c-222">cpp</span></span>|
|<span data-ttu-id="4f60c-223">C++/CX</span><span class="sxs-lookup"><span data-stu-id="4f60c-223">C++/CX</span></span>|<span data-ttu-id="4f60c-224">cppcx</span><span class="sxs-lookup"><span data-stu-id="4f60c-224">cppcx</span></span>|
|<span data-ttu-id="4f60c-225">C++/WinRT</span><span class="sxs-lookup"><span data-stu-id="4f60c-225">C++/WinRT</span></span>|<span data-ttu-id="4f60c-226">cppwinrt</span><span class="sxs-lookup"><span data-stu-id="4f60c-226">cppwinrt</span></span>|
|<span data-ttu-id="4f60c-227">C#</span><span class="sxs-lookup"><span data-stu-id="4f60c-227">C#</span></span>|<span data-ttu-id="4f60c-228">csharp</span><span class="sxs-lookup"><span data-stu-id="4f60c-228">csharp</span></span>|
|<span data-ttu-id="4f60c-229">C# en el explorador</span><span class="sxs-lookup"><span data-stu-id="4f60c-229">C# in browser</span></span>|<span data-ttu-id="4f60c-230">csharp-interactive</span><span class="sxs-lookup"><span data-stu-id="4f60c-230">csharp-interactive</span></span>|
|<span data-ttu-id="4f60c-231">Consola</span><span class="sxs-lookup"><span data-stu-id="4f60c-231">Console</span></span>|<span data-ttu-id="4f60c-232">consola</span><span class="sxs-lookup"><span data-stu-id="4f60c-232">console</span></span>|
|<span data-ttu-id="4f60c-233">CSHTML</span><span class="sxs-lookup"><span data-stu-id="4f60c-233">CSHTML</span></span>|<span data-ttu-id="4f60c-234">cshtml</span><span class="sxs-lookup"><span data-stu-id="4f60c-234">cshtml</span></span>|
|<span data-ttu-id="4f60c-235">DAX</span><span class="sxs-lookup"><span data-stu-id="4f60c-235">DAX</span></span>|<span data-ttu-id="4f60c-236">dax</span><span class="sxs-lookup"><span data-stu-id="4f60c-236">dax</span></span>|
|<span data-ttu-id="4f60c-237">F#</span><span class="sxs-lookup"><span data-stu-id="4f60c-237">F#</span></span>|<span data-ttu-id="4f60c-238">fsharp</span><span class="sxs-lookup"><span data-stu-id="4f60c-238">fsharp</span></span>|
|<span data-ttu-id="4f60c-239">Go</span><span class="sxs-lookup"><span data-stu-id="4f60c-239">Go</span></span>|<span data-ttu-id="4f60c-240">go</span><span class="sxs-lookup"><span data-stu-id="4f60c-240">go</span></span>|
|<span data-ttu-id="4f60c-241">HTML</span><span class="sxs-lookup"><span data-stu-id="4f60c-241">HTML</span></span>|<span data-ttu-id="4f60c-242">html</span><span class="sxs-lookup"><span data-stu-id="4f60c-242">html</span></span>|
|<span data-ttu-id="4f60c-243">HTTP</span><span class="sxs-lookup"><span data-stu-id="4f60c-243">HTTP</span></span>|<span data-ttu-id="4f60c-244">http</span><span class="sxs-lookup"><span data-stu-id="4f60c-244">http</span></span>|
|<span data-ttu-id="4f60c-245">Java</span><span class="sxs-lookup"><span data-stu-id="4f60c-245">Java</span></span>|<span data-ttu-id="4f60c-246">java</span><span class="sxs-lookup"><span data-stu-id="4f60c-246">java</span></span>|
|<span data-ttu-id="4f60c-247">JavaScript</span><span class="sxs-lookup"><span data-stu-id="4f60c-247">JavaScript</span></span>|<span data-ttu-id="4f60c-248">javascript</span><span class="sxs-lookup"><span data-stu-id="4f60c-248">javascript</span></span>|
|<span data-ttu-id="4f60c-249">JSON</span><span class="sxs-lookup"><span data-stu-id="4f60c-249">JSON</span></span>|<span data-ttu-id="4f60c-250">json</span><span class="sxs-lookup"><span data-stu-id="4f60c-250">json</span></span>|
|<span data-ttu-id="4f60c-251">Markdown</span><span class="sxs-lookup"><span data-stu-id="4f60c-251">Markdown</span></span>|<span data-ttu-id="4f60c-252">md</span><span class="sxs-lookup"><span data-stu-id="4f60c-252">md</span></span>|
|<span data-ttu-id="4f60c-253">NodeJS</span><span class="sxs-lookup"><span data-stu-id="4f60c-253">NodeJS</span></span>|<span data-ttu-id="4f60c-254">nodejs</span><span class="sxs-lookup"><span data-stu-id="4f60c-254">nodejs</span></span>|
|<span data-ttu-id="4f60c-255">Objective-C</span><span class="sxs-lookup"><span data-stu-id="4f60c-255">Objective-C</span></span>|<span data-ttu-id="4f60c-256">objc</span><span class="sxs-lookup"><span data-stu-id="4f60c-256">objc</span></span>|
|<span data-ttu-id="4f60c-257">OData</span><span class="sxs-lookup"><span data-stu-id="4f60c-257">OData</span></span>|<span data-ttu-id="4f60c-258">odata</span><span class="sxs-lookup"><span data-stu-id="4f60c-258">odata</span></span>|
|<span data-ttu-id="4f60c-259">PHP</span><span class="sxs-lookup"><span data-stu-id="4f60c-259">PHP</span></span>|<span data-ttu-id="4f60c-260">php</span><span class="sxs-lookup"><span data-stu-id="4f60c-260">php</span></span>|
|<span data-ttu-id="4f60c-261">Power Apps Formula</span><span class="sxs-lookup"><span data-stu-id="4f60c-261">Power Apps Formula</span></span>|<span data-ttu-id="4f60c-262">powerappsfl</span><span class="sxs-lookup"><span data-stu-id="4f60c-262">powerappsfl</span></span>|
|<span data-ttu-id="4f60c-263">PowerShell</span><span class="sxs-lookup"><span data-stu-id="4f60c-263">PowerShell</span></span>|<span data-ttu-id="4f60c-264">powershell</span><span class="sxs-lookup"><span data-stu-id="4f60c-264">powershell</span></span>|
|<span data-ttu-id="4f60c-265">Python</span><span class="sxs-lookup"><span data-stu-id="4f60c-265">Python</span></span>|<span data-ttu-id="4f60c-266">python</span><span class="sxs-lookup"><span data-stu-id="4f60c-266">python</span></span>|
|<span data-ttu-id="4f60c-267">Q#</span><span class="sxs-lookup"><span data-stu-id="4f60c-267">Q#</span></span>|<span data-ttu-id="4f60c-268">qsharp</span><span class="sxs-lookup"><span data-stu-id="4f60c-268">qsharp</span></span>|
|<span data-ttu-id="4f60c-269">R</span><span class="sxs-lookup"><span data-stu-id="4f60c-269">R</span></span>|<span data-ttu-id="4f60c-270">r</span><span class="sxs-lookup"><span data-stu-id="4f60c-270">r</span></span>|
|<span data-ttu-id="4f60c-271">Ruby</span><span class="sxs-lookup"><span data-stu-id="4f60c-271">Ruby</span></span>|<span data-ttu-id="4f60c-272">ruby</span><span class="sxs-lookup"><span data-stu-id="4f60c-272">ruby</span></span>|
|<span data-ttu-id="4f60c-273">SQL</span><span class="sxs-lookup"><span data-stu-id="4f60c-273">SQL</span></span>|<span data-ttu-id="4f60c-274">sql</span><span class="sxs-lookup"><span data-stu-id="4f60c-274">sql</span></span>|
|<span data-ttu-id="4f60c-275">Swift</span><span class="sxs-lookup"><span data-stu-id="4f60c-275">Swift</span></span>|<span data-ttu-id="4f60c-276">swift</span><span class="sxs-lookup"><span data-stu-id="4f60c-276">swift</span></span>|
|<span data-ttu-id="4f60c-277">TypeScript</span><span class="sxs-lookup"><span data-stu-id="4f60c-277">TypeScript</span></span>|<span data-ttu-id="4f60c-278">typescript</span><span class="sxs-lookup"><span data-stu-id="4f60c-278">typescript</span></span>|
|<span data-ttu-id="4f60c-279">VB</span><span class="sxs-lookup"><span data-stu-id="4f60c-279">VB</span></span>|<span data-ttu-id="4f60c-280">vb</span><span class="sxs-lookup"><span data-stu-id="4f60c-280">vb</span></span>|
|<span data-ttu-id="4f60c-281">VSTS CLI</span><span class="sxs-lookup"><span data-stu-id="4f60c-281">VSTS CLI</span></span>|<span data-ttu-id="4f60c-282">vstscli</span><span class="sxs-lookup"><span data-stu-id="4f60c-282">vstscli</span></span>|
|<span data-ttu-id="4f60c-283">XAML</span><span class="sxs-lookup"><span data-stu-id="4f60c-283">XAML</span></span>|<span data-ttu-id="4f60c-284">xaml</span><span class="sxs-lookup"><span data-stu-id="4f60c-284">xaml</span></span>|
|<span data-ttu-id="4f60c-285">XML</span><span class="sxs-lookup"><span data-stu-id="4f60c-285">XML</span></span>|<span data-ttu-id="4f60c-286">xml</span><span class="sxs-lookup"><span data-stu-id="4f60c-286">xml</span></span>|

<span data-ttu-id="4f60c-287">El nombre `csharp-interactive` especifica el lenguaje C#, y la capacidad de ejecutar los ejemplos desde el explorador.</span><span class="sxs-lookup"><span data-stu-id="4f60c-287">The `csharp-interactive` name specifies the C# language, and the ability to run the samples from the browser.</span></span> <span data-ttu-id="4f60c-288">Estos fragmentos de código se compilan y ejecutan en un contenedor de Docker, y los resultados de la ejecución del programa se muestran en la ventana del explorador del usuario.</span><span class="sxs-lookup"><span data-stu-id="4f60c-288">These snippets are compiled and executed in a Docker container, and the results of that program execution are displayed in the user's browser window.</span></span>

#### <a name="example-c"></a><span data-ttu-id="4f60c-289">Ejemplo: C\#</span><span class="sxs-lookup"><span data-stu-id="4f60c-289">Example: C\#</span></span>

<span data-ttu-id="4f60c-290">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="4f60c-290">__Markdown__</span></span>

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

<span data-ttu-id="4f60c-291">__Representación__</span><span class="sxs-lookup"><span data-stu-id="4f60c-291">__Render__</span></span>

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

#### <a name="example-sql"></a><span data-ttu-id="4f60c-292">Ejemplo: SQL</span><span class="sxs-lookup"><span data-stu-id="4f60c-292">Example: SQL</span></span>

<span data-ttu-id="4f60c-293">__Markdown__</span><span class="sxs-lookup"><span data-stu-id="4f60c-293">__Markdown__</span></span>

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

<span data-ttu-id="4f60c-294">__Representación__</span><span class="sxs-lookup"><span data-stu-id="4f60c-294">__Render__</span></span>

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a><span data-ttu-id="4f60c-295">Extensiones de Markdown personalizadas para OPS</span><span class="sxs-lookup"><span data-stu-id="4f60c-295">OPS custom Markdown extensions</span></span>

> [!NOTE]
> <span data-ttu-id="4f60c-296">La plataforma de Servicios de publicación abierta (OPS) implementa Markdig Parser para Markdown, que ofrece una alta compatibilidad con GitHub Flavored Markdown (GFM).</span><span class="sxs-lookup"><span data-stu-id="4f60c-296">Open Publishing Services (OPS) implements a Markdig Parser for Markdown, which is highly compatible with GitHub Flavored Markdown (GFM).</span></span> <span data-ttu-id="4f60c-297">Markdig agrega algunas funcionalidades a través de extensiones de Markdown.</span><span class="sxs-lookup"><span data-stu-id="4f60c-297">Markdig adds some functionality through Markdown extensions.</span></span> <span data-ttu-id="4f60c-298">Por tanto, determinados artículos de la guía completa de creación de OPS se han incluido en esta guía a efectos de referencia.</span><span class="sxs-lookup"><span data-stu-id="4f60c-298">As such, selected articles from the full OPS Authoring Guide are included in this guide for reference.</span></span> <span data-ttu-id="4f60c-299">Por ejemplo, vea "Markdig and Markdown extensions" (Markdig y extensiones de Markdown) y "Code snippets" (Fragmentos de código) en la tabla de contenido.</span><span class="sxs-lookup"><span data-stu-id="4f60c-299">(For example, see "Markdig and Markdown extensions" and "Code snippets" in the table of contents.)</span></span>

<span data-ttu-id="4f60c-300">Los artículos de Docs usan GFM para aplicar formato a la mayoría de los artículos, como párrafos, vínculos, listas y encabezados.</span><span class="sxs-lookup"><span data-stu-id="4f60c-300">Docs articles use GFM for most article formatting, such as paragraphs, links, lists, and headings.</span></span> <span data-ttu-id="4f60c-301">Para un formato más enriquecido, los artículos pueden usar características de Markdig como:</span><span class="sxs-lookup"><span data-stu-id="4f60c-301">For richer formatting, articles can use Markdig features such as:</span></span>

- <span data-ttu-id="4f60c-302">Bloques de notas</span><span class="sxs-lookup"><span data-stu-id="4f60c-302">Note blocks</span></span>
- <span data-ttu-id="4f60c-303">Archivos de inclusión</span><span class="sxs-lookup"><span data-stu-id="4f60c-303">Includes</span></span>
- <span data-ttu-id="4f60c-304">Selectores</span><span class="sxs-lookup"><span data-stu-id="4f60c-304">Selectors</span></span>
- <span data-ttu-id="4f60c-305">Vídeos insertados</span><span class="sxs-lookup"><span data-stu-id="4f60c-305">Embedded videos</span></span>
- <span data-ttu-id="4f60c-306">Ejemplos y fragmentos de código</span><span class="sxs-lookup"><span data-stu-id="4f60c-306">Code snippets/samples</span></span>

<span data-ttu-id="4f60c-307">Para obtener una lista completa, vea "Markdig and Markdown extensions" (Markdig y extensiones de Markdown) y "Code snippets" (Fragmentos de código) en la tabla de contenido.</span><span class="sxs-lookup"><span data-stu-id="4f60c-307">For the complete list, refer to "Markdig and Markdown extensions" and "Code snippets" in the table of contents.</span></span>

### <a name="note-blocks"></a><span data-ttu-id="4f60c-308">Bloques de notas</span><span class="sxs-lookup"><span data-stu-id="4f60c-308">Note blocks</span></span>

<span data-ttu-id="4f60c-309">Puede elegir entre cuatro tipos de bloques de notas para centrar la atención en contenido específico:</span><span class="sxs-lookup"><span data-stu-id="4f60c-309">You can choose from four types of note blocks to draw attention to specific content:</span></span>

- <span data-ttu-id="4f60c-310">NOTA</span><span class="sxs-lookup"><span data-stu-id="4f60c-310">NOTE</span></span>
- <span data-ttu-id="4f60c-311">ADVERTENCIA</span><span class="sxs-lookup"><span data-stu-id="4f60c-311">WARNING</span></span>
- <span data-ttu-id="4f60c-312">SUGERENCIA</span><span class="sxs-lookup"><span data-stu-id="4f60c-312">TIP</span></span>
- <span data-ttu-id="4f60c-313">IMPORTANTE</span><span class="sxs-lookup"><span data-stu-id="4f60c-313">IMPORTANT</span></span>

<span data-ttu-id="4f60c-314">En general, los bloques de notas deben usarse con moderación porque pueden ser problemáticos.</span><span class="sxs-lookup"><span data-stu-id="4f60c-314">In general, note blocks should be used sparingly because they can be disruptive.</span></span> <span data-ttu-id="4f60c-315">Aunque también admiten bloques de código, imágenes, listas y vínculos, trate de mantener los bloques de notas sencillos y directos.</span><span class="sxs-lookup"><span data-stu-id="4f60c-315">Although they also support code blocks, images, lists, and links, try to keep your note blocks simple and straightforward.</span></span>

<span data-ttu-id="4f60c-316">Ejemplos:</span><span class="sxs-lookup"><span data-stu-id="4f60c-316">Examples:</span></span>

```markdown
> [!NOTE]
> This is a NOTE

> [!WARNING]
> This is a WARNING

> [!TIP]
> This is a TIP

> [!IMPORTANT]
> This is IMPORTANT
```

<span data-ttu-id="4f60c-317">Se representan de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4f60c-317">These render as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="4f60c-318">Esto es una NOTA</span><span class="sxs-lookup"><span data-stu-id="4f60c-318">This is a NOTE</span></span>

> [!WARNING]
> <span data-ttu-id="4f60c-319">Esto es una ADVERTENCIA</span><span class="sxs-lookup"><span data-stu-id="4f60c-319">This is a WARNING</span></span>

> [!TIP]
> <span data-ttu-id="4f60c-320">Esto es una SUGERENCIA</span><span class="sxs-lookup"><span data-stu-id="4f60c-320">This is a TIP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4f60c-321">Esto es IMPORTANTE</span><span class="sxs-lookup"><span data-stu-id="4f60c-321">This is IMPORTANT</span></span>

### <a name="includes"></a><span data-ttu-id="4f60c-322">Archivos de inclusión</span><span class="sxs-lookup"><span data-stu-id="4f60c-322">Includes</span></span>

<span data-ttu-id="4f60c-323">Si tiene archivos de texto o imagen reutilizables que deben incluirse en archivos de artículos, puede usar una referencia al archivo "de inclusión" a través de la característica de inclusión de archivos de Markdig.</span><span class="sxs-lookup"><span data-stu-id="4f60c-323">When you have reusable text or image files that need to be included in article files, you can use a reference to the "include" file via the Markdig file include feature.</span></span> <span data-ttu-id="4f60c-324">Esta característica da la orden a OPS para que incluya el archivo en el archivo del artículo en el momento de la compilación, con lo que se convierte en una parte del artículo publicado.</span><span class="sxs-lookup"><span data-stu-id="4f60c-324">This feature instructs OPS to include the file in your article file at build time, making it part of your published article.</span></span> <span data-ttu-id="4f60c-325">Hay tres tipos de archivos de inclusión disponibles para facilitar la reutilización del contenido:</span><span class="sxs-lookup"><span data-stu-id="4f60c-325">Three types of includes are available to help you reuse content:</span></span>

- <span data-ttu-id="4f60c-326">Insertado: reutiliza fragmentos de texto comunes insertados en otra oración.</span><span class="sxs-lookup"><span data-stu-id="4f60c-326">Inline: Reuse a common text snippet inline with within another sentence.</span></span>
- <span data-ttu-id="4f60c-327">Bloque: reutiliza un archivo Markdown completo como un bloque, anidado en una sección de un artículo.</span><span class="sxs-lookup"><span data-stu-id="4f60c-327">Block: Reuse an entire Markdown file as a block, nested within a section of an article.</span></span>
- <span data-ttu-id="4f60c-328">Imágenes: se trata de la forma en que se implementa la inclusión de imágenes estándar en Docs.</span><span class="sxs-lookup"><span data-stu-id="4f60c-328">Image: This is how standard image inclusion is implemented in Docs.</span></span>

<span data-ttu-id="4f60c-329">Los archivos de inclusión insertados y en bloque no son más que un archivo Markdown (.md) sencillo.</span><span class="sxs-lookup"><span data-stu-id="4f60c-329">An inline or block include is just a simple Markdown (.md) file.</span></span> <span data-ttu-id="4f60c-330">Pueden contener cualquier archivo Markdown válido.</span><span class="sxs-lookup"><span data-stu-id="4f60c-330">It can contain any valid Markdown.</span></span> <span data-ttu-id="4f60c-331">Todos los archivos de inclusión Markdown deben colocarse en un [subdirectorio `/includes` común](git-github-fundamentals.md#includes-subdirectory), en la raíz del repositorio.</span><span class="sxs-lookup"><span data-stu-id="4f60c-331">All include Markdown files should be placed in a [common `/includes` subdirectory](git-github-fundamentals.md#includes-subdirectory), in the root of the repository.</span></span> <span data-ttu-id="4f60c-332">Cuando se publica el artículo, el archivo incluido se integra perfectamente en él.</span><span class="sxs-lookup"><span data-stu-id="4f60c-332">When the article is published, the included file is seamlessly integrated into it.</span></span>

<span data-ttu-id="4f60c-333">A continuación se indican requisitos y consideraciones relacionados con los archivos de inclusión:</span><span class="sxs-lookup"><span data-stu-id="4f60c-333">Here are requirements and considerations for includes:</span></span>

- <span data-ttu-id="4f60c-334">Use archivos de inclusión siempre que necesite que el mismo texto aparezca en varios artículos.</span><span class="sxs-lookup"><span data-stu-id="4f60c-334">Use includes whenever you need the same text to appear in multiple articles.</span></span>
- <span data-ttu-id="4f60c-335">Use archivos de inclusión en bloque con volúmenes grandes de contenido, como un párrafo o dos, un procedimiento compartido o una sección compartida.</span><span class="sxs-lookup"><span data-stu-id="4f60c-335">Use block includes for significant amounts of content--a paragraph or two, a shared procedure, or a shared section.</span></span> <span data-ttu-id="4f60c-336">No los use para una unidad inferior a una oración.</span><span class="sxs-lookup"><span data-stu-id="4f60c-336">Do not use them for anything smaller than a sentence.</span></span>
- <span data-ttu-id="4f60c-337">Los archivos de inclusión no se representarán en la vista representada del artículo en GitHub, porque se basan en las extensiones de Markdig.</span><span class="sxs-lookup"><span data-stu-id="4f60c-337">Includes won't be rendered in the GitHub rendered view of your article, because they rely on Markdig extensions.</span></span> <span data-ttu-id="4f60c-338">Se representarán después de la publicación.</span><span class="sxs-lookup"><span data-stu-id="4f60c-338">They'll be rendered only after publication.</span></span>
- <span data-ttu-id="4f60c-339">Asegúrese de que todo el texto de un archivo de inclusión se escribe en oraciones o frases completas que no dependen del texto anterior o del texto siguiente del artículo al que hace referencia el archivo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="4f60c-339">Ensure that all the text in an include is written in complete sentences or phrases that do not depend on preceding text or following text in the article that references the include.</span></span> <span data-ttu-id="4f60c-340">Si ignora esta instrucción, se crea una cadena no traducible en el artículo que rompe la experiencia localizada.</span><span class="sxs-lookup"><span data-stu-id="4f60c-340">Ignoring this guidance creates an untranslatable string in the article that breaks the localized experience.</span></span>
- <span data-ttu-id="4f60c-341">No inserte archivos de inclusión en otros archivos de inclusión.</span><span class="sxs-lookup"><span data-stu-id="4f60c-341">Don't embed includes within other includes.</span></span> <span data-ttu-id="4f60c-342">No son compatibles.</span><span class="sxs-lookup"><span data-stu-id="4f60c-342">They are not supported.</span></span>
- <span data-ttu-id="4f60c-343">Coloque los archivos multimedia en una carpeta de medios específica del subdirectorio de archivos de inclusión, por ejemplo, la carpeta `<repo>`/includes/media.</span><span class="sxs-lookup"><span data-stu-id="4f60c-343">Place media files in a media folder that's specific to the include subdirectory--for instance, the `<repo>`/includes/media folder.</span></span> <span data-ttu-id="4f60c-344">El directorio multimedia no debe contener ninguna imagen en su raíz.</span><span class="sxs-lookup"><span data-stu-id="4f60c-344">The media directory should not contain any images in its root.</span></span> <span data-ttu-id="4f60c-345">Si el archivo de inclusión no tiene imágenes, no se necesita un directorio multimedia correspondiente.</span><span class="sxs-lookup"><span data-stu-id="4f60c-345">If the include does not have images, a corresponding media directory is not required.</span></span>
- <span data-ttu-id="4f60c-346">Como sucede con los artículos habituales, no comparta contenido multimedia entre los archivos de inclusión.</span><span class="sxs-lookup"><span data-stu-id="4f60c-346">As with regular articles, don't share media between include files.</span></span> <span data-ttu-id="4f60c-347">Use un archivo independiente con un nombre exclusivo para cada archivo de inclusión y cada artículo.</span><span class="sxs-lookup"><span data-stu-id="4f60c-347">Use a separate file with a unique name for each include and article.</span></span> <span data-ttu-id="4f60c-348">Almacene el archivo multimedia en la carpeta de medios asociada con el archivo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="4f60c-348">Store the media file in the media folder that's associated with the include.</span></span>
- <span data-ttu-id="4f60c-349">No use un archivo de inclusión como el único contenido de un artículo.</span><span class="sxs-lookup"><span data-stu-id="4f60c-349">Don't use an include as the only content of an article.</span></span>  <span data-ttu-id="4f60c-350">Se supone que los archivos de inclusión deben ser complementarios al contenido del resto del artículo.</span><span class="sxs-lookup"><span data-stu-id="4f60c-350">Includes are meant to be supplemental to the content in the rest of the article.</span></span>

<span data-ttu-id="4f60c-351">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4f60c-351">Example:</span></span>

```markdown
[!INCLUDE[sample include file](../includes/sampleinclude.md)]
```

### <a name="selectors"></a><span data-ttu-id="4f60c-352">Selectores</span><span class="sxs-lookup"><span data-stu-id="4f60c-352">Selectors</span></span>

<span data-ttu-id="4f60c-353">Use los selectores en los artículos técnicos cuando cree varias versiones del mismo artículo, a fin de solucionar las diferencias de implementación entre tecnologías o plataformas.</span><span class="sxs-lookup"><span data-stu-id="4f60c-353">Use selectors in technical articles when you author multiple flavors of the same article, to  address differences in implementation across technologies or platforms.</span></span> <span data-ttu-id="4f60c-354">Esto suele aplicarse sobre todo a nuestro contenido en de plataformas móviles destinado a desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="4f60c-354">This is typically most applicable to our mobile platform content for developers.</span></span> <span data-ttu-id="4f60c-355">Actualmente hay dos tipos diferentes de selectores en Markdig, un selector único y un selector múltiple.</span><span class="sxs-lookup"><span data-stu-id="4f60c-355">There are currently two different types of selectors in Markdig, a single selector and a multi-selector.</span></span>

<span data-ttu-id="4f60c-356">Como se coloca el mismo selector de Markdown en cada artículo de la selección, se recomienda colocar el selector del artículo en un archivo de inclusión.</span><span class="sxs-lookup"><span data-stu-id="4f60c-356">Because the same selector Markdown goes in each article in the selection, we recommend placing the selector for your article in an include.</span></span> <span data-ttu-id="4f60c-357">Después, puede hacer referencia a dicho archivo de inclusión en todos los artículos que usan el mismo selector.</span><span class="sxs-lookup"><span data-stu-id="4f60c-357">Then you can reference that include in all your articles that use the same selector.</span></span>

<span data-ttu-id="4f60c-358">A continuación se muestra un selector de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4f60c-358">The following shows an example selector:</span></span>

```markdown
> [!div class="op_single_selector"]
- [macOS](../docs/core/tutorials/using-on-macos.md)
- [Windows](../docs/core/tutorials/with-visual-studio.md)
```

<span data-ttu-id="4f60c-359">Puede ver un ejemplo de los selectores en acción en la [documentación de Azure](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span><span class="sxs-lookup"><span data-stu-id="4f60c-359">You can see an example of selectors in action at the [Azure docs](https://docs.microsoft.com/azure/expressroute/expressroute-howto-circuit-classic).</span></span>

### <a name="code-includes"></a><span data-ttu-id="4f60c-360">Inclusiones de código</span><span class="sxs-lookup"><span data-stu-id="4f60c-360">Code includes</span></span>

<span data-ttu-id="4f60c-361">Markdig admite la inclusión avanzada de código en un artículo, a través de su extensión de fragmento de código.</span><span class="sxs-lookup"><span data-stu-id="4f60c-361">Markdig supports advanced inclusion of code in an article, via its code snippet extension.</span></span> <span data-ttu-id="4f60c-362">Proporciona una representación avanzada basada en las características de GFM, como la selección del lenguaje de programación y el color de sintaxis, además de características útiles como:</span><span class="sxs-lookup"><span data-stu-id="4f60c-362">It provides advanced rendering that builds on GFM features such as programming language selection and syntax coloring, plus nice features such as:</span></span>

- <span data-ttu-id="4f60c-363">Inclusión de fragmentos y muestras de código centralizados desde un repositorio externo.</span><span class="sxs-lookup"><span data-stu-id="4f60c-363">Inclusion of centralized code samples/snippets from an external repository.</span></span>
- <span data-ttu-id="4f60c-364">Interfaz de usuario con pestañas para mostrar varias versiones de ejemplos de código en diferentes lenguajes.</span><span class="sxs-lookup"><span data-stu-id="4f60c-364">Tabbed UI to show multiple versions of code samples in different languages.</span></span>

## <a name="gotchas-and-troubleshooting"></a><span data-ttu-id="4f60c-365">Dificultades y solución de problemas</span><span class="sxs-lookup"><span data-stu-id="4f60c-365">Gotchas and troubleshooting</span></span>

### <a name="alt-text"></a><span data-ttu-id="4f60c-366">Texto alternativo</span><span class="sxs-lookup"><span data-stu-id="4f60c-366">Alt text</span></span>

<span data-ttu-id="4f60c-367">El texto alternativo que contiene guiones bajos no se procesa correctamente.</span><span class="sxs-lookup"><span data-stu-id="4f60c-367">Alt text that contains underscores won't be rendered properly.</span></span> <span data-ttu-id="4f60c-368">Por ejemplo, en lugar de usar esto:</span><span class="sxs-lookup"><span data-stu-id="4f60c-368">For example, instead of using this:</span></span>

```markdown
![ADextension_2FA_Configure_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

<span data-ttu-id="4f60c-369">Incluya una secuencia de escape de guiones bajos como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="4f60c-369">Escape the underscores like this:</span></span>

```markdown
![ADextension\_2FA\_Configure\_Step4](./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a><span data-ttu-id="4f60c-370">Apóstrofos y comillas</span><span class="sxs-lookup"><span data-stu-id="4f60c-370">Apostrophes and quotation marks</span></span>

<span data-ttu-id="4f60c-371">Si copia texto de Word en Markdown editor, el texto debe contener apóstrofos o comillas (inglesas) "inteligentes".</span><span class="sxs-lookup"><span data-stu-id="4f60c-371">If you copy from Word into a Markdown editor, the text might contain "smart" (curly) apostrophes or quotation marks.</span></span> <span data-ttu-id="4f60c-372">Es necesario codificarlos o bien cambiarlos a apóstrofos o comillas básicos.</span><span class="sxs-lookup"><span data-stu-id="4f60c-372">These need to be encoded or changed to basic apostrophes or quotation marks.</span></span> <span data-ttu-id="4f60c-373">De lo contrario, cuando se publique el archivo, aparecerán cosas como esta: Itâ€™s</span><span class="sxs-lookup"><span data-stu-id="4f60c-373">Otherwise, you end up with things like this when the file is published: Itâ€™s</span></span>

<span data-ttu-id="4f60c-374">A continuación se especifica la codificación para las versiones "inteligentes" de estos signos de puntuación:</span><span class="sxs-lookup"><span data-stu-id="4f60c-374">Here are the encodings for the "smart" versions of these punctuation marks:</span></span>

- <span data-ttu-id="4f60c-375">Comilla izquierda de apertura: `&#8220;`</span><span class="sxs-lookup"><span data-stu-id="4f60c-375">Left (opening) quotation mark: `&#8220;`</span></span>
- <span data-ttu-id="4f60c-376">Comilla derecha de cierre: `&#8221;`</span><span class="sxs-lookup"><span data-stu-id="4f60c-376">Right (closing) quotation mark: `&#8221;`</span></span>
- <span data-ttu-id="4f60c-377">Apóstrofo o comilla simple derecha de cierre: `&#8217;`</span><span class="sxs-lookup"><span data-stu-id="4f60c-377">Right (closing) single quotation mark or apostrophe: `&#8217;`</span></span>
- <span data-ttu-id="4f60c-378">Comilla simple izquierda de apertura (uso poco común): `&#8216;`</span><span class="sxs-lookup"><span data-stu-id="4f60c-378">Left (opening) single quotation mark (rarely used): `&#8216;`</span></span>

### <a name="angle-brackets"></a><span data-ttu-id="4f60c-379">Corchetes angulares</span><span class="sxs-lookup"><span data-stu-id="4f60c-379">Angle brackets</span></span>

<span data-ttu-id="4f60c-380">Es habitual usar corchetes angulares para indicar un marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="4f60c-380">It is common to use angle brackets to denote a placeholder.</span></span> <span data-ttu-id="4f60c-381">Cuando lo haga en el texto (no en el código), tendrá que codificar los corchetes angulares.</span><span class="sxs-lookup"><span data-stu-id="4f60c-381">When you do this in text (not code), you must encode the angle brackets.</span></span> <span data-ttu-id="4f60c-382">De lo contrario, Markdown considera que se han insertado como una etiqueta HTML.</span><span class="sxs-lookup"><span data-stu-id="4f60c-382">Otherwise, Markdown thinks that they're intended to be an HTML tag.</span></span>

<span data-ttu-id="4f60c-383">Por ejemplo, codifique `<script name>` como `&lt;script name&gt;`.</span><span class="sxs-lookup"><span data-stu-id="4f60c-383">For example, encode `<script name>` as `&lt;script name&gt;`</span></span>

## <a name="see-also"></a><span data-ttu-id="4f60c-384">Vea también:</span><span class="sxs-lookup"><span data-stu-id="4f60c-384">See also:</span></span>

### <a name="markdown-resources"></a><span data-ttu-id="4f60c-385">Recursos de Markdown</span><span class="sxs-lookup"><span data-stu-id="4f60c-385">Markdown resources</span></span>

- [<span data-ttu-id="4f60c-386">Introducción a Markdown</span><span class="sxs-lookup"><span data-stu-id="4f60c-386">Introduction to Markdown</span></span>](https://daringfireball.net/projects/markdown/syntax)
- [<span data-ttu-id="4f60c-387">Hoja de referencia rápida sobre Markdown para Docs</span><span class="sxs-lookup"><span data-stu-id="4f60c-387">Docs Markdown cheat sheet</span></span>](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [<span data-ttu-id="4f60c-388">Aspectos básicos de Markdown en GitHub</span><span class="sxs-lookup"><span data-stu-id="4f60c-388">GitHub's Markdown Basics</span></span>](https://help.github.com/articles/markdown-basics/)
- [<span data-ttu-id="4f60c-389">La guía de Markdown</span><span class="sxs-lookup"><span data-stu-id="4f60c-389">The Markdown Guide</span></span>](https://www.markdownguide.org/)
