---
title: 'Guía para colaboradores de Microsoft Docs: información general'
description: En esta guía se describe cómo puede contribuir al sitio de documentación de Microsoft docs.microsoft.com.
author: billwagner
ms.author: wiwagn
manager: wpickett
ms.date: 04/17/2018
ms.openlocfilehash: 6206f61a69c14575a726da9ce64ad0b765c7aa87
ms.sourcegitcommit: 886ca76086a302d1d6124967df12a5bcfe4fd4b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2018
ms.locfileid: "40251426"
---
# <a name="microsoft-docs-contributor-guide-overview"></a>Guía para colaboradores de Microsoft Docs: información general

Le damos la bienvenida a la guía para colaboradores de [docs.microsoft.com](https://docs.microsoft.com) (Docs).

Algunos de nuestros conjuntos de documentación son de código abierto y están hospedados en GitHub. Cada vez son más los equipos en Microsoft que están adoptando este modelo. Incluso los conjuntos de documentos que no son completamente de código abierto tienen repositorios públicos en los que se pueden realizar solicitudes de incorporación de cambios. De este modo, se optimiza y se mejora la comunicación entre los ingenieros de productos, los equipos de contenido y nuestros clientes. Al trabajar a la vista, se puede disfrutar de diversas ventajas:

- Los repositorios de código abierto se planean a la vista para obtener comentarios sobre qué documentos son más necesarios.
- Los repositorios de código abierto se revisan a la vista para publicar el contenido más útil en la primera versión.
- Los repositorios de código abierto se actualizan a la vista para facilitar la mejora continua de los contenidos.

La experiencia del usuario de [docs.microsoft.com](https://docs.microsoft.com) integra directamente flujos de trabajo de [GitHub](https://github.com) para que resulte todavía más fácil. Para comenzar, [edite el documento que está viendo](#quick-edits-to-existing-documents). También puede [revisar nuevos temas](#review-open-prs) o [notificar problemas de calidad](#create-quality-issues).

> [!IMPORTANT]
> Todos los repositorios que publican en docs.microsoft.com han adoptado el [Código de conducta de código abierto de Microsoft](https://opensource.microsoft.com/codeofconduct/) o el [Código de conducta de .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Para obtener más información, vea las [preguntas más frecuentes del Código de conducta](https://opensource.microsoft.com/codeofconduct/faq/). O póngase en contacto con [opencode@microsoft.com](mailto:opencode@microsoft.com) o [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) para enviar sus preguntas o comentarios.<br>
>
> Las correcciones menores o aclaraciones de la documentación y los ejemplos de código de los repositorios públicos se rigen por los [Términos de uso del sitio docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). Los cambios importantes o nuevos generan un comentario en la solicitud de incorporación de cambios que le pide que acepte el contrato de licencia de colaboración (CLA, por sus siglas en inglés) si no es un empleado de Microsoft. Necesitamos que rellene el formulario en línea para revisar o aceptar su solicitud de incorporación de cambios.

## <a name="quick-edits-to-existing-documents"></a>Ediciones rápidas en documentos existentes

Las ediciones rápidas optimizan el proceso de notificación y corrección de pequeños errores y omisiones en los documentos. A pesar de todos los esfuerzos, en ocasiones los documentos que publicamos contienen algunos errores gramaticales y erratas. Aunque puede notificar un problema para informar sobre estos errores, es más rápido y fácil crear una solicitud de incorporación de cambios para corregirlo. Prácticamente en todos los artículos aparece un botón para editar, como se muestra en la imagen siguiente. Al hacer clic en el botón **Editar**, se le redirige al archivo de código fuente en GitHub.

![Ubicación del vínculo Editar](./media/index/edit-article.png)

Después, haga clic en el icono de lápiz para editar el artículo, como se muestra en la imagen siguiente.

> [!NOTE]
> Si el icono de lápiz aparece atenuado, debe iniciar sesión en su cuenta de GitHub o crear una cuenta. Haga los cambios necesarios en el editor web. Puede hacer clic en la pestaña **Vista previa de los cambios** para comprobar el formato del cambio.

![Ubicación del icono de lápiz](./media/index/editicon.png)

Una vez que haya realizado los cambios, desplácese hasta la parte inferior de la página. Escriba un título y una descripción para la solicitud de incorporación de cambios y haga clic en **Propose file change** (Proponer cambio de archivo), como se muestra en la imagen siguiente:

![propuesta de cambio](./media/index/submit-pull-request.png)

Eso es todo. Los miembros del equipo de contenido revisarán y combinarán la solicitud de incorporación de cambios. Es probable que reciba un comentario en el que se le solicite algún cambio si ha realizado cambios grandes.

La interfaz de usuario de edición de GitHub responde a sus permisos en el repositorio. Las imágenes anteriores hacen referencia a colaboradores que no tienen permisos de escritura en el repositorio de destino. GitHub crea automáticamente una rama del repositorio de destino en su cuenta. Si tiene acceso de escritura al repositorio de destino, GitHub crea en él una rama. El nombre de la rama tiene el formato **\<GitHubId\>-patch-n**, en el que se usa su identificador de GitHub y un identificador numérico para la rama de la revisión.

Usamos solicitudes de incorporación de cambios para todos los cambios, incluso en el caso de los colaboradores que tienen acceso de escritura. La mayoría de los repositorios tienen la rama `master` protegida para que las actualizaciones se tengan que enviar como solicitudes de incorporación de cambios.

La experiencia de edición en el explorador es mejor para los cambios menores o poco frecuentes. Si realiza grandes colaboraciones o usa características avanzadas de Git (como la administración de ramas o la resolución avanzada de conflictos de fusión), debe [bifurcar el repositorio y trabajar localmente](how-to-write-workflows-major.md).

## <a name="review-open-prs"></a>Revisión de solicitudes de incorporación de cambios abiertas

Para leer nuevos temas antes de que se publiquen, consulte las solicitudes de incorporación de cambios abiertas. Las revisiones siguen el proceso del [flujo de GitHub](https://guides.github.com/introduction/flow/). Puede ver las actualizaciones propuestas o artículos nuevos en los repositorios públicos. Revíselos y agregue sus comentarios. Examine cualquiera de nuestros repositorios de documentos y consulte las solicitudes de incorporación de cambios abiertas para las áreas que le interesen. Los comentarios de la comunidad sobre las actualizaciones propuestas ayudan al conjunto de la comunidad.

## <a name="create-quality-issues"></a>Notificación de problemas de calidad

Nuestros documentos son siempre un trabajo en curso. Los problemas positivos nos ayudan a centrar nuestros esfuerzos en las prioridades de la comunidad. Cuantos más detalles aporte, más útil será el problema notificado. Díganos qué información buscaba. O enumere los términos de búsqueda empleó. Si no es capaz de comenzar, coméntenos cómo le gustaría empezar a explorar una tecnología desconocida.

Los problemas ayudan a iniciar una conversación sobre lo que hace falta. El equipo de contenido responderá a estos problemas con ideas sobre lo que se puede agregar y le pedirá su opinión. Cuando creemos un borrador, le pediremos que [revise la solicitud de incorporación de cambios](#review-open-prs).

## <a name="get-more-involved"></a>Mayor implicación

Otros temas le ayudarán a empezar a colaborar de manera productiva en Microsoft Docs. En ellos se explica cómo trabajar con repositorios de GitHub, herramientas de Markdown y extensiones usadas en la plataforma de Microsoft Docs.
