---
title: Contribución a docs.microsoft.com
description: En este artículo se describen las diferentes formas de aportar contenido a docs.microsoft.com.
author: billwagner
ms.author: wiwagn
manager: wpickett
ms.date: 01/17/2018
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: bc6f9c314eda5f0d950da049374a7a157f16782a
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-contribute-to-docsmicrosoftcom"></a>Contribución a docs.microsoft.com

Hay diferentes formas de colaborar en la mejora del contenido que se ofrece en [docs.microsoft.com](https://docs.microsoft.com):

- Puede [crear problemas](#create-issues) para recomendar nuevos artículos o mejorar los artículos existentes.
- Puede [editar rápidamente](#quick-edits) artículos para hacer pequeños cambios en el editor en línea de GitHub.
- Puede [revisar los borradores de nuevos artículos](#review-new-articles) para asegurar la calidad y precisión técnica.
- Puede [crear artículos](#create-new-articles) para temas si desea ayudar a impulsar la historia del contenido.
- Puede [actualizar](#update-samples) o [crear](#create-samples) ejemplos para mejorar los ejemplos de código que refuerzan conceptos importantes.

En este artículo, obtendrá información sobre las diferentes formas de colaborar, la manera de realizar cada una de las tareas de colaboración y cómo encontrar vínculos a más información sobre cada una de esas tareas.

Los repositorios públicos están hospedados en [GitHub](https://wwww.GitHub.com).  Debe crear una cuenta en GitHub para participar en nuestros repositorios de documentación.

También necesita un editor de texto para actualizar los documentos. Se recomienda [Visual Studio Code](https://www.visualstudio.com/code). Debe tener conocimientos básicos de la sintaxis de [Markdown](https://daringfireball.net/projects/markdown/syntax).

Si va a agregar o modificar ejemplos, precisa de un entorno de desarrollo. Se recomienda [Visual Studio](https://www.visualstudio.com) en PC y Mac, o [Visual Studio Code](https://www.visualstudio.com/code) en todas las plataformas.

## <a name="create-issues"></a>Creación de problemas

Si encuentra omisiones o imprecisiones en un artículo, cree un problema para ese artículo. La manera más fácil de encontrar la ubicación correcta es hacer clic en el botón "Edit" (Editar) en el explorador, que le llevará al origen del artículo en el repositorio de GitHub público adecuado. Desde ahí, puede recuperar la dirección URL del origen del artículo en la barra de direcciones. Haga clic en "Create Issue" (Crear problema) para crear un problema con el artículo.

> [!NOTE]
> Si encuentra problemas que se pueden corregir con pequeñas modificaciones, como errores tipográficos o gramaticales, puede ahorrar tiempo tanto para usted como para nosotros si [envía la corrección](#quick-edits) mediante el explorador para modificar el artículo original.

La mayoría de los repositorios públicos contienen plantillas para los nuevos problemas que le ayudarán a proporcionar la información necesaria para corregir el problema.

También puede contribuir con nuevos problemas en los que no pueda encontrar la información que necesita. El proceso es el mismo: cree un problema en alguno de los repositorios públicos de Docs. Díganos lo que busca, lo que quiere hacer y por qué los archivos que encuentra no le sirven como esperaba.

## <a name="review-new-articles"></a>Revisión de nuevos artículos

Si trabaja con software nuevo, posiblemente CTP o beta, es probable que la creación de los documentos esté en curso mientras explora sobre la tecnología. Puede encontrar documentos en proceso en nuestros repositorios públicos. Si tiene comentarios, puede ayudarnos a mejorarlos antes de su publicación.

Los artículos nuevos se revisan de forma pública, con el proceso de [GitHub Flow](https://guides.github.com/introduction/flow/). Examine cualquiera de nuestros repositorios de documentos y consulte las solicitudes de incorporación de cambios abiertas. Agradecemos los comentarios y opiniones enviados en las solicitudes de incorporación de cambios abiertas. Nos ayudan a mejorar el contenido en la primera versión, en lugar de tener que esperar a recibir los comentarios después de publicarlo.

Estamos estudiando formas de mejorar la precisión técnica, la claridad de las descripciones y la precisión gramatical.

## <a name="quick-edits"></a>Ediciones rápidas

Las ediciones rápidas son una forma de realizar pequeñas correcciones mediante el editor basado en el explorador. Si encuentra pequeños errores tipográficos o gramaticales o nombres incorrectos de API, puede omitir la creación de un problema si realiza la modificación y envía una solicitud de incorporación de cambios.

En cualquier artículo, haga clic en el botón "Edit" (Editar) (normalmente, en la parte superior derecha de la página), realice las modificaciones y haga clic en "Submit PR" (Enviar solicitud de incorporación de cambios) en la parte inferior de la página. Revisaremos la solicitud de incorporación de cambios y la fusionaremos mientras hacemos las revisiones diarias de estas solicitudes.

## <a name="create-new-articles"></a>Creación de artículos

Si hay conceptos que le apasionan y quiere explicarlos a otros, puede crear artículos y enviar una solicitud de incorporación de cambios.

Crear artículos lleva mucho tiempo y, por ello, agradecemos su tiempo y sus contribuciones. Preferimos participar al inicio del proceso para asegurarnos del cumplimiento de nuestras directrices y estilo desde el principio. Se recomiendan los pasos siguientes:

1. [Cree un problema](#create-issues) en el que describa lo que falta y cómo solucionarlo.
1. Comente el problema, indicando que le gustaría trabajar en él y sugiriendo un esquema y un resumen del artículo.
1. Le responderemos con sugerencias. En ellas se podrán incluir vínculos a artículos relacionados, sugerencias de ejemplos o cómo se organizará el artículo.
1. Si estamos de acuerdo con el esquema, bifurque el repositorio y empiece a trabajar.
1. En la primera fase del proceso, abra una solicitud de incorporación de cambios, con "[WIP] al principio del título.
1. Uno de los principales colaboradores le proporcionará sus comentarios.
1. Siga escribiendo y mencione, con @-mention, a la persona que revisó el primer borrador cuando quiera recibir más comentarios.
1. Elimine "[WIP]" cuando esté listo para la revisión final.
1. Respuesta a los comentarios
1. Los colaboradores principales fusionarán su solicitud de incorporación de cambios.

Hay un par de puntos de la lista que habría que ampliar. Por norma general, seguimos el proceso de [GitHub Flow](https://guides.github.com/introduction/flow/) para revisar el contenido lo antes posible. De esta forma, acordamos dónde debe ir el artículo en la tabla de contenido, qué ventajas aportará el nuevo artículo al lector y el ámbito de cualquier ejemplo que se cree. Podemos realizar las correcciones necesarias sobre la marcha en una fase temprana, antes de que ya haya dedicado demasiado tiempo a escribir.

## <a name="update-samples"></a>Actualización de ejemplos

Puede que algunos ejemplos se escribieran originalmente para varias versiones anteriores, con prácticas que ya no se recomiendan. Puede ayudarnos a actualizar dichos ejemplos. También puede observar que un sencillo cambio de nombre de variable podría aumentar la claridad de una explicación.

Los códigos de ejemplo mostrados con cada artículo forman parte de los programas compilados y se suelen probar en nuestro sistema de integración continua (CI).

Para realizar pequeñas actualizaciones, localice el origen en el repositorio apropiado, realice el cambio de código en el explorador y envíe una solicitud de incorporación de cambios. El sistema de CI generará los cambios, y nosotros fusionaremos la solicitud de incorporación de cambios cuando el sistema termine.

Si se trata de cambios a gran escala, bifurque el repositorio y realice los cambios en su entorno de desarrollo favorito. Asegúrese de agregar algunas pruebas para garantizar que los cambios se aplican según lo previsto. Envíe una solicitud de incorporación de cambios y nosotros la revisaremos.

Para todos los cambios de código, siga las convenciones de código existentes para el código de ejemplo que va a modificar. Las normas de codificación de nuestros repositorios de ejemplo reflejarán las de los equipos de productos correspondientes. Compruebe cada repositorio para obtener instrucciones específicas.

> [!NOTE]
> Estamos trabajando para seguir estas instrucciones nosotros mismos. Algunos de los ejemplos anteriores a las normas actuales aún no se han actualizado. Estamos trabajando para conseguir el objetivo de que todo el código de ejemplo en ejecución se muestre para fines de trabajo, pruebas y ejemplos.

## <a name="create-samples"></a>Creación de ejemplos

También puede crear ejemplos que muestren conceptos o escenarios. Los ejemplos deben ir acompañados de un artículo en el que se explique la información principal del ejemplo.

Si un ejemplo nuevo complementa un artículo existente, agregue una referencia al ejemplo en dicho artículo. De lo contrario, colabore con nosotros para [escribir el artículo](#create-new-articles) que acompaña al ejemplo.

En cualquier caso, nuestro código de ejemplo sigue las convenciones de codificación utilizadas por los equipos de productos relacionados. Una excepción es que es más probable que utilicemos variables escritas de forma explícita en lugar de escribirlas de forma implícita (declaradas con `var`), a fin de aportar claridad cuando tales declaraciones se incluyan en el artículo.

Siga el proceso de ejemplo descrito en la sección anterior para [nuevos artículos](#create-new-articles), a fin de que podamos revisar el código al principio del proceso de desarrollo.
