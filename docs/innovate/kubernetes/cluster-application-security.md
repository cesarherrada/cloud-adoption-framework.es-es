---
title: Seguridad de clústeres y aplicaciones
description: Más información sobre Kubernetes en Cloud Adoption Framework para la seguridad de clústeres y aplicaciones.
author: sabbour
ms.author: asabbour
ms.topic: guide
ms.date: 03/20/2020
ms.service: cloud-adoption-framework
ms.subservice: innovate
ms.openlocfilehash: 64a7f4097a75b54ef4f91b5889fa31fc3b98d61a
ms.sourcegitcommit: 1a4b140f09bdaa141037c54a4a3b5577cda269db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "80392744"
---
<!-- cSpell:ignore asabbour sabbour kured -->

# <a name="cluster-and-application-security"></a>Seguridad de clústeres y aplicaciones

Familiarícese con los elementos esenciales de seguridad de Kubernetes y revise la configuración de seguridad de clústeres y aplicaciones.

## <a name="plan-train-and-proof"></a>Planeamiento, entrenamiento y prueba

Al principio, la lista de comprobación y los recursos siguientes le ayudarán a planear las operaciones y la seguridad de los clústeres. Debe ser capaz de responder a estas preguntas:

> [!div class="checklist"]
>
> - ¿Ha revisado el modelo de seguridad y amenazas de los clústeres de Kubernetes?
> - ¿Está el clúster habilitado para el control de acceso basado en roles?

<!-- markdownlint-disable MD033 -->

