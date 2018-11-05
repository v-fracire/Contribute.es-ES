---
title: Cómo usar vínculos en la documentación
description: En este artículo se explica cómo crear vínculos al contenido de docs.microsoft.com.
ms.date: 06/29/2017
ms.openlocfilehash: 1820ed9af561964d7afe0b29827ee43526c72489
ms.sourcegitcommit: d3c7b49dc854dae8da9cd49da8ac4035789a5010
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "49805778"
---
# <a name="using-links-in-documentation"></a>Uso de vínculos en la documentación
En este artículo se describe cómo se usan los hipervínculos de páginas hospedadas en docs.microsoft.com. Es fácil agregar vínculos en Markdown con una serie de convenciones. Los vínculos señalan contenido de la misma página, de páginas vecinas o de sitios o direcciones URL externos.

El backend del sitio docs.microsoft.com utiliza Open Publishing Services (OPS), que implementa DocFX Flavored Markdown (DFM). DFM muestra una gran compatibilidad con GitHub Flavored Markdown (GFM), y además agrega otras funcionalidades mediante extensiones de Markdown.

> [!IMPORTANT]
> Todos los vínculos deben estar protegidos (`https` frente a `http`) siempre que el destino lo admita (lo que la inmensa mayoría debería hacer).

## <a name="link-text"></a>Texto del vínculo

Las palabras que incluya en el texto del vínculo deben ser descriptivas. Es decir, deben ser palabras normales en español o el título de la página a la que remite el vínculo.

> [!IMPORTANT]
> No use "haga clic aquí". No se trata de un texto conveniente para la optimización del motor de búsqueda (SEO) ni describe correctamente el destino.

**Correcto:**

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

**Incorrecto:**

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a>Vínculos de un artículo a otro

Para crear un vínculo insertado desde un artículo técnico de Docs a otro artículo técnico de Docs incluido en el mismo docset, use la siguiente sintaxis para vínculos:

- Un artículo de un directorio se vincula con otro artículo del mismo directorio:

  `[link text](article-name.md)`

- Un artículo de un subdirectorio se vincula con un artículo del directorio raíz:

  `[link text](../article-name.md)`

- Un artículo del directorio raíz se vincula con un artículo de un subdirectorio:

  `[link text](./directory/article-name.md)`

- Un artículo de un subdirectorio se vincula con un artículo de otro subdirectorio:

  `[link text](../directory/article-name.md)`

- Un artículo con vínculos a varios conjuntos de documentos (incluso si están en el mismo repositorio): `[link text](./directory/article-name)`

> [!IMPORTANT]
> En ninguno de los ejemplos anteriores se usa `~/` como parte del vínculo. Si se trata de un vínculo a una ruta de acceso a la raíz del repositorio, inícielo con `/`. El hecho de incluir `~/` produce vínculos no válidos al navegar por los repositorios de origen en GitHub. Si se inicia la ruta de acceso con `/`, se resolverá correctamente.

## <a name="links-to-anchors"></a>Vínculos a delimitadores

No tiene que crear delimitadores. Se generan automáticamente el momento de la publicación para todos los encabezados H2. Lo único que tiene que hacer es crear vínculos a las secciones H2.

- Para vincular un encabezado dentro del mismo artículo:

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- Para vincular a un delimitador de otro artículo del mismo subdirectorio:

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- Para vincular a un delimitador en un subdirectorio del servicio:

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a>Vínculos desde archivos de inclusión

Como los archivos de inclusión están ubicados en otro directorio, debe usar rutas de acceso relativas más largas. Para vincular un artículo desde un archivo de inclusión, use este formato:

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a>Vínculos en selectores

Si tiene selectores insertados en un archivo de inclusión, como hace el equipo de documentación de Azure, use la siguiente estructura de vínculo:

    > [AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]
    - [(Text1 | Example1 )](../articles/folder/article-name1.md)
    - [(Text1 | Example2 )](../articles/folder/article-name2.md)
    - [(Text2 | Example3 )](../articles/folder/article-name3.md)
    - [(Text2 | Example4 )](../articles/folder/article-name4.md) -->

## <a name="reference-style-links"></a>Vínculos tipo referencias

