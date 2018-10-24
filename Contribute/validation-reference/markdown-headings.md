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
# <a name="markdown-headings"></a>Encabezados de Markdown

Los siguientes requisitos de validación se aplican a los encabezados en los archivos Markdown de OPS.

## <a name="h1"></a>H1

`H1` hace referencia al primer encabezado de un archivo Markdown. Al publicarse en docs.microsoft.com, H1 se muestra en la parte superior de la página en una fuente grande.

Los H1 se crean empezando una línea con una almohadilla (`#`) seguida por un espacio y después el texto del título. Por ejemplo, el H1 de este artículo es:

```md
# Markdown headings
```

Las siguientes reglas se aplican a los títulos H1:

- El archivo debe tener un H1.
- Solo puede haber un H1.
- El H1 debe tener contenido.

  ```markdown
  # 
  This is not allowed.
  ```
- Debe introducirse un espacio entre `#` y el contenido de H1. Si no se introduce el espacio en H1, no se representará como un título en la página una vez publicada.

  ```markdown
  #This looks bad on the site.
  ```
- El H1 debe ser el primer contenido del archivo después del encabezado de metadatos YML. No se puede introducir contenido como texto o imágenes entre el fin del encabezado YML y H1.

  ```markdown
  ---
  ... YML would go here
  ---
  ![cheerful image](not-allowed.jpg)
  # This cheer is not allowed
  ```
- El elemento HTML no se puede utilizar en los títulos de primer nivel, `<h1>`. Use la sintaxis de Markdown (`# `).
- H1 no puede tener más de 100 caracteres de longitud. Esto es una directriz de estilo.

## <a name="h2---h6"></a>H2 - H6

En OPS se admiten los títulos de H2 (`## `) a H6 (`###### `). Para crear títulos, use los encabezados de Markdown, no los de HTML (`<h2>` - `<h6>`).
