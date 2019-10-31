---
title: 'Guía de supervisión de la nube: estrategia de supervisión para los modelos de implementación en la nube'
titleSuffix: Microsoft Cloud Adoption Framework for Azure
description: Decida cuándo usar Azure Monitor o System Center Operations Manager en Microsoft Azure.
author: MGoedtel
ms.author: magoedte
ms.date: 10/04/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: operate
services: azure-monitor
ms.openlocfilehash: 9fdef4d5d3d9cd39d16566221262330ef110bb3a
ms.sourcegitcommit: 35c162d2d09ec1c4a57d3d57a5db1d56ee883806
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72548168"
---
# <a name="cloud-monitoring-guide-monitoring-strategy-for-cloud-deployment-models"></a>Guía sobre la supervisión en la nube: estrategia de supervisión para los modelos de implementación en la nube

En este artículo se incluye la estrategia de supervisión recomendada para cada uno de los modelos de implementación en la nube, según los criterios siguientes:

- Es necesario mantener el compromiso con Operations Manager u otra plataforma de supervisión empresarial porque aún no están disponibles en Azure Monitor la integración con los procesos de operaciones de TI, el conocimiento y la experiencia o determinada funcionalidad.
- Debe supervisar las cargas de trabajo tanto en el entorno local como en la nube pública, o solo en la nube.
- La estrategia de migración a la nube incluye modernizar las operaciones de TI y trasladarse a nuestros servicios y soluciones de supervisión en la nube.
- Es posible que cuente con sistemas críticos que no tienen una conexión física o que están aislados físicamente, hospedados en una nube privada o en hardware físico, y que sea necesario supervisarlos.

Nuestra estrategia incluye compatibilidad con la supervisión de los recursos de infraestructura (cargas de trabajo de proceso, almacenamiento y servidor), aplicación (usuario final, excepciones y cliente) y red para ofrecer una perspectiva completa de supervisión orientada a servicios.

## <a name="azure-cloud-monitoring"></a>Supervisión de la nube de Azure

Azure Monitor es el servicio de plataforma nativo de Azure que proporciona un único origen para la supervisión de recursos de Azure. Está diseñado para soluciones en la nube que se basan en Azure y que admiten una funcionalidad empresarial basada en cargas de trabajo de máquinas virtuales o en arquitecturas complejas que usan microservicios y otros recursos de la plataforma. Supervisa todos los niveles de la pila, empezando por los servicios de inquilino como Azure Active Directory Domain Services, y los eventos de suscripción y el estado del servicio de Azure. También supervisa los recursos de infraestructura, como las máquinas virtuales, el almacenamiento y los recursos de red, y, en el nivel superior, la aplicación. La supervisión de cada una de estas dependencias y la recopilación de las señales correctas que cada una puede emitir proporcionan la observabilidad de las aplicaciones y la infraestructura clave que necesita.

En la tabla siguiente se resume el enfoque recomendado para supervisar cada nivel de la pila.

<!-- markdownlint-disable MD033 -->