Puede usar vínculos con estilo de referencia para que el contenido de origen resulte más fácil de leer. Estos vínculos reemplazan la sintaxis del vínculo insertado por sintaxis simplificada que permite mover las direcciones URL largas al final del artículo. Este es un ejemplo de [Daring Fireball](https://daringfireball.net/projects/markdown/):

Texto insertado:

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

Referencias de vínculos al final del artículo:

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

Asegúrese de incluir el espacio después de los dos puntos, antes del vínculo. Cuando inserta un vínculo a otro artículo técnico, si se olvida de incluir el espacio, el vínculo se romperá en el artículo publicado.

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a>Vínculos a páginas que no forman parte de la serie de documentos técnicos

Para vincular a una página que no sea propiedad de Microsoft (como una página de precios, una página del Acuerdo de Nivel de Servicio o cualquier otra página que no se corresponda con un artículo de documentación), use una dirección URL absoluta, pero omita la configuración regional. El objetivo en este caso es que los vínculos funcionen en GitHub y en el sitio representado.

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a>Vínculos a sitios de terceros

La mejor experiencia del usuario minimiza el redireccionamiento de los usuarios a otro sitio. Por tanto, base todos los vínculos a sitios de terceros, que a veces necesitamos incluir, en esta información:

- **Responsabilidad:** vínculo a contenido de terceros cuando va a compartir la información del tercero. Por ejemplo, no es responsabilidad de Microsoft informar sobre cómo se usan las herramientas para desarrolladores de Android, sino que le corresponde a Google. Si resulta necesario, se puede explicar cómo usar las herramientas para desarrolladores de Android *con* Azure, pero Google informará sobre el procedimiento para usar sus herramientas.
- **Aprobación de PM**: solicitar la aprobación de Microsoft en contenido de terceros. Al insertar un vínculo a dicho contenido, es un indicativo de la confianza depositada en él y de la obligación asumida en caso de que los usuarios sigan las instrucciones.
- **Revisiones de actualizaciones:** asegúrese de que la información de terceros está actualizada, es correcta y pertinente y de que el vínculo no ha cambiado.
- **Fuera del sitio:** asegúrese de que los usuarios tienen constancia de que van a visitar otro sitio. Si el contexto no lo deja claro, agregue una frase aplicable. Por ejemplo: "Los requisitos previos comprenden las herramientas para desarrolladores de Android, que puede descargar en el sitio de Android Studio".
- **Pasos siguientes:** es buena idea agregar un vínculo, por ejemplo, a un blog de MVP en una sección de "Pasos siguientes". Una vez más, debe asegurarse de que los usuarios saben que van a abandonar el sitio.
- **Legal:** estamos cubiertos legalmente por la sección **Vínculos a sitios web de terceros** de los **Términos de uso** cuyo vínculo se encuentra en el pie de página de todas las páginas de ms.com.

## <a name="links-to-msdn-or-technet"></a>Vínculos a MSDN o TechNet

Cuando necesite insertar un vínculo a MSDN o TechNet, use el vínculo completo al tema y quite la configuración regional de idioma "en-us" del vínculo.

## <a name="links-to-azure-powershell-reference-content"></a>Vínculos al contenido de referencia de Azure PowerShell

El contenido de referencia de Azure PowerShell ha experimentado varias modificaciones desde noviembre de 2016. Aplique las siguientes instrucciones para vincular a este contenido desde otros artículos de docs.microsoft.com.

Estructura de la dirección URL:

* Para cmdlets:
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* Para temas conceptuales:
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

La parte &lt;moniker-name&gt; es opcional. Si se omite, se le redireccionará a la última versión del contenido. La información correspondiente a la sección &lt;service-name&gt; es la que aparece en los ejemplos expuestos en las siguientes direcciones URL base:

- Contenido de Azure PowerShell (AzureRM): [https://docs.microsoft.com/powershell/azure/](https://docs.microsoft.com/powershell/azure/)
- Contenido de Azure PowerShell (ASM): [https://docs.microsoft.com/powershell/azure/_servicemanagement_](https://docs.microsoft.com/powershell/azure/servicemanagement)
- Contenido de Azure Active Directory (AzureAD) PowerShell: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/active-directory)
- Azure Service Fabric PowerShell: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/service-fabric)
- Azure Information Protection PowerShell: [https://docs.microsoft.com/powershell/azure/_aip_](https://docs.microsoft.com/powershell/azure/aip)
- Azure Elastic DB Jobs PowerShell: [https://docs.microsoft.com/powershell/azure/_elasticdbjobs_](https://docs.microsoft.com/powershell/azure/elasticdbjobs)

Si hace clic en estas direcciones URL, se le redireccionará a la última versión del contenido. De esta forma, no tiene que especificar un moniker de versión. Además, evita tener vínculos a contenido conceptual que se deba actualizar cuando la versión cambia.

Para crear el vínculo correcto, busque la página a la que quiere redireccionar en el explorador y copie la dirección URL.
Después, quite `https://docs.microsoft.com` y la información de configuración regional.

Cuando el vínculo remita a una tabla de contenido, debe usar la dirección URL completa sin la información de configuración regional.

Markdown de ejemplo:

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
