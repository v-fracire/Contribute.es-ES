---
title: Cómo usar vínculos en la documentación
description: En este artículo se explica cómo crear vínculos al contenido de docs.microsoft.com.
author: bryanla
ms.author: bryanla
manager: mbaldwin
ms.date: 06/29/2017
ms.prod: non-product-specific
ms.topic: contributor-guide
ms.custom: external-contributor-guide
ms.openlocfilehash: 1699e57ac6a4dc4c5a1ef099ea183b3cbc6307cd
ms.sourcegitcommit: e046e7aad8ed22bffe5380d63a9d40f0baeecc57
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2018
---
# <a name="using-links-in-documentation"></a><span data-ttu-id="27909-103">Uso de vínculos en la documentación</span><span class="sxs-lookup"><span data-stu-id="27909-103">Using links in documentation</span></span>
<span data-ttu-id="27909-104">En este artículo se describe cómo se usan los hipervínculos de páginas hospedadas en docs.microsoft.com. Es fácil agregar vínculos en Markdown con una serie de convenciones.</span><span class="sxs-lookup"><span data-stu-id="27909-104">This article describes how to use hyperlinks from pages hosted at docs.microsoft.com. Links are easy to add into markdown with a few varying conventions.</span></span> <span data-ttu-id="27909-105">Los vínculos señalan contenido de la misma página, de páginas vecinas o de sitios o direcciones URL externos.</span><span class="sxs-lookup"><span data-stu-id="27909-105">Links point users to content in the same page, point off into other neighboring pages, or point to external sites and URLs.</span></span>

<span data-ttu-id="27909-106">El backend del sitio docs.microsoft.com utiliza Open Publishing Services (OPS), que implementa DocFX Flavored Markdown (DFM).</span><span class="sxs-lookup"><span data-stu-id="27909-106">The docs.microsoft.com site backend uses Open Publishing Services (OPS) which implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="27909-107">DFM muestra una gran compatibilidad con GitHub Flavored Markdown (GFM), y además agrega otras funcionalidades mediante extensiones de Markdown.</span><span class="sxs-lookup"><span data-stu-id="27909-107">DFM is highly compatible with GitHub Flavored Markdown (GFM), and DFM adds additional functionality through Markdown extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27909-108">Todos los vínculos deben estar protegidos (`https` frente a `http`) siempre que el destino lo admita (lo que la inmensa mayoría debería hacer).</span><span class="sxs-lookup"><span data-stu-id="27909-108">All links must be secure (`https` vs `http`) whenever the target supports it (which the vast majority should).</span></span>

## <a name="link-text"></a><span data-ttu-id="27909-109">Texto del vínculo</span><span class="sxs-lookup"><span data-stu-id="27909-109">Link text</span></span>

<span data-ttu-id="27909-110">Las palabras que incluya en el texto del vínculo deben ser descriptivas.</span><span class="sxs-lookup"><span data-stu-id="27909-110">The words that you include in link text should be friendly.</span></span> <span data-ttu-id="27909-111">Es decir, deben ser palabras normales en español o el título de la página a la que remite el vínculo.</span><span class="sxs-lookup"><span data-stu-id="27909-111">In other words, they should be normal English words or the title of the page that you're linking to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="27909-112">No use "haga clic aquí".</span><span class="sxs-lookup"><span data-stu-id="27909-112">Do not use "click here."</span></span> <span data-ttu-id="27909-113">No se trata de un texto conveniente para la optimización del motor de búsqueda (SEO) ni describe correctamente el destino.</span><span class="sxs-lookup"><span data-stu-id="27909-113">It's bad for SEO and doesn't adequately describe the target.</span></span>

<span data-ttu-id="27909-114">**Correcto:**</span><span class="sxs-lookup"><span data-stu-id="27909-114">**Correct:**</span></span>

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

