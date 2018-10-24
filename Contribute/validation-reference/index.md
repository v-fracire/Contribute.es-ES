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
# <a name="docs-pr-validation-service"></a><span data-ttu-id="14216-101">Servicio de validación de la solicitud de incorporación de cambios en documentos</span><span class="sxs-lookup"><span data-stu-id="14216-101">Docs PR validation service</span></span>

<span data-ttu-id="14216-102">El servicio de validación de incorporación de cambios en documentos es una aplicación de GitHub que ejecuta reglas de validación en los archivos en solicitudes de incorporación de cambios.</span><span class="sxs-lookup"><span data-stu-id="14216-102">The Docs PR validation service is a GitHub app that runs validation rules on the files in a PR.</span></span>

<span data-ttu-id="14216-103">Cuando un servicio de validación está habilitado en un repositorio, verá el comportamiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="14216-103">When the validation service is enabled on a repo, you'll see the following behavior:</span></span>

1. <span data-ttu-id="14216-104">Envía una solicitud de incorporación de cambios.</span><span class="sxs-lookup"><span data-stu-id="14216-104">You submit a PR.</span></span>
1. <span data-ttu-id="14216-105">En el comentario de GitHub en el que se indica el estado de su solicitud, verá el estado de las "comprobaciones" habilitadas en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="14216-105">In the GitHub comment that indicates the status of your PR, you'll see the status of "checks" enabled on the repo.</span></span> <span data-ttu-id="14216-106">Tenga en cuenta que en este ejemplo se han marcado dos comprobaciones: “Ejecutar validación” y “OpenPublishing.Build”:</span><span class="sxs-lookup"><span data-stu-id="14216-106">Note that in this example, there are two checks enabled, "Commit Validation" and "OpenPublishing.Build":</span></span>

   ![algunas comprobaciones fallan](media/validation-failed.png)

   <span data-ttu-id="14216-108">La compilación puede pasar aunque la validación de la confirmación falle.</span><span class="sxs-lookup"><span data-stu-id="14216-108">Build can pass even if commit validation fails.</span></span>

1. <span data-ttu-id="14216-109">Haga clic en **Detalles** para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="14216-109">Click **Details** for more information.</span></span>
1. <span data-ttu-id="14216-110">En la página Detalles, verá todas las comprobaciones de validación que han fallado, con información sobre cómo corregir los errores:</span><span class="sxs-lookup"><span data-stu-id="14216-110">On the Details page, you'll see all the validation checks that failed, with information about how to fix the issues:</span></span>

   ![mensaje de validación](media/validation-details.png)

<span data-ttu-id="14216-112">Vea la tabla de contenido a la izquierda de este artículo para consultar la lista de validaciones de que dispone actualmente el servicio.</span><span class="sxs-lookup"><span data-stu-id="14216-112">See the left-hand TOC of this article for the list of validations currently in the service.</span></span>