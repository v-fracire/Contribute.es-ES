---
title: Flujo de trabajo de colaboración de GitHub para cambios mayores o de larga duración
description: En este artículo se explica cómo usar el flujo de trabajo para colaboradores "principales" con vistas a realizar colaboraciones en los artículos de docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 08/30/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: e26b62923eed22d5b2005b1d84dc4ae240d262b1
ms.sourcegitcommit: dd1b4e915f4996ac029d2a0704ced785438d3484
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2018
---
# <a name="github-contribution-workflow-for-major-or-long-running-changes"></a>Flujo de trabajo de colaboración de GitHub para cambios mayores o de larga duración

> [!IMPORTANT]
> Todos los repositorios que publican en docs.microsoft.com han adoptado el [Código de conducta de código abierto de Microsoft](https://opensource.microsoft.com/codeofconduct/) o el [Código de conducta de .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Para obtener más información, vea las [preguntas más frecuentes del Código de conducta](https://opensource.microsoft.com/codeofconduct/faq/). O póngase en contacto con [opencode@microsoft.com](mailto:opencode@microsoft.com) o [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) para enviar sus preguntas o comentarios.<br>
>
> Las correcciones menores o aclaraciones de la documentación y los ejemplos de código de los repositorios públicos se rigen por los [Términos de uso del sitio docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). Los cambios importantes o nuevos generarán un comentario en la solicitud de incorporación de cambios para solicitarle que acepte el contrato de licencia de colaboración (CLA, por sus siglas en inglés) si no es un empleado de Microsoft. Deberá rellenar el formulario en línea para que se pueda fusionar la solicitud de incorporación de cambios.

## <a name="overview"></a>Información general

Este flujo de trabajo resulta conveniente para un colaborador que necesita realizar un cambio mayor o que será un colaborador frecuente de un repositorio. Los colaboradores frecuentes suelen realizar cambios constantes (de larga duración), que pasan por varios ciclos de compilación, validación y almacenamiento provisional o duran varios días antes de aprobar y fusionar la solicitud de incorporación de cambios.

Los ejemplos de estos tipos de colaboradores incluyen:

[!INCLUDE[contribute-major-changes-change-definition](includes/contribute-how-to-write-workflows-major-change-definition.md)]

### <a name="terminology"></a>Terminología

Antes de empezar, debe revisar algunos de los términos y moniker de Git/GitHub utilizados en este flujo de trabajo. No se preocupe ahora si no los entiende. Solo debe saber que la información proporcionada está relacionada con ellos y que puede volver a consultar esta sección cuando necesite comprobar una definición.

| Nombre | Descripción |
|-----------|-------------|
|bifurcación|Suele usarse como sustantivo para hacer referencia a una copia de un repositorio principal de GitHub. En la práctica, una bifurcación no es más que otro repositorio. No obstante, resulta especial por el hecho de que GitHub establece una nueva conexión con el repositorio principal o primario. A veces se usa como verbo, como en el caso de "Primero debe bifurcar el repositorio".|
|Conexión remota|Una conexión con nombre a un repositorio remoto, como la conexión remota con el "origen" o con el repositorio "ascendente". Git hace referencia a estos supuestos con el término "conexiones remotas", ya que estas se usan para hacer referencia a un repositorio hospedado en otro equipo. En este flujo de trabajo, una conexión remota es siempre un repositorio de GitHub.|
|origen|El nombre asignado a la conexión entre el repositorio local y el repositorio a partir del que se ha realizado la clonación. En este flujo de trabajo, el origen representa la conexión con la bifurcación. A veces se usa como un moniker para el repositorio de origen, como en "Recuerde insertar los cambios en el origen".|
|ascendente|Como la conexión remota al origen, el término "ascendente" se corresponde con una conexión con nombre a otro repositorio. En este flujo de trabajo, el término "ascendente" representa la conexión entre el repositorio local y el repositorio principal a partir del que se creó la bifurcación. A veces se usa como un moniker para el repositorio ascendente, como en "Recuerde extraer los cambios del repositorio ascendente".|

## <a name="workflow"></a>Flujo de trabajo

>[!IMPORTANT]
> Si aún no lo ha hecho, debe completar estos pasos en la sección de [configuración](get-started-setup-github.md). Esta sección sirve de guía para configurar la cuenta de GitHub, instalar Git Bash y Markdown editor, crear una bifurcación y configurar el repositorio local. Si no está familiarizado con los conceptos de Git o de GitHub, como los repositorios o las ramas, primero revise el artículo [Aspectos básicos sobre Git y GitHub](git-github-fundamentals.md).

En este flujo de trabajo, los cambios se realizan dentro de un ciclo repetitivo. A partir del repositorio local del dispositivo, los cambios se dirigen a la bifurcación de GitHub, entran en el repositorio principal de GitHub y vuelven a la ubicación local mientras se incorporan los cambios de otros colaboradores.

### <a name="use-github-flow"></a>Uso del flujo de GitHub

Según se indica en el artículo [Aspectos básicos sobre Git y GitHub](git-github-fundamentals.md#git), un repositorio de Git contiene una bifurcación principal, además de ramas de trabajo en proceso que no se han integrado en la principal. Siempre que incorpore un conjunto de cambios relacionados de forma lógica, un procedimiento recomendado consiste en crear una *rama de trabajo* para administrar los cambios a través del flujo de trabajo. Se hace referencia aquí a ello como rama de trabajo porque se trata de un área de trabajo donde se iteran y se refinan los cambios, hasta que se vuelven a integrar en la rama principal.

El aislamiento de cambios relacionados en una rama específica permite controlar e incorporar dichos cambios de forma independiente, para centrarse en ellos en un momento de lanzamiento especifico durante el ciclo de publicación. En realidad, en función del tipo de trabajo que realice, podría terminar fácilmente con varias ramas de trabajo en el repositorio. No es raro trabajar en varias ramas al mismo tiempo, pues cada una de ellas representa un proyecto diferente.

>[!TIP]
>Realizar los cambios directamente en la rama principal *no* es un procedimiento recomendado. Imagine que usa la rama principal para incorporar una serie de cambios para el lanzamiento de una característica en un momento determinado. Ha terminado de incorporar los cambios y espera a que se lancen. Mientras tanto, tiene una solicitud urgente para corregir algo, por lo que hace un cambio en un archivo en la rama principal y después publica el cambio. En este ejemplo, publicaría de forma involuntaria la corrección *y* los cambios cuyo lanzamiento esperaba en una fecha concreta.

Ahora vamos a crear una rama de trabajo en el repositorio local, para capturar los cambios propuestos. Cada cliente de Git es diferente, así que consulte la ayuda para su cliente preferido. Puede ver un resumen del proceso en la guía de GitHub, en [GitHub Flow](https://guides.github.com/introduction/flow/).

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Pasos siguientes

Eso es todo. Ya ha hecho una colaboración en el contenido de docs.microsoft.com.

- Para obtener más información sobre temas como Markdown y la sintaxis de las extensiones de Markdown, continúe con la sección de los aspectos básicos de escritura.