<span data-ttu-id="27909-115">**Incorrecto:**</span><span class="sxs-lookup"><span data-stu-id="27909-115">**Incorrect:**</span></span>

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a><span data-ttu-id="27909-116">Vínculos de un artículo a otro</span><span class="sxs-lookup"><span data-stu-id="27909-116">Links from one article to another</span></span>

<span data-ttu-id="27909-117">Para crear un vínculo insertado desde un artículo técnico de Docs a otro artículo técnico de Docs incluido en el mismo docset, use la siguiente sintaxis para vínculos:</span><span class="sxs-lookup"><span data-stu-id="27909-117">To create an inline link from a Docs technical article to another Docs technical article within the same docset, use the following link syntax:</span></span>

- <span data-ttu-id="27909-118">Un artículo de un directorio se vincula con otro artículo del mismo directorio:</span><span class="sxs-lookup"><span data-stu-id="27909-118">An article in a directory links to another article in the same directory:</span></span>

  `[link text](article-name.md)`

- <span data-ttu-id="27909-119">Un artículo de un subdirectorio se vincula con un artículo del directorio raíz:</span><span class="sxs-lookup"><span data-stu-id="27909-119">An article links from a subdirectory to an article in the root directory:</span></span>

  `[link text](../article-name.md)`

- <span data-ttu-id="27909-120">Un artículo del directorio raíz se vincula con un artículo de un subdirectorio:</span><span class="sxs-lookup"><span data-stu-id="27909-120">An article in the root directory links to an article in a subdirectory:</span></span>

  `[link text](./directory/article-name.md)`

- <span data-ttu-id="27909-121">Un artículo de un subdirectorio se vincula con un artículo de otro subdirectorio:</span><span class="sxs-lookup"><span data-stu-id="27909-121">An article in a subdirectory links to an article in another subdirectory:</span></span>

  `[link text](../directory/article-name.md)`

- <span data-ttu-id="27909-122">Un artículo con vínculos a varios conjuntos de documentos (incluso si están en el mismo repositorio): `[link text](./directory/article-name)`</span><span class="sxs-lookup"><span data-stu-id="27909-122">An article linking across docsets (even if in the same repository): `[link text](./directory/article-name)`</span></span>
  
## <a name="links-to-anchors"></a><span data-ttu-id="27909-123">Vínculos a delimitadores</span><span class="sxs-lookup"><span data-stu-id="27909-123">Links to anchors</span></span>

<span data-ttu-id="27909-124">No tiene que crear delimitadores.</span><span class="sxs-lookup"><span data-stu-id="27909-124">You do not have to create anchors.</span></span> <span data-ttu-id="27909-125">Se generan automáticamente el momento de la publicación para todos los encabezados H2.</span><span class="sxs-lookup"><span data-stu-id="27909-125">They're automatically generated at publishing time for all H2 headings.</span></span> <span data-ttu-id="27909-126">Lo único que tiene que hacer es crear vínculos a las secciones H2.</span><span class="sxs-lookup"><span data-stu-id="27909-126">The only thing you have to do is create links to the H2 sections.</span></span>

- <span data-ttu-id="27909-127">Para vincular un encabezado dentro del mismo artículo:</span><span class="sxs-lookup"><span data-stu-id="27909-127">To link to a heading within the same article:</span></span>

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- <span data-ttu-id="27909-128">Para vincular a un delimitador de otro artículo del mismo subdirectorio:</span><span class="sxs-lookup"><span data-stu-id="27909-128">To link to an anchor in another article in the same subdirectory:</span></span>

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- <span data-ttu-id="27909-129">Para vincular a un delimitador en un subdirectorio del servicio:</span><span class="sxs-lookup"><span data-stu-id="27909-129">To link to an anchor in another service subdirectory:</span></span>

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a><span data-ttu-id="27909-130">Vínculos desde archivos de inclusión</span><span class="sxs-lookup"><span data-stu-id="27909-130">Links from includes</span></span>

<span data-ttu-id="27909-131">Como los archivos de inclusión están ubicados en otro directorio, debe usar rutas de acceso relativas más largas.</span><span class="sxs-lookup"><span data-stu-id="27909-131">Because include files are located in another directory, you must use longer relative paths.</span></span> <span data-ttu-id="27909-132">Para vincular un artículo desde un archivo de inclusión, use este formato:</span><span class="sxs-lookup"><span data-stu-id="27909-132">To link to an article from an include file, use this format:</span></span>

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a><span data-ttu-id="27909-133">Vínculos en selectores</span><span class="sxs-lookup"><span data-stu-id="27909-133">Links in selectors</span></span>

<span data-ttu-id="27909-134">Si tiene selectores insertados en un archivo de inclusión, como hace el equipo de documentación de Azure, use la siguiente estructura de vínculo:</span><span class="sxs-lookup"><span data-stu-id="27909-134">If you have selectors that are embedded in an include--as does the Azure documentation team--use the following link structure:</span></span>

    > <span data-ttu-id="27909-135">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span><span class="sxs-lookup"><span data-stu-id="27909-135">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span></span>
    - [<span data-ttu-id="27909-136">(Text1 | Example1 )</span><span class="sxs-lookup"><span data-stu-id="27909-136">(Text1 | Example1 )</span></span>](../articles/folder/article-name1.md)
    - [<span data-ttu-id="27909-137">(Text1 | Example2 )</span><span class="sxs-lookup"><span data-stu-id="27909-137">(Text1 | Example2 )</span></span>](../articles/folder/article-name2.md)
    - [<span data-ttu-id="27909-138">(Text2 | Example3 )</span><span class="sxs-lookup"><span data-stu-id="27909-138">(Text2 | Example3 )</span></span>](../articles/folder/article-name3.md)
    - <span data-ttu-id="27909-139">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span><span class="sxs-lookup"><span data-stu-id="27909-139">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span></span>

## <a name="reference-style-links"></a><span data-ttu-id="27909-140">Vínculos tipo referencias</span><span class="sxs-lookup"><span data-stu-id="27909-140">Reference-style links</span></span>

