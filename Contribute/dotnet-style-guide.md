---
title: Plantilla y hoja de referencia para los artículos de .NET
description: Este artículo contiene una plantilla muy útil que se puede usar para crear artículos para los repositorios de documentación de .NET.
ms.date: 11/07/2018
ms.openlocfilehash: 8980f5e39213d8f2edd1d29e66d900f2c3d04bbc
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609748"
---
# <a name="metadata-and-markdown-template-for-net-docs"></a>Metadatos y plantilla de Markdown para la documentación de .NET

Esta plantilla de dotnet/docs contiene ejemplos de sintaxis de Markdown, además de instrucciones sobre cómo establecer los metadatos.

Al crear un archivo Markdown, debe copiar la plantilla incluida en un archivo nuevo, completar los metadatos como se especifica a continuación y establecer el encabezado H1 anterior en el título del artículo.

## <a name="metadata"></a>Metadatos

El bloque de metadatos necesario está en el siguiente bloque de metadatos de ejemplo:

```markdown
---
title: [ARTICLE TITLE]
description: [usually a summary of your first paragraph. It gets displayed in search results, and can help drive the correct traffic if well written.]
author: [GITHUB USERNAME]
ms.date: [CREATION/UPDATE DATE - mm/dd/yyyy]
---
# The H1 should not be the same as the title, but should describe the article contents
```

- **Debe** haber un espacio entre los dos puntos (:) y el valor de un elemento de metadatos.
- En un valor (por ejemplo en un título) los dos puntos interrumpen al analizador de metadatos. En este caso, incluya el título entre comillas dobles (por ejemplo, `title: "Writing .NET Core console apps: An advanced step-by-step guide"`).
- **title**: aparece en los resultados de los motores de búsqueda. El título no debe ser idéntico al del encabezado H1, y debe contener 60 caracteres o menos.
- **description**: resume el contenido del artículo. Se suele mostrar en la página de resultados de la búsqueda, pero no se usa para la clasificación de la búsqueda. La longitud debe ser de 115-145 caracteres (espacios incluidos).
- **author**: el campo del autor debe contener el **nombre de usuario de GitHub** del autor.
- **ms.date**: la fecha de la última actualización importante. Actualice este valor en los artículos existentes si ha revisado y actualizado el artículo completo. Las correcciones menores, como los errores tipográficos y similares, no merecen una actualización.

A los artículos se anexan otros metadatos, pero por lo general la mayoría se aplican en el nivel de carpeta, y se especifican en **docfx.json**.

## <a name="basic-markdown-gfm-and-special-characters"></a>Markdown básico, GFM y caracteres especiales

Puede obtener información sobre los conceptos básicos de Markdown, GitHub Flavored Markdown (GFM) y extensiones específicas de OPS en los artículos generales de [Markdown](how-to-write-use-markdown.md) y [Referencia de Markdown](markdown-reference.md).

En Markdown se usan caracteres especiales como \*, \` y \# para el formato. Si quiere incluir uno de estos caracteres en el contenido, debe realizar una de estas dos cosas:

- Colocar una barra diagonal inversa delante del carácter especial para aplicarle el "escape" (por ejemplo, `\*` para \*)
- Usar el [código de entidad HTML](http://www.ascii.cl/htmlcodes.htm) para el carácter (por ejemplo, `&#42;` para &#42;).

## <a name="file-names"></a>Nombres de archivo

En los nombres de archivo se usan las reglas siguientes:

* Solo pueden contener letras minúsculas, números y guiones.
* No pueden contener espacios ni caracteres de puntuación. Use guiones para separar palabras y números en el nombre de archivo.
* Use verbos de acción que sean específicos, como "desarrollar", "comprar", "compilar" o "solucionar problemas". No use gerundios.
* No use palabras cortas ni incluya "un", "y", "el", "en", "o", etc.
* Deben estar en Markdown y usar la extensión de archivo .md.
* Use nombres de archivo relativamente cortos. Forman parte de la dirección URL de los artículos.

## <a name="headings"></a>Encabezados

Use mayúsculas de estilo de frase. Siempre debe poner en mayúscula la primera palabra de un título.

## <a name="text-styling"></a>Estilo de texto

*Cursiva* Se usa para archivos, carpetas, rutas de acceso (para elementos largos, divididos en su propia línea), términos nuevos.

**Negrita** Se usa para los elementos de la interfaz de usuario.

