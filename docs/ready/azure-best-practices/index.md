---
title: Procedimientos recomendados de preparación para Azure
description: Una introducción a los procedimientos recomendados de preparación para Azure.
author: BrianBlanchard
ms.author: brblanch
ms.date: 05/10/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: ready
ms.openlocfilehash: d7889b4020d906bb452ded413f6ff5e603bb9881
ms.sourcegitcommit: 58ea417a7df3318e3d1a76d3807cc4e7e3976f52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2020
ms.locfileid: "78892623"
---
# <a name="best-practices-for-azure-readiness"></a>Procedimientos recomendados de preparación para Azure

Una parte importante del proceso de preparación para la nube consiste en dotar al personal de las aptitudes técnicas necesarias para comenzar un proceso de adopción de la nube y preparar el entorno de destino de la migración para los recursos y las cargas de trabajo que trasladará a la nube. Lea estos procedimientos recomendados e instrucciones adicionales para ayudar al equipo a preparar el entorno de Azure.

## <a name="azure-fundamentals"></a>Aspectos básicos de Azure

Organice e implemente los recursos en el entorno de Azure.

- [Conceptos básicos de Azure](../considerations/fundamental-concepts.md). Conozca los conceptos y términos clave de Azure y cómo se relacionan entre sí estos conceptos.
- [Convenciones de nomenclatura y etiquetado recomendadas](../azure-best-practices/naming-and-tagging.md). Revise las recomendaciones detalladas para asignar nombres a los recursos y etiquetarlos. Estas recomendaciones son aplicables a los procesos de adopción de la nube empresarial.
- [Escalado de varias suscripciones de Azure](../azure-best-practices/scaling-subscriptions.md). Comprenda las estrategias de escalado de varias suscripciones de Azure.
- [Organización de los recursos con grupos de administración de Azure](https://docs.microsoft.com/azure/governance/management-groups/?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Conozca cómo los grupos de administración de Azure pueden administrar recursos, roles, directivas e implementaciones en varias suscripciones.
- [Creación de coherencia en la nube híbrida](../considerations/hybrid-consistency.md). Cree soluciones de nube híbrida que ofrezcan las ventajas de la innovación en la nube conservando muchas de las comodidades de la administración local.

## <a name="networking"></a>Redes

Prepare la infraestructura de red en la nube para admitir las cargas de trabajo.

- [Decisiones respecto a las redes](../considerations/networking-options.md). Elija los servicios, herramientas y arquitecturas de redes que satisfagan los requisitos de carga de trabajo, gobernanza y conectividad de la organización.
- [Planeamiento de redes virtuales](https://docs.microsoft.com/azure/virtual-network/virtual-network-vnet-plan-design-arm?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Planee redes virtuales según los requisitos de aislamiento, conectividad y ubicación.
- [Procedimientos recomendados de seguridad de la red](https://docs.microsoft.com/azure/security/azure-security-network-security-best-practices?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Conozca los procedimientos recomendados para solucionar problemas habituales de seguridad de la red mediante las funcionalidades de Azure integradas.
- [Redes perimetrales](./perimeter-networks.md). Permita la conectividad segura entre las redes de la nube y las redes de los centros de datos locales o físicos, así como todo tipo de conectividad hacia Internet y desde este.
- [Topología de red en estrella tipo hub-and-spoke](./hub-spoke-network-topology.md). Administre los requisitos comunes de comunicación o seguridad de manera eficaz para cargas de trabajo complicadas y afronte posibles limitaciones de suscripción.

## <a name="identity-and-access-control"></a>Control de identidades y acceso

Diseñe la infraestructura de control de identidades y acceso para mejorar la seguridad y la eficacia de la administración de las cargas de trabajo.

- [Procedimientos recomendados de seguridad para la administración de identidades y el control de acceso en Azure](https://docs.microsoft.com/azure/security/azure-security-identity-management-best-practices?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Conozca los procedimientos recomendados para la administración de identidades y la seguridad del control de acceso mediante las funcionalidades integradas de Azure.
- [Procedimientos recomendados del control de acceso basado en rol](../considerations/roles.md). Habilite la administración de acceso específico basado en grupos para recursos organizados en torno a roles de usuario.
- [Protección del acceso con privilegios para las implementaciones híbridas y en la nube en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-admin-roles-secure?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Asegúrese de que las cuentas de acceso administrativo y las cuentas con privilegios de la organización son seguras en la nube y en el entorno local.

## <a name="storage"></a>Storage

- [Guía de Azure Storage](../considerations/storage-options.md). Seleccione la solución de Azure Storage adecuada que admita sus escenarios de uso.
- [Guía de seguridad de Azure Storage](https://docs.microsoft.com/azure/storage/blobs/security-recommendations?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Obtenga más información sobre las características de seguridad de Azure Storage.

## <a name="databases"></a>Bases de datos

- [Elección de la opción correcta de SQL Server en Azure](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Elija la solución PaaS o IaaS que mejor admita las cargas de trabajo de SQL Server.
- [Procedimientos recomendados sobre la seguridad de las bases de datos](https://docs.microsoft.com/azure/security/azure-database-security-best-practices?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Conozca los procedimientos recomendados sobre la seguridad de las bases de datos en la plataforma Azure.
- [Elija el almacén de datos apropiado](https://docs.microsoft.com/azure/architecture/guide/technology-choices/data-store-overview). Seleccione el almacén de datos adecuado que satisfaga sus necesidades. Hay cientos de opciones de implementación disponibles entre bases de datos SQL y NoSQL. Los almacenes de datos a menudo se clasifican según la forma de estructurar los datos y según los tipos de operaciones que admiten. Este artículo describe algunos de los modelos de almacenamiento habituales.

## <a name="cost-management"></a>Administración de costos

- [Seguimiento de los costos a través de las unidades de negocio, entornos o proyectos](./track-costs.md). Obtenga información sobre los procedimientos recomendados para crear mecanismos adecuados de seguimiento de costos.
- [Optimización de la inversión en la nube con Azure Cost Management](https://docs.microsoft.com/azure/cost-management-billing/costs/cost-mgt-best-practices?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Implemente una estrategia de administración de costos y obtenga información sobre las herramientas disponibles para afrontar los desafíos de los costos.
- [Creación y administración de presupuestos](https://docs.microsoft.com/azure/cost-management-billing/costs/tutorial-acm-create-budgets?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Aprenda a crear y administrar presupuestos con Azure Cost Management.
- [Exportación de datos de costos](https://docs.microsoft.com/azure/cost-management-billing/costs/tutorial-export-acm-data?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Aprenda a exportar datos de costos mediante Azure Cost Management.
- [Optimización de los costos a partir de las recomendaciones](https://docs.microsoft.com/azure/cost-management-billing/costs/tutorial-acm-opt-recommendations?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Aprenda a identificar recursos infrautilizados y a reducir los costos con Azure Cost Management y Azure Advisor.
- [Uso de alertas de costos para supervisar el uso y el gasto](https://docs.microsoft.com/azure/cost-management-billing/costs/cost-mgt-alerts-monitor-usage-spending?toc=https://docs.microsoft.com/azure/cloud-adoption-framework/toc.json&bc=https://docs.microsoft.com/azure/cloud-adoption-framework/_bread/toc.json). Aprenda a usar las alertas de Cost Management para supervisar el uso y el gasto en Azure.