Nivel | Resource | Ámbito | Método
---|---|---|----
Application | Aplicación basada en web que se ejecuta en la plataforma .NET, .NET Core, Java, JavaScript y Node.js en una instancia de Azure VM, Azure App Service, Azure Service Fabric, Azure Functions y Azure Cloud Services | Supervisa una aplicación web activa para detectar automáticamente anomalías de rendimiento, identificar problemas y excepciones de código, y recopilar análisis de comportamiento del usuario. |  Azure Monitor (Application Insights)
Recursos de Azure: PaaS | 1. Servicios de Azure Database (por ejemplo, SQL o mySQL) | 1. Métricas de rendimiento de Azure Database for SQL. | 1. Habilita el registro de diagnósticos para transmitir datos de SQL a registros de Azure Monitor.
Recursos de Azure: IaaS | 1. Azure Storage<br/> 2. Azure Application Gateway<br/> 3. Grupos de seguridad de red<br/> 4. Administrador de tráfico de Azure<br/> 5. Máquina virtual<br/> 6. Instancias de Azure Kubernetes Service o Azure Container Instances | 1. Capacidad, disponibilidad y rendimiento.<br/> 2. Registros de rendimiento y diagnóstico (actividad, acceso, rendimiento y firewall).<br/> 3. Supervisa los eventos que se producen cuando se aplican las reglas y el contador de la regla para determinar el número de veces que se aplica una regla a las acciones de denegar o permitir.<br/> 4. Supervisa la disponibilidad del estado del punto de conexión.<br/> 5. Supervisa la capacidad, la disponibilidad y el rendimiento en el sistema operativo de la máquina virtual invitada. Asigna las dependencias de aplicaciones hospedadas en cada máquina virtual, incluida la visibilidad de las conexiones de red activas entre servidores, la latencia de conexiones entrantes y salientes, y los puertos en cualquier arquitectura conectada a TCP.<br/> 6. Supervisa la capacidad, la disponibilidad y el rendimiento de las cargas de trabajo que se ejecutan en contenedores e instancias de contenedor. | 1. Métricas de almacenamiento para Blob Storage.<br/> 2. Habilita el registro de diagnóstico y configura la transmisión a los registros de Azure Monitor.<br/> 3. Habilita el registro de diagnóstico de los grupos de seguridad de red y configura la transmisión a los registros de Azure Monitor.<br/> 4. Habilita el registro de diagnóstico de los puntos de conexión de Traffic Manager y configura la transmisión a los registros de Azure Monitor.<br/> 5. Habilitar Azure Monitor para VM<br/> 6. Habilita Azure Monitor para contenedores.
Red| Comunicación entre la máquina virtual y uno o más puntos de conexión (otra máquina virtual, un nombre de dominio completo, un identificador uniforme de recursos o una dirección IPv4). | Supervisa la disponibilidad, la latencia y los cambios de la topología de red que se producen entre la máquina virtual y el punto de conexión. | Azure Network Watcher
Suscripción de Azure | Estado del servicio de Azure y estado básico de los recursos | <li> Acciones administrativas realizadas en un servicio o recurso.<br/><li> El mantenimiento del servicio con un servicio de Azure se encuentra en un estado degradado o no disponible.<br/><li> Problemas de estado detectados con un recurso de Azure desde la perspectiva del servicio de Azure.<br/><li> Operaciones realizadas con la escalabilidad automática de Azure que indican un error o una excepción. <br/><li> Operaciones realizadas con Azure Policy que indican que se ha producido una acción permitida o denegada.<br/><li> Registro de las alertas generadas por Azure Security Center. |Se entrega en el registro de actividad para la supervisión y alertas mediante el uso de Azure Resource Manager.
Inquilino de Azure|Azure Active Directory || Habilita el registro de diagnóstico y configura la transmisión a los registros de Azure Monitor.

<!-- markdownlint-enable MD033 -->

## <a name="hybrid-cloud-monitoring"></a>Supervisión de la nube híbrida

En muchas organizaciones, la nube se debe abordar gradualmente y el modelo de nube híbrida suele ser el primer paso del recorrido. Puede seleccionar cuidadosamente el subconjunto adecuado de aplicaciones e infraestructura para comenzar la migración, a la vez que evita la interrupción de su actividad empresarial. Sin embargo, como ofrecemos dos plataformas de supervisión que admiten este modelo de nube, los responsables de la toma de decisiones de TI pueden tener dudas sobre cuál es la mejor opción para respaldar sus objetivos de negocio y operaciones de TI. Vamos a revisar diversos factores para despejar esa incertidumbre y que pueda decidir con conocimientos la plataforma que debe considerar.

Algunos de los aspectos técnicos clave que se deben tener en cuenta son:

- Debe recopilar datos de los recursos de Azure compatibles con la carga de trabajo y reenviarlos a las herramientas del proveedor de servicios locales o administrados existentes.