`Code` Se usa para código insertado, palabras clave del lenguaje, nombres de paquetes NuGet, comandos de la línea de comandos, nombres de tablas y columnas de bases de datos y direcciones URL en las que no quiera que se pueda hacer clic.

## <a name="links"></a>Vínculos

Vea el artículo general sobre [Vínculos](how-to-write-links.md) para obtener información sobre delimitadores, vínculos internos, vínculos a otros documentos, archivos de inclusión de código y vínculos externos.

El equipo de documentación de .NET usa las convenciones siguientes:

- En la mayoría de los casos, se usan los vínculos relativos y se desaconseja el uso de `~/` en los vínculos, ya que los vínculos relativos se resuelven en el origen en GitHub. Pero siempre que se vincula a un archivo en un repositorio dependiente, se usará el carácter `~/` para proporcionar la ruta de acceso. Como los archivos del repositorio dependiente están en otra ubicación de GitHub, los vínculos no se resolverán de forma correcta con vínculos relativos con independencia de cómo se hayan escrito.
- La especificación de los lenguajes C# y Visual Basic se incluye en la documentación de .NET mediante la inclusión del origen de los repositorios de lenguaje. Los orígenes de Markdown se administran en los repositorios [csharplang](https://github.com/dotnet/csharplang) y [vblang](https://github.com/dotnet/vblang).

Los vínculos a la especificación deben apuntar a los directorios de origen en los que se incluyen esas especificaciones. Para C#, es **~/_csharplang/spec** y para VB, **~/_vblang/spec**.

- Ejemplo: `[C# Query Expressions](~/_csharplang/spec/expressions.md#query-expressions)`

### <a name="links-to-apis"></a>Vínculos a las API

El sistema de compilación tiene algunas extensiones que nos permiten vincular a las API de .NET sin tener que usar vínculos externos. Se usa una de las sintaxis siguientes:

1. Vinculación automática: `<xref:UID>` o `<xref:UID?displayProperty=nameWithType>`

   El parámetro de consulta `displayProperty` produce un texto de vínculo completo. De forma predeterminada, el texto del vínculo muestra solo el nombre de miembro o tipo.

2. Vínculo de Markdown: `[link text](xref:UID)`

   Se utiliza cuando se desea personalizar el texto del vínculo mostrado.

Ejemplos:

- `<xref:System.String>` se representa como [String](https://docs.microsoft.com/dotnet/api/system.string)
- `<xref:System.String?displayProperty=nameWithType>` se representa como [System.String](https://docs.microsoft.com/dotnet/api/system.string)
- `[String class](xref:System.String)` se representa como [String class](https://docs.microsoft.com/dotnet/api/system.string)

Para obtener más información acerca de cómo utilizar esta notación, consulte [Using cross reference](https://dotnet.github.io/docfx/tutorial/links_and_cross_references.html#using-cross-reference) (Uso de referencia cruzada).

Cuando algunos UID contienen los caracteres especiales \`, \# o \*, el valor de UID se debe codificar en HTML como `%60`, `%23` y `%2A`, respectivamente. En ocasiones verá paréntesis codificados, pero no es un requisito.

Ejemplos:

- System.Threading.Tasks.Task\`1 se convierte en `System.Threading.Tasks.Task%601`
- System.Exception.\#ctor se convierte en `System.Exception.%23ctor`
- System.Lazy\`1.\#ctor(System.Threading.LazyThreadSafetyMode) se convierte en `System.Lazy%601.%23ctor%28System.Threading.LazyThreadSafetyMode%29`

Puede encontrar los UID de tipos, una lista de sobrecargas de miembros, o bien un miembro de sobrecarga concreto, en `https://xref.docs.microsoft.com/autocomplete`. La cadena de consulta "?text=*\<nombre_del_miembro_tipo>*" identifica el tipo o miembro cuyos UID quiere ver. Por ejemplo, `https://xref.docs.microsoft.com/autocomplete?text=string.format` recupera las sobrecargas de [String.Format](https://docs.microsoft.com/dotnet/api/system.string.format). La herramienta busca el parámetro de consulta `text` proporcionado en cualquier parte del UID. Por ejemplo, puede buscar por nombre de miembro (ToString), nombre de miembro parcial (ToStri), nombre de miembro y tipo (Double.ToString), etc.

Si agrega \* (o %2A) después del UID, el vínculo representará la página de sobrecarga y no una API específica. Por ejemplo, puede usarlo si desea vincular a la página [List\<T>.BinarySearch Method](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch) de forma genérica en lugar de a una sobrecarga específica como [List\<T>.BinarySearch(T, IComparer\<T>)](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1.binarysearch#System_Collections_Generic_List_1_BinarySearch__0_). También puede usar \* para vincular a la página de un miembro cuando el miembro no está sobrecargado; esto evita tener que incluir la lista de parámetros en el UID.

Para vincular a una sobrecarga de método concreta, debe incluir el nombre de tipo completo de todos los parámetros del método. Por ejemplo, \<xref:System.DateTime.ToString> vincula al método [DateTime.ToString](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString) sin parámetros, mientras que \<xref:System.DateTime.ToString(System.String,System.IFormatProvider)> vincula al método [DateTime.ToString(String,IFormatProvider)](https://docs.microsoft.com/dotnet/api/system.datetime.tostring#System_DateTime_ToString_System_String_System_IFormatProvider_).

Para vincular a un tipo genérico, como [System.Collections.Generic.List\<T>](https://docs.microsoft.com/dotnet/api/system.collections.generic.list-1), se usa el carácter \` (%60) seguido del número de parámetros de tipo genérico. Por ejemplo, \<xref:System.Nullable%601> vincula al tipo [System.Nullable\<T>](https://docs.microsoft.com/dotnet/api/system.nullable-1), mientras que \<xref:System.Func%602> vincula al delegado [System.Func\<T,TResult>](https://docs.microsoft.com/dotnet/api/system.func-2).

## <a name="code"></a>Código

La mejor forma de incluir código consiste en incluir fragmentos de código de un ejemplo que funcione. Para crear el ejemplo, siga las instrucciones del artículo [Contribuciones a .NET](dotnet-contribute-process.md#contributing-to-samples). Las reglas básicas para incluir código se encuentran en las instrucciones generales sobre [código](how-to-write-use-markdown.md#code-includes).

Puede incluir el código mediante la sintaxis siguiente:

```markdown
[!code-<language>[<name>](<pathToFile><queryoption><queryoptionvalue>)]
```

* `-<language>` (*opcional* pero *recomendado*)
  * Lenguaje del fragmento de código al que se hace referencia. Para obtener una lista de los valores admitidos, vea [Lenguajes admitidos](#supported-languages).

* `<name>` (*opcional*)
  * Nombre del fragmento de código. No tiene ningún impacto en el HTML de salida, pero puede usarlo para mejorar la legibilidad del código fuente de Markdown.

* `<pathToFile>` (*obligatorio*)
  * Ruta de acceso relativa del sistema de archivos que indica el archivo del fragmento de código al que se hace referencia. Esto lo pueden complicar los diferentes repositorios que forman el conjunto de documentación de .NET. Los ejemplos de .NET están en el repositorio dotnet/samples. Las rutas de acceso de todos los fragmentos de código deben empezar por `~/samples`, y el resto es la ruta de acceso al origen desde la raíz de ese repositorio.

* `<queryoption>` (*opcional*)
  * Se usa para especificar cómo se debe recuperar el código del archivo:
    * `#`: `#{tagname}` (nombre de etiqueta) *o* `#L{startlinenumber}-L{endlinenumber}` (intervalo de líneas).
    No se recomienda el uso de números de línea porque son muy frágiles. El nombre de etiqueta es la forma preferida de hacer referencia a los fragmentos de código. Use nombres de etiqueta descriptivos. Muchos fragmentos de código se han migrado de una plataforma anterior y las etiquetas tienen nombres como `Snippet1` y `Snippet2`, entre otros. Esa práctica es mucho más difícil de mantener).
    * `range`: `?range=1,3-5` Un intervalo de líneas. Este ejemplo incluye las líneas 1, 3, 4 y 5.

Se recomienda usar la opción del nombre de etiqueta siempre que sea posible. El nombre de etiqueta es el nombre de una región o un comentario de código con el formato `Snippettagname` presente en el código fuente. En el ejemplo siguiente se muestra cómo hacer referencia al nombre de etiqueta `BasicThrow`:

```markdown
[!code-csharp[csrefKeyword#1](~/samples/snippets/snippets/csharp/language-reference/operators/ConditionalExamples.csConditionalRef)]
```

La ruta de acceso relativa al origen en el repositorio **dotnet/samples** sigue la ruta de acceso `~/samples`.

Y en [este archivo de código fuente](https://github.com/dotnet/samples/blob/master/snippets/csharp/language-reference/operators/ConditionalExamples.cs) puede ver la estructura de las etiquetas de fragmento de código. Para obtener más información sobre la presentación en archivos de origen de fragmento de código por idioma, vea las [directrices de DocFX ](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#tag-name-representation-in-code-snippet-source-file).

En el ejemplo siguiente se muestra el código incluido en los tres lenguajes de .NET:

```markdown
[!code-fsharp[ToPigLatin](../../../samples/snippets/fsharp/getting-started/pig-latin.fs#L1-L14)]
 [!code-csharp[ADCreateDomain#2](../../../samples/snippets/csharp/VS_Snippets_CLR/ADCreateDomain/CS/source2.cs#2)]
 [!code-vb[ADCreateDomain#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/ADCreateDomain/VB/source2.vb#2)]  
```

La inclusión de fragmentos de código desde programas completos garantiza que todo el código se ejecuta a través de nuestro sistema de Integración continua (CI). Pero si tiene que mostrar algo que produce errores en tiempo de compilación o ejecución, puede usar bloques de código insertado.

## <a name="images"></a>Imágenes

### <a name="static-image-or-animated-gif"></a>Imagen estática o GIF animado

```markdown
![this is the alt text](../images/Logo_DotNet.png)
```

### <a name="linked-image"></a>Imagen vinculada

```markdown
[![alt text for linked image](../images/Logo_DotNet.png)](https://dot.net)
```

## <a name="videos"></a>Vídeos

En la actualidad, puede insertar vídeos de Channel 9 y YouTube con la sintaxis siguiente:

### <a name="channel-9"></a>Channel 9

```markdown
> [!VIDEO <channel9_video_link>]
```

Para obtener la dirección URL correcta del vídeo, haga clic en la pestaña **Insertar** situada debajo del marco del vídeo y copie la dirección URL del elemento `<iframe>`. Por ejemplo:

```markdown
> [!VIDEO https://channel9.msdn.com/Blogs/dotnet/NET-Core-20-Released/player]
```

### <a name="youtube"></a>YouTube

Para obtener la dirección URL correcta del vídeo, haga clic con el botón derecho en el vídeo, seleccione **Copiar código para insertar**, y copie la dirección URL del elemento `<iframe>`.

```markdown
> [!VIDEO <youtube_video_link>]
```

Por ejemplo:

```markdown
> [!VIDEO https://www.youtube.com/embed/Q2mMbjw6cLA]
```

## <a name="docsmicrosoft-extensions"></a>Extensiones de docs.microsoft

En docs.microsoft se proporcionan varias extensiones adicionales para GitHub Flavored Markdown.

### <a name="checked-lists"></a>Listas de comprobación probadas

Hay disponible un estilo personalizado para las listas. Puede representar listas con marcas de verificación verdes.

```markdown
> [!div class="checklist"]
> * How to create a .NET Core app
> * How to add a reference to the Microsoft.XmlSerializer.Generator package
> * How to edit your MyApp.csproj to add dependencies
> * How to add a class and an XmlSerializer
> * How to build and run the application
```

Esto se representa como:

> [!div class="checklist"]
> * Cómo crear una aplicación .NET Core
> * Cómo agregar una referencia al paquete Microsoft.XmlSerializer.Generator
> * Cómo editar el archivo MyApp.csproj para agregar dependencias
> * Cómo agregar una clase y un XmlSerializer
> * Cómo compilar y ejecutar la aplicación

Puede ver un ejemplo de listas de comprobación en acción en la [documentación de .NET Core](https://docs.microsoft.com/dotnet/core/additional-tools/xml-serializer-generator).

### <a name="buttons"></a>Botones

Vínculos de botón:

```markdown
> [!div class="button"]
[button links](dotnet-contribute.md)
```

Esto se representa como:

> [!div class="button"]
[Vínculos de botón](dotnet-contribute.md)

Puede ver un ejemplo de botones en acción en la [documentación de Visual Studio](https://docs.microsoft.com/visualstudio/install/install-visual-studio#step-2---download-visual-studio).

### <a name="step-by-steps"></a>Guías paso a paso

```markdown
>[!div class="step-by-step"]
[Pre](../docs/csharp/expression-trees-interpreting.md)
[Next](../docs/csharp/expression-trees-translating.md)
```

Puede ver un ejemplo de guía paso a paso en acción en la [guía de C#](https://docs.microsoft.com/dotnet/csharp/tour-of-csharp/program-structure).
