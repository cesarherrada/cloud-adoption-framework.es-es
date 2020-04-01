---
title: Diseño y operaciones de clústeres
description: Más información sobre Kubernetes en Cloud Adoption Framework para el diseño y las operaciones de los clústeres.
author: sabbour
ms.author: asabbour
ms.topic: guide
ms.date: 12/16/2019
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: 1a4bcb42ec8fdcdbdb53d918c8348c22c2606649
ms.sourcegitcommit: 1a4b140f09bdaa141037c54a4a3b5577cda269db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "80392731"
---
<!-- cSpell:ignore asabbour sabbour autoscaler PDBs -->

# <a name="cluster-design-and-operations"></a>Diseño y operaciones de clústeres

Identifíquese para la configuración de clústeres y el diseño de la red. Realice una prueba de la escalabilidad mediante la automatización del aprovisionamiento de la infraestructura. Mantenga una alta disponibilidad mediante el planeamiento de la continuidad empresarial y recuperación ante desastres.

## <a name="plan-train-and-proof"></a>Planeamiento, entrenamiento y prueba

Al principio, la lista de comprobación y los recursos siguientes le ayudarán a planear el diseño del clúster. Debe ser capaz de responder a estas preguntas:

<!-- markdownlint-disable MD033 -->

> [!div class="checklist"]
>
> - ¿Ha identificado los requisitos de diseño de red para el clúster?
> - ¿Tiene cargas de trabajo con requisitos variables? ¿Cuántos grupos de nodos va a utilizar?

<!-- -->

