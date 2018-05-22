---
title: Paquete de creación de Docs para VS Code
description: En este artículo se describe el paquete de extensiones de VS Code que facilita la creación de contenido para docs.microsoft.com con Markdown.
author: meganbradley
ms.author: mbradley
manager: jemash
ms.date: 04/06/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: d0d61db2faf88598ecd2c800fb5fbe8df8ec44f5
ms.sourcegitcommit: 7b668124f25b8ad0442937a3ad05b19a47af5970
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="docs-authoring-pack-for-vs-code"></a>Paquete de creación de Docs para VS Code

El paquete de creación de Docs (Docs Authoring Pack) es una colección de extensiones de VS Code que facilita la creación de contenidos para docs.microsoft.com con Markdown. El paquete está [disponible en VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) y contiene las extensiones siguientes:

- **DocFx:** proporciona una vista previa de Markdown específica de docs.microsoft.com. Para obtener más información, vea [DocFx](https://marketplace.visualstudio.com/items?itemName=ms-docfx.DocFX).
- **markdownlint:** popular linter de Markdown creado por David Anson para ayudar a aplicar los procedimientos recomendados en su código de Markdown. Para obtener más información, vea [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint).
- **Docs Markdown:** proporciona ayuda para la creación de contenido de docs.microsoft.com con Markdown en Open Publishing System (OPS), e incluye asistencia básica para Markdown y asistencia para sintaxis personalizada de Markdown en OPS. En el resto de este tema se describe la extensión Docs Markdown.

## <a name="prerequisites-and-assumptions"></a>Requisitos previos y suposiciones

Para insertar de manera precisa vínculos relativos, imágenes y otro contenido insertado con la extensión Docs Markdown, el ámbito de su área de trabajo de VS Code debe ser la raíz de su repositorio clonado de OPS.

Parte de la sintaxis admitida por la extensión, como las alertas y los fragmentos de código, son código Markdown personalizado para OPS y no se representará correctamente a menos que se publique vía OPS.

## <a name="how-to-use-the-docs-markdown-extension"></a>Uso de la extensión Docs Markdown

Para acceder al menú de Docs Markdown, presione `ALT+M`. Para seleccionar una función, haga clic en ella o use las flechas arriba/abajo, o bien escriba para empezar a filtrar y presione `ENTER` cuando la función que quiera esté resaltada en el menú. Estas son las funciones disponibles:

|Función     |Comando             |Descripción           |
|-------------|--------------------|----------------------|
|Negrita         |`formatBold`        |Aplica un formato de **negrita** al texto.|
|Cursiva       |`formatItalic`      |Aplica un formato de *cursiva* al texto.|
|Código         |`formatCode`        |Si se selecciona una línea o menos, aplica formato al texto como `inline code`.<br><br>Si hay varias líneas seleccionadas, se aplica en ellas un formato de bloque de código cerrado y se ofrece la opción de seleccionar un lenguaje de programación compatible con OPS.|
|Alerta        |`insertAlert`       |Inserta un elemento Nota, Importante, Advertencia o Sugerencia.<br><br>Seleccione Alerta en el menú y el tipo de alerta. Si previamente ha seleccionado texto, se rodeará con la sintaxis de alerta que se haya seleccionado. Si no se ha seleccionado texto, se agregará una alerta nueva con texto de marcador de posición.|
|Lista numerada|`insertNumberedList` |Inserta una nueva lista numerada.<br><br> Si hay varias líneas seleccionadas, cada una pasará a ser un elemento de la lista. Observe que las listas numeradas muestran todas el número 1 en Markdown, pero en docs.microsoft.com se representarán como una secuencia de números o, en el caso de listas anidadas, como letras. Para crear una lista numerada anidada, desplácese por la lista principal mediante el tabulador.|
|Lista con viñetas|`insertBulletedList` |Inserta una nueva lista con viñetas.|
|Tabla        |`insertTable`        |Inserta una estructura de tabla de Markdown.<br><br>Después de seleccionar el comando de tabla, especifique el número de columnas y filas en el formato columnas:filas, por ejemplo, 3:4. Tenga en cuenta que esta extensión no permite especificar más de 5 columnas, que es el número recomendado para una buena comprensión lectora.|
|Vínculo         |`selectLinkType`      |Inserta un vínculo. Al seleccionar este comando, aparece el submenú siguiente:<br><br>`External`: vínculo a una página web por URI. Debe incluir "http" o "https".<br>`Internal`: inserta un vínculo relativo a otro archivo ubicado en el mismo repositorio. Después de seleccionar esta opción, escriba en la ventana de comandos para filtrar los archivos por nombre y, después, seleccione el archivo que quiera. <br>`Bookmark in this file`: elija en la lista de títulos del archivo actual para insertar un marcador con formato correcto.<br>`Bookmark in another file`: primero, filtre por nombre y seleccione el archivo con el que se va a establecer el vínculo y, después, elija el título apropiado en el archivo seleccionado.|
|Imagen        |`insertImage`     |Escriba texto alternativo (necesario para mejorar la accesibilidad) y selecciónelo. Después, llame a este comando para filtrar la lista de archivos de imagen compatibles del repositorio y seleccione el que quiera. Si en el momento de llamar a este comando aún no ha seleccionado texto alternativo, se le pedirá que lo haga antes de poder seleccionar un archivo de imagen.|
|Incluir      |`insertInclude`   |Buque un archivo para insertarlo en el archivo actual.|
|Fragmento de código      |`insertSnippet`   |Busque un fragmento de código en el repositorio para insertarlo en el archivo actual.|
|Vídeo        |`insertVideo`     |Agregue un vídeo insertado.|
|Vista previa      |`previewTopic`    |Obtenga una vista previa del tema activo en una ventana paralela con la extensión DocFX.  Si la extensión DocFX no se ha instalado o está deshabilitada, no se mostrará una representación del tema.


## <a name="how-to-assign-keyboard-shortcuts"></a>Cómo asignar métodos abreviados de teclado

1. Presione `CTRL+K` y, después, `CTRL+S` para abrir la lista de métodos abreviados de teclado.
1. Busque el comando (por ejemplo `formatBold`) para el que quiere crear un enlace de teclado personalizado.
1. Haga clic en el signo más que aparece junto al nombre del comando cuando pasa el mouse sobre la línea.
1. Cuando se muestre un nuevo cuadro de entrada, escriba el método abreviado de teclado que quiera enlazar a ese comando en particular. Por ejemplo, para usar el acceso directo común para letra negrita, escriba `ctrl+b`.
1. Se recomienda insertar una cláusula `when` en el enlace de teclado para que solo esté disponible en los archivos de Markdown. Para ello, abra *keybindings.json* e inserte la línea siguiente debajo del nombre del comando (asegúrese de agregar una coma entre líneas):
   
    `"when": "editorTextFocus && editorLangId == 'markdown'"`

    Una vez completado, su enlace de teclado personalizado debería tener un aspecto como el siguiente en keybindings.json:

    ```json
    // Place your key bindings in this file to overwrite the defaults
    [
        {
            "key": "ctrl+b",
            "command": "formatBold",
            "when": "editorTextFocus && editorLangId == 'markdown'"
        }
    ]
    ```

1. Guarde keybindings.json.

Consulte el artículo [Keybindings](https://code.visualstudio.com/docs/getstarted/keybindings) (Enlaces de teclado) de la documentación de VS Code para obtener más información.

## <a name="how-to-show-the-legacy-gauntlet-toolbar"></a>Uso de la barra de herramientas "Gauntlet" heredada

Los antiguos usuarios de la extensión de código "Gauntlet" observarán que la barra de herramientas de creación ya no se muestra en la parte inferior de la ventana de VS Code cuando se instala la extensión Docs Markdown. Esto se debe a que la barra de herramientas ocupaba demasiado espacio en la barra de estado de VS Code y no seguía los procedimientos recomendados para la extensión UX, por lo que ha quedado en desuso con la nueva extensión. No obstante, tiene la opción de mostrar la barra de herramientas si actualiza el archivo settings.json de VS Code de la manera siguiente:

1. En VS Code, vaya a Archivo -> Preferencias -> Configuración (`CTRL+Comma`).
1. Seleccione Configuración de usuario para cambiar la configuración de todas las áreas de trabajo de VS Code, o Configuración del área de trabajo si quiere modificar solo el área de trabajo actual.
1. En el panel Configuración predeterminada, busque Docs Authoring Extension Configuration (Configuración de extensión para creación de Docs) y seleccione el icono de lápiz junto a la opción de configuración deseada. A continuación, se le pedirá que seleccione entre `true` o `false`. Una vez hecha la selección, VS Code agregará automáticamente el valor al archivo de configuración settings.json. Para que los cambios surtan efecto, se le pedirá que vuelva a cargar la ventana.

## <a name="known-issues"></a>Problemas conocidos

- Vista previa de DocFX: en MacOS y Linux, la vista previa de DocFX no se inicia correctamente (para estas plataformas, la vista previa predeterminada es la de VS Code Markdown).
- Vista previa de DocFx: en todas las plataformas, parte de la sintaxis, como vínculos xref (de referencia cruzada) a las API, no se representa correctamente en la vista previa, ya que en algunos casos deja espacios de contenido en blanco.
- Marcadores externos: en Linux, aparece la lista de archivos, pero no se muestra ningún título para seleccionar.
- Incluye: en Linux, se muestra la lista de archivos, pero no se agrega ningún vínculo después de realizar la selección.
