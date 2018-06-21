---
title: Instalación de herramientas de creación de contenido
description: Este artículo le ayuda a descargar e instalar las herramientas de cliente que necesitará para Git y la edición de archivos de Markdown.
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.date: 04/30/2018
ms.openlocfilehash: 00631485f1f4eed9e0de2f6df98d973a819dfe4d
ms.sourcegitcommit: 92aef5ea8bdd692c5c393d5c8f99b9e4f672ef2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238929"
---
# <a name="install-content-authoring-tools"></a>Instalación de herramientas de creación de contenido

En este artículo se describen los pasos para instalar de forma interactiva herramientas de cliente de Git y Visual Studio Code.
> [!div class="checklist"]
> * Instalación de [Git para Windows](https://git-scm.com/download/win)
> * Instalación de [Visual Studio Code](https://code.visualstudio.com/)
> * Instalación del [paquete de creación de Docs](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack)

>[!IMPORTANT]
> Si solo va a realizar cambios de menor importancia en un artículo, *no* necesita realizar todos los pasos del artículo y, por tanto, puede continuar directamente con el [flujo de trabajo para cambios rápidos](index.md#quick-edits-to-existing-documents).
>
> Se pide a los principales colaboradores que completen estos pasos, que le permiten usar el [flujo de trabajo de cambios mayores y de larga duración](how-to-write-workflows-major.md). Aunque disponga de permisos de escritura en el repositorio principal, *se recomienda encarecidamente que bifurque y clone el repositorio (y en esta guía se supone que así lo ha hecho)*, de manera que tendrá permisos de lectura y escritura para almacenar los cambios propuestos en la bifurcación.

## <a name="install-git-client-tools-on-windows"></a>Instalación de las herramientas de cliente para Git en Windows

 Instale la última versión de las [herramientas de cliente para Git de Software Freedom Conservancy](https://git-scm.com/download/). La instalación incluye el sistema de control de versiones de Git y Git Bash, la aplicación de línea de comandos que usa para interactuar con el repositorio de Git local.

Si prefiere una interfaz gráfica de usuario (GUI) en lugar de una interfaz de la línea de comandos (CLI), vea la [página de clientes de la GUI disponible de Software Freedom Conservancy](https://git-scm.com/downloads/guis), [GitHub Desktop de GitHub](https://desktop.github.com/) o [Visual Studio Code](https://www.visualstudio.com/products/code-vs.aspx) para consultar algunas opciones populares.

Siga las instrucciones de su cliente elegido para la instalación y configuración.

En el siguiente artículo, podrá [configurar un repositorio de Git local](get-started-setup-local.md).

   Aquí encontrará recursos adicionales de Git: [Git terminology](https://help.github.com/articles/github-glossary) (Terminología de Git) | [Git basics](https://git-scm.com/book/en/v2/Getting-Started-Git-Basics) (Conceptos básicos de Git) | [Learning Git and GitHub](https://help.github.com/articles/good-resources-for-learning-git-and-github/) (Información sobre Git y GitHub)

## <a name="understand-markdown-editors"></a>Descripción de los editores de Markdown

Markdown es un lenguaje de marcado ligero fácil de leer y de aprender. Por ello, se ha convertido rápidamente en un estándar del sector. Para escribir artículos en Markdown, se recomienda que primero descargue e instale Markdown editor.  [Visual Studio Code](https://code.visualstudio.com/) es la herramienta preferida para la edición de Markdown en Microsoft. [Atom](https://atom.io) es otra herramienta popular para la edición de Markdown.

El texto de Markdown se guarda en archivos con extensión .md.

La información adicional sobre cómo escribir con Markdown, incluidos los aspectos básicos y las características de Markdown compatibles con las extensiones de Markdown personalizadas para OPS, se proporciona más adelante en el artículo [Uso de Markdown](how-to-write-use-markdown.md).

## <a name="visual-studio-code"></a>Visual Studio Code

[Visual Studio Code](https://code.visualstudio.com/), también conocido como VS Code, es un editor ligero que funciona en Windows, Linux y Mac. Incluye integración de Git y compatibilidad con las extensiones.

Descargue e instale [VS Code](https://code.visualstudio.com/). La página principal de VS Code debería detectar correctamente el sistema operativo.

- [Windows](https://code.visualstudio.com/docs/setup/windows)
- [Mac](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)

> [!TIP]
> Para ejecutar VS Code y abrir la carpeta actual, ejecute el comando `code .` en la línea de comandos o el shell de bash. Si la carpeta actual forma parte de un repositorio de Git local, la integración de github aparece automáticamente en Visual Studio Code.

## <a name="docs-authoring-pack"></a>Paquete de creación de Docs
Instale el paquete de creación de Docs para Visual Studio Code. Este conjunto de extensiones incluye asistencia básica de creación para facilitar la escritura de Markdown, además de una característica de vista previa, para que pueda ver el aspecto de Markdown con el estilo del sitio docs.microsoft.com.

   Visite esta [página de Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) y seleccione **Install** (Instalar) o busque `docsmsft.docs-authoring-pack` en la lista de extensiones en la ventana de VS Code. 

   Presione Alt+M en VS Code para acceder al paquete de creación de Docs. La barra de herramientas está oculta de forma predeterminada, pero se puede mostrar. Edite la configuración de VS Code (Control+coma) y agregue los ajustes de usuario `"markdown.showToolbar": true` para mostrar la barra de herramientas.

   Para más información, vea la página del [paquete de creación de Docs](how-to-write-docs-auth-pack.md).


## <a name="next-steps"></a>Pasos siguientes

Ahora está listo para la [configuración de un repositorio de Git local](get-started-setup-local.md).
