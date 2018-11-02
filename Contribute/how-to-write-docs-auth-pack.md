---
title: Paquete de creación de Docs para Visual Studio Code
description: En este artículo se describe el paquete de extensiones de Visual Studio Code que facilita la creación de contenido para docs.microsoft.com con Markdown.
author: meganbradley
ms.author: mbradley
ms.date: 10/22/2018
ms.openlocfilehash: 00afafbbf16096ac6433c0ab276578d8d9084b51
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805663"
---
# <a name="docs-authoring-pack-for-vs-code"></a>Paquete de creación de Docs para VS Code

El paquete de creación de Docs es una colección de extensiones de Visual Studio Code que facilita la creación de contenidos para docs.microsoft.com con Markdown. El paquete está [disponible en VS Code Marketplace](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-authoring-pack) y contiene las extensiones siguientes:

- [markdownlint:](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint) popular linter de Markdown creado por David Anson para ayudar a aplicar los procedimientos recomendados en su código de Markdown.
- [Code Spell Checker](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker): un corrector ortográfico que funciona totalmente sin conexión de Street Side Software.
- [Docs Preview](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-preview): usa las hojas de estilo CSS de docs.microsoft.com para brindar una vista previa más precisa de Markdown, incluido Markdown personalizado.
- [Docs Markdown:](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-markdown) proporciona ayuda para la creación de contenido de docs.microsoft.com con Markdown en Open Publishing System (OPS), e incluye asistencia básica para Markdown y asistencia para sintaxis personalizada de Markdown en OPS. En el resto de este tema se describe la extensión Docs Markdown.
- [Docs Article Templates](https://marketplace.visualstudio.com/items?itemName=docsmsft.docs-article-templates): permite a los usuarios aplicar el contenido del esqueleto de Markdown a nuevos archivos.

## <a name="prerequisites-and-assumptions"></a>Requisitos previos y suposiciones

Para insertar de manera precisa vínculos relativos, imágenes y otro contenido insertado con la extensión Docs Markdown, el ámbito de su área de trabajo de VS Code debe ser la raíz de su repositorio clonado de Open Publishing System (OPS).

Parte de la sintaxis admitida por la extensión, como las alertas y los fragmentos de código, son código Markdown personalizado para OPS y no se representará correctamente a menos que se publique vía OPS.

## <a name="how-to-use-the-docs-markdown-extension"></a>Uso de la extensión Docs Markdown

Para acceder al menú de Docs Markdown, presione `ALT+M`. Para seleccionar una función, haga clic en ella o use las flechas arriba/abajo, o bien escriba para empezar a filtrar y presione `ENTER` cuando la función que quiera esté resaltada en el menú. Estas son las funciones disponibles:

|Función     |Descripción           |
|-------------|----------------------|
|Vista previa      |Obtenga una vista previa del tema activo en una ventana paralela con la extensión Docs Preview. Esta opción está disponible solo si Docs Preview está instalado.|
|Negrita         |Aplica un formato de **negrita** al texto.|
|Cursiva       |Aplica un formato de *cursiva* al texto.|
|Código         |Si se selecciona una línea o menos, aplica formato al texto como `inline code`.<br><br>Si hay varias líneas seleccionadas, se aplica en ellas un formato de bloque de código cerrado y se ofrece la opción de seleccionar un lenguaje de programación compatible con OPS.|
|Alerta        |Inserta un elemento Nota, Importante, Advertencia o Sugerencia.<br><br>Seleccione Alerta en el menú y el tipo de alerta. Si previamente ha seleccionado texto, se rodeará con la sintaxis de alerta que se haya seleccionado. Si no se ha seleccionado texto, se agregará una alerta nueva con texto de marcador de posición.|
|Lista numerada|Inserta una nueva lista numerada.<br><br> Si hay varias líneas seleccionadas, cada una pasará a ser un elemento de la lista. Observe que las listas numeradas muestran todas el número 1 en Markdown, pero en docs.microsoft.com se representarán como una secuencia de números o, en el caso de listas anidadas, como letras. Para crear una lista numerada anidada, desplácese por la lista principal mediante el tabulador.|
|Lista con viñetas|Inserta una nueva lista con viñetas.|
|Tabla        |Inserta una estructura de tabla de Markdown.<br><br>Después de seleccionar el comando de tabla, especifique el número de columnas y filas en el formato columnas:filas, por ejemplo, 3:4. Tenga en cuenta que esta extensión no permite especificar más de 5 columnas, que es el número recomendado para una buena comprensión lectora.|
|Vínculo al archivo en el repositorio|Inserta un vínculo relativo a otro archivo ubicado en el repositorio actual. Después de seleccionar esta opción, escriba en la ventana de comandos para filtrar los archivos por nombre y, después, seleccione el archivo que quiera. Si ha seleccionado texto previamente, será el texto del vínculo. De lo contrario, el H1 del archivo de destino se usará como texto del vínculo.|
|Vínculo a la página web    |Inserta un vínculo a una página web. Después de seleccionar esta opción, pegue o escriba el URI en la ventana de comandos. `https://` es obligatorio. Si ha seleccionado texto previamente, será el texto del vínculo. De lo contrario, el URI se usará como texto del vínculo.|
|Vínculo al encabezado     |Vincula a un delimitador en el archivo actual u otro archivo en el repositorio.<br>`Bookmark in this file`: elija en la lista de títulos del archivo actual para insertar un marcador con formato correcto.<br>`Bookmark in another file`: primero, filtre por nombre y seleccione el archivo con el que se va a establecer el vínculo y, después, elija el título apropiado en el archivo seleccionado.|
|Imagen        |Escriba texto alternativo (necesario para mejorar la accesibilidad) y selecciónelo. Después, llame a este comando para filtrar la lista de archivos de imagen compatibles del repositorio y seleccione el que quiera. Si en el momento de llamar a este comando aún no ha seleccionado texto alternativo, se le pedirá que lo haga antes de poder seleccionar un archivo de imagen.|
|Incluir      |Buque un archivo para insertarlo en el archivo actual.|
|Fragmento de código      |Busque un fragmento de código en el repositorio para insertarlo en el archivo actual.|
|Vídeo        |Agregue un vídeo insertado.|
|Plantilla     |Cree un nuevo archivo y aplique una plantilla de Markdown. Para obtener más información, consulte [Plantillas](#how-to-use-docs-templates) a continuación.|

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

## <a name="how-to-show-the-legacy-toolbar"></a>Uso de la barra de herramientas heredada

Los usuarios de la versión preliminar de la extensión observarán que la barra de herramientas de creación ya no se muestra en la parte inferior de la ventana de VS Code cuando se instala la extensión Docs Markdown. Esto se debe a que la barra de herramientas ocupaba demasiado espacio en la barra de estado de VS Code y no seguía los procedimientos recomendados para la extensión UX, por lo que ha quedado en desuso con la nueva extensión. No obstante, tiene la opción de mostrar la barra de herramientas si actualiza el archivo settings.json de VS Code de la manera siguiente:

1. En VS Code, vaya a Archivo -> Preferencias -> Configuración (`CTRL+Comma`).
1. Seleccione Configuración de usuario para cambiar la configuración de todas las áreas de trabajo de VS Code, o Configuración del área de trabajo si quiere modificar solo el área de trabajo actual.
1. En el panel Configuración predeterminada, busque Docs Authoring Extension Configuration (Configuración de extensión para creación de Docs) y seleccione el icono de lápiz junto a la opción de configuración deseada. A continuación, se le pedirá que seleccione entre `true` o `false`. Una vez hecha la selección, VS Code agregará automáticamente el valor al archivo de configuración settings.json. Para que los cambios surtan efecto, se le pedirá que vuelva a cargar la ventana.

## <a name="how-to-use-docs-templates"></a>Uso de las plantillas de Docs

La extensión Docs Article Templates permite a los escritores de VS Code extraer una plantilla de Markdown de un almacén centralizado y aplicarla a un archivo. Las plantillas pueden ayudar a garantizar que se incluyan los metadatos requeridos en los artículos, que se sigan las normas de contenido, etc. Las plantillas se administran como archivos Markdown en un repositorio de GitHub público.

### <a name="to-apply-a-template-in-vs-code"></a>Para aplicar una plantilla en VS Code

1. Si no tiene instalada la extensión Docs Markdown, pulse F1 para abrir la paleta de comandos, empiece a escribir "template" para filtrar y, luego, haga clic en `Docs: Template`. Si tiene instalado Docs Markdown, puede usar la paleta de comandos o hacer clic en `Alt+M` para que aparezca el menú de selección rápida de Docs Markdown, y luego seleccione `Template` en la lista.
1. Seleccione la plantilla deseada en la lista que aparece.

### <a name="to-add-your-github-id-andor-microsoft-alias-to-your-vs-code-settings"></a>Para agregar el id. de GitHub o el alias de Microsoft a la configuración de VS Code

La extensión Templates admite tres campos de metadatos dinámicos: author, ms.author y ms.date. Eso significa que si un creador de plantilla usa estos campos en el encabezado de metadatos de una plantilla de Markdown, se rellenarán automáticamente en su archivo cuando aplique la plantilla, de la siguiente manera:

|Metadatos  |Valor|
|----------|---------------|
|author    |El id. de GitHub, si se especifica en el archivo de configuración de VS Code.|
|ms.author |El alias de Microsoft, si se especifica en el archivo de configuración de VS Code. Si no es empleado de Microsoft, deje esto sin especificar.|
|ms.date   |La fecha actual en formato admitido por Docs; esto es, MM/DD/AAAA. Tenga en cuenta que la fecha no se actualiza de forma automática si posteriormente actualiza el archivo. Tendrá que actualizar de forma manual el valor ms.date para indicar la fecha de publicación más reciente en el sitio docs.microsoft.com.|

### <a name="to-set-author-github-id-andor-msauthor-microsoft-alias"></a>Para establecer el valor author (id. de GitHub) o ms.author (alias de Microsoft)

1. En VS Code, vaya a Archivo -> Preferencias -> Configuración (`CTRL+Comma`).
1. Seleccione Configuración de usuario para cambiar la configuración de todas las áreas de trabajo de VS Code, o Configuración de área de trabajo si quiere modificar solo el área de trabajo actual.
1. En la página Configuración predeterminada de la izquierda, busque la configuración de la extensión Docs Article Templates, haga clic en el icono de lápiz junto al parámetro deseado y luego haga clic en Reemplazar en Configuración.
1. Se abrirá el panel Configuración de usuario en paralelo, con una nueva entrada en la parte inferior.
1. Agregue su id. de GitHub o su alias de correo de Microsoft, según corresponda, y guarde el archivo.
1. Quizá tenga que cerrar y reiniciar VS Code para que los cambios surtan efecto.
1. Ahora, cuando aplique una plantilla que use campos dinámicos, el id. de GitHub o el alias de Microsoft se completarán automáticamente en el encabezado de los metadatos.
