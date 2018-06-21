---
title: Uso de Markdown para escribir Docs
description: En este artículo se proporciona información básica y de referencia para el lenguaje Markdown que se utiliza para escribir artículos de docs.microsoft.com.
ms.date: 07/13/2017
ms.openlocfilehash: dca1ccba2ae4ebd08b6039f5d780e7a7ac92e79f
ms.sourcegitcommit: 92aef5ea8bdd692c5c393d5c8f99b9e4f672ef2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238975"
---
# <a name="how-to-use-markdown-for-writing-docs"></a>Uso de Markdown para escribir Docs

Los artículos de docs.microsoft.com están escritos en un lenguaje de marcado ligero denominado [Markdown](https://daringfireball.net/projects/markdown/), que resulta fácil de leer y de aprender. Por ello, se ha convertido rápidamente en un estándar del sector.

Como el contenido de Docs está almacenado en GitHub, puede usar un superconjunto de Markdown denominado [GitHub Flavored Markdown (GFM)](https://help.github.com/categories/writing-on-github/), que proporciona una funcionalidad adicional para necesidades comunes de aplicación de formato. Además, la plataforma de Servicios de publicación abierta (OPS) implementa Markdig Markdown Parser. Markdig ofrece una alta compatibilidad con GitHub Flavored Markdown (GFM) y agrega una funcionalidad para habilitar características específicas para Docs.

* Markdig es un procesador de Markdown extensible para .NET rápido, potente y conforme a CommonMark.
* https://github.com/lunet-io/markdig
* Mejor soporte técnico de la comunidad
* Mejor soporte técnico para los estándares

## <a name="markdown-basics"></a>Aspectos básicos de Markdown

### <a name="headings"></a>Encabezados

Para crear un encabezado, debe usar una marca hash (#) como sigue:

```markdown
    # This is heading 1
    ## This is heading 2
    ### This is heading 3
    #### This is heading 4
```

### <a name="bold-and-italic-text"></a>Texto en negrita y cursiva

Para aplicar formato de **negrita** al texto, debe encerrarlo entre dos asteriscos:

```markdown
    This text is **bold**.
```

Para aplicar formato de *cursiva* al texto, debe encerrarlo entre un solo asterisco:

```markdown
    This text is *italic*.
```

Para aplicar formato de ***negrita y cursiva*** al texto, debe encerrarlo entre tres asteriscos:

```markdown
    This is text is both ***bold and italic***.
```

### <a name="lists"></a>Listas

#### <a name="unordered-list"></a>Listas sin ordenar

Para aplicar formato a una lista sin ordenar o con viñetas, puede usar asteriscos o guiones. Por ejemplo, el siguiente código Markdown:

```markdown
- List item 1
- List item 2
- List item 3
```

se representará como:

- Elemento de lista 1
- Elemento de lista 2
- Elemento de lista 3

Para anidar una lista dentro de otra, tiene que aplicar sangría a los elementos de lista secundarios. Por ejemplo, el siguiente código Markdown:

```markdown
- List item 1
  - List item A
  - List item B
- List item 2
```

se representará como:

- Elemento de lista 1
  - Elemento de lista A
  - Elemento de lista B
- Elemento de lista 2

#### <a name="ordered-list"></a>Listas ordenada

Para aplicar formato a una lista ordenada o de pasos, debe usar los números correspondientes. Por ejemplo, el siguiente código Markdown:

```markdown
1. First instruction
2. Second instruction
3. Third instruction
```

se representará como:

1. Primera instrucción
2. Segunda instrucción
3. Tercera instrucción

Para anidar una lista dentro de otra, tiene que aplicar sangría a los elementos de lista secundarios. Por ejemplo, el siguiente código Markdown:

```markdown
1. First instruction
    1. Sub-instruction
    2. Sub-instruction
2. Second instruction
```

se representará como:

1. Primera instrucción
    1. Subinstrucción
    2. Subinstrucción
2. Segunda instrucción

### <a name="tables"></a>Tablas

Las tablas no forman parte de la especificación principal de Markdown, pero son compatibles con GFM. Puede crear tablas con los caracteres de barra vertical (|) y guion (-). Los guiones crean cada encabezado de columna, mientras que las barras verticales separan cada columna. Incluya una línea en blanco antes de la tabla para que se represente correctamente.

Por ejemplo, el siguiente código Markdown:

```markdown
| Fun                  | With                 | Tables          |
| :------------------- | -------------------: |:---------------:|
| left-aligned column  | right-aligned column | centered column |
| $100                 | $100                 | $100            |
| $10                  | $10                  | $10             |
| $1                   | $1                   | $1              |
```

se representará como:

| Diversión                  | Con                 | Tablas          |
| :------------------- | -------------------: |:---------------:|
| columna alineada a la izquierda  | columna alineada a la derecha | columna centrada |
| 100 USD                 | 100 USD                 | 100 USD            |
| 10 USD                  | 10 USD                  | 10 USD             |
| 1 USD                   | 1 USD                   | 1 USD              |

Para obtener más información sobre la creación de tablas, consulte:

- La [característica de ajuste de tabla](#table-wrapping) de Markdig, que puede ayudar a aplicar formato a las tablas anchas
- La [organización de información con tablas](https://help.github.com/articles/organizing-information-with-tables/) de GitHub
- Las aplicación web del [generador de tablas de Markdown](https://www.tablesgenerator.com/markdown_tables)
- La [Hoja de referencia de Adam Pritchard sobre Markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet#wiki-tables)
- La [información adicional de Michel Fortin sobre Markdown](https://michelf.ca/projects/php-markdown/extra/#table)
- [Conversión de tablas HTML en Markdown](https://jmalarcon.github.io/markdowntables/)

### <a name="links"></a>Vínculos

La sintaxis de Markdown de un vínculo insertado consta de la parte `[link text]`, que es el texto que se va a enlazar, seguida de la parte `(file-name.md)`, que es la dirección URL o el nombre de archivo a los que se va a realizar la vinculación:

 `[link text](file-name.md)`

Para obtener más información sobre la vinculación, vea:

- La [guía de sintaxis de Markdown](https://daringfireball.net/projects/markdown/syntax#link) para obtener información detallada sobre la compatibilidad de vínculos base de Markdown.
- La sección [Vínculos](how-to-write-links.md) de esta guía para obtener información sobre la sintaxis de vinculación adicional proporcionada por Markdig.

### <a name="code-snippets"></a>Fragmentos de código

Markdown admite la inserción de fragmentos de código en una oración y como un bloque "delimitado" independiente entre oraciones. Para obtener información, vea:

- [Compatiblidad nativa de Markdown para bloques de código](https://daringfireball.net/projects/markdown/syntax#precode)
- [Compatibilidad de GFM para delimitación de código y resaltado de sintaxis](https://help.github.com/articles/creating-and-highlighting-code-blocks/)

Los bloques de código delimitados son una forma sencilla de habilitar el resaltado de sintaxis de los fragmentos de código. El formato general del bloque de código delimitado es:

    ```alias
    ...
    your code goes in here
    ...
    ```

El alias después de los tres caracteres iniciales de acento grave (`) define el resaltado de sintaxis que se va a usar. A continuación se muestra una lista de lenguajes de programación de uso común en contenido de Docs y la etiqueta asociada:

Estos lenguajes tienen nombres descriptivos y la mayoría de ellos realzan el lenguaje.

|Nombre|Etiqueta de Markdown|
|-----|-------|
|.NET Console|dotnetcli|
|ASP.NET (C#)|aspx-csharp|
|ASP.NET (VB)|aspx-vb|
|AzCopy|azcopy|
|CLI de Azure|azurecli|
|Azure PowerShell|azurepowershell|
|C++|cpp|
|C++/CX|cppcx|
|C++/WinRT|cppwinrt|
|C#|csharp|
|CSHTML|cshtml|
|DAX|dax|
|F#|fsharp|
|Go|go|
|HTML|html|
|HTTP|http|
|Java|java|
|JavaScript|javascript|
|JSON|json|
|Markdown|md|
|NodeJS|nodejs|
|Objective-C|objc|
|OData|odata|
|PHP|php|
|Power Apps Formula|powerappsfl|
|PowerShell|powershell|
|Python|python|
|Q#|qsharp|
|Ruby|ruby|
|SQL|sql|
|Swift|swift|
|TypeScript|typescript|
|VB|vb|
|VSTS CLI|vstscli|
|XAML|xaml|
|XML|xml|

#### <a name="example-c"></a>Ejemplo: C\#

__Markdown__

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

__Representación__

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

#### <a name="example-sql"></a>Ejemplo: SQL

__Markdown__

    ```sql
    CREATE TABLE T1 (
      c1 int PRIMARY KEY,
      c2 varchar(50) SPARSE NULL
    );
    ```

__Representación__

```sql
CREATE TABLE T1 (
  c1 int PRIMARY KEY,
  c2 varchar(50) SPARSE NULL
);
```

## <a name="ops-custom-markdown-extensions"></a>Extensiones de Markdown personalizadas para OPS

> [!NOTE]
> La plataforma de Servicios de publicación abierta (OPS) implementa Markdig Parser para Markdown, que ofrece una alta compatibilidad con GitHub Flavored Markdown (GFM). Markdig agrega algunas funcionalidades a través de extensiones de Markdown. Por tanto, determinados artículos de la guía completa de creación de OPS se han incluido en esta guía a efectos de referencia. Por ejemplo, vea "Markdig and Markdown extensions" (Markdig y extensiones de Markdown) y "Code snippets" (Fragmentos de código) en la tabla de contenido.

Los artículos de Docs usan GFM para aplicar formato a la mayoría de los artículos, como párrafos, vínculos, listas y encabezados. Para un formato más enriquecido, los artículos pueden usar características de Markdig como:

- Bloques de notas
- Archivos de inclusión
- Selectores
- Vídeos insertados
- Ejemplos y fragmentos de código

Para obtener una lista completa, vea "Markdig and Markdown extensions" (Markdig y extensiones de Markdown) y "Code snippets" (Fragmentos de código) en la tabla de contenido.

### <a name="note-blocks"></a>Bloques de notas

Puede elegir entre cuatro tipos de bloques de notas para centrar la atención en contenido específico:

- NOTA
- ADVERTENCIA
- SUGERENCIA
- IMPORTANTE

En general, los bloques de notas deben usarse con moderación porque pueden ser problemáticos. Aunque también admiten bloques de código, imágenes, listas y vínculos, trate de mantener los bloques de notas sencillos y directos.

### <a name="includes"></a>Archivos de inclusión

Si tiene archivos de texto o imagen reutilizables que deben incluirse en archivos de artículos, puede usar una referencia al archivo "de inclusión" a través de la característica de inclusión de archivos de Markdig. Esta característica da la orden a OPS para que incluya el archivo en el archivo del artículo en el momento de la compilación, con lo que se convierte en una parte del artículo publicado. Hay tres tipos de archivos de inclusión disponibles para facilitar la reutilización del contenido:

- Insertado: reutiliza fragmentos de texto comunes insertados en otra oración.
- Bloque: reutiliza un archivo Markdown completo como un bloque, anidado en una sección de un artículo.
- Imágenes: se trata de la forma en que se implementa la inclusión de imágenes estándar en Docs.

Los archivos de inclusión insertados y en bloque no son más que un archivo Markdown (.md) sencillo. Pueden contener cualquier archivo Markdown válido. Todos los archivos de inclusión Markdown deben colocarse en un [subdirectorio `/includes` común](git-github-fundamentals.md#includes-subdirectory), en la raíz del repositorio. Cuando se publica el artículo, el archivo incluido se integra perfectamente en él.

A continuación se indican requisitos y consideraciones relacionados con los archivos de inclusión:

- Use archivos de inclusión siempre que necesite que el mismo texto aparezca en varios artículos.
- Use archivos de inclusión en bloque con volúmenes grandes de contenido, como un párrafo o dos, un procedimiento compartido o una sección compartida. No los use para una unidad inferior a una oración.
- Los archivos de inclusión no se representarán en la vista representada del artículo en GitHub, porque se basan en las extensiones de Markdig. Se representarán después de la publicación.
- Asegúrese de que todo el texto de un archivo de inclusión se escribe en oraciones o frases completas que no dependen del texto anterior o del texto siguiente del artículo al que hace referencia el archivo de inclusión. Si ignora esta instrucción, se crea una cadena no traducible en el artículo que rompe la experiencia localizada.
- No inserte archivos de inclusión en otros archivos de inclusión. No son compatibles.
- Coloque los archivos multimedia en una carpeta de medios específica del subdirectorio de archivos de inclusión, por ejemplo, la carpeta `<repo>`/includes/media. El directorio multimedia no debe contener ninguna imagen en su raíz. Si el archivo de inclusión no tiene imágenes, no se necesita un directorio multimedia correspondiente.
- Como sucede con los artículos habituales, no comparta contenido multimedia entre los archivos de inclusión. Use un archivo independiente con un nombre exclusivo para cada archivo de inclusión y cada artículo. Almacene el archivo multimedia en la carpeta de medios asociada con el archivo de inclusión.
- No use un archivo de inclusión como el único contenido de un artículo.  Se supone que los archivos de inclusión deben ser complementarios al contenido del resto del artículo.

### <a name="selectors"></a>Selectores

Use los selectores en los artículos técnicos cuando cree varias versiones del mismo artículo, a fin de abordar las diferencias de implementación entre tecnologías o plataformas. Esto suele aplicarse sobre todo a nuestro contenido en de plataformas móviles destinado a desarrolladores. Actualmente hay dos tipos diferentes de selectores en Markdig, un selector único y un selector múltiple.

Como se coloca el mismo selector de Markdown en cada artículo de la selección, se recomienda colocar el selector del artículo en un archivo de inclusión. Después, puede hacer referencia a dicho archivo de inclusión en todos los artículos que usan el mismo selector.

### <a name="code-snippets"></a>Fragmentos de código

Markdig admite la inclusión avanzada de código en un artículo, a través de su extensión de fragmento de código. Proporciona una representación avanzada basada en las características de GFM, como la selección del lenguaje de programación y el color de sintaxis, además de características útiles como:

- Inclusión de fragmentos y muestras de código centralizados desde un repositorio externo.
- Interfaz de usuario con pestañas para mostrar varias versiones de ejemplos de código en diferentes lenguajes.

## <a name="gotchas-and-troubleshooting"></a>Dificultades y solución de problemas

### <a name="alt-text"></a>Texto alternativo

El texto alternativo que contiene guiones bajos no se procesa correctamente. Por ejemplo, en lugar de usar esto:

```markdown
![ADextension_2FA_Configure_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

Incluya una secuencia de escape de guiones bajos como se indica a continuación:

```markdown
![ADextension\_2FA\_Configure\_Step4] (./media/bogusfilename/ADextension_2FA_Configure_Step4.PNG)
```

### <a name="apostrophes-and-quotation-marks"></a>Apóstrofos y comillas

Si copia texto de Word en Markdown editor, el texto debe contener apóstrofos o comillas (inglesas) "inteligentes". Es necesario codificarlos o bien cambiarlos a apóstrofos o comillas básicos. De lo contrario, cuando se publique el archivo, aparecerán cosas como esta: Itâ€™s

A continuación se especifica la codificación para las versiones "inteligentes" de estos signos de puntuación:

- Comilla izquierda de apertura: `&#8220;`
- Comilla derecha de cierre: `&#8221;`
- Apóstrofo o comilla simple derecha de cierre: `&#8217;`
- Comilla simple izquierda de apertura (uso poco común): `&#8216;`

### <a name="angle-brackets"></a>Corchetes angulares

Si usa corchetes angulares en el texto (sin codificar) en el archivo, por ejemplo, para denotar un marcador de posición, debe codificar manualmente los corchetes angulares. De lo contrario, Markdown considera que se han insertado como una etiqueta HTML.

Por ejemplo, codifique `<script name>` como `&lt;script name&gt;`.

## <a name="see-also"></a>Otras referencias

### <a name="markdown-resources"></a>Recursos de Markdown

- [Introducción a Markdown](https://daringfireball.net/projects/markdown/syntax)
- [Hoja de referencia rápida sobre Markdown para Docs](./media/documents/markdown-cheatsheet.pdf?raw=true)
- [Aspectos básicos de Markdown en GitHub](https://help.github.com/articles/markdown-basics/)
