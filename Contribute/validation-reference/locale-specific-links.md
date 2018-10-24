# <a name="locale-specific-links"></a>Vínculos específicos de la configuración regional

Los códigos de configuración regional, como `en-us`, no deberían incluirse en vínculos a determinados sitios de Microsoft. Si incluye un código de configuración regional en un vínculo de contenido en inglés, también se incluirá en los vínculos localizados, con lo que se ofrecerá una mala experiencia de localización. Por ejemplo, si un vínculo en contenido localizado al alemán incluye `en-us`, los clientes que lean este contenido se conducirán al artículo en inglés vinculado, aunque haya una versión disponible en alemán.

Elimine los códigos de configuración regional de los vínculos a sitios de Microsoft. A continuación se muestra un ejemplo.

Antes:

`https://docs.microsoft.com/en-us/vsts/load-test/app-service-web-app-performance-test`

Después:

`https://docs.microsoft.com/vsts/load-test/app-service-web-app-performance-test`

Los sitios siguientes están dentro del ámbito de esta validación:

- azure.microsoft.com
- docs.microsoft.com
- msdn.microsoft.com
- technet.microsoft.com