- Debe mantener la inversión actual en System Center Operations Manager y configurarlo para supervisar los recursos IaaS y PaaS que se ejecutan en Azure. De manera opcional, debido a que supervisa dos entornos con características diferentes, debe determinar, en función de los requisitos, si la integración con Azure Monitor respalda su estrategia.

- Como parte de la estrategia de modernización para normalizar una única herramienta para reducir costes y complejidad, se debe comprometer con Azure Monitor para la supervisión de los recursos en Azure y en la red corporativa.

En la tabla siguiente se resumen los requisitos que Azure Monitor y System Center Operations Manager admiten con la supervisión del modelo de nube híbrida según un conjunto de criterios comunes.

<!-- markdownlint-disable MD033 -->

|Requisito | Azure Monitor | Operations Manager |
|:--|:---|:---|
|Requisitos de infraestructura | **No** | **Sí**<br> Requiere como mínimo un servidor de administración y una instancia de SQL Server para hospedar la base de datos operativa y la base de datos de almacenamiento de datos de informes. Es más complejo cuando se requiere alta disponibilidad y recuperación ante desastres, máquinas en varios sitios, sistemas que no son de confianza y otras consideraciones de diseño complejas.|
|Conectividad limitada: sin Internet<br> o red aislada | **No** | **Sí** |
|Conectividad limitada: acceso a Internet controlado | **Sí** | **Sí** |
|Conectividad limitada: desconexión frecuente | **Sí** | **Sí** |
|Supervisión del estado configurable | **No** | **Sí** |
| Prueba de disponibilidad de la aplicación web (red aislada) | **Sí, limitada**<br> Azure Monitor tiene compatibilidad limitada en esta área y requiere excepciones de firewall personalizadas. | **Sí** |
| Prueba de disponibilidad de la aplicación web (distribuida globalmente) | **No** | **Sí** |
|Supervisión de cargas de trabajo de máquinas virtuales | **Sí, limitada**<br> Puede recopilar registros de errores, eventos de Windows y contadores de rendimiento de IIS y SQL Server. Requiere la creación de consultas, alertas y visualizaciones personalizadas. | **Sí**<br> Admite la supervisión de la mayoría de las cargas de trabajo de servidor con los módulos de administración disponibles. Requiere que el agente de Windows de Log Analytics o el agente de Operations Manager de la máquina virtual informe al grupo de administración de la red corporativa.|
|Supervisión de IaaS de Azure | **Sí** | **Sí**<br> Admite la supervisión de la mayor parte de la infraestructura de la red corporativa. Realiza un seguimiento del estado de disponibilidad, las métricas y las alertas de máquinas virtuales de Azure, SQL y almacenamiento a través del módulo de administración de Azure.|
|Supervisión de PaaS de Azure | **Sí** | **Sí, limitada**<br> En función de lo que se admite en el módulo de administración de Azure. |
|Supervisión del servicio de Azure | **Sí**<br> | **Sí**<br> Aunque actualmente no se proporciona ninguna supervisión nativa del estado del servicio de Azure a través de un módulo de administración, puede crear flujos de trabajo personalizados para consultar las alertas de estado del servicio de Azure. Use la API de REST de Azure para obtener alertas a través de las notificaciones existentes.|
|Supervisión de aplicaciones web modernas | **Sí** | **No** |
|Supervisión de aplicaciones web heredadas | **Sí, la limitación varía según el SDK**<br> Admite la supervisión de versiones anteriores de aplicaciones web de Java y .NET. | **Sí, limitada** |
|Supervisión de contenedores de Azure Kubernetes Service | **Sí** | **No** |
|Supervisión de contenedores de Docker y Windows | **Sí** | **No** |
|Supervisión del rendimiento de red | **Sí** | **Sí, limitada**<br> Admite comprobaciones de disponibilidad y recopila estadísticas básicas de los dispositivos de red mediante el protocolo SNMP de la red corporativa.|
|Análisis de datos interactivos | **Sí** | **No**<br> Se basa en informes predefinidos o personalizados de SQL Server Reporting Services, soluciones de visualización de terceros o una implementación de Power BI personalizada. Existen limitaciones de escala y rendimiento en el almacenamiento de datos de Operations Manager. Se puede integrar con los registros de Azure Monitor como alternativa para los requisitos de agregación de datos. La integración se logra configurando el conector de Log Analytics.|
|Diagnósticos de un extremo a otro, análisis de la causa principal y solución de problemas puntuales | **Sí** | **Sí, limitada**<br> Admite los diagnósticos de un extremo a otro y la solución de problemas solo para infraestructuras y aplicaciones locales. Utiliza otros componentes de System Center o soluciones de asociados.|
|Visualizaciones interactivas (paneles) | **Sí** | **Sí, limitada**<br> Proporciona los paneles esenciales con su consola web de HTLM5 o una experiencia avanzada de soluciones de asociados, como Squared Up y Savision. |
|Integración con herramientas de IT y DevOps | **Sí** | **Sí, limitada** |