> [!div class="tdCol2BreakAll"]
>
> | Lista de comprobación  | Recursos |
> |------------------------------------------------------------------|-----------------------------------------------------------------|
> | **Identificación de los aspectos sobre el diseño de red**. Comprenda los aspectos del diseño de red del clúster, compare modelos de red y elija el complemento de red de Kubernetes que mejor se adapte a sus necesidades.    | [Kubenet y Azure Container Networking Interface (CNI)](https://docs.microsoft.com/azure/aks/concepts-network#azure-virtual-networks) <br/> [Uso de redes kubenet con intervalos de direcciones IP propios en Azure Kubernetes Service (AKS)](https://docs.microsoft.com/azure/aks/configure-kubenet) <br/> [Configuración de redes de Azure CNI en Azure Kubernetes Service (AKS)](https://docs.microsoft.com/azure/aks/configure-azure-cni) <br/> [Diseño de red seguro para un clúster de AKS](https://github.com/Azure/sg-aks-workshop/blob/master/cluster-design/NetworkDesign.md)|
> | **Creación de grupos de varios nodos**. Para admitir aplicaciones con diferentes necesidades de proceso o almacenamiento, puede configurar opcionalmente el clúster con grupos de varios nodos. Por ejemplo, puede usar grupos de nodos adicionales para proporcionar GPU para aplicaciones de proceso intensivo o acceso a almacenamiento SSD de alto rendimiento.   | [Creación y administración de varios grupos de nodos para un clúster de Azure Kubernetes Service](https://docs.microsoft.com/azure/aks/use-multiple-node-pools) |
> | **Decidir los requisitos de disponibilidad**. Para proporcionar un mayor nivel de disponibilidad a sus aplicaciones, los clústeres se pueden distribuir en zonas de disponibilidad. Estas zonas son centros de datos físicamente separados dentro de una región determinada. Si los componentes del clúster se distribuyen entre varias zonas, el clúster podrá tolerar un error en una de esas zonas. Sus aplicaciones y operaciones de administración continuarán disponibles incluso si todo un centro de datos tiene problemas.   | [Creación de un clúster de Azure Kubernetes Service (AKS) que use zonas de disponibilidad](https://docs.microsoft.com/azure/aks/availability-zones) |

## <a name="go-to-production-and-apply-best-practices"></a>Traslado a producción y aplicación de procedimientos recomendados

Cuando prepare la aplicación para producción, debe implementar un conjunto mínimo de procedimientos recomendados. Use la siguiente lista de comprobación en esta fase. Debe ser capaz de responder a estas preguntas:

> [!div class="checklist"]
>
> - ¿Puede reimplementar con confianza la infraestructura del clúster?
> - ¿Ha aplicado cuotas de recurso?

<!-- -->

> [!div class="tdCol2BreakAll"]
>
> | Lista de comprobación  | Recursos                                                                                                     |
> |------------------------------------------------------------------|-----------------------------------------------------------------|
> | **Automatización del aprovisionamiento del clúster**. Mediante la infraestructura como código, puede automatizar el aprovisionamiento de la infraestructura para proporcionar una mayor resistencia durante desastres y ganar agilidad a la hora de reimplementar la infraestructura según sea necesario.     | [Creación de un clúster de Kubernetes con Azure Kubernetes Service mediante Terraform](https://docs.microsoft.com/azure/terraform/terraform-create-k8s-cluster-with-tf-and-aks)|
> | **Planeación de disponibilidad mediante presupuestos de interrupciones de pods**. Para mantener la disponibilidad de las aplicaciones, defina presupuestos de interrupciones de pods para asegurarse de que haya un número mínimo de pods disponible en el clúster durante los errores de hardware o las actualizaciones del clúster. | [Planeación de disponibilidad mediante presupuestos de interrupciones de pods](https://docs.microsoft.com/azure/aks/operator-best-practices-scheduler#plan-for-availability-using-pod-disruption-budgets)  |
> | **Aplicación de cuotas de recursos en espacios de nombres**. Planee y aplique cuotas de recursos en el nivel del espacio de nombres. Las cuotas se pueden establecer en los recursos de proceso, de almacenamiento y en el recuento de objetos.| [Aplicación de cuotas de recursos](https://docs.microsoft.com/azure/aks/operator-best-practices-scheduler#enforce-resource-quotas)  |

## <a name="optimize-and-scale"></a>Optimización y escalado

Ahora que la aplicación está en producción, ¿cómo puede optimizar el flujo de trabajo y preparar la aplicación y el equipo para el escalado? Use la lista de comprobación de optimización y escalado para la preparación. Debe ser capaz de responder a estas preguntas:

> [!div class="checklist"]
>
> - ¿Dispone de un plan de continuidad empresarial y recuperación ante desastres?
> - ¿Puede escalarse el clúster para satisfacer las necesidades de la aplicación?
> - ¿Puede supervisar el estado del clúster y la aplicación y recibir alertas?

<!-- -->

> [!div class="tdCol2BreakAll"]
>
> | Lista de comprobación  | Recursos |
> |------------------------------------------------------------------|-----------------------------------------------------------------|
> | **Escalado automático de un clúster para satisfacer las necesidades de la aplicación**. Para satisfacer las necesidades de la aplicación, es posible que deba ajustar el número de nodos que ejecutan las cargas de trabajo mediante la escalabilidad automática del clúster. | [Configuración de la escalabilidad automática de clústeres de Kubernetes](https://docs.microsoft.com/azure/aks/cluster-autoscaler)    |
> | **Planes de continuidad empresarial y recuperación ante desastres**. Planee una implementación en varias regiones, cree un plan de migración del almacenamiento y habilite la replicación geográfica para las imágenes de contenedor. | [Procedimientos recomendados para implementaciones en varias regiones](https://docs.microsoft.com/azure/aks/operator-best-practices-multi-region)  <br/> [Replicación geográfica de Azure Container Registry](https://docs.microsoft.com/azure/container-registry/container-registry-geo-replication)  |
> | **Configuración de la supervisión y solución de problemas a escala.** Configure las alertas y la supervisión de aplicaciones en Kubernetes. Obtenga más información sobre la configuración predeterminada, la integración de más métricas avanzadas y la incorporación de una configuración personalizada de supervisión y alertas que le permita manejar la aplicación de forma confiable. | [Introducción a la supervisión y las alertas de Kubernetes (vídeo)](https://www.youtube.com/watch?v=W7aN_z-cyUw&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=16) <br/> [Configuración de alertas mediante Azure Monitor para contenedores](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview) <br/> [Revisión de los registros de diagnóstico de los componentes maestros](https://docs.microsoft.com/azure/aks/view-master-logs) <br/> [Diagnósticos de Azure Kubernetes Service (AKS)](https://docs.microsoft.com/azure/aks/concepts-diagnostics)    |
