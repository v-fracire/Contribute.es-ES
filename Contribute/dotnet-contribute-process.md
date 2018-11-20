---
title: Proceso de contribución a los repositorios de documentación de .NET
description: En este artículo se proporciona una breve introducción a la contribución a los repositorios de documentación de .NET. Obtendrá información sobre los repositorios que se usan, el proceso para organizar el contenido y las directivas para la administración de ejemplos de código y otros recursos.
ms.date: 11/07/2018
ms.openlocfilehash: b83a3080f1abd4df8caaa9d10859760006216e86
ms.sourcegitcommit: 44eb4f5ee65c1848d7f36fca107b296eb7687397
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "51609771"
---
# <a name="process-for-contributing-to-net-docs"></a>Proceso para contribuir a la documentación de .NET

Agradecemos las contribuciones de la comunidad a la documentación. En la lista siguiente se muestran algunas reglas que se deben tener en cuenta a la hora de contribuir a la documentación de .NET:

- **NO** nos sorprenda con solicitudes de incorporación de cambios grandes. En su lugar, abra una incidencia e inicie una discusión de modo que podamos acordar un rumbo antes de que invierta una gran cantidad de tiempo.
- **SIGA** estas instrucciones y directrices de [voz y tono](dotnet-voice-tone.md).
- **USE** el archivo de [plantilla](dotnet-style-guide.md) como punto de partida de su trabajo.
- **CREE** una rama independiente en su bifurcación antes de trabajar en los artículos.
- **SIGA** el [flujo de trabajo de GitHub Flow](https://guides.github.com/introduction/flow/).
- **PUBLIQUE** entradas de blog o tweets (o lo que prefiera) de sus contribuciones con frecuencia.

Seguir estas instrucciones garantizará una mejor experiencia para usted y para nosotros.

## <a name="make-a-contribution-to-net-docs"></a>Realizar una contribución a la documentación de .NET

**Paso 1:** omita este paso para los cambios pequeños. Si le interesa escribir contenido nuevo o revisar de forma exhaustiva el contenido existente, abra una [incidencia](https://github.com/dotnet/docs/issues) en la que se describa lo que quiere hacer.

El contenido de la carpeta **docs** se organiza en secciones que se reflejan en la Tabla de contenido (TOC). Defina dónde se va a ubicar el tema en la Tabla de contenido. Obtenga comentarios sobre su propuesta.

O bien,

También puede elegir entre las incidencias existentes para las que las contribuciones son bienvenidas. En [Projects for .NET Community contributors](https://github.com/dotnet/docs/projects/35) (Proyectos para los Colaboradores de la comunidad de .NET) se enumeran muchas de las incidencias disponibles para los colaboradores de la comunidad. En función de su interés y nivel de compromiso, puede elegir entre incidencias de las categorías siguientes:

- **Mantenimiento**. En esta categoría se incluyen contribuciones bastante simples, como la corrección de vínculos rotos o incorrectos, la adición de ejemplos de código que faltan, o la solución de problemas de contenido limitado. En algunos casos, estos problemas pueden afectar a un gran número de archivos. En ese caso, infórmenos de en qué le gustaría trabajar antes de empezar. Agregue un comentario en la incidencia para avisarnos de que está trabajando en ella.

- **Actualizaciones de contenido**. Debido al tamaño del conjunto de documentación, el contenido se desactualiza con facilidad y requiere revisiones. Además, por diversos motivos, hay contenido duplicado o incluso triplicado. La actualización del contenido implica asegurarse de que los temas individuales son actuales o la revisión del contenido en un área de características para eliminar los duplicados y asegurar que todo el contenido exclusivo se conserva en el conjunto de documentación más pequeño.

- **Creación de contenido**. Si le interesa crear un tema propio, en estas incidencias se enumeran temas que nos gustaría añadir al conjunto de documentación. Pero infórmenos antes de empezar a trabajar en un tema. Si le interesa escribir un tema que no aparece en la lista, abra una incidencia.

También puede examinar la lista de [incidencias abiertas](https://github.com/dotnet/docs/issues) y trabajar de forma voluntaria en las que le interesen. Usamos la etiqueta [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) (disponibles) para las incidencias identificadas para la colaboración de la comunidad. Suelen requerir un contexto mínimo y son adecuadas para primeras incidencias. Recomendamos a los colaboradores con experiencia de la comunidad que examinen las incidencias de interés. Si encuentra una, agregue un comentario para preguntar si está abierta.

Después de elegir una tarea en la que trabajar, siga la guía de [inicio](get-started-setup-github.md) para crear una cuenta de GitHub y configurar el entorno.

**Paso 2:** bifurque los repositorios `/dotnet/docs`, `dotnet/samples`, `dotnet/dotnet-api-docs`, `dotnet/roslyn-api-docs` o `dotnet/ml-api-docs` según sea necesario y cree una rama para los cambios.

Para los cambios pequeños, vea las instrucciones sobre cómo realizar modificaciones en GitHub en la [página principal](index.md#quick-edits-to-existing-documents) de la guía del colaborador.

**Paso 3:** realice los cambios en esta rama nueva.

Si es un tema nuevo, puede usar este [archivo de plantilla](dotnet-style-guide.md) como punto de partida. Contiene las instrucciones de escritura y también se explican los metadatos necesarios para cada artículo, como por ejemplo la información del autor.

Vaya hasta la carpeta correspondiente a la ubicación de la Tabla de contenidos determinada para el artículo en el paso 1. Esa carpeta contiene los archivos Markdown para todos los artículos de esa sección. Si es necesario, cree una carpeta para colocar los archivos del contenido. El artículo principal para esa sección se denomina *index.md*. Para las imágenes y otros recursos estáticos, cree una subcarpeta denominada **media** dentro de la carpeta que contiene el artículo, si todavía no existe. Dentro de la carpeta **media**, cree una subcarpeta con el nombre del artículo (menos para el archivo de índice). El código de ejemplo se debe incluir en el repositorio `dotnet/samples`, como se describe en la sección sobre [ejemplos](#contributing-to-samples).

Asegúrese de seguir la sintaxis de Markdown adecuada. Para obtener ejemplos comunes, vea la [plantilla y hoja de referencia de Markdown](dotnet-style-guide.md).

## <a name="example-structure"></a>Estructura de ejemplo

    docs
      /about
      /core
        /porting
          porting-overview.md
          /media
            /porting-overview
                portability_report.png

**Paso 4:** envíe una solicitud de incorporación de cambios (PR) desde su rama a la rama principal.

> [!IMPORTANT]
> Por el momento la funcionalidad de [automatización de comentarios](how-to-write-workflows-major.md#review-and-sign-off) no está disponible en ninguno de los repositorios de documentación de .NET. Los miembros del equipo de documentación de .NET revisarán y combinarán su PR.

Por lo general, cada PR debe solucionar una incidencia cada vez. La PR puede modificar uno o varios archivos. Si va a abordar varias correcciones en diferentes archivos, es preferible usar PR independientes. Si va a crear ejemplos además de actualizar el marcado, tendrá que crear una PR independiente para los ejemplos.

Si la PR corrige una incidencia existente, agregue la palabra clave `Fixes #Issue_Number` al mensaje de confirmación o la descripción de la PR. De ese modo, la incidencia se cierra automáticamente cuando se combine la PR. Para obtener más información, vea [Closing issues via commit messages](https://help.github.com/articles/closing-issues-via-commit-messages/) (Cierre de incidencias a través de mensajes de confirmación).

El equipo de .NET revisará la PR y le notificará si hay otras actualizaciones o cambios necesarios para poder aprobarla.

**Paso 5:** realice las actualizaciones necesarias en la rama según lo acordado con el equipo.

Los mantenedores combinarán la PR en la rama principal una vez que se hayan aplicado los comentarios y el cambio se haya aprobado.

Periódicamente se envían todas las confirmaciones de la rama principal a la rama activa, y después podrá ver su contribución activa en https://docs.microsoft.com/dotnet/. Por lo general, se realizan publicaciones diarias durante la semana laboral. Las actividades de mantenimiento pueden retrasar unos días la publicación.

## <a name="contributing-to-samples"></a>Contribución a los ejemplos

El repositorio [dotnet/samples](https://github.com/dotnet/samples) contiene todo el código de ejemplo que forma parte de cualquier tema de la documentación de .NET. Hay varios proyectos diferentes que se organizan en subcarpetas. Estas subcarpetas se organizan de forma similar a la documentación de .NET.

Realizamos la distinción siguiente para el código existente en nuestro repositorio:

- Ejemplos: los lectores pueden descargar y ejecutar los ejemplos. Todos los ejemplos deben ser aplicaciones o bibliotecas completas. Cuando en el ejemplo se crea una biblioteca, debe incluir pruebas unitarias o una aplicación que permita a los lectores ejecutar el código. Por lo general, usan más de una tecnología, característica o kit de herramientas. En el archivo readme.md de cada ejemplo se hará referencia al artículo, para que se pueda leer más información sobre los conceptos descritos en cada ejemplo.
- Fragmentos de código: ilustran un concepto o una tarea más pequeña. Se compilan, pero no están pensados para ser aplicaciones completas. Se deben ejecutar correctamente, pero no son una aplicación de ejemplo para un escenario típico. En su lugar, están diseñados con el menor tamaño posible para ilustrar un único concepto o característica. No deben ocupar más de una pantalla de código.

Todo el código se encuentra en el repositorio [dotnet/samples](https://github.com/dotnet/samples). Estamos trabajando para crear un modelo en el que la estructura de nuestra carpeta de ejemplos coincida con la de la carpeta de documentación. Seguimos estos estándares:

- La carpeta *snippets* de nivel superior contiene fragmentos de código de ejemplos más pequeños y concretos.
- Los ejemplos de referencia de API se incluyen en una carpeta con este patrón: *fragmentosDeCódigo/\<Lenguaje>/API/\<espacioDeNombres>/\<nombreDeAPI>*.
- Otras carpetas de nivel superior coinciden con las carpetas de nivel superior del repositorio *docs*. Por ejemplo, el repositorio docs tiene una carpeta *machine-learning/tutorials*, y los ejemplos para los tutoriales de aprendizaje automático se incluyen en la carpeta *samples/machine-learning/tutorials*.

Además, todos los ejemplos situados bajos las carpetas *core* y *standard* se deben compilar y ejecutar en todas las plataformas compatibles con .NET Core. En nuestro sistema de compilación de integración continua se aplicará esta estructura. La carpeta *framework* de nivel superior contiene ejemplos que solo se compilan y validan en Windows.

Los proyectos de ejemplo se deben compilar en el conjunto de plataformas más amplio posible para el ejemplo proporcionado. En la práctica, eso significa la compilación de aplicaciones de consola basadas en .NET Core siempre que sea posible. Los ejemplos específicos de la web o marco de trabajo de la interfaz de usuario deben agregar esas herramientas según sea necesario. Algunos ejemplos son aplicaciones web, aplicaciones móviles, aplicaciones de WPF o WinForms, etc.

Estamos trabajando para implantar un sistema de integración continua para todo el código. Cuando actualice los ejemplos, asegúrese de que todas las actualizaciones formen parte de un proyecto que admita la compilación. Lo ideal sería agregar pruebas de exactitud también en los ejemplos.

Cada ejemplo completo que cree debe contener un archivo *readme.md*. Este archivo debe contener una descripción breve del ejemplo (de uno o dos párrafos). El archivo *readme.md* debe indicar a los lectores lo que van a aprender al explorar este ejemplo. El archivo *readme.md* también debe contener un vínculo al documento activo en el [sitio de documentación de .NET](https://docs.microsoft.com/dotnet/welcome). Para determinar qué parte de un archivo dado del repositorio se asigna a ese sitio, sustituya `/docs` en la ruta de acceso del repositorio por `http://docs.microsoft.com/dotnet`.

El tema también contendrá vínculos al ejemplo. Vincule directamente a la carpeta del ejemplo en GitHub.

### <a name="writing-a-new-snippet-or-sample"></a>Escritura de un nuevo fragmento de código o ejemplo

1. El ejemplo **debe formar parte de un proyecto que admita la compilación**. Siempre que sea posible, los proyectos se deben compilar en todas las plataformas compatibles con .NET Core. Las excepciones son los ejemplos en los que se describe una característica o herramienta concreta de la plataforma.

2. El ejemplo se debe ajustar al [estilo de codificación CoreFX](https://github.com/dotnet/corefx/blob/master/Documentation/coding-guidelines/coding-style.md) para mantener la coherencia.

    - Además, preferimos el uso de métodos `static` en lugar de métodos de instancia cuando se ilustre algo que no requiera la creación de instancias de un objeto nuevo.

3. En el ejemplo se debe incluir el **control de excepciones adecuado**. Debe controlar todas las excepciones que es probable que se inicien en el contexto del ejemplo. Por ejemplo, en un ejemplo en el que se llame al método [Console.ReadLine](https://docs.microsoft.com/dotnet/api/system.console.readline) para recuperar la entrada del usuario, se debe usar el control de excepciones adecuado cuando la cadena de entrada se pase como argumento a un método. De forma similar, si en el ejemplo se espera que se no pueda llamar a un método, se debe controlar la excepción resultante. Controle siempre las excepciones específicas iniciadas por el método, en lugar de las de la clase base como [Exception](https://docs.microsoft.com/dotnet/api/system.exception) o [SystemException](https://docs.microsoft.com/dotnet/api/system.systemexception).

4. Si el ejemplo compila un paquete independiente, debe incluir los runtimes que se usan en nuestro sistema de compilación de integración continua, además de los que se usen en el ejemplo:
    - `win7-x64`
    - `win8-x64`
    - `win81-x64`
    - `ubuntu.16.04-x64`

Implantaremos un sistema de integración continua para compilar estos proyectos en breve.

Para crear un ejemplo:

1. Abra una [incidencia](https://github.com/dotnet/docs/issues) o agregue un comentario a una incidencia existente en la que esté trabajando.
2. Escriba el tema que explique los conceptos descritos en el ejemplo (por ejemplo: `docs/standard/linq/where-clause.md`).
3. Escriba el ejemplo (por ejemplo: `WhereClause-Sample1.cs`).
4. Cree un archivo Program.cs con un punto de entrada Main en el que se llame a los ejemplos. Si ya hay uno, agregue la llamada al ejemplo:
    ```csharp
    public class Program
    {
        public void Main(string[] args)
        {
            WhereClause1.QuerySyntaxExample();

            // Add the method syntax as an example.
            WhereClause1.MethodSyntaxExample();
        }
    }
    ```
Los fragmentos de código o ejemplos de .NET Core se compilan mediante la CLI de .NET Core, que se puede instalar con [el SDK de .NET Core](https://www.microsoft.com/net/download). Para compilar y ejecutar el ejemplo:

1. Vaya a la carpeta de ejemplo y compile para comprobar los errores:

    ```console
    dotnet build
    ```
2. Ejecute el ejemplo:

    ```console
    dotnet run
    ```

3. Agregue un archivo readme.md al directorio raíz del ejemplo. 

   Debe incluir una breve descripción del código y enviar a los usuarios al artículo en el que se hace referencia al ejemplo.

Excepto donde se indique, todos los ejemplos se compilan desde la línea de comandos en todas las plataformas compatibles con .NET Core. Hay algunos ejemplos específicos de Visual Studio y requieren Visual Studio 2017 o una versión posterior. Además, en algunos ejemplos se describen características específicas de la plataforma, y requerirán una plataforma concreta. Otros ejemplos y fragmentos de código requerirán .NET Framework y se ejecutarán en plataformas Windows, y necesitarán el paquete de desarrollador para la versión de Framework de destino.

## <a name="the-c-interactive-experience"></a>La experiencia interactiva de C#

En todos los ejemplos incluidos en un artículo se usa una [etiqueta de lenguaje](how-to-write-use-markdown.md#code-snippets) para indicar el lenguaje fuente. En los ejemplos de código breves de C# se puede usar la etiqueta de lenguaje `csharp-interactive` para especificar un ejemplo de C# que se ejecuta en el explorador. En los ejemplos de código insertado, use la etiqueta `csharp-interactive`; para los ejemplos incluidos desde el origen, use la etiqueta `code-csharp-interactive`. Estos ejemplos de código muestran una ventana de código y una ventana de salida en el artículo. En la ventana de salida se muestra la salida tras ejecutar el código interactivo una vez que el usuario ha ejecutado el ejemplo.

La experiencia interactiva de C# cambia la forma de trabajar con los ejemplos. Los visitantes pueden ejecutar el ejemplo para ver los resultados. Una serie de factores ayudan a determinar si el ejemplo o el texto correspondiente debe incluir información sobre la salida.

### <a name="when-to-display-the-expected-output-without-running-the-sample"></a>Cuándo mostrar la salida esperada sin ejecutar el ejemplo

- Los artículos destinados a principiantes deben proporcionar la salida para que los lectores puedan comparar la de su trabajo con la respuesta esperada.
- Los ejemplos en los que la salida sea integral para el tema deben mostrarla. Por ejemplo, en los artículos sobre texto con formato se debe mostrar el formato de texto sin ejecutar el ejemplo.
- Cuando el ejemplo y la salida esperada son breves, considere la posibilidad de mostrar la salida. Ahorra algo de tiempo.
- En los artículos en los que se explique cómo afecta la referencia cultural actual o la referencia cultural invariable a la salida, se debe explicar la salida esperada. El REPL (bucle de lectura, evaluación e impresión) interactivo se ejecuta en un host basado en Linux. La referencia cultural predeterminada y la referencia cultural invariable generan otra salida en otros sistemas operativos y equipos. El artículo debe explicar la salida en los sistemas Windows, Linux y Mac.

### <a name="when-to-exclude-expected-output-from-the-sample"></a>Cuándo excluir la salida esperada del ejemplo

- En los artículos en los que el ejemplo genere una salida más grande no se debe incluir en los comentarios. Oculta el código una vez ejecutado el ejemplo.
- En los artículos en los que el ejemplo describa un tema, pero la salida no sea esencial para entenderlo. Por ejemplo, el código en el que se ejecuta una consulta LINQ para explicar la sintaxis de la consulta y después se muestran todos los elementos en la colección de salida.

> [!NOTE]
> Es posible que observe que en algunos de los temas no se siguen las instrucciones que se especifican aquí. Estamos trabajando para lograr la coherencia en la totalidad del sitio. Consulte la lista de [incidencias abiertas](https://github.com/dotnet/docs/issues?q=is%3Aopen+is%3Aissue+label%3A%22%3Abookmark_tabs%3A+Information+Architecture%22) de las que en la actualidad estamos realizando el seguimiento para ese objetivo concreto.

## <a name="contributor-license-agreement"></a>Contrato de licencia para el colaborador

Debe firmar el [Contrato de licencia de colaboración de .NET Foundation](https://cla.dotnetfoundation.org) antes de que se combine la PR. Es un requisito único para los proyectos de .NET Foundation. Puede obtener más información sobre los [contratos de licencia de colaboración (CLA)](http://en.wikipedia.org/wiki/Contributor_License_Agreement) en Wikipedia.

El contrato: [net-foundation-contribution-license-agreement.pdf](https://github.com/dotnet/home/blob/master/guidance/net-foundation-contribution-license-agreement.pdf)

No es necesario firmar el contrato por adelantado. Puede clonar, bifurcar y enviar la PR como de costumbre. Cuando se crea la PR, un bot de CAL la clasifica. Si el cambio es pequeño (por ejemplo, ha corregido un error ortográfico), la PR se etiqueta con `cla-not-required`. En caso contrario, se clasifica como `cla-required`. Después de firmar el CLA, la solicitud de incorporación de cambios actual y todas las posteriores se etiquetarán como `cla-signed`.
