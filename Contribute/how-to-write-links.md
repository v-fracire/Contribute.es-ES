---
title: Cómo usar vínculos en la documentación
description: En este artículo se explica cómo crear vínculos al contenido de docs.microsoft.com.
ms.date: 06/29/2017
ms.openlocfilehash: dad0460cfb36594c17cef1b079c5fc14191f56f7
ms.sourcegitcommit: 886ca76086a302d1d6124967df12a5bcfe4fd4b5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2018
ms.locfileid: "40251466"
---
# <a name="using-links-in-documentation"></a><span data-ttu-id="c09aa-103">Uso de vínculos en la documentación</span><span class="sxs-lookup"><span data-stu-id="c09aa-103">Using links in documentation</span></span>
<span data-ttu-id="c09aa-104">En este artículo se describe cómo se usan los hipervínculos de páginas hospedadas en docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c09aa-104">This article describes how to use hyperlinks from pages hosted at docs.microsoft.com.</span></span> <span data-ttu-id="c09aa-105">Es fácil agregar vínculos en Markdown con una serie de convenciones.</span><span class="sxs-lookup"><span data-stu-id="c09aa-105">Links are easy to add into markdown with a few varying conventions.</span></span> <span data-ttu-id="c09aa-106">Los vínculos señalan contenido de la misma página, de páginas vecinas o de sitios o direcciones URL externos.</span><span class="sxs-lookup"><span data-stu-id="c09aa-106">Links point users to content in the same page, point off into other neighboring pages, or point to external sites and URLs.</span></span>

<span data-ttu-id="c09aa-107">El backend del sitio docs.microsoft.com utiliza Open Publishing Services (OPS), que implementa DocFX Flavored Markdown (DFM).</span><span class="sxs-lookup"><span data-stu-id="c09aa-107">The docs.microsoft.com site backend uses Open Publishing Services (OPS) which implements DocFX Flavored Markdown (DFM).</span></span> <span data-ttu-id="c09aa-108">DFM muestra una gran compatibilidad con GitHub Flavored Markdown (GFM), y además agrega otras funcionalidades mediante extensiones de Markdown.</span><span class="sxs-lookup"><span data-stu-id="c09aa-108">DFM is highly compatible with GitHub Flavored Markdown (GFM), and DFM adds additional functionality through Markdown extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c09aa-109">Todos los vínculos deben estar protegidos (`https` frente a `http`) siempre que el destino lo admita (lo que la inmensa mayoría debería hacer).</span><span class="sxs-lookup"><span data-stu-id="c09aa-109">All links must be secure (`https` vs `http`) whenever the target supports it (which the vast majority should).</span></span>

## <a name="link-text"></a><span data-ttu-id="c09aa-110">Texto del vínculo</span><span class="sxs-lookup"><span data-stu-id="c09aa-110">Link text</span></span>

<span data-ttu-id="c09aa-111">Las palabras que incluya en el texto del vínculo deben ser descriptivas.</span><span class="sxs-lookup"><span data-stu-id="c09aa-111">The words that you include in link text should be friendly.</span></span> <span data-ttu-id="c09aa-112">Es decir, deben ser palabras normales en español o el título de la página a la que remite el vínculo.</span><span class="sxs-lookup"><span data-stu-id="c09aa-112">In other words, they should be normal English words or the title of the page that you're linking to.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c09aa-113">No use "haga clic aquí".</span><span class="sxs-lookup"><span data-stu-id="c09aa-113">Do not use "click here."</span></span> <span data-ttu-id="c09aa-114">No se trata de un texto conveniente para la optimización del motor de búsqueda (SEO) ni describe correctamente el destino.</span><span class="sxs-lookup"><span data-stu-id="c09aa-114">It's bad for SEO and doesn't adequately describe the target.</span></span>

<span data-ttu-id="c09aa-115">**Correcto:**</span><span class="sxs-lookup"><span data-stu-id="c09aa-115">**Correct:**</span></span>

