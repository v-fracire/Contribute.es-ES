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
ms.openlocfilehash: e248eafb0247b200313ba198f2545eca947f5627
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805940"
---
# <a name="markdown-reference-for-ops"></a>Referencia de Markdown para OPS

Markdown es un lenguaje de marcado ligero con sintaxis de texto sin formato. OPS admite el estándar CommonMark para Markdown, además de algunas extensiones de Markdown personalizadas diseñadas para proporcionar contenido más enriquecido en docs.microsoft.com. En este artículo se proporciona una referencia alfabética para el uso de Markdown en OPS para docs.microsoft.com.

Puede usar cualquier editor de texto para crear contenido de Markdown. Como editor que facilita la inserción de la sintaxis estándar de Markdown y extensiones de OPS personalizadas, se recomienda [VS Code](https://code.visualstudio.com/) con el [Paquete de creación de Docs](https://aka.ms/DocsAuthoringPack) instalado.

En OPS se ha estandarizado Markdig para todos los repositorios nuevos, mientras que los antiguos se están migrando a Markdig. Puede probar la representación de Markdown en Markdig frente a otros motores en [https://babelmark.github.io/](https://babelmark.github.io/).

## <a name="alerts-note-tip-important-caution-warning"></a>Alertas (Nota, Sugerencia, Importante, Precaución, Advertencia)

Las alertas son una extensión de Markdown específica de OPS para crear citas en bloque que se representan en docs.microsoft.com con iconos y colores que indican la importancia del contenido. Se admiten los tipos de alerta siguientes:

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

Estas alertas tienen este aspecto en docs.microsoft.com:

> [!NOTE]
> Información que el usuario debe apreciar aunque simplemente esté ojeando.

> [!TIP]
> Información opcional para ayudar al usuario a tener más éxito.

> [!IMPORTANT]
> Información esencial requerida para el éxito del usuario.

> [!CAUTION]
> Las posibles consecuencias negativas de una acción.

> [!WARNING]
> Consecuencias peligrosas concretas de una acción.

## <a name="code-snippets"></a>Fragmentos de código

Puede insertar fragmentos de código en los archivos Markdown:

```markdown
[!code-<language>[<name>](<codepath><queryoption><queryoptionvalue> "<title>")]
```

## <a name="headings"></a>Encabezados

OPS admite seis niveles de título de Markdown:

```markdown
# This is a first level heading (H1)

## This is a second level heading (H2)

...

###### This is a sixth level heading (H6)
```

- Debe haber un espacio entre el último `#` y el texto del título.
- En cada archivo Markdown solo puede haber un título H1.
- El título H1 debe ser el primer contenido del archivo después del bloque de metadatos YML.
- Los títulos H2 aparecen de forma automáticamente en el menú de navegación de la derecha del archivo publicado. Los títulos de nivel inferior no, por lo que debe usar los títulos H2 de forma estratégica para ayudar a los lectores a desplazarse por el contenido.
- Los títulos HTML, como `<h1>`, no se recomiendan, y en algunos casos generarán advertencias de compilación.
- Puede vincular a los títulos individuales de un archivo mediante [marcadores](#bookmark-links).

## <a name="html"></a>HTML

Aunque Markdown admite HTML insertado, no se recomienda HTML para la publicación a través de OPS y, a excepción de una lista limitada de valores, provocará errores o advertencias de compilación. <!--For more information, see HTML Whitelist. // do we want to add the whitelist? -->

## <a name="images"></a>Imágenes

La sintaxis para incluir una imagen es:

```markdown
![[alt text]](<folderPath>)

Example:
![alt text for image](../images/Introduction.png)
```

Donde `alt text` es una breve descripción de la imagen y `<folder path>` es una ruta de acceso relativa a la imagen. El texto alternativo es obligatorio para los lectores de pantalla destinados a usuarios con discapacidad visual. También es útil si hay un error del sitio donde no se puede representar la imagen.

Las imágenes se deben almacenar en una carpeta `/media` dentro del conjunto de documentación. De forma predeterminada, se admiten los tipos de archivo siguientes para las imágenes:

- .jpg
- .png

Puede agregar compatibilidad con otros tipos de imagen si los agrega como recursos al archivo docfx.json <!--add link to reference when available--> del conjunto de documentación.

## <a name="links"></a>Vínculos

En la mayoría de los casos, OPS usa vínculos de Markdown estándar a otros archivos y páginas. Los tipos de vínculos se describen en las subsecciones siguientes.

> [!TIP]
> El Paquete de creación de Docs para VS Code puede ayudar a insertar vínculos relativos y marcadores de forma correcta sin la tediosa tarea de tener que determinar las rutas de acceso.

> [!IMPORTANT]
> No incluya códigos de configuración regional, como es-ES, en los vínculos a los sitios de Microsoft. Los códigos de configuración regional codificados de forma rígida evitan que se represente el contenido localizado, lo que es una mala experiencia para los usuarios de otras configuraciones regionales e incurre en costes de localización importantes. Al copiar una dirección URL de un explorador, el código de configuración regional se incluye de forma predeterminada, por lo que tendrá que eliminarlo manualmente al crear el vínculo. Por ejemplo, use:
>
> `[Microsoft](https://www.microsoft.com)`
>
> No:
>
> `[Microsoft](https://www.microsoft.com/en-us/)`

### <a name="relative-links-to-files-in-the-same-doc-set"></a>Vínculos relativos a archivos del mismo conjunto de documentación

Una ruta de acceso relativa es la ruta de acceso al archivo de destino con respecto al archivo actual. En OPS, se puede usar una ruta de acceso relativa para vincular a otro archivo del mismo conjunto de documentación. La sintaxis para una ruta de acceso relativa es la siguiente:

```markdown
[link text](../../folder/filename.md)
```

Donde `../` indica un nivel superior en la jerarquía.

- La ruta de acceso relativa se resolverá durante la compilación, incluida la eliminación de la extensión .md.
- Puede usar "../" para vincular a un archivo de la carpeta principal, pero ese archivo tiene que estar en el mismo conjunto de documentación. No puede usar "../" para vincular a un archivo en la carpeta de otro conjunto de documentación.
- OPS también admite una forma especial de ruta de acceso relativa que empieza por "~" (por ejemplo, ~/foo/bar.md). Esta sintaxis indica un archivo relativo a la carpeta raíz de un conjunto de documentación. Este tipo de ruta de acceso también se valida y resuelve durante la compilación.

> [!IMPORTANT]
> Incluya la extensión de archivo en la ruta de acceso relativa. La compilación valida la existencia del archivo de destino de esa ruta de acceso relativa. Si la ruta de acceso relativa no incluye la extensión de archivo, es probable que la compilación notifique una advertencia de vínculo roto. Por ejemplo, use:
>
> `[link text](../../folder/filename.md)`
>
> No:
>
> `[link text](../../folder/filename)`

### <a name="absolute-links-to-other-files-in-ops"></a>Vínculos absolutos a otros archivos en OPS

```markdown
[Azure and Linux](/articles/virtual-machines/linux/overview)
```

No incluya la extensión de archivo (.md). Esto se vincula al archivo de información general de Linux desde fuera del conjunto de documentación "articles" de Azure.

### <a name="links-to-external-sites"></a>Vínculos a sitios externos

```markdown
[Microsoft](https://www.microsoft.com)
```

Vínculo basado en una dirección URL a otra página web (debe incluir https://).

### <a name="bookmark-links"></a>Vínculos de marcador

Vínculo de marcador a un título de otro archivo en el mismo repositorio:

```markdown
[Managed Disks](../../linux/overview.md#managed-disks)
```

Vínculo de marcador a un título del archivo actual:

```markdown
[Managed Disks](#managed-disks)
```

Use una etiqueta hash seguida de las palabras del título sin puntuación y sustituya los espacios por guiones.

### <a name="explicit-anchor-links"></a>Vínculos delimitadores explícitos

Los vínculos delimitadores explícitos en los que se usa la etiqueta `<a>` de HTML **no son necesarios ni se recomiendan**, excepto en páginas de sitio central o de aterrizaje. Use los marcadores como se describió anteriormente en los archivos Markdown generales. Para las páginas de sitio central o de aterrizaje, use los delimitadores de esta forma:

`## <a id="AnchorText"> </a>Header text` o `## <a name="AnchorText"> </a>Header text`

Para vincular a delimitadores explícitos, use la sintaxis siguiente:

```markdown
To go to a section on the same page:
[text](#AnchorText)

To go to a section on another page.
[text](FileName.md#AnchorText)
```

### <a name="xref-cross-reference-links"></a>Vínculos XREF (de referencia cruzada)

Para vincular a páginas de referencia de API generadas automáticamente del conjunto de documentación actual o de otros, use vínculos XREF con el identificador único (UID).

> [!NOTE]
> Para hacer referencia a páginas de referencia de API en otros conjuntos de documentación, tendrá que agregar la configuración `xrefService` en el archivo `docfx.json`.
> ```
> "build": {
>   ...
>   "xrefService": [ "https://xref.docs.microsoft.com/query?uid={uid}" ]
> }
> ```

El UID equivale al nombre de clase y miembro completo. Si agrega un * después del UID, el vínculo representará a la página de sobrecarga y no a una API específica. Por ejemplo, use `List<T>.BinarySearch*` para vincular a la página del método BinarySearch en lugar de vincular a una sobrecarga específica como `List<T>.BinarySearch(T, IComparer<T>)`.

Puede usar una de las sintaxis siguientes:

- Vinculación automática: `<xref:UID> or <xref:UID?displayProperty=nameWithType>`

  El parámetro de consulta `displayProperty` opcional genera un texto de vínculo completo. De forma predeterminada, el texto del vínculo muestra solo el nombre de miembro o tipo.

- Vínculo de Markdown: `[link text](xref:UID)`
  
  Se utiliza cuando se desea personalizar el texto del vínculo mostrado.

Ejemplos:

- `<xref:System.String>` se representa como "String".
- `<xref:System.String?displayProperty=nameWithType>` se representa como "System.String".
- `[String class](xref:System.String)` se representa como "String class".

En este momento, no hay manera de encontrar con facilidad los UID. <!-- ? -->La mejor manera de encontrar el UID de una API es ver el origen de la página de API a la que se quiere vincular y buscar el valor ms.assetid. No se muestran los valores individuales de sobrecarga en el origen. Estamos trabajando para mejorar el sistema próximamente.

Cuando el UID contiene los caracteres especiales \`, \# o \*, el valor de UID debe codificarse en HTML como `%60`, `%23` y `%2A`, respectivamente. En ocasiones verá paréntesis codificados, pero no es un requisito.

Ejemplos:

- System.Threading.Tasks.Task\`1 se convierte en `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor se convierte en `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se convierte en `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

<!-- leave out of Contributor Guide for now
Using XREF may require some configuration. For more information, see XREF Service.
-->

## <a name="lists-numbered-bulleted-checklist"></a>Listas (Numeradas, Con viñetas, De comprobación)

### <a name="numbered-list"></a>Lista numerada

Para crear una lista numerada, puede usar todo números 1, que se representarán como una lista secuencial cuando se publique. Para mejorar la legibilidad del origen, puede incrementar las listas.

No use letras en las listas, ni siquiera en las anidadas, dado que no se representan correctamente cuando se publican a través de OPS. Las listas anidadas en las que se usan números se representarán como letras en minúscula al publicarse. Por ejemplo:

```markdown
1. This is
1. a parent numbered list
   1. and this is
   1. a nested numbered list
1. (fin)
```

Esto se representa de la forma siguiente:

1. Esto es
1. una lista numerada principal
   1. y esto es
   1. una lista numerada anidada
1. (fin)

### <a name="bulleted-list"></a>Lista con viñetas

Para crear una lista con viñetas, use `-` seguido de un espacio al principio de cada línea:

```markdown
- This is
- a parent bulleted list
  - and this is
  - a nested bulleted list
- All done!
```

Esto se representa de la forma siguiente:

- Esto es
- una lista con viñetas principal
  - y esto es
  - una lista con viñetas anidada
- Listo.

### <a name="checklist"></a>Lista de comprobación

Las listas de comprobación se pueden usar en docs.microsoft.com (solo) a través de una extensión de Markdown personalizada:

```markdown
> [!div class="checklist"]
> * List item 1
> * List item 2
> * List item 3
```

Este ejemplo se representa en docs.microsoft.com de esta forma:

> [!div class="checklist"]
> * Elemento de lista 1
> * Elemento de lista 2
> * Elemento de lista 3

Use las listas de comprobación al principio o el final de un artículo para resumir contenido de tipo "Qué aprenderá" o "Qué ha aprendido". No agregue listas de comprobación aleatorias en los artículos.
<!-- is this guidance still accurate? -->

## <a name="next-step-action"></a>Acción "Paso siguiente"

Puede usar una extensión personalizada para agregar un botón de acción "Paso siguiente" a las páginas de docs.microsoft.com (solamente).

La sintaxis es la siguiente:

```markdown
> [!div class="nextstepaction"]
> [button text](link to topic)
```

Por ejemplo:

```markdown
> [!div class="nextstepaction"]
> [Learn about basic style](style-quick-start.md)
```

Esto se representa de la forma siguiente:

> [!div class="nextstepaction"]
> [Más información sobre el estilo básico](style-quick-start.md)

Puede usar cualquier vínculo compatible en una acción "Paso siguiente", incluido un vínculo de Markdown a otra página web. En la mayoría de los casos, el vínculo de la acción "Paso siguiente" será relativo a otro archivo del mismo conjunto de documentación.

## <a name="section-definition"></a>Definición de secciones

<!-- more info about this would be helpful! --> Es posible que necesite definir una sección. Esta sintaxis se suele usar en tablas de código.
Vea el siguiente ejemplo:

````
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```
````

El texto de Markdown de la cita en bloque anterior se mostrará como:
> [!div class="tabbedCodeSnippets" data-resources="OutlookServices.Calendar"]
> ```cs
> <cs code text>
> ```
> ```javascript
> <js code text>
> ```

## <a name="selectors"></a>Selectores

<!-- could be more clear! --> Puede usar un selector cuando quiera conectar páginas diferentes del mismo artículo. Así, los lectores podrán alternar entre esas páginas.

> [!NOTE]
> Esta extensión funciona de forma diferente en docs.microsoft.com y en MSDN. <!-- should we keep info about MSDN? If so say how they differ?-->

### <a name="single-selector"></a>Selector único

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

...se mostrará así:

> [!div class="op_single_selector"]
> - [Windows universal](how-to-write-use-markdown.md)
> - [Windows Phone](how-to-write-use-markdown.md)
> - [iOS](how-to-write-use-markdown.md)
> - [Android](how-to-write-use-markdown.md)
> - [Kindle](how-to-write-use-markdown.md)
> - [Baidu](how-to-write-use-markdown.md)
> - [Xamarin.iOS](how-to-write-use-markdown.md)
> - [Xamarin.Android](how-to-write-use-markdown.md)

### <a name="multi-selector"></a>Selector múltiple

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

...se mostrará así:

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

## <a name="tables"></a>Tablas

La forma más sencilla de crear una tabla en Markdown es usar barras verticales y líneas. Para crear una tabla estándar con un encabezado, siga la primera línea con una línea discontinua:

```markdown
|This is   |a simple   |table header|
|----------|-----------|------------|
|table     |data       |here        |
|it doesn't|actually   |have to line up nicely!|
```

Esto se representa de la forma siguiente:

|Esto es   |un sencillo   |encabezado de tabla|
|----------|-----------|------------|
|los datos     |de la tabla       |aquí        |
|no es|necesario que   |se alineen correctamente.||

También puede crear una tabla sin encabezado. Por ejemplo, para crear una lista con varias columnas:

```markdown
|   |   |
| - | - |
| This | table |
| has no | header |
```

Esto se representa de esta forma:

|   |   |
| - | - |
| Esta | tabla |
| no tiene | encabezado |

Las columnas se pueden alinear usando dos puntos:

```markdown
|                  |
|------------------|
|    right aligned:|
|:left aligned     |
|:centered        :|
```

Se representa de esta forma:

|                  |
|------------------|
|    alineado a la derecha:|
|:alineado a la izquierda     |
|:centrado        :|

> [!TIP]
> La Extensión de creación de Docs para VS Code facilita la adición de tablas de Markdown básicas.
>
> También puede usar un [generador de tablas en línea](http://www.tablesgenerator.com/markdown_tables).

### <a name="mx-tdbreakall"></a>mx-tdBreakAll

> [!IMPORTANT]
> Esto solo funciona en el sitio docs.microsoft.com.

Si crea una tabla en Markdown, podría expandirse hacia el panel de navegación de la derecha y llegar a ser ilegible. Este problema se puede solucionar permitiendo que la representación de Docs interrumpa la tabla cuando sea necesario. Basta con ajustar la tabla con la clase personalizada `[!div class="mx-tdBreakAll"]`.

Aquí tiene un código de Markdown de ejemplo de una tabla con tres filas que se ajustará con un elemento `div` con el nombre de clase `mx-tdBreakAll`.

```markdown
> [!div class="mx-tdBreakAll"]
> |Name|Syntax|Mandatory for silent installation?|Description|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Yes|Runs the installer, displaying no UI and no prompts.|
> |NoRestart|/norestart|No|Suppresses any attempts to restart. By default, the UI will prompt before restart.|
> |Help|/help|No|Provides help and quick reference. Displays the correct use of the setup command, including a list of all options and behaviors.|
```

Se mostrará así:

> [!div class="mx-tdBreakAll"]
> |Nombre|Sintaxis|¿Es obligatorio para la instalación silenciosa?|Descripción|
> |-------------|----------|---------|---------|
> |Quiet|/quiet|Sí|Ejecuta el instalador sin mostrar ni interfaz de usuario ni avisos.|
> |NoRestart|/norestart|No|Omite cualquier intento de reinicio. La interfaz de usuario se mostrará de manera predeterminada después de reiniciar.|
> |Help|/help|No|Proporciona ayuda y referencia rápida. Muestra el uso correcto del comando de instalación, incluida una lista de todas las opciones y los comportamientos.|

### <a name="mx-tdcol2breakall"></a>mx-tdCol2BreakAll

> [!IMPORTANT]
> Esto solo funciona en el sitio docs.microsoft.com.

De vez en cuando, es posible que haya palabras muy largas en la segunda columna de una tabla. Para asegurarse de que se dividan correctamente, puede aplicar la clase `mx-tdCol2BreakAll` mediante la sintaxis de ajuste `div` mostrada anteriormente.

### <a name="html-tables"></a>Tablas HTML

Las tablas HTML no se recomiendan para docs.microsoft.com. No son lenguaje natural en el código, lo que es un principio clave de Markdown.

<!--If you use HTML tables and your Markdown is not being rendered between the two tables, you need to add a closing `br` tag after the closing `table` tag.

![break HTML tables](media/break-tables.png)
-->

## <a name="videos"></a>Vídeos

### <a name="embedding-videos-into-a-markdown-page"></a>Inserción de vídeos en una página de Markdown

En la actualidad, OPS puede admitir vídeos publicados en una de estas tres ubicaciones:

- YouTube
- Channel 9
- El sistema "One Player" de Microsoft

Así, puede insertar un vídeo usando la siguiente sintaxis y OPS lo mostrará.

```markdown
> [!VIDEO <embedded_video_link>]
```

Ejemplo:

```markdown
> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
```

...se representará como:

```html
<iframe src="https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>

<iframe src="https://www.youtube-nocookie.com/embed/iAtwVM-Z7rY" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
<iframe src="https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS" width="640" height="320" allowFullScreen="true" frameBorder="0"></iframe>
```

Y aparecerá así en las páginas publicadas:

> [!VIDEO https://channel9.msdn.com/Series/Youve-Got-Key-Values-A-Redis-Jump-Start/03/player]

> [!VIDEO https://www.youtube.com/embed/iAtwVM-Z7rY]

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]

> [!IMPORTANT]
> La dirección URL del vídeo de CH9 debe empezar por `https` y acabar en `/player`. De lo contrario, se insertará toda la página en lugar de insertarse solo el vídeo.

### <a name="uploading-new-videos"></a>Carga de vídeos nuevos

Todos los vídeos nuevos se deben cargar mediante el proceso siguiente:

1. Únase al grupo **docs_video_users** en IDWEB.
1. Vaya a https://aka.ms/VideoUploadRequest y rellene los detalles del vídeo. Necesitará lo siguiente (tenga en cuenta que ninguno de estos elementos será visible para el público):
    1. Un título para el vídeo.
    1. Una lista de los productos y servicios con los que está relacionado el vídeo.
    1. La página de destino o, si todavía no la tiene, el conjunto de documentación en el que se va a hospedar el vídeo.
    1. Un vínculo al archivo MP4 del vídeo (si no tiene una ubicación para colocar el archivo, lo puede colocar aquí de forma temporal: `\\scratch2\scratch\apex`). Los archivos MP4 deben tener una resolución de 720p o superior.
    1. Una descripción del vídeo.
1. Envíe (guarde) ese elemento.
1. El vídeo se cargará en el plazo de dos días laborables. El vínculo que necesita para insertar se colocará en el elemento de trabajo, y se le *devolverá* para resolverlo.
1. Una vez que haya obtenido el vínculo del vídeo, cierre el elemento de trabajo.
1. Después, puede agregar el vínculo del vídeo a la publicación, mediante esta sintaxis:

   ```markdown
   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE1XVQS]
   ```