<!-- markdownlint-enable MD033 -->

### <a name="collect-and-stream-monitoring-data-to-third-party-or-on-premises-tools"></a>Recopilación y transmisión en secuencia datos de supervisión a herramientas de terceros o locales

Para recopilar métricas y registros de recursos de la infraestructura y la plataforma de Azure, debe habilitar los registros de diagnósticos de Azure para esos recursos. Además, con las máquinas virtuales de Azure, puede recopilar métricas y registros del sistema operativo invitado habilitando la extensión de Azure Diagnostics. Para reenviar los datos de diagnóstico que se emiten desde los recursos de Azure a sus herramientas locales o al proveedor de servicios administrados, configure [Event Hubs](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-logs-stream-event-hubs) para transmitir en secuencias los datos.

### <a name="monitor-with-system-center-operations-manager"></a>Supervisión con System Center Operations Manager

Si bien System Center Operations Manager se diseñó originalmente como una solución local para supervisar las aplicaciones, las cargas de trabajo y la infraestructura que se ejecuta en el entorno de TI, evolucionó para incluir capacidades de supervisión en la nube y se integra con Azure, Office 365 y Amazon Web Services (AWS). Puede supervisar los distintos entornos con módulos de administración diseñados y actualizados para admitirlos.  

En el caso de los clientes que han realizado grandes inversiones en Operations Manager para lograr una supervisión completa que se integre estrechamente con sus procesos y herramientas de Administración de servicios de TI, o los nuevos clientes de Azure, es comprensible que se hagan las preguntas siguientes:

- ¿Puede Operations Manager continuar proporcionando valor y tiene sentido para la empresa?

- ¿Hacen las características de Operations Manager que sea adecuado para nuestra organización de TI?

- ¿Proporciona la integración de Operations Manager con Azure Monitor la solución de supervisión rentable y completa que se requiere?

Si ya ha invertido en Operations Manager, no es necesario concentrarse en planear una migración para reemplazarlo inmediatamente. Con Azure u otros proveedores de nube presentes como una extensión de su propia red local, Operations Manager puede supervisar las máquinas virtuales invitadas y los recursos de Azure como si estuvieran en la red corporativa. Esto requiere tener una conexión de red confiable entre la red y la red virtual de Azure con el ancho de banda suficiente.

Para supervisar las cargas de trabajo que se ejecutan en Azure, necesita:

