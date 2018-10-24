---
author: meganbradley
ms.author: mbradley
ms.openlocfilehash: fa048980afcf3c50f7d990f9c88064df6ee5ebb5
ms.sourcegitcommit: 6f1997864c000a9cd25fb9171a8f8fdb8b5b5ece
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084626"
---
# <a name="docs-pr-validation-service"></a>Servicio de validación de la solicitud de incorporación de cambios en documentos

El servicio de validación de incorporación de cambios en documentos es una aplicación de GitHub que ejecuta reglas de validación en los archivos en solicitudes de incorporación de cambios.

Cuando un servicio de validación está habilitado en un repositorio, verá el comportamiento siguiente:

1. Envía una solicitud de incorporación de cambios.
1. En el comentario de GitHub en el que se indica el estado de su solicitud, verá el estado de las "comprobaciones" habilitadas en el repositorio. Tenga en cuenta que en este ejemplo se han marcado dos comprobaciones: “Ejecutar validación” y “OpenPublishing.Build”:

   ![algunas comprobaciones fallan](media/validation-failed.png)

   La compilación puede pasar aunque la validación de la confirmación falle.

1. Haga clic en **Detalles** para obtener más información.
1. En la página Detalles, verá todas las comprobaciones de validación que han fallado, con información sobre cómo corregir los errores:

   ![mensaje de validación](media/validation-details.png)

Vea la tabla de contenido a la izquierda de este artículo para consultar la lista de validaciones de que dispone actualmente el servicio.