---
title: Desarrollo e implementación de aplicaciones
description: Más información sobre el uso de Kubernetes en Cloud Adoption Framework para el desarrollo y la arquitectura de aplicaciones.
author: sabbour
ms.author: asabbour
ms.topic: guide
ms.date: 03/20/2020
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: 6ad36a6dfbce83b23bfcee382ff44daeb9db5f7f
ms.sourcegitcommit: 1a4b140f09bdaa141037c54a4a3b5577cda269db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "80392761"
---
<!-- cSpell:ignore asabbour sabbour autoscaler Istio Linkerd -->

# <a name="application-development-and-deployment"></a>Desarrollo e implementación de aplicaciones

Examine los patrones y prácticas del desarrollo de aplicaciones, configure canalizaciones de DevOps e implemente los procedimientos recomendados de ingeniería de confiabilidad de sitios (SRE).

## <a name="plan-train-and-proof"></a>Planeamiento, entrenamiento y prueba

Al principio, la lista de comprobación y los recursos siguientes le ayudarán a planear el desarrollo y la implementación de aplicaciones. Debe ser capaz de responder a estas preguntas:

> [!div class="checklist"]
>
> - ¿Ha preparado el entorno de desarrollo y el flujo de trabajo de configuración?
> - ¿Cómo estructurará la carpeta del proyecto para dar respaldo al desarrollo de aplicaciones de Kubernetes?
> - ¿Ha identificado los requisitos de estado, configuración y almacenamiento de la aplicación?

<!-- markdownlint-disable MD033 -->

> [!div class="tdCol2BreakAll"]
>
> | Lista de comprobación | Recursos |
> |------------------------------------------------------------------|-----------------------------------------------------------------|
> | **Preparación del entorno de desarrollo**. Configure el entorno con las herramientas que necesita para crear contenedores y configurar el flujo de trabajo de desarrollo. | [Uso de Docker en Visual Studio Code](https://code.visualstudio.com/docs/azure/docker) <br/>[Uso&nbsp;de&nbsp;Kubernetes&nbsp;en&nbsp;Visual&nbsp;Studio Code](https://code.visualstudio.com/docs/azure/kubernetes) <br/> [Introducción a Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/about) |
> | **Inclusión de la aplicación en contenedores**. Familiarícese con la experiencia global de desarrollo de Kubernetes, en la que se incluyen scaffolding de aplicaciones, flujos de trabajo de bucle interno, marcos de administración de aplicaciones, canalizaciones de CI/CD, agregación de registros, supervisión y métricas de aplicaciones. | [Inclusión de aplicaciones en contenedores con Docker y Kubernetes (libro electrónico)](https://azure.microsoft.com/resources/containerize-your-apps-with-docker-and-kubernetes) <br/> [Experiencia global de desarrollo de Kubernetes en Azure (seminario web)](https://info.microsoft.com/AU-AzureApp-WBNR-FY20-11Nov-12-ContainerizeYourApplicationswithKubernetesonAzure-SRDEM10557_LP02OnDemandRegistration-ForminBody.html) |
> | **Revisión de escenarios habituales de Kubernetes.** A menudo se considera a Kubernetes como una plataforma que proporciona microservicios, pero se está convirtiendo en una plataforma mucho más amplia. Vea este vídeo para más información sobre escenarios de Kubernetes habituales como el análisis y el flujo de trabajo por lotes.    | [Escenarios&nbsp;habituales&nbsp;de&nbsp;uso de&nbsp;Kubernetes&nbsp;(vídeo)](https://www.youtube.com/watch?v=zd8vYhrFXp4&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=7) |
> | **Preparación de la aplicación para Kubernetes**. Prepare el diseño del sistema de archivos de la aplicación para Kubernetes y organice las versiones semanales o diarias. Obtenga información sobre cómo el proceso de implementación de Kubernetes permite actualizaciones confiables sin tiempo de inactividad. | [Diseño de proyectos para aplicaciones de Kubernetes correctas (seminario web)](https://info.microsoft.com/ww-OnDemandRegistration-successful-kubernetes-applications-webinar.html) <br/> [Funcionamiento de las implementaciones de Kubernetes (vídeo)](https://www.youtube.com/watch?v=mNK14yXIZF4&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=3) </br> [Realización de un taller de AKS](https://aka.ms/learn/aksworkshop) |
> | **Administración del almacenamiento de aplicaciones.** Comprenda las necesidades de rendimiento y los métodos de acceso a los pods para que pueda proporcionar las opciones de almacenamiento adecuadas. También debe planear las formas de realizar copias de seguridad y probar el proceso de restauración en busca de almacenamiento conectado. | [Aspectos básicos de las aplicaciones con estado en Kubernetes (vídeo)](https://www.youtube.com/watch?v=GieXzb91I40&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=9) <br/> [Estado y datos en aplicaciones de Docker](https://docs.microsoft.com/dotnet/architecture/microservices/architect-microservice-container-applications/docker-application-state-data) <br/>[Opciones de almacenamiento de Azure Kubernetes Service](https://docs.microsoft.com/azure/aks/operator-best-practices-storage) |
> | **Administración de secretos de aplicación**. No almacene las credenciales en el código de la aplicación. Se debe usar un almacén de claves para almacenar y recuperar las claves y credenciales.  | [Funcionamiento de Kubernetes y la administración de configuración (vídeo)](https://www.youtube.com/watch?v=vRcQOZLnKUk&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=11) <br/> [Descripción de la administración de secretos en Kubernetes (vídeo)](https://www.youtube.com/watch?v=KmhM33j5WYk&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=10) <br/>[Uso de Azure Key Vault con Kubernetes](https://github.com/Azure/kubernetes-keyvault-flexvol) <br/>[Uso de Pod Identity para autenticarse y acceder a los recursos de Azure](https://github.com/Azure/aad-pod-identity) |

## <a name="deploy-to-production-and-apply-best-practices"></a>Implementación en producción y aplicación de procedimientos recomendados

Cuando prepare la aplicación para producción, debe implementar un conjunto mínimo de procedimientos recomendados. Use la siguiente lista de comprobación en esta fase. Debe ser capaz de responder a estas preguntas:

> [!div class="checklist"]
>
> - ¿Puede supervisar todos los aspectos de la aplicación?
> - ¿Ha definido los requisitos de los recursos para la aplicación? ¿De qué información dispone sobre los requisitos de escalado?
> - ¿Puede implementar nuevas versiones de la aplicación sin que afecte a los sistemas de producción?

<!-- -->

> [!div class="tdCol2BreakAll"]
>
> | Lista de comprobación  | Recursos                                                                                                     |
> |------------------------------------------------------------------|-----------------------------------------------------------------|
> | **Configuración de las comprobaciones del estado de preparación y ejecución.** Kubernetes usa comprobaciones de preparación y ejecución para saber cuándo la aplicación está lista para recibir tráfico y cuándo debe reiniciarse. Si no se definen estas comprobaciones, Kubernetes no podrá determinar si la aplicación está en funcionamiento.   | [Comprobaciones de ejecución y preparación](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes) |
> | **Configuración del registro, la supervisión de aplicaciones y las alertas.** La supervisión de los contenedores es fundamental, sobre todo cuando se ejecuta un clúster de producción, a escala, con varias aplicaciones.  El método recomendado de registro para las aplicaciones incluidas en contenedores consiste en escribir en los flujos de salida estándar (stdout) y de error estándar (stderr).   | [Registro en Kubernetes](https://kubernetes.io/docs/concepts/cluster-administration/logging) <br/> [Introducción a la supervisión y las alertas de Kubernetes (vídeo)](https://www.youtube.com/watch?v=W7aN_z-cyUw&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=16) <br/> [Azure Monitor para contenedores](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview) <br/> [Habilitación y revisión de los registros del nodo maestro de Kubernetes en Azure Kubernetes Service (AKS)](https://docs.microsoft.com/azure/aks/view-master-logs)  <br/> [Visualización de registros, eventos y métricas de pods de Kubernetes en tiempo real](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-livedata-overview) |
> | **Definición de los requisitos de los recursos para la aplicación.** La manera principal de administrar los recursos de proceso en un clúster de Kubernetes consiste en usar solicitudes y límites de pods. Estos límites y solicitudes le indican al programador de Kubernetes qué recursos de proceso deben asignarse a un pod.     | [Definición&nbsp;de las&nbsp;solicitudes y&nbsp;límites&nbsp;de los&nbsp;recursos del pod](https://docs.microsoft.com/azure/aks/developer-best-practices-resource-management) |
> | **Configuración de los requisitos de escalado de la aplicación.** Kubernetes admite el escalado automático horizontal de pods para ajustar el número de pods en una implementación en función del uso de la CPU o de otras métricas de selección. Para usar la escalabilidad automática, todos los contenedores de los pod deben tener definidos solicitudes y límites de CPU.    | [Configuración de Horizontal Pod Autoscaler](https://docs.microsoft.com/azure/aks/tutorial-kubernetes-scale#autoscale-pods) |
> | **Implementación de aplicaciones mediante una canalización automatizada y DevOps.**  La automatización completa de todos los pasos entre la confirmación del código y la implementación en producción permite a los equipos concentrarse en la compilación del código y elimina la sobrecarga, y los posibles errores humanos, en los pasos manuales corrientes. La implementación de nuevo código es más rápida y menos arriesgada, y esto ayuda a los equipos a ser más ágiles, productivos y a confiar en la ejecución del código.    | [Logre que sus prácticas de DevOps evolucionen](https://docs.microsoft.com/learn/paths/evolve-your-devops-practices) <br/> [Configuración de una canalización de compilación de Kubernetes (vídeo)](https://www.youtube.com/watch?v=5irsAdKoEBU&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=6) <br/> [Centro de implementación de Azure Kubernetes Service](https://docs.microsoft.com/azure/aks/deployment-center-launcher) <br/> [Acciones de GitHub para la implementación de Azure Kubernetes Service](https://docs.microsoft.com/azure/aks/kubernetes-action) <br/>  [CI/CD en Azure Kubernetes Service con Jenkins](https://docs.microsoft.com/azure/aks/jenkins-continuous-deployment) |

## <a name="optimize-and-scale"></a>Optimización y escalado

Ahora que la aplicación está en producción, ¿cómo puede optimizar el flujo de trabajo y preparar la aplicación y el equipo para el escalado? Use la lista de comprobación de optimización y escalado para la preparación. Debe ser capaz de responder a estas preguntas:

> [!div class="checklist"]
>
> - ¿Se han eliminado las cuestiones transversales de la aplicación?
> - ¿Puede mantener la confiabilidad del sistema y de la aplicación mientras recorre en iteración nuevas características y versiones?

<!-- -->

> [!div class="tdCol2BreakAll"]
>
> | Lista de comprobación  | Recursos                                                                                                     |
> |------------------------------------------------------------------|-----------------------------------------------------------------|
> | **Implementación de una puerta de enlace de API**. Una puerta de enlace de API actúa como puerta de entrada de los microservicios, desacopla los clientes de los microservicios, agrega una capa de seguridad adicional y reduce la complejidad de los microservicios al eliminar la carga que supone el control de las cuestiones transversales.     | [Uso de Azure API Management con microservicios implementados en Azure Kubernetes Service](https://docs.microsoft.com/azure/api-management/api-management-kubernetes) |
> | **Implementación de una malla de servicio**. Una malla de servicio proporciona a las cargas de trabajo funcionalidades como administración del tráfico, resistencia, directiva, seguridad, identidad sólida y observabilidad. La aplicación se desacopla de estas funciones operativas y la malla del servicio las retira de la capa de la aplicación, bajándolas al nivel de infraestructura.     | [Funcionamiento de las&nbsp;mallas de&nbsp;servicio&nbsp;&nbsp;en&nbsp;Kubernetes&nbsp;(vídeo)](https://www.youtube.com/watch?v=izVWk7rYqWI&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=15&t=0s) <br/> [Más información sobre mallas de servicio](https://docs.microsoft.com/azure/aks/servicemesh-about) <br/> [Uso de Istio con Azure Kubernetes Service](https://docs.microsoft.com/azure/aks/servicemesh-istio-about) <br/> [Uso de Linkerd con Azure Kubernetes Service](https://docs.microsoft.com/azure/aks/servicemesh-linkerd-about) <br/> [Uso de Consul con Azure Kubernetes Service](https://docs.microsoft.com/azure/aks/servicemesh-consul-about) |
> | **Implementación de procedimientos de ingeniería de confiabilidad de sitios (SRE).**  La ingeniería de confiabilidad de sitios (SRE) es un enfoque de eficacia probada a la hora de mantener la confiabilidad de sistemas y aplicaciones cruciales mientras se realizan las iteraciones al ritmo que el mercado demanda.   | [Introducción a la ingeniería de confiabilidad de sitios (SRE)](https://docs.microsoft.com/learn/modules/intro-to-site-reliability-engineering) <br/> [DevOps at Microsoft: Game streaming SRE](https://azure.microsoft.com/resources/devops-at-microsoft-game-streaming-sre) (DevOps en Microsoft: SRE de streaming de juegos) |