> [!div class="tdCol2BreakAll"]
>
> | Lista de comprobación  | Recursos |
> |------------------------------------------------------------------|-----------------------------------------------------------------|
> | **Familiarización con las notas del producto sobre los aspectos esenciales de la seguridad**. Los objetivos principales de un entorno de Kubernetes seguro son garantizar que las aplicaciones que ejecuta están protegidas, que los problemas de seguridad se pueden identificar y resolver rápidamente, y que se impedirán problemas similares en el futuro. | [La guía definitiva sobre la seguridad de Kubernetes (notas del producto)](https://clouddamcdnprodep.azureedge.net/gdc/gdc8LXmoZ/original)     |
> | **Revisión de la configuración de mejora de la seguridad en los nodos de clúster**. Un sistema operativo host con seguridad mejorada reduce el área expuesta a los ataques y permite implementar contenedores de forma segura. | [Mejora de la seguridad en hosts de máquinas virtuales de AKS](https://docs.microsoft.com/azure/aks/security-hardened-vm-host-image)     |
> | **Configuración del control de acceso basado en rol (RBAC) del clúster**. Este mecanismo de control le permite asignar a usuarios o grupos de usuarios, permiso para realizar acciones como crear o modificar recursos, o ver registros de cargas de trabajo de aplicaciones en ejecución. | [Descripción del control de acceso basado en rol (RBAC) en Kubernetes (vídeo)](https://www.youtube.com/watch?v=G3R24JSlGjY&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=12) <br/> [Integración de Azure AD con Azure Kubernetes Service](https://docs.microsoft.com/azure/aks/azure-ad-integration) <br/> [Limitación del acceso al archivo de configuración de clúster](https://docs.microsoft.com/azure/aks/control-kubeconfig-access)   |

## <a name="deploy-to-production-and-apply-best-practices"></a>Implementación en producción y aplicación de procedimientos recomendados

Cuando prepare la aplicación para producción, debe implementar un conjunto mínimo de procedimientos recomendados. Use la siguiente lista de comprobación en esta fase. Debe ser capaz de responder a estas preguntas:

> [!div class="checklist"]
>
> - ¿Ha configurado las reglas de seguridad de red para la comunicación de entrada, salida y entre pods?
> - ¿Está el clúster configurado para aplicar automáticamente las actualizaciones de seguridad del nodo?
> - ¿Va a ejecutar una solución de examen de seguridad para las cargas de trabajo del clúster y del contenedor?

<!-- markdownlint-disable MD033 -->

> [!div class="tdCol2BreakAll"]
>
> | Lista de comprobación  | Recursos |
> |------------------------------------------------------------------|-----------------------------------------------------------------|
> | **Control del acceso a clústeres mediante la pertenencia a grupos**. Configure el control de acceso basado en rol (RBAC) de Kubernetes para limitar el acceso a los recursos de clúster en función de la identidad de los usuarios o su pertenencia a un grupo. | [Control del acceso a clústeres mediante RBAC y grupos de Azure AD](https://docs.microsoft.com/azure/aks/azure-ad-rbac)    |
> | **Creación de una directiva de administración de secretos**. Implemente y administre información confidencial como, por ejemplo, contraseñas y certificados, mediante la administración de secretos en Kubernetes. | [Descripción de la administración de secretos en Kubernetes (vídeo)](https://www.youtube.com/watch?v=KmhM33j5WYk&list=PLLasX02E8BPCrIhFrc_ZiINhbRkYMKdPT&index=10) |
> | **Protección del tráfico de red entre pods con directivas de red**. Aplique el principio del privilegio mínimo para controlar el flujo del tráfico de red entre los pods del clúster. | [Protección del tráfico entre pods con directivas de red](https://docs.microsoft.com/azure/aks/use-network-policies) |
> | **Restricción del acceso al servidor de API mediante direcciones IP autorizadas**. Para mejorar la seguridad del clúster y reducir el área expuesta a ataques restrinja el acceso al servidor de API a un conjunto limitado de intervalos de direcciones IP. | [Protección del acceso al servidor de API](https://docs.microsoft.com/azure/aks/api-server-authorized-ip-ranges) |
> | **Restricción del tráfico de salida del clúster**. Averigüe qué puertos y direcciones debe permitir si restringe el tráfico de salida para el clúster. Puede usar Azure Firewall o un dispositivo de firewall de terceros para proteger el tráfico de salida y definir estos puertos y direcciones obligatorios. | [Control del tráfico de salida de los nodos de clúster en AKS](https://docs.microsoft.com/azure/aks/limit-egress-traffic) |
> | **Protección del tráfico con un firewall de aplicaciones web (WAF)** . Utilice Azure Application Gateway como controlador de entrada para los clústeres de Kubernetes.  | [Configuración de Azure Application Gateway como controlador de entrada](https://docs.microsoft.com/azure/application-gateway/ingress-controller-overview)    |
> | **Aplicación de actualizaciones de seguridad y de kernel en nodos de trabajo**. Conozca la experiencia de actualización de nodos de AKS. Para proteger los clústeres, las actualizaciones de seguridad se aplican automáticamente a los nodos de Linux en AKS. Estas actualizaciones incluyen las revisiones de seguridad del sistema operativo o las actualizaciones del kernel. Algunas de estas actualizaciones requieren un reinicio del nodo para completar el proceso. | [Uso de Kured para reiniciar automáticamente los nodos para aplicar actualizaciones](https://docs.microsoft.com/azure/aks/node-updates-kured) |
> | **Configuración de un contenedor y una solución de examen del clúster**. Examine los contenedores insertados en Azure Container Registry y obtenga una mayor visibilidad sobre los nodos de clúster, el tráfico en la nube y los controles de seguridad. | [Integración de Azure Container Registry con Security Center](https://docs.microsoft.com/azure/security-center/azure-container-registry-integration) <br/> [Integración de Azure Kubernetes Service con Security Center](https://docs.microsoft.com/azure/security-center/azure-kubernetes-service-integration)  |

## <a name="optimize-and-scale"></a>Optimización y escalado

Ahora que la aplicación está en producción, ¿cómo puede optimizar el flujo de trabajo y preparar la aplicación y el equipo para el escalado? Use la lista de comprobación de optimización y escalado para la preparación. Debe ser capaz de responder a esta pregunta:

> [!div class="checklist"]
>
> - ¿Puedo aplicar directivas de gobernanza y clúster a escala?

<!-- markdownlint-disable MD033 -->

> [!div class="tdCol2BreakAll"]
>
> | Lista de comprobación  | Recursos |
> |------------------------------------------------------------------|-----------------------------------------------------------------|
> | **Aplicación de directivas de gobernanza del clúster**. Aplique medidas de seguridad y cumplimiento a escala en los clústeres de una manera centralizada y coherente. | [Control de implementaciones con Azure Policy](https://docs.microsoft.com/azure/governance/policy/concepts/rego-for-aks)    |
> | **Rotación periódica de los certificados del clúster**. Kubernetes usa certificados para la autenticación con muchos de sus componentes. Puede que desee rotar periódicamente esos certificados por motivos de seguridad o de directivas. | [Rotación de certificados en Azure Kubernetes Service (AKS)](https://docs.microsoft.com/azure/aks/certificate-rotation)    |
