---
title: Flujo de trabajo de colaboración de GitHub para cambios menores o poco frecuentes
description: En este artículo se explica cómo usar el flujo de trabajo para colaboradores "secundarios" con vistas a realizar colaboraciones en los artículos de docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 10/06/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 8bde44d502e1942b0870df9dd546a97705c2bb4f
ms.sourcegitcommit: de6e6b6ca641fdd5b30eb46deee9ac3a500089ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="github-contribution-workflow-for-minor-or-infrequent-changes"></a>Flujo de trabajo de colaboración de GitHub para cambios menores o poco frecuentes

> [!IMPORTANT]
> Todos los repositorios que publican en docs.microsoft.com han adoptado el [Código de conducta de código abierto de Microsoft](https://opensource.microsoft.com/codeofconduct/) o el [Código de conducta de .NET Foundation](https://dotnetfoundation.org/code-of-conduct). Para obtener más información, vea las [preguntas más frecuentes del Código de conducta](https://opensource.microsoft.com/codeofconduct/faq/). O póngase en contacto con [opencode@microsoft.com](mailto:opencode@microsoft.com) o [conduct@dotnetfoundation.org](mailto:conduct@dotnetfoundation.org) para enviar sus preguntas o comentarios.<br>
>
> Las correcciones menores o aclaraciones de la documentación y los ejemplos de código de los repositorios públicos se rigen por los [Términos de uso del sitio docs.microsoft.com](https://docs.microsoft.com/legal/termsofuse). Los cambios importantes o nuevos generarán un comentario en la solicitud de incorporación de cambios para solicitarle que acepte el contrato de licencia de colaboración (CLA, por sus siglas en inglés) si no es un empleado de Microsoft. Necesitamos que rellene el formulario en línea para aceptar su solicitud de incorporación de cambios.

## <a name="overview"></a>Información general

Este flujo de trabajo es conveniente para realizar cambios menores o poco frecuentes, mediante el uso de Markdown editor basado en Web de GitHub. El editor de GitHub presenta restricciones de uso, ya que la interfaz de usuario no admite todos los escenarios de creación ni todas las operaciones de Git. Si necesita realizar grandes colaboraciones o admitir características avanzadas de Git (como la administración de bifurcaciones o la resolución avanzada de conflictos de fusión), consulte el [flujo de trabajo para cambios mayores o de larga duración](full-workflow.md).

## <a name="procedure-for-using-the-github-editor-to-propose-your-changes"></a>Procedimiento de uso del editor de GitHub para proponer cambios

1. Vaya al repositorio de GitHub y al archivo Markdown correspondientes a su artículo. Puede usar cualquiera de los métodos siguientes:

   - Examine los archivos Markdown del repositorio de GitHub relacionado para buscar el artículo.
   - Vaya al artículo en [docs.microsoft.com](https://docs.microsoft.com/) y seleccione el vínculo **Editar** que encontrará en la esquina superior derecha de la página.

     ![Ubicación del vínculo Editar](./media/light-workflow/contributetogit.png)

2. Seleccione el icono de lápiz **Editar este archivo** para entrar en el modo de edición:

    ![Ubicación del icono de lápiz](./media/light-workflow/editicon.png)

3. Realice los cambios con Markdown en la pestaña **Editar archivo** y previsualice los cambios en la pestaña **Vista previa de los cambios**. El uso del editor es bastante sencillo, pero puede consultar las siguientes guías si necesita ayuda:

   - [Uso de Markdown](how-to-write-use-markdown.md)
   - [Creación de archivos en GitHub](https://github.com/blog/1327-creating-files-on-github)
   - [Carga de archivos en los repositorios](https://github.com/blog/2105-upload-files-to-your-repositories)

4. Desplácese hasta el final de la página, donde verá algunos de los elementos siguientes:

   - **Proponer cambio de archivo**: se muestra si tiene acceso de solo lectura al repositorio, como la [edición de archivos del repositorio de otro usuario](https://help.github.com/articles/editing-files-in-another-user-s-repository/). En este caso, GitHub creará una rama de "revisión" en la bifurcación del repositorio y automáticamente creará una bifurcación en caso de que esta no exista. Después de seleccionar **Proponer cambio de archivo**, aparecerá la página **Comparar cambios** para que pueda comprobar los cambios. Después, haga clic en el botón **Crear solicitud de incorporación de cambios** para enviar los cambios a la cola de solicitudes de incorporación de cambios y continúe con la [siguiente sección](#pull-request-processing).

   - **Confirmar cambios**: aparece cuando tiene derechos de escritura en un repositorio, como la [edición de archivos en su propio repositorio](https://help.github.com/articles/editing-files-in-your-repository/). En este caso, GitHub ofrece dos opciones para guardar los cambios:

     - **Confirmar directamente en la rama `<branch-name>`**, donde `<branch-name>` es el nombre de la rama en la que se encontraba al seleccionar el botón **Editar**. Aplica los cambios directamente en la rama, en lugar de tener que usar una solicitud de incorporación de cambios. Después de este paso, ya habrá terminado.

     - **Crear una rama para esta confirmación e iniciar una solicitud de incorporación de cambios**, que solicita un nombre predeterminado para crear una rama. Después de seleccionar **Proponer cambio de archivo**, aparecerá la página **Comparar cambios** para que pueda comprobar los cambios. Después, haga clic en el botón **Crear solicitud de incorporación de cambios** para enviar los cambios a la cola de solicitudes de incorporación de cambios y continúe con la [siguiente sección](#pull-request-processing).

[!INCLUDE[contribute-how-to-write-workflows-pull-request-processing](includes/contribute-how-to-write-workflows-pull-request-processing.md)]

## <a name="next-steps"></a>Pasos siguientes

- Continúe con los artículos de los aspectos básicos de escritura para obtener más información sobre Markdown, la sintaxis de las extensiones de Markdown y mucho más.
