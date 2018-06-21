---
title: Aspectos básicos sobre Git y GitHub para documentación
description: En este artículo se ofrece información general sobre Git, el repositorio GitHub, la organización del contenido y las convenciones de nomenclatura usadas para docs.microsoft.com.
ms.date: 06/30/2017
ms.openlocfilehash: 8a116067fdd7d031c560abfb7055236e0bfb1a3d
ms.sourcegitcommit: 92aef5ea8bdd692c5c393d5c8f99b9e4f672ef2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36239811"
---
# <a name="git-and-github-essentials-for-docs"></a>Aspectos básicos sobre Git y GitHub para Docs

## <a name="overview"></a>Información general

Como colaborador del contenido de Docs interactuará con múltiples herramientas y procesos. Además, trabajará en paralelo con otros colaboradores en el mismo proyecto, posiblemente sobre el mismo contenido e incluso al mismo tiempo. Todo esto es posible gracias al software de Git y GitHub.

Git es un sistema de control de versiones de código abierto. Facilita este tipo de colaboración de proyectos a través del *control de versiones distribuido* de los archivos que residen en los *repositorios*. Básicamente, Git permite integrar los flujos de trabajo realizados por varios colaboradores a lo largo del tiempo en relación con un repositorio determinado.

GitHub es un servicio de hospedaje basado en Web de repositorios de Git, como los que se usan para almacenar contenido de [docs.microsoft.com](https://docs.microsoft.com). Para un proyecto concreto, GitHub hospeda el repositorio principal, del que los colaboradores pueden realizar copias para llevar a cabo su propio trabajo.

## <a name="git"></a>Git

Si está familiarizado con los sistemas centralizados de control de versiones (como Team Foundation Server, SharePoint o Visual SourceSafe), observará que Git tiene un flujo de trabajo de colaboración y una terminología exclusivos para admitir su modelo distribuido. Por ejemplo, no hay ningún bloqueo de archivo que suela estar asociado con las operaciones de protección y desprotección. De hecho, Git realmente se ocupa de los cambios a un nivel más pormenorizado, ya que compara los archivos byte por byte.

Git también una estructura en capas para almacenar y administrar el contenido de un proyecto:

- *Repositorio*: se conoce también como *repo* y se trata de la unidad de almacenamiento más grande. Un repositorio contiene una o varias ramas.
- *Rama*: unidad de almacenamiento que contiene los archivos y las carpetas que componen el conjunto de contenido de un proyecto. Las ramas separan los flujos de trabajo, a los que se suele hacer referencia como versiones. Las colaboraciones siempre se realizan en una rama específica, a la que están limitadas exclusivamente. Todos los repositorios contienen una rama predeterminada (que suele denominarse "principal") y una o varias ramas destinadas a fusionarse en la rama "principal". La rama principal sirve como la versión actual y la "única fuente de confianza" del proyecto. Se trata del elemento principal a partir del que se crean todas las demás ramas del repositorio.

Los colaboradores interactúan con Git para actualizar y manipular los repositorios tanto a nivel local como en GitHub:

- La colaboración puede realizarse de forma local con herramientas como la consola de Git Bash, que admite los comandos de Git para administrar los repositorios locales y establecer conexiones con los repositorios de GitHub.
- También puede realizarse directamente en [www.github.com](https://www.github.com), donde se integra Git para administrar la conciliación de las colaboraciones que se dirigen de nuevo al repositorio principal.

## <a name="github"></a>GitHub

> [!NOTE]
> Aunque las instrucciones de Docs se basan en el uso de GitHub, algunos equipos usan Visual Studio Team Services para hospedar los repositorios de Git. El cliente Visual Studio Team Explorer proporciona una interfaz gráfica de usuario (GUI) para interactuar con los repositorios de Team Services, que es una alternativa al uso de los comandos de Git a través de una línea de comandos.
> </br>
> Además, muchas de las instrucciones siguientes se han desarrollado como procedimientos recomendados aprendidos a lo largo de años de experiencia en el hospedaje del contenido del servicio de Azure en GitHub. Pueden ser necesarias en algunos repositorios de Docs.

Todos los flujos de trabajo empiezan y terminan en GitHub, donde se almacena el repositorio principal de cualquier proyecto de Docs específico. Las copias que los colaboradores crean para su propio uso se distribuyen entre varios equipos. Estas copias se concilian finalmente en el repositorio de GitHub principal del proyecto.

### <a name="directory-organization"></a>Organización de directorios

Como se ha mencionado anteriormente, la rama predeterminada o principal de un proyecto sirve como la versión actual del contenido del proyecto. El contenido de la rama principal y de las ramas creadas a partir de ella se alinea de forma general con la organización de los artículos en las páginas de Docs correspondientes. Los subdirectorios se usan para separar el contenido similar (como los servicios) y el contenido multimedia (como los archivos de imagen), e "incluyen" archivos, que permiten reutilizar el contenido.

Por norma general, encontrará un directorio principal `articles` que parte directamente de la raíz del repositorio. El directorio de artículos contiene un conjunto de subdirectorios. Los artículos de los subdirectorios presentan el formato de archivos Markdown, que usan una extensión *.md*. Algunos repositorios compatibles con varios servicios usan un subdirectorio `/articles` genérico, como el repositorio [https://github.com/microsoft/Azure-Docs](https://github.com/microsoft/Azure-Docs). Otros pueden usar un nombre específico del servicio, como el repositorio [https://github.com/microsoft/IntuneDocs](https://github.com/microsoft/IntuneDocs), que usa `/IntuneDocs`.

En la raíz de este directorio, puede encontrar artículos generales relacionados con el servicio o producto general. Además, normalmente puede encontrar otra serie de subdirectorios, que concilian las características y los servicios o escenarios comunes. Por ejemplo, los artículos sobre "máquinas virtuales" de Azure se encuentran en el subdirectorio `/virtual-machines`, y los artículos de "comprensión y exploración" de Intune, en el subdirectorio `/understand-explore`.

### <a name="media-subdirectory"></a>Subdirectorio multimedia

Cada directorio de artículos contiene un subdirectorio `/media` para los archivos multimedia correspondientes. Los archivos multimedia contienen las imágenes que usan los artículos que tienen referencias de imagen.

### <a name="includes-subdirectory"></a>Subdirectorio de archivos de inclusión

Siempre que tengamos contenido reutilizable que se comparta entre dos o más artículos, se coloca en un subdirectorio `/includes` que parte directamente del directorio `articles` principal. En un archivo Markdown que use el archivo de inclusión, se coloca una extensión de Markdown "include" correspondiente en la ubicación en la que debe estar la referencia al archivo de inclusión.

Vea [Uso de Markdown: archivos de inclusión](how-to-write-use-markdown.md#includes) para obtener orientación adicional.

### <a name="markdown-file-template"></a>Plantilla de archivo Markdown

Para mayor comodidad, el directorio raíz de cada repositorio suele contener un archivo de plantilla Markdown denominado `template.md`. Puede usar este archivo de plantilla como un "archivo de inicio" si necesita crear un artículo que quiere enviar al repositorio. El archivo contiene los siguientes elementos:

- Un **encabezado de metadatos** en la parte superior, delimitado por dos líneas de tres guiones. Incluye las diferentes etiquetas que se usan para realizar el seguimiento de la información relacionada con el artículo. Los metadatos de los artículos habilitan ciertas funcionalidades, como la atribución de autor, la atribución de colaborador, las rutas de navegación y las descripciones de los artículos. También incluyen optimizaciones del motor de búsqueda, así como procesos de creación de informes que Microsoft usa para evaluar el rendimiento del contenido. Por lo tanto, los metadatos son importantes.
- Una **sección de metadatos** en la que se describen las diferentes etiquetas y valores de metadatos. Si no está seguro de los valores que debe usar en la sección de metadatos, puede dejarlos en blanco o comentarlos con un hashtag inicial (#), y el revisor de la solicitud de incorporación de cambios del repositorio los revisará o los completará.
- Varios **ejemplos del uso de Markdown** para dar formato a los elementos de un artículo.
- **Instrucciones generales sobre el uso de extensiones de Markdown**, que puede usar para varios tipos de alertas.
- Ejemplos de **vídeo insertado** mediante un iframe.
- **Instrucciones generales sobre el uso de extensiones de docs.microsoft.com**, que puede usar para controles especiales, como botones y selectores.

## <a name="pull-requests"></a>Solicitudes de incorporación de cambios

Una *solicitud de incorporación de cambios* es un método cómodo para que un colaborador proponga una serie de cambios aplicables a la rama predeterminada. Los cambios (conocidos también como *confirmaciones*) se almacenan en la rama de un colaborador, de tal forma que se permite a GitHub modelar primero el impacto que tiene *fusionarlos* en la rama predeterminada. Una solicitud de incorporación de cambios también sirve como un mecanismo para proporcionar comentarios al colaborador sobre un proceso de compilación o validación, para que el revisor de la solicitud pueda resolver los posibles problemas o preguntas antes de que los cambios se fusionen en la rama predeterminada.

Hay dos maneras de contribuir por solicitud de extracción, en función del tamaño de los cambios que quiere proponer. Trataremos esta cuestión más a fondo posteriormente, en la sección sobre el [flujo de trabajo de GitHub](how-to-write-workflows-major.md) de esta guía.

<!---- Reference links for Docs landing pages, associated GitHub repositories, and related Forums matrix. ------------------>
<!---- PLEASE INSERT URLS IN ASCENDING SORT ORDER, AND REMOVE LOCALE SEGMENT FROM URLS (that is, en-us) FOR LOCALIZED FORUMS! -->
<!---- NOTE: these links are saved for future use in another/new article; no longer used above in this article --->
[Visual-Studio-Page]:(https://docs.microsoft.com/en-us/visualstudio/index)
[Visual-Studio-Repo-Internal]:(https://github.com/Microsoft/vsdocs)
[Visual-Studio-Repo-External]:(https://github.com/Microsoft/visualstudio-docs)
[Visual-Studio-SO]: (https://stackoverflow.com/search?q=Visual+Studio+2017)
[Dotnet-Page]: https://docs.microsoft.com/dotnet
[Dotnet-Core-Page]: https://docs.microsoft.com/dotnet/articles/welcome
[Dotnet-Core-Repo]: https://github.com/dotnet/docs
[EM-ATA-Land]: https://docs.microsoft.com/advanced-threat-analytics/
[EM-ATA-Repo]: https://github.com/Microsoft/ATADocs
[EM-AzureAD-Land]: https://docs.microsoft.com/active-directory/
[EM-AzureAD-Repo]: https://github.com/Azure/azure-content/tree/master/articles/active-directory/
[EM-AzureRMS-Land]: https://docs.microsoft.com/rights-management/
[EM-AzureRMS-Repo]: https://github.com/Microsoft/Azure-RMSDocs
[EM-Intune-Land]: https://docs.microsoft.com/intune/
[EM-Intune-Repo]: https://github.com/microsoft/intuneDocs
[EM-Land-Page]: https://docs.microsoft.com/enterprise-mobility/
[EM-Land-Repo]: https://github.com/Microsoft/EMDocs/
[EM-MFA-Land]: https://docs.microsoft.com/multi-factor-authentication/
[EM-MFA-Repo]: https://github.com/Azure/azure-content/tree/master/articles/multi-factor-authentication
[EM-MIM-Land]: https://docs.microsoft.com/microsoft-identity-manager/
[EM-MIM-Repo]: https://github.com/Microsoft/MIMDocs
[EM-RemoteApp-Land]: https://docs.microsoft.com/en-us/remoteapp/
[EM-RemoteApp-Repo]: https://github.com/Azure/azure-content/tree/master/articles/remoteapp
[Forum-MSDN-ATA]: https://social.technet.microsoft.com/Forums/en-US/home?forum=mata
[Forum-MSDN-AzureAD]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=WindowsAzureAD
[Forum-MSDN-AzureRMS]: https://social.technet.microsoft.com/Forums/en-US/home?forum=rmsapps%2Crmscloud&filter=alltypes&sort=lastpostdesc
[Forum-MSDN-EM]: https://social.technet.microsoft.com/Forums/en-US/home?sort=relevancedesc&brandIgnore=True&searchTerm=Enterprise+Mobility
[Forum-MSDN-Intune]: https://social.technet.microsoft.com/Forums/en-us/home?category=microsoftintune
[Forum-MSDN-Main]: https://social.msdn.microsoft.com/Forums/home
[Forum-MSDN-MFA]: https://social.msdn.microsoft.com/Forums/en-US/home?forum=windowsazureactiveauthentication
[Forum-MSDN-MIM]: https://social.technet.microsoft.com/Forums/en-US/home?category=identitymanagement
[Forum-MSDN-RemoteApp]: https://social.technet.microsoft.com/Forums/en-US/home?filter=alltypes&brandIgnore=True&sort=relevancedesc&searchTerm=Azure+Remote+or+RemoteApp
[Forum-SO-AzureAD]: https://stackoverflow.com/questions/tagged/azure-active-directory
[Forum-SO-AzureRMS]: https://stackoverflow.com/questions/tagged/rights-management
[Forum-SO-Dotnet]: https://stackoverflow.com/questions/tagged/.net
[Forum-SO-Dotnet-Core]: https://stackoverflow.com/questions/tagged/.net-core
[Forum-SO-Main]: https://stackoverflow.com/tags
[Forum-SO-Intune]: https://stackoverflow.com/questions/tagged/intune
[Forum-SO-MFA]: https://stackoverflow.com/search?q=%5Bazure%5D+multi-factor
[Forum-SO-MIM]: https://stackoverflow.com/search?q=Microsoft+Identity+Manager
[Forum-SO-RemoteApp]: https://stackoverflow.com/questions/tagged/remoteapp
[Forum-TechNet-Main]: https://social.technet.microsoft.com/Forums/home
[Forum-Yammer-AzureRMS]: https://www.yammer.com/AskIPTeam
[Forum-Yammer-Main]: https://www.yammer.com/
