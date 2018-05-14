## <a name="pull-request-processing"></a>Procesamiento de solicitudes de incorporación de cambios

La sección anterior le guía en el proceso de envío de enviar los cambios propuestos, agrupados en una nueva solicitud de incorporación de cambios (PR) que se agrega a la cola de solicitudes de incorporación de cambios del repositorio de destino. Una solicitud de incorporación de cambios permite el modelo de colaboración de GitHub. Para ello, se solicita que se "incorporen" los cambios de la rama de trabajo y se combinen con los de otra rama. En la mayoría de los casos, la otra rama es la rama predeterminada/"master" en el repositorio principal.

### <a name="validation"></a>Validación

Antes de que la solicitud de incorporación de cambios se pueda combinar en su rama de destino, puede que sea necesario pasar uno o varios procesos de validación de PR. Los procesos de validación pueden variar en función del alcance de los cambios propuestos y de la reglas del repositorio de destino. Tras enviar la solicitud de incorporación de cambios, cabría esperar que suceda algo de lo siguiente:

- **Capacidad de combinación**: primero se realiza una prueba de la capacidad de combinación de GitHub de línea base para comprobar si los cambios propuestos en la rama entran en conflicto con la rama de destino. Si la solicitud de incorporación de cambios indica que no se ha superado la prueba, será necesario reconciliar el contenido que provoca los conflictos que impiden la combinación para continuar con el proceso.
- **CLA**: si contribuye a un repositorio público y no es empleado de Microsoft, según la magnitud de los cambios propuestos, es posible que se le solicite que rellene un breve Contrato de licencia de colaboración (CLA) la primera vez que envíe una solicitud de incorporación de cambios a ese repositorio. Después de que se realiza el paso del CLA, se procesa la solicitud de incorporación de cambios.
- **Etiquetado**: se aplican automáticamente etiquetas a la solicitud de incorporación de cambios para indicar su estado a medida que pasa por el flujo de trabajo de validación. Por ejemplo, una nueva solicitud de incorporación de cambios podría recibir automáticamente la etiqueta "no combinar", que indica que la solicitud de incorporación de cambios aún no ha completado los pasos de validación, revisión y aprobación.
- **Validación y compilación**: comprobaciones automatizadas certifican que los cambios pasan las pruebas de validación. Las pruebas de validación pueden generar avisos o errores que requieran realizar cambios en uno o varios archivos de la solicitud de incorporación de cambios antes de poder combinarla. Los resultados de la prueba de validación se agregan como comentario a la solicitud de incorporación de cambios para que puedan revisarse posteriormente y enviarse por correo electrónico.
- **Ensayo**: las páginas del artículo afectadas por los cambios se implementan automáticamente en un entorno de ensayo para revisarlas una vez que se han validado y compilado correctamente. En los comentarios de solicitud de incorporación de cambios, aparecen direcciones URL de vista previa.
- **Combinación automática**: si la solicitud de incorporación de cambios supera la prueba de validación y cumple ciertos criterios, puede combinarse automáticamente. En este caso, no es necesario realizar ninguna acción.

### <a name="review-and-sign-off"></a>Revisión y aprobación

Una vez que han finalizado todos los procesos de la solicitud de incorporación de cambios, convendría revisar los resultados (comentarios de la solicitud de incorporación de cambios, las URL de vista previa, etc.) para determinar si es necesario realizar más cambios en los archivos antes de que se aprueben para la combinación. Si el revisor de una solicitud de incorporación de cambios ya ha revisado la solicitud y ha detectado algunos problemas o cuestiones destacados que deban resolverse antes de la combinación, también puede proporcionar sus comentarios.

[!INCLUDE[contribute-how-to-pull-requests-apex-automation.md](contribute-how-to-pull-requests-apex-automation.md)]

Una vez que la solicitud no presente ningún problema y esté aprobada, los cambios se combinan en la rama primaria y la solicitud de incorporación de cambios se cierra.

### <a name="publishing"></a>Publicación

Recuerde que la solicitud de incorporación de cambios debe combinarla un revisor antes de que los cambios se incluyan en la siguiente ronda programada de publicación. Normalmente, las solicitudes se revisan o combinan según el orden de envío. Si la solicitud de incorporación de cambios debe combinarse para una ronda de publicación específica, deberá trabajar con el revisor de la solicitud con la antelación suficiente para garantizar que la combinación se realice a tiempo.

Una vez que se hayan aprobado y combinado las contribuciones, el proceso de publicación Docs.Microsoft.Com las recoge. Dependiendo del equipo que administre el repositorio en el que esté realizando la contribución, el tiempo de publicación puede variar. Los artículos publicados en las siguientes rutas de acceso normalmente se implementan de lunes a viernes entre las 10:30 y las 15:30 (PST):

- https://docs.microsoft.com/azure/
- https://docs.microsoft.com/aspnet/
- https://docs.microsoft.com/dotnet/
- https://docs.microsoft.com/enterprise-mobility-security

Es posible que los artículos tarden hasta 45 minutos en aparecer en línea tras publicarlos. Después de que el artículo se ha publicado, puede comprobar los cambios en la URL apropiada: `https://docs.microsoft.com/<path-to-your-article-without-the-md-extension>`.