- `For more information, see the [contributor guide index](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

- `For more details, see the [SET TRANSACTION ISOLATION LEVEL](https://msdn.microsoft.com/library/ms173763.aspx) reference.`

<span data-ttu-id="c09aa-116">**Incorrecto:**</span><span class="sxs-lookup"><span data-stu-id="c09aa-116">**Incorrect:**</span></span>

- `For more details, see [https://msdn.microsoft.com/library/ms173763.aspx](https://msdn.microsoft.com/library/ms173763.aspx).`

- `For more information, click [here](https://github.com/Azure/azure-content/blob/master/contributor-guide/contributor-guide-index.md).`

## <a name="links-from-one-article-to-another"></a><span data-ttu-id="c09aa-117">Vínculos de un artículo a otro</span><span class="sxs-lookup"><span data-stu-id="c09aa-117">Links from one article to another</span></span>

<span data-ttu-id="c09aa-118">Para crear un vínculo insertado desde un artículo técnico de Docs a otro artículo técnico de Docs incluido en el mismo docset, use la siguiente sintaxis para vínculos:</span><span class="sxs-lookup"><span data-stu-id="c09aa-118">To create an inline link from a Docs technical article to another Docs technical article within the same docset, use the following link syntax:</span></span>

- <span data-ttu-id="c09aa-119">Un artículo de un directorio se vincula con otro artículo del mismo directorio:</span><span class="sxs-lookup"><span data-stu-id="c09aa-119">An article in a directory links to another article in the same directory:</span></span>

  `[link text](article-name.md)`

- <span data-ttu-id="c09aa-120">Un artículo de un subdirectorio se vincula con un artículo del directorio raíz:</span><span class="sxs-lookup"><span data-stu-id="c09aa-120">An article links from a subdirectory to an article in the root directory:</span></span>

  `[link text](../article-name.md)`

- <span data-ttu-id="c09aa-121">Un artículo del directorio raíz se vincula con un artículo de un subdirectorio:</span><span class="sxs-lookup"><span data-stu-id="c09aa-121">An article in the root directory links to an article in a subdirectory:</span></span>

  `[link text](./directory/article-name.md)`

- <span data-ttu-id="c09aa-122">Un artículo de un subdirectorio se vincula con un artículo de otro subdirectorio:</span><span class="sxs-lookup"><span data-stu-id="c09aa-122">An article in a subdirectory links to an article in another subdirectory:</span></span>

  `[link text](../directory/article-name.md)`

- <span data-ttu-id="c09aa-123">Un artículo con vínculos a varios conjuntos de documentos (incluso si están en el mismo repositorio): `[link text](./directory/article-name)`</span><span class="sxs-lookup"><span data-stu-id="c09aa-123">An article linking across docsets (even if in the same repository): `[link text](./directory/article-name)`</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c09aa-124">En ninguno de los ejemplos anteriores se usa `~/` como parte del vínculo.</span><span class="sxs-lookup"><span data-stu-id="c09aa-124">None of the above examples use the `~/` as part of the link.</span></span> <span data-ttu-id="c09aa-125">Si se trata de un vínculo a una ruta de acceso a la raíz del repositorio, inícielo con `/`.</span><span class="sxs-lookup"><span data-stu-id="c09aa-125">If you are linking to a path at the root of the repository, start with the `/`.</span></span> <span data-ttu-id="c09aa-126">El hecho de incluir `~/` produce vínculos no válidos al navegar por los repositorios de origen en GitHub.</span><span class="sxs-lookup"><span data-stu-id="c09aa-126">Including the `~/` produces invalid links when navigating the source repositories on GitHub.</span></span> <span data-ttu-id="c09aa-127">Si se inicia la ruta de acceso con `/`, se resolverá correctamente.</span><span class="sxs-lookup"><span data-stu-id="c09aa-127">Starting the path with `/` resolves correctly.</span></span>

## <a name="links-to-anchors"></a><span data-ttu-id="c09aa-128">Vínculos a delimitadores</span><span class="sxs-lookup"><span data-stu-id="c09aa-128">Links to anchors</span></span>

<span data-ttu-id="c09aa-129">No tiene que crear delimitadores.</span><span class="sxs-lookup"><span data-stu-id="c09aa-129">You do not have to create anchors.</span></span> <span data-ttu-id="c09aa-130">Se generan automáticamente el momento de la publicación para todos los encabezados H2.</span><span class="sxs-lookup"><span data-stu-id="c09aa-130">They're automatically generated at publishing time for all H2 headings.</span></span> <span data-ttu-id="c09aa-131">Lo único que tiene que hacer es crear vínculos a las secciones H2.</span><span class="sxs-lookup"><span data-stu-id="c09aa-131">The only thing you have to do is create links to the H2 sections.</span></span>

- <span data-ttu-id="c09aa-132">Para vincular un encabezado dentro del mismo artículo:</span><span class="sxs-lookup"><span data-stu-id="c09aa-132">To link to a heading within the same article:</span></span>

  `[link](#the-text-of-the-H2-section-separated-by-hyphens)`
  `[Create cache](#create-cache)`

- <span data-ttu-id="c09aa-133">Para vincular a un delimitador de otro artículo del mismo subdirectorio:</span><span class="sxs-lookup"><span data-stu-id="c09aa-133">To link to an anchor in another article in the same subdirectory:</span></span>

  `[link text](article-name.md#anchor-name)`
  `[Configure your profile](media-services-create-account.md#configure-your-profile)`

- <span data-ttu-id="c09aa-134">Para vincular a un delimitador en un subdirectorio del servicio:</span><span class="sxs-lookup"><span data-stu-id="c09aa-134">To link to an anchor in another service subdirectory:</span></span>

  `[link text](../directory/article-name.md#anchor-name)`
  `[Configure your profile](../directory/media-services-create-account.md#configure-your-profile)`

## <a name="links-from-includes"></a><span data-ttu-id="c09aa-135">Vínculos desde archivos de inclusión</span><span class="sxs-lookup"><span data-stu-id="c09aa-135">Links from includes</span></span>

<span data-ttu-id="c09aa-136">Como los archivos de inclusión están ubicados en otro directorio, debe usar rutas de acceso relativas más largas.</span><span class="sxs-lookup"><span data-stu-id="c09aa-136">Because include files are located in another directory, you must use longer relative paths.</span></span> <span data-ttu-id="c09aa-137">Para vincular un artículo desde un archivo de inclusión, use este formato:</span><span class="sxs-lookup"><span data-stu-id="c09aa-137">To link to an article from an include file, use this format:</span></span>

    [link text](../articles/folder/article-name.md)

## <a name="links-in-selectors"></a><span data-ttu-id="c09aa-138">Vínculos en selectores</span><span class="sxs-lookup"><span data-stu-id="c09aa-138">Links in selectors</span></span>

<span data-ttu-id="c09aa-139">Si tiene selectores insertados en un archivo de inclusión, como hace el equipo de documentación de Azure, use la siguiente estructura de vínculo:</span><span class="sxs-lookup"><span data-stu-id="c09aa-139">If you have selectors that are embedded in an include--as does the Azure documentation team--use the following link structure:</span></span>

    > <span data-ttu-id="c09aa-140">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span><span class="sxs-lookup"><span data-stu-id="c09aa-140">[AZURE.SELECTOR-LIST (Dropdown1 | Dropdown2 )]</span></span>
    - [<span data-ttu-id="c09aa-141">(Text1 | Example1 )</span><span class="sxs-lookup"><span data-stu-id="c09aa-141">(Text1 | Example1 )</span></span>](../articles/folder/article-name1.md)
    - [<span data-ttu-id="c09aa-142">(Text1 | Example2 )</span><span class="sxs-lookup"><span data-stu-id="c09aa-142">(Text1 | Example2 )</span></span>](../articles/folder/article-name2.md)
    - [<span data-ttu-id="c09aa-143">(Text2 | Example3 )</span><span class="sxs-lookup"><span data-stu-id="c09aa-143">(Text2 | Example3 )</span></span>](../articles/folder/article-name3.md)
    - <span data-ttu-id="c09aa-144">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span><span class="sxs-lookup"><span data-stu-id="c09aa-144">[(Text2 | Example4 )](../articles/folder/article-name4.md) --></span></span>

## <a name="reference-style-links"></a><span data-ttu-id="c09aa-145">Vínculos tipo referencias</span><span class="sxs-lookup"><span data-stu-id="c09aa-145">Reference-style links</span></span>

<span data-ttu-id="c09aa-146">Puede usar vínculos con estilo de referencia para que el contenido de origen resulte más fácil de leer.</span><span class="sxs-lookup"><span data-stu-id="c09aa-146">You can use reference-style links to make your source content easier to read.</span></span> <span data-ttu-id="c09aa-147">Estos vínculos reemplazan la sintaxis del vínculo insertado por sintaxis simplificada que permite mover las direcciones URL largas al final del artículo.</span><span class="sxs-lookup"><span data-stu-id="c09aa-147">Reference-style links replace inline link syntax with simplified syntax that allows you to move the long URLs to the end of the article.</span></span> <span data-ttu-id="c09aa-148">Este es un ejemplo de [Daring Fireball](https://daringfireball.net/projects/markdown/):</span><span class="sxs-lookup"><span data-stu-id="c09aa-148">Here's [Daring Fireball](https://daringfireball.net/projects/markdown/) 's example:</span></span>

<span data-ttu-id="c09aa-149">Texto insertado:</span><span class="sxs-lookup"><span data-stu-id="c09aa-149">Inline text:</span></span>

    I get 10 times more traffic from [Google][1] than from [Yahoo][2] or [MSN][3].

<span data-ttu-id="c09aa-150">Referencias de vínculos al final del artículo:</span><span class="sxs-lookup"><span data-stu-id="c09aa-150">Link references at the end of the article:</span></span>

    <!--Reference links in article-->
    [1]: http://google.com/
    [2]: http://search.yahoo.com/
    [3]: http://search.msn.com/

<span data-ttu-id="c09aa-151">Asegúrese de incluir el espacio después de los dos puntos, antes del vínculo.</span><span class="sxs-lookup"><span data-stu-id="c09aa-151">Make sure that you include the space after the colon, before the link.</span></span> <span data-ttu-id="c09aa-152">Cuando inserta un vínculo a otro artículo técnico, si se olvida de incluir el espacio, el vínculo se romperá en el artículo publicado.</span><span class="sxs-lookup"><span data-stu-id="c09aa-152">When you link to other technical articles, if you forget to include the space, the link will be broken in the published article.</span></span>

## <a name="links-to-pages-that-are-not-part-of-the-technical-documentation-set"></a><span data-ttu-id="c09aa-153">Vínculos a páginas que no forman parte de la serie de documentos técnicos</span><span class="sxs-lookup"><span data-stu-id="c09aa-153">Links to pages that are not part of the technical documentation set</span></span>

<span data-ttu-id="c09aa-154">Para vincular a una página que no sea propiedad de Microsoft (como una página de precios, una página del Acuerdo de Nivel de Servicio o cualquier otra página que no se corresponda con un artículo de documentación), use una dirección URL absoluta, pero omita la configuración regional.</span><span class="sxs-lookup"><span data-stu-id="c09aa-154">To link to a page on another Microsoft property (such as a pricing page, SLA page, or anything else that is not a documentation article), use an absolute URL, but omit the locale.</span></span> <span data-ttu-id="c09aa-155">El objetivo en este caso es que los vínculos funcionen en GitHub y en el sitio representado.</span><span class="sxs-lookup"><span data-stu-id="c09aa-155">The goal here is that links work in GitHub and on the rendered site:</span></span>

    [link text](https://azure.microsoft.com/pricing/details/virtual-machines/)

## <a name="links-to-third-party-sites"></a><span data-ttu-id="c09aa-156">Vínculos a sitios de terceros</span><span class="sxs-lookup"><span data-stu-id="c09aa-156">Links to third-party sites</span></span>

<span data-ttu-id="c09aa-157">La mejor experiencia del usuario minimiza el redireccionamiento de los usuarios a otro sitio.</span><span class="sxs-lookup"><span data-stu-id="c09aa-157">The best user experience minimizes sending users to another site.</span></span> <span data-ttu-id="c09aa-158">Por tanto, base todos los vínculos a sitios de terceros, que a veces necesitamos incluir, en esta información:</span><span class="sxs-lookup"><span data-stu-id="c09aa-158">So base any links to third-party sites, which we do sometimes need, on this info:</span></span>

- <span data-ttu-id="c09aa-159">**Responsabilidad:** vínculo a contenido de terceros cuando va a compartir la información del tercero.</span><span class="sxs-lookup"><span data-stu-id="c09aa-159">**Accountability**: Link to third-party content when it's the third-party's information to share.</span></span> <span data-ttu-id="c09aa-160">Por ejemplo, no es responsabilidad de Microsoft informar sobre cómo se usan las herramientas para desarrolladores de Android, sino que le corresponde a Google.</span><span class="sxs-lookup"><span data-stu-id="c09aa-160">For example, it's not Microsoft's place to tell people how to use Android developer tools--that is Google's story to tell.</span></span> <span data-ttu-id="c09aa-161">Si resulta necesario, se puede explicar cómo usar las herramientas para desarrolladores de Android *con* Azure, pero Google informará sobre el procedimiento para usar sus herramientas.</span><span class="sxs-lookup"><span data-stu-id="c09aa-161">If we need to, we can explain how to use Android developer tools *with* Azure, but Google should tell the story of how to use their tools.</span></span>
- <span data-ttu-id="c09aa-162">**Aprobación de PM**: solicitar la aprobación de Microsoft en contenido de terceros.</span><span class="sxs-lookup"><span data-stu-id="c09aa-162">**PM signoff**: Request that Microsoft sign off on third-party content.</span></span> <span data-ttu-id="c09aa-163">Al insertar un vínculo a dicho contenido, es un indicativo de la confianza depositada en él y de la obligación asumida en caso de que los usuarios sigan las instrucciones.</span><span class="sxs-lookup"><span data-stu-id="c09aa-163">By linking to it, we are saying something about our trust in it and our obligation if people follow the instructions.</span></span>
- <span data-ttu-id="c09aa-164">**Revisiones de actualizaciones:** asegúrese de que la información de terceros está actualizada, es correcta y pertinente y de que el vínculo no ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="c09aa-164">**Freshness reviews**: Make sure that the third-party info is still current, correct, and relevant, and that the link hasn’t changed.</span></span>
- <span data-ttu-id="c09aa-165">**Fuera del sitio:** asegúrese de que los usuarios tienen constancia de que van a visitar otro sitio.</span><span class="sxs-lookup"><span data-stu-id="c09aa-165">**Offsite**: Make users aware that they are going to another site.</span></span> <span data-ttu-id="c09aa-166">Si el contexto no lo deja claro, agregue una frase aplicable.</span><span class="sxs-lookup"><span data-stu-id="c09aa-166">If the context does not make that clear, add a qualifying phrase.</span></span> <span data-ttu-id="c09aa-167">Por ejemplo: "Los requisitos previos comprenden las herramientas para desarrolladores de Android, que puede descargar en el sitio de Android Studio".</span><span class="sxs-lookup"><span data-stu-id="c09aa-167">For example: “Prerequisites include the Android Developer Tools, which you can download on the Android Studio site.”</span></span>
- <span data-ttu-id="c09aa-168">**Pasos siguientes:** es buena idea agregar un vínculo, por ejemplo, a un blog de MVP en una sección de "Pasos siguientes".</span><span class="sxs-lookup"><span data-stu-id="c09aa-168">**Next steps**: It’s fine to add a link to, say, an MVP blog in a "Next steps" section.</span></span> <span data-ttu-id="c09aa-169">Una vez más, debe asegurarse de que los usuarios saben que van a abandonar el sitio.</span><span class="sxs-lookup"><span data-stu-id="c09aa-169">Again, just make sure that users understand they’ll be leaving the site.</span></span>
- <span data-ttu-id="c09aa-170">**Legal:** estamos cubiertos legalmente por la sección **Vínculos a sitios web de terceros** de los **Términos de uso** cuyo vínculo se encuentra en el pie de página de todas las páginas de ms.com.</span><span class="sxs-lookup"><span data-stu-id="c09aa-170">**Legal**: We are covered legally under **Links to Third Party Sites** in the **Terms of Use** footer on every ms.com page.</span></span>

## <a name="links-to-msdn-or-technet"></a><span data-ttu-id="c09aa-171">Vínculos a MSDN o TechNet</span><span class="sxs-lookup"><span data-stu-id="c09aa-171">Links to MSDN or TechNet</span></span>

<span data-ttu-id="c09aa-172">Cuando necesite insertar un vínculo a MSDN o TechNet, use el vínculo completo al tema y quite la configuración regional de idioma "en-us" del vínculo.</span><span class="sxs-lookup"><span data-stu-id="c09aa-172">When you need to link to MSDN or TechNet, use the full link to the topic, and remove the "en-us" language locale from the link.</span></span>

## <a name="links-to-azure-powershell-reference-content"></a><span data-ttu-id="c09aa-173">Vínculos al contenido de referencia de Azure PowerShell</span><span class="sxs-lookup"><span data-stu-id="c09aa-173">Links to Azure PowerShell reference content</span></span>

<span data-ttu-id="c09aa-174">El contenido de referencia de Azure PowerShell ha experimentado varias modificaciones desde noviembre de 2016.</span><span class="sxs-lookup"><span data-stu-id="c09aa-174">The Azure PowerShell reference content has been through several changes since November 2016.</span></span> <span data-ttu-id="c09aa-175">Aplique las siguientes instrucciones para vincular a este contenido desde otros artículos de docs.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="c09aa-175">Use the following guidelines for linking to this content from other articles on docs.microsoft.com.</span></span>

<span data-ttu-id="c09aa-176">Estructura de la dirección URL:</span><span class="sxs-lookup"><span data-stu-id="c09aa-176">Structure of the URL:</span></span>

* <span data-ttu-id="c09aa-177">Para cmdlets:</span><span class="sxs-lookup"><span data-stu-id="c09aa-177">For cmdlets:</span></span>
  - `/powershell/module/<module-name>/<cmdlet-name>[?view=<moniker-name>]`
* <span data-ttu-id="c09aa-178">Para temas conceptuales:</span><span class="sxs-lookup"><span data-stu-id="c09aa-178">For conceptual topics:</span></span>
  - `/powershell/azure/<topic-file-name>[?view=<moniker-name>]`
  - `/powershell/azure/<service-name>/<topic-file-name>[?view=<moniker-name>]`

<span data-ttu-id="c09aa-179">La parte &lt;moniker-name&gt; es opcional.</span><span class="sxs-lookup"><span data-stu-id="c09aa-179">The &lt;moniker-name&gt; portion is optional.</span></span> <span data-ttu-id="c09aa-180">Si se omite, se le redireccionará a la última versión del contenido.</span><span class="sxs-lookup"><span data-stu-id="c09aa-180">If it's omitted, you will be directed to the latest version of the content.</span></span> <span data-ttu-id="c09aa-181">La información correspondiente a la sección &lt;service-name&gt; es la que aparece en los ejemplos expuestos en las siguientes direcciones URL base:</span><span class="sxs-lookup"><span data-stu-id="c09aa-181">The &lt;service-name&gt; portion is one of the examples shown in the following base URLs:</span></span>

- <span data-ttu-id="c09aa-182">Contenido de Azure PowerShell (AzureRM): [https://docs.microsoft.com/powershell/azure/](https://docs.microsoft.com/powershell/azure/)</span><span class="sxs-lookup"><span data-stu-id="c09aa-182">Azure PowerShell (AzureRM) content: [https://docs.microsoft.com/powershell/azure/](https://docs.microsoft.com/powershell/azure/)</span></span>
- <span data-ttu-id="c09aa-183">Contenido de Azure PowerShell (ASM): [https://docs.microsoft.com/powershell/azure/_servicemanagement_](https://docs.microsoft.com/powershell/azure/servicemanagement)</span><span class="sxs-lookup"><span data-stu-id="c09aa-183">Azure PowerShell (ASM) content: [https://docs.microsoft.com/powershell/azure/_servicemanagement_](https://docs.microsoft.com/powershell/azure/servicemanagement)</span></span>
- <span data-ttu-id="c09aa-184">Contenido de Azure Active Directory (AzureAD) PowerShell: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/active-directory)</span><span class="sxs-lookup"><span data-stu-id="c09aa-184">Azure Active Directory (AzureAD) PowerShell content: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/active-directory)</span></span>
- <span data-ttu-id="c09aa-185">Azure Service Fabric PowerShell: [https://docs.microsoft.com/powershell/azure/_active-directory_](https://docs.microsoft.com/powershell/azure/service-fabric)</span><span class="sxs-lookup"><span data-stu-id="c09aa-185">Azure Service Fabric PowerShell: [https://docs.microsoft.com/powershell/azure/_service-fabric_](https://docs.microsoft.com/powershell/azure/service-fabric)</span></span>
- <span data-ttu-id="c09aa-186">Azure Information Protection PowerShell: [https://docs.microsoft.com/powershell/azure/_aip_](https://docs.microsoft.com/powershell/azure/aip)</span><span class="sxs-lookup"><span data-stu-id="c09aa-186">Azure Information Protection PowerShell: [https://docs.microsoft.com/powershell/azure/_aip_](https://docs.microsoft.com/powershell/azure/aip)</span></span>
- <span data-ttu-id="c09aa-187">Azure Elastic DB Jobs PowerShell: [https://docs.microsoft.com/powershell/azure/_elasticdbjobs_](https://docs.microsoft.com/powershell/azure/elasticdbjobs)</span><span class="sxs-lookup"><span data-stu-id="c09aa-187">Azure Elastic DB Jobs PowerShell: [https://docs.microsoft.com/powershell/azure/_elasticdbjobs_](https://docs.microsoft.com/powershell/azure/elasticdbjobs)</span></span>

<span data-ttu-id="c09aa-188">Si hace clic en estas direcciones URL, se le redireccionará a la última versión del contenido.</span><span class="sxs-lookup"><span data-stu-id="c09aa-188">When you use these URLs, you will be redirected to the latest version of the content.</span></span> <span data-ttu-id="c09aa-189">De esta forma, no tiene que especificar un moniker de versión.</span><span class="sxs-lookup"><span data-stu-id="c09aa-189">This way, you don't have to specify a version moniker.</span></span> <span data-ttu-id="c09aa-190">Además, evita tener vínculos a contenido conceptual que se deba actualizar cuando la versión cambia.</span><span class="sxs-lookup"><span data-stu-id="c09aa-190">And you won't have links to conceptual content that must be updated when the version changes.</span></span>

<span data-ttu-id="c09aa-191">Para crear el vínculo correcto, busque la página a la que quiere redireccionar en el explorador y copie la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="c09aa-191">To create the correct link, find the page that you want to link to in your browser, and copy the URL.</span></span>
<span data-ttu-id="c09aa-192">A continuación, quite "https://docs.microsoft.com" y la información de configuración regional.</span><span class="sxs-lookup"><span data-stu-id="c09aa-192">Then, remove "https://docs.microsoft.com" and the locale info.</span></span>

<span data-ttu-id="c09aa-193">Cuando el vínculo remita a una tabla de contenido, debe usar la dirección URL completa sin la información de configuración regional.</span><span class="sxs-lookup"><span data-stu-id="c09aa-193">When you're linking from a TOC, you must use the full URL without the locale information.</span></span>

<span data-ttu-id="c09aa-194">Markdown de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c09aa-194">Example markdown:</span></span>

```markdown
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup)
[Get-AzureRmResourceGroup](/powershell/module/azurerm.resources/get-azurermresourcegroup?view=azurermps-4.1.0)
[New-AzureVM](/powershell/module/azure/new-azurevm?view=azuresmps-4.0.0)
[New-AzureRmVM](/powershell/module/azurerm.compute/new-azurermvm)
[Install Azure PowerShell for Service Management](/powershell/azure/servicemanagement/install-azurerm-ps)
[Install Azure PowerShell](/powershell/azure/install-azurerm-ps)
```