<span data-ttu-id="27909-141">Puede usar vínculos con estilo de referencia para que el contenido de origen resulte más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="27909-141">You can use reference-style links to make your source content easier to read.</span></span> <span data-ttu-id="27909-142">Estos vínculos reemplazan la sintaxis del vínculo insertado por sintaxis simplificada que permite mover las direcciones URL largas al final del artículo.</span><span class="sxs-lookup"><span data-stu-id="27909-142">Reference-style links replace inline link syntax with simplified syntax that allows you to move the long URLs to the end of the article.</span></span> <span data-ttu-id="27909-143">Este es un ejemplo de [Daring Fireball](https://daringfireball.net/projects/markdown/):</span><span class="sxs-lookup"><span data-stu-id="27909-143">Here's [Daring Fireball](https://daringfireball.net/projects/markdown/) 's example:</span></span>

<span data-ttu-id="27909-144">Texto insertado:</span><span class="sxs-lookup"><span data-stu-id="27909-144">Inline text:</span></span>

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

<span data-ttu-id="27909-145">Referencias de vínculos al final del artículo:</span><span class="sxs-lookup"><span data-stu-id="27909-145">Link references at the end of the article:</span></span>

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

<span data-ttu-id="27909-146">Asegúrese de incluir el espacio después de los dos puntos, antes del vínculo.</span><span class="sxs-lookup"><span data-stu-id="27909-146">Make sure that you include the space after the colon, before the link.</span></span> <span data-ttu-id="27909-147">Cuando inserta un vínculo a otro artículo técnico, si se olvida de incluir el espacio, el vínculo se romperá en el artículo publicado.</span><span class="sxs-lookup"><span data-stu-id="27909-147">When you link to other technical articles, if you forget to include the space, the link will be broken in the published article.</span></span>

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a><span data-ttu-id="27909-148">Vínculos a páginas que no forman parte de la serie de documentos técnicos</span><span class="sxs-lookup"><span data-stu-id="27909-148">Links to pages that are not part of the technical documentation set</span></span>

<span data-ttu-id="27909-149">Para vincular a una página que no sea propiedad de Microsoft (como una página de precios, una página del Acuerdo de Nivel de Servicio o cualquier otra página que no se corresponda con un artículo de documentación), use una dirección URL absoluta, pero omita la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="27909-149">To link to a page on another Microsoft property (such as a pricing page, SLA page, or anything else that is not a documentation article), use an absolute URL, but omit the locale.</span></span> <span data-ttu-id="27909-150">El objetivo en este caso es que los vínculos funcionen en GitHub y en el sitio representado.</span><span class="sxs-lookup"><span data-stu-id="27909-150">The goal here is that links work in GitHub and on the rendered site:</span></span>

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a><span data-ttu-id="27909-151">Vínculos a sitios de terceros</span><span class="sxs-lookup"><span data-stu-id="27909-151">Links to third-party sites</span></span>

<span data-ttu-id="27909-152">La mejor experiencia del usuario minimiza el redireccionamiento de los usuarios a otro sitio.</span><span class="sxs-lookup"><span data-stu-id="27909-152">The best user experience minimizes sending users to another site.</span></span> <span data-ttu-id="27909-153">Por tanto, base todos los vínculos a sitios de terceros, que a veces necesitamos incluir, en esta información:</span><span class="sxs-lookup"><span data-stu-id="27909-153">So base any links to third-party sites, which we do sometimes need, on this info:</span></span>

- <span data-ttu-id="27909-154">**Responsabilidad:** vínculo a contenido de terceros cuando va a compartir la información del tercero.</span><span class="sxs-lookup"><span data-stu-id="27909-154">**Accountability**: Link to third-party content when it's the third-party's information to share.</span></span> <span data-ttu-id="27909-155">Por ejemplo, no es responsabilidad de Microsoft informar sobre cómo se usan las herramientas para desarrolladores de Android, sino que le corresponde a Google.</span><span class="sxs-lookup"><span data-stu-id="27909-155">For example, it's not Microsoft's place to tell people how to use Android developer tools--that is Google's story to tell.</span></span> <span data-ttu-id="27909-156">Si resulta necesario, se puede explicar cómo usar las herramientas para desarrolladores de Android *con* Azure, pero Google informará sobre el procedimiento para usar sus herramientas.</span><span class="sxs-lookup"><span data-stu-id="27909-156">If we need to, we can explain how to use Android developer tools *with* Azure, but Google should tell the story of how to use their tools.</span></span>
- <span data-ttu-id="27909-157">**Aprobación de PM**: solicitar la aprobación de Microsoft en contenido de terceros.</span><span class="sxs-lookup"><span data-stu-id="27909-157">**PM signoff**: Request that Microsoft sign off on third-party content.</span></span> <span data-ttu-id="27909-158">Al insertar un vínculo a dicho contenido, es un indicativo de la confianza depositada en él y de la obligación asumida en caso de que los usuarios sigan las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="27909-158">By linking to it, we are saying something about our trust in it and our obligation if people follow the instructions.</span></span>
- <span data-ttu-id="27909-159">**Revisiones de actualizaciones:** asegúrese de que la información de terceros está actualizada, es correcta y pertinente y de que el vínculo no ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="27909-159">**Freshness reviews**: Make sure that the third-party info is still current, correct, and relevant, and that the link hasn’t changed.</span></span>
- <span data-ttu-id="27909-160">**Fuera del sitio:** asegúrese de que los usuarios tienen constancia de que van a visitar otro sitio.</span><span class="sxs-lookup"><span data-stu-id="27909-160">**Offsite**: Make users aware that they are going to another site.</span></span> <span data-ttu-id="27909-161">Si el contexto no lo deja claro, agregue una frase aplicable.</span><span class="sxs-lookup"><span data-stu-id="27909-161">If the context does not make that clear, add a qualifying phrase.</span></span> <span data-ttu-id="27909-162">Por ejemplo: "Los requisitos previos comprenden las herramientas para desarrolladores de Android, que puede descargar en el sitio de Android Studio".</span><span class="sxs-lookup"><span data-stu-id="27909-162">For example: “Prerequisites include the Android Developer Tools, which you can download on the Android Studio site.”</span></span>
- <span data-ttu-id="27909-163">**Pasos siguientes:** es buena idea agregar un vínculo, por ejemplo, a un blog de MVP en una sección de "Pasos siguientes".</span><span class="sxs-lookup"><span data-stu-id="27909-163">**Next steps**: It’s fine to add a link to, say, an MVP blog in a "Next steps" section.</span></span> <span data-ttu-id="27909-164">Una vez más, debe asegurarse de que los usuarios saben que van a abandonar el sitio.</span><span class="sxs-lookup"><span data-stu-id="27909-164">Again, just make sure that users understand they’ll be leaving the site.</span></span>
- <span data-ttu-id="27909-165">**Legal:** estamos cubiertos legalmente por la sección **Vínculos a sitios web de terceros** de los **Términos de uso** cuyo vínculo se encuentra en el pie de página de todas las páginas de ms.com.</span><span class="sxs-lookup"><span data-stu-id="27909-165">**Legal**: We are covered legally under **Links to Third Party Sites** in the **Terms of Use** footer on every ms.com page.</span></span>

## <a name="links-to-msdn-or-technet"></a><span data-ttu-id="27909-166">Vínculos a MSDN o TechNet</span><span class="sxs-lookup"><span data-stu-id="27909-166">Links to MSDN or TechNet</span></span>

<span data-ttu-id="27909-167">Cuando necesite insertar un vínculo a MSDN o TechNet, use el vínculo completo al tema y quite la configuración regional de idioma "en-us" del vínculo.</span><span class="sxs-lookup"><span data-stu-id="27909-167">When you need to link to MSDN or TechNet, use the full link to the topic, and remove the "en-us" language locale from the link.</span></span>

## <a name="links-to-azure-powershell-reference-content"></a><span data-ttu-id="27909-168">Vínculos al contenido de referencia de Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="27909-168">Links to Azure PowerShell reference content</span></span>

<span data-ttu-id="27909-169">El contenido de referencia de Azure PowerShell ha experimentado varias modificaciones desde noviembre de 2016.</span><span class="sxs-lookup"><span data-stu-id="27909-169">The Azure PowerShell reference content has been through several changes since November 2016.</span></span> <span data-ttu-id="27909-170">Aplique las siguientes instrucciones para vincular a este contenido desde otros artículos de docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="27909-170">Use the following guidelines for linking to this content from other articles on docs.microsoft.com.</span></span>

<span data-ttu-id="27909-171">Estructura de la dirección URL:</span><span class="sxs-lookup"><span data-stu-id="27909-171">Structure of the URL:</span></span>

* <span data-ttu-id="27909-172">Para cmdlets:</span><span class="sxs-lookup"><span data-stu-id="27909-172">For cmdlets:</span></span>
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* <span data-ttu-id="27909-173">Para temas conceptuales:</span><span class="sxs-lookup"><span data-stu-id="27909-173">For conceptual topics:</span></span>
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

<span data-ttu-id="27909-174">La parte &lt;moniker-name&gt; es opcional.</span><span class="sxs-lookup"><span data-stu-id="27909-174">The &lt;moniker-name&gt; portion is optional.</span></span> <span data-ttu-id="27909-175">Si se omite, se le redireccionará a la última versión del contenido.</span><span class="sxs-lookup"><span data-stu-id="27909-175">If it's omitted, you will be directed to the latest version of the content.</span></span> <span data-ttu-id="27909-176">La información correspondiente a la sección &lt;service-name&gt; es la que aparece en los ejemplos expuestos en las siguientes direcciones URL base:</span><span class="sxs-lookup"><span data-stu-id="27909-176">The &lt;service-name&gt; portion is one of the examples shown in the following base URLs:</span></span>

- <span data-ttu-id="27909-177">Contenido de Azure PowerShell (AzureRM): https://docs.microsoft.com/powershell/azure/</span><span class="sxs-lookup"><span data-stu-id="27909-177">Azure PowerShell (AzureRM) content: https://docs.microsoft.com/powershell/azure/</span></span>
- <span data-ttu-id="27909-178">Contenido de Azure PowerShell (ASM): https://docs.microsoft.com/powershell/azure/_servicemanagement_</span><span class="sxs-lookup"><span data-stu-id="27909-178">Azure PowerShell (ASM) content: https://docs.microsoft.com/powershell/azure/_servicemanagement_</span></span>
- <span data-ttu-id="27909-179">Contenido de Azure Active Directory (AzureAD) PowerShell: https://docs.microsoft.com/powershell/azure/_active-directory_</span><span class="sxs-lookup"><span data-stu-id="27909-179">Azure Active Directory (AzureAD) PowerShell content: https://docs.microsoft.com/powershell/azure/_active-directory_</span></span>
- <span data-ttu-id="27909-180">Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_</span><span class="sxs-lookup"><span data-stu-id="27909-180">Azure Service Fabric PowerShell: https://docs.microsoft.com/powershell/azure/_service-fabric_</span></span>
- <span data-ttu-id="27909-181">Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_</span><span class="sxs-lookup"><span data-stu-id="27909-181">Azure Information Protection PowerShell: https://docs.microsoft.com/powershell/azure/_aip_</span></span>
- <span data-ttu-id="27909-182">Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_</span><span class="sxs-lookup"><span data-stu-id="27909-182">Azure Elastic DB Jobs PowerShell: https://docs.microsoft.com/powershell/azure/_elasticdbjobs_</span></span>

<span data-ttu-id="27909-183">Si hace clic en estas direcciones URL, se le redireccionará a la última versión del contenido.</span><span class="sxs-lookup"><span data-stu-id="27909-183">When you use these URLs, you will be redirected to the latest version of the content.</span></span> <span data-ttu-id="27909-184">De esta forma, no tiene que especificar un moniker de versión.</span><span class="sxs-lookup"><span data-stu-id="27909-184">This way, you don't have to specify a version moniker.</span></span> <span data-ttu-id="27909-185">Además, evita tener vínculos a contenido conceptual que se deba actualizar cuando la versión cambia.</span><span class="sxs-lookup"><span data-stu-id="27909-185">And you won't have links to conceptual content that must be updated when the version changes.</span></span>

<span data-ttu-id="27909-186">Para crear el vínculo correcto, busque la página a la que quiere redireccionar en el explorador y copie la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="27909-186">To create the correct link, find the page that you want to link to in your browser, and copy the URL.</span></span>
<span data-ttu-id="27909-187">A continuación, quite "https://docs.microsoft.com" y la información de configuración regional.</span><span class="sxs-lookup"><span data-stu-id="27909-187">Then, remove "https://docs.microsoft.com" and the locale info.</span></span>

<span data-ttu-id="27909-188">Cuando el vínculo remita a una tabla de contenido, debe usar la dirección URL completa sin la información de configuración regional.</span><span class="sxs-lookup"><span data-stu-id="27909-188">When you're linking from a TOC, you must use the full URL without the locale information.</span></span>

<span data-ttu-id="27909-189">Markdown de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="27909-189">Example markdown:</span></span>

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