- El [módulo de administración de Azure](https://www.microsoft.com/download/details.aspx?id=50013) para recopilar las métricas de rendimiento que los servicios de Azure emiten, como los roles web y de trabajo, las pruebas de disponibilidad de Application Insights (pruebas web), Service Bus, etc. El módulo de administración usa la API de REST de Azure para supervisar la disponibilidad y el rendimiento de estos recursos. Algunos tipos de servicio de Azure no tienen ninguna métrica ni supervisor predefinido en el módulo de administración, pero se pueden supervisar a través de las relaciones definidas en el módulo de administración de Azure para los servicios detectados.

- El [módulo de administración de Azure SQL Database](https://www.microsoft.com/download/details.aspx?id=38829) para supervisar la disponibilidad y el rendimiento de las instancias de Azure SQL Database y los servidores de Azure SQL Database mediante la API de REST de Azure y las consultas de T-SQL en vistas del sistema SQL Server.

- Para supervisar el sistema operativo invitado y las cargas de trabajo que se ejecutan en la máquina virtual, como SQL Server, IIS o Apache Tomcat, deberá descargar e importar el módulo de administración compatible con la aplicación, el servicio y el sistema operativo.

La información se define en el módulo de administración, que describe cómo supervisar las dependencias y los componentes individuales. Para ambos módulos de administración de Azure, es necesario realizar un conjunto de pasos de configuración en Azure y Operations Manager para comenzar a supervisar estos recursos.

En la capa de aplicación, Operations Manager ofrece funciones básicas de supervisión de rendimiento de aplicaciones para algunas versiones heredadas de .NET y Java. Si algunas aplicaciones del entorno de la nube híbrida operan en modo sin conexión o con aislamiento de red, de manera que no pueden comunicarse con un servicio en la nube pública, la Supervisión de rendimiento de aplicaciones (APM) de Operations Manager puede ser una opción viable para ciertos escenarios limitados. En el caso de las aplicaciones que no se ejecutan en plataformas heredadas, hospedadas tanto en el entorno local como en cualquier nube pública que permita la comunicación a través de un firewall (directo o a través de un proxy) con Azure, use Azure Monitor Application Insights. Esto ofrece una supervisión profunda y en el nivel de código, con compatibilidad de primera clase con ASP.NET, ASP.NET Core, Java, JavaScript y Node.js.

En el caso de las aplicaciones web a las que se puede acceder externamente, debe habilitar un tipo de transacciones sintéticas conocido como [supervisión de la disponibilidad]( https://docs.microsoft.com/azure/azure-monitor/app/monitor-web-app-availability). Es importante saber si la aplicación o un punto de conexión HTTP/HTTPS crítico en el que se basa la aplicación está disponible y con capacidad de respuesta. La supervisión de la disponibilidad de Application Insights le permite ejecutar pruebas desde varios centros de datos de Azure y proporcionar una conclusión del estado de la aplicación desde una perspectiva global.

Aunque Operations Manager sea capaz de supervisar los recursos hospedados en Azure, existen varias ventajas si se incluye Azure Monitor, ya que sus capacidades solventan las limitaciones de Operations Manager y establece una base sólida para respaldar una eventual migración. Aquí revisamos cada uno de ellos y recomendamos incluir Azure Monitor en su estrategia de supervisión híbrida.  

#### <a name="disadvantage-of-using-operations-manager-by-itself"></a>Desventaja de usar únicamente Operations Manager

1. El análisis de los datos de supervisión en Operations Manager se suele realizar mediante vistas predefinidas en módulos de administración a los que se tiene acceso desde la consola, los informes de SQL Server Reporting Services (SSRS) o las vistas personalizadas creadas por el usuario final. No es posible realizar de serie un análisis ad hoc de los datos. El informe de Operations Manager no es flexible, no se puede escalar el almacenamiento de datos que proporciona la retención a largo plazo de los datos de supervisión o no funciona bien, y se necesita experiencia en la escritura de instrucciones de T-SQL, el desarrollo de una solución de Power BI o el uso de soluciones de terceros para compatibilidad con los requisitos de los diferentes roles de la organización de TI.

2. Las alertas de Operations Manager no proporcionan compatibilidad con expresiones complejas e incluyen lógica de correlación en un esfuerzo por reducir el ruido de las alertas y agrupan las alertas en un esfuerzo por mostrar la relación entre ellas para ayudar a identificar la causa principal del problema.

#### <a name="advantage-of-operations-manager--azure-monitor"></a>Ventaja de Operations Manager con Azure Monitor

1. Los registros de Azure Monitor son la solución alternativa a las limitaciones de Operations Manager y complementa la base de datos de almacenamiento de datos de Operations Manager para recopilar datos importantes de rendimiento y registro. Azure Monitor ofrece un mejor análisis, rendimiento al consultar grandes volúmenes de datos y retención que el almacenamiento de datos de Operations Manager. Su lenguaje de consulta permite crear consultas mucho más complejas y sofisticadas, con capacidad para ejecutar consultas en terabytes de datos en segundos. Puede transformar rápidamente los datos en gráficos circulares, gráficos de tiempo y muchas otras visualizaciones. Ya no estará limitado por el trabajo con informes en SQL Server Reporting Services basados en Operations Manager, consultas SQL personalizadas u otras soluciones alternativas para analizar estos datos.

2. Ofrezca una experiencia de alertas mejorada mediante la implementación de la solución de administración de alertas de Azure Monitor. Las alertas generadas en el grupo de administración de Operations Manager se pueden reenviar al área de trabajo de Log Analytics de Azure Monitor. Puede configurar la suscripción responsable de reenviar alertas desde Operations Manager a Azure Monitor Logs para que reenvíe solo determinadas alertas. Por ejemplo, puede reenviar únicamente las alertas que cumplan con sus criterios para las consultas que ayuden a la administración de problemas de tendencias y la investigación de la causa principal de errores o problemas, a través de un único panel. Además, puede correlacionar otros datos de registro de Application Insights u otros orígenes para obtener información que ayude a mejorar la experiencia del usuario, aumentar el tiempo de actividad y reducir el tiempo de resolución de incidentes.

3. Supervise la infraestructura y las aplicaciones nativas en la nube desde una arquitectura simple o de varios niveles en Azure y use Operations Manager para supervisar la infraestructura local. Esto incluye una o más máquinas virtuales, varias máquinas virtuales colocadas en un conjunto de disponibilidad o un conjunto de escalado de máquinas virtuales, o una aplicación en contenedor implementada en Azure Kubernetes Service (AKS) que se ejecuta en contenedores de Windows Server o Linux.

4. Puede usar la solución System Center Operations Manager Health Check para evaluar proactivamente el riesgo y el estado del grupo de administración de System Center Operations Manager a intervalos regulares. Esto puede reemplazar o complementar cualquier funcionalidad personalizada que haya agregado al grupo de administración.

5. Con la característica de asignación de Azure Monitor para VM, permite supervisar las métricas de conectividad estándar de las conexiones de red entre las máquinas virtuales de Azure y las máquinas virtuales locales. Las métricas incluyen el tiempo de respuesta, las solicitudes por minuto, el rendimiento del tráfico y los vínculos. Puede identificar las conexiones con errores, solucionar problemas, realizar la validación de la migración, ejecutar el análisis de seguridad y verificar la arquitectura general del servicio. La asignación puede detectar automáticamente componentes de aplicación en sistemas Windows y Linux y asignar la comunicación entre servicios. Esto le ayuda a identificar las conexiones y las dependencias de las que no tenía constancia, a planear y validar la migración a Azure y a minimizar la especulación durante la resolución de incidentes.

6. Con Network Performance Monitor, supervise la conectividad de red entre:

   - La red corporativa y Azure.

   - Aplicaciones y microservicios críticos de varios niveles.

   - Ubicaciones de usuario y aplicaciones basadas en web (HTTP/HTTP).

   Esta estrategia ofrece visibilidad del nivel de red, sin necesidad de SNMP. También puede presentarse en un mapa de topología interactivo, la topología salto a salto de rutas entre el punto de conexión de origen y de destino. Es una opción mejor que intentar lograr el mismo resultado con la supervisión de red en Operations Manager u otras herramientas de supervisión de red que se usan actualmente en su entorno.

### <a name="monitor-with-azure-monitor"></a>Supervisión con Azure Monitor

Aunque una migración a la nube presenta numerosos desafíos, también incluye numerosas oportunidades. Permite a la organización migrar desde una o varias herramientas locales de supervisión de la empresa para no solo reducir potencialmente los gastos de capital y los costos operativos, sino también para beneficiarse de las ventajas que una plataforma de supervisión en la nube como Azure Monitor ofrece a escala de nube. Examine los requisitos de supervisión y alertas, la configuración de las herramientas de supervisión existentes, las cargas de trabajo que pasan a la nube y configure Azure Monitor una vez finalizado el plan.

- Supervise la infraestructura y las aplicaciones híbridas, desde una arquitectura simple o de varios niveles en la que los componentes se hospedan entre Azure, otros proveedores de nube y la red corporativa. Esto incluye una o más máquinas virtuales, varias máquinas virtuales colocadas en un conjunto de disponibilidad o un conjunto de escalado de máquinas virtuales, o una aplicación en contenedor implementada en Azure Kubernetes Service (AKS) que se ejecuta en contenedores de Windows Server o Linux.

- Habilite Azure Monitor para VM, Azure Monitor para contenedores y Application Insights para detectar y diagnosticar problemas entre la infraestructura y las aplicaciones. Para un análisis y una correlación más completos de los datos recopilados de los diversos componentes o dependencias compatibles con la aplicación, debe usar los registros de Azure Monitor.

- Cree alertas inteligentes que se puedan aplicar a un conjunto básico de aplicaciones y componentes de servicio, ayude a reducir el ruido de las alertas con umbrales dinámicos para señales complejas y use la agregación de alertas basada en algoritmos de aprendizaje automático para ayudar a identificar rápidamente el problema.

- Defina una biblioteca de consultas y paneles para respaldar los requisitos de los diferentes roles de la organización de TI.

- Defina estándares y métodos para habilitar la supervisión en los recursos híbridos y en la nube, una línea de base de supervisión para cada recurso, umbrales de alerta, etc.  

- Configure el control de acceso basado en rol (RBAC) para conceder a los usuarios y grupos únicamente el nivel de acceso que necesiten para trabajar con los datos de supervisión de los recursos de cuya administración son responsables.

- Incluya automatización y autoservicio para permitir que cada equipo cree, habilite y ajuste las configuraciones de supervisión y alertas que necesiten.

## <a name="private-cloud-monitoring"></a>Supervisión de la nube privada

Puede lograr una supervisión holística de Azure Stack con System Center Operations Manager. En concreto, puede supervisar las cargas de trabajo que se ejecutan en el inquilino, en el nivel de recurso, en las máquinas virtuales y en la infraestructura que hospeda a Azure Stack (servidores físicos y conmutadores de red). También puede lograr una supervisión holística con una combinación de las [funcionalidades de supervisión de infraestructuras](https://docs.microsoft.com/azure/azure-stack/azure-stack-monitor-health) incluidas en Azure Stack. Estas funcionalidades ayudan a ver el estado y las alertas de una región de Azure Stack y el [servicio de Azure Monitor](https://docs.microsoft.com/azure/azure-stack/user/azure-stack-metrics-azure-data) en Azure Stack, que proporciona registros y métricas de infraestructura de nivel básico para la mayoría de los servicios.

Si ya ha invertido en Operations Manager, use el módulo de administración de Azure Stack para supervisar la disponibilidad y el estado de mantenimiento de las implementaciones de Azure Stack. Esto incluye las regiones, los proveedores de recursos, las actualizaciones, las ejecuciones de actualización, las unidades de escalado, los nodos de unidad, los roles de infraestructura y sus instancias (entidades lógicas que constan de los recursos de hardware). Este módulo utiliza las API REST del proveedor de recursos de mantenimiento y actualización para comunicarse con Azure Stack. Para supervisar los servidores físicos y los dispositivos de almacenamiento, use el módulo de administración de los proveedores OEM (proporcionado, por ejemplo, por Lenovo, Hewlett Packard o Dell). Operations Manager puede supervisar de forma nativa los conmutadores de red para recopilar estadísticas básicas mediante el protocolo SNMP. Es posible supervisar las cargas de trabajo de inquilinos con el módulo de administración de Azure siguiendo dos pasos básicos. Configure la suscripción que desea supervisar y, a continuación, agregue los monitores de dicha suscripción.

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [Recopilación de los datos adecuados](./data-collection.md)
