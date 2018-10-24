---
title: Encabezados de Markdown
description: Describe los requisitos para los encabezados de Markdown.
author: meganbradley
ms.author: mbradley
ms.topic: error-reference
ms.date: 05/03/2017
ms.openlocfilehash: 18beb815fdf7caad3e8e675e8d79853d8a5688f2
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084564"
---
# <a name="markdown-headings"></a><span data-ttu-id="2e58d-103">Encabezados de Markdown</span><span class="sxs-lookup"><span data-stu-id="2e58d-103">Markdown headings</span></span>

<span data-ttu-id="2e58d-104">Los siguientes requisitos de validación se aplican a los encabezados en los archivos Markdown de OPS.</span><span class="sxs-lookup"><span data-stu-id="2e58d-104">The following validation requirements apply to headings in OPS Markdown files.</span></span>

## <a name="h1"></a><span data-ttu-id="2e58d-105">H1</span><span class="sxs-lookup"><span data-stu-id="2e58d-105">H1</span></span>

<span data-ttu-id="2e58d-106">`H1` hace referencia al primer encabezado de un archivo Markdown.</span><span class="sxs-lookup"><span data-stu-id="2e58d-106">`H1` refers to the first heading in a Markdown file.</span></span> <span data-ttu-id="2e58d-107">Al publicarse en docs.microsoft.com, H1 se muestra en la parte superior de la página en una fuente grande.</span><span class="sxs-lookup"><span data-stu-id="2e58d-107">When published to docs.microsoft.com, the H1 shows at the top of the page in a large font.</span></span>

<span data-ttu-id="2e58d-108">Los H1 se crean empezando una línea con una almohadilla (`#`) seguida por un espacio y después el texto del título.</span><span class="sxs-lookup"><span data-stu-id="2e58d-108">An H1 is created by beginning a line with a single hash (`#`) followed by a space, then the heading text.</span></span> <span data-ttu-id="2e58d-109">Por ejemplo, el H1 de este artículo es:</span><span class="sxs-lookup"><span data-stu-id="2e58d-109">For example, the H1 of this article is:</span></span>

```md
# Markdown headings
```

<span data-ttu-id="2e58d-110">Las siguientes reglas se aplican a los títulos H1:</span><span class="sxs-lookup"><span data-stu-id="2e58d-110">The following rules apply to H1 headings:</span></span>

- <span data-ttu-id="2e58d-111">El archivo debe tener un H1.</span><span class="sxs-lookup"><span data-stu-id="2e58d-111">An H1 must be present in the file.</span></span>
- <span data-ttu-id="2e58d-112">Solo puede haber un H1.</span><span class="sxs-lookup"><span data-stu-id="2e58d-112">There can only be one H1.</span></span>
- <span data-ttu-id="2e58d-113">El H1 debe tener contenido.</span><span class="sxs-lookup"><span data-stu-id="2e58d-113">The H1 must have content.</span></span>

  ```markdown
  # 
  This is not allowed.
  ```
- <span data-ttu-id="2e58d-114">Debe introducirse un espacio entre `#` y el contenido de H1.</span><span class="sxs-lookup"><span data-stu-id="2e58d-114">There must be a space between the `#` and the H1 content.</span></span> <span data-ttu-id="2e58d-115">Si no se introduce el espacio en H1, no se representará como un título en la página una vez publicada.</span><span class="sxs-lookup"><span data-stu-id="2e58d-115">An H1 with no space doesn't render as a heading on the published page.</span></span>

  ```markdown
  #This looks bad on the site.
  ```
- <span data-ttu-id="2e58d-116">El H1 debe ser el primer contenido del archivo después del encabezado de metadatos YML.</span><span class="sxs-lookup"><span data-stu-id="2e58d-116">The H1 must be the first content in the file after the YML metadata header.</span></span> <span data-ttu-id="2e58d-117">No se puede introducir contenido como texto o imágenes entre el fin del encabezado YML y H1.</span><span class="sxs-lookup"><span data-stu-id="2e58d-117">No content, such as text or images, is allowed between the end of the YML header and the H1.</span></span>

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- <span data-ttu-id="2e58d-118">El elemento HTML no se puede utilizar en los títulos de primer nivel, `<h1>`.</span><span class="sxs-lookup"><span data-stu-id="2e58d-118">The HTML element for first-level headings, `<h1>`, should not be used.</span></span> <span data-ttu-id="2e58d-119">Use la sintaxis de Markdown (`# `).</span><span class="sxs-lookup"><span data-stu-id="2e58d-119">Use the Markdown syntax (`# `).</span></span>
- <span data-ttu-id="2e58d-120">H1 no puede tener más de 100 caracteres de longitud.</span><span class="sxs-lookup"><span data-stu-id="2e58d-120">The H1 should be no more than 100 characters long.</span></span> <span data-ttu-id="2e58d-121">Esto es una directriz de estilo.</span><span class="sxs-lookup"><span data-stu-id="2e58d-121">This is a style guideline.</span></span>

## <a name="h2---h6"></a><span data-ttu-id="2e58d-122">H2 - H6</span><span class="sxs-lookup"><span data-stu-id="2e58d-122">H2 - H6</span></span>

<span data-ttu-id="2e58d-123">En OPS se admiten los títulos de H2 (`## `) a H6 (`###### `).</span><span class="sxs-lookup"><span data-stu-id="2e58d-123">H2 (`## `) through H6 (`###### `) are allowed in OPS.</span></span> <span data-ttu-id="2e58d-124">Para crear títulos, use los encabezados de Markdown, no los de HTML (`<h2>` - `<h6>`).</span><span class="sxs-lookup"><span data-stu-id="2e58d-124">Use the Markdown headers, not the HTML (`<h2>` - `<h6>`), to create headings.</span></span>
