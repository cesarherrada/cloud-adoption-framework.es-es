---
title: Herramientas de Cost Management en Azure
description: Herramientas de Cost Management en Azure
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: e35530fbf3a858c000cb78c0c076d7d56d5fbd86
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76806414"
---
# <a name="cost-management-tools-in-azure"></a>Herramientas de Cost Management en Azure

[Cost Management](./index.md) es una de las [cinco disciplinas de gobernanza en la nube](../governance-disciplines.md). Esta disciplina se centra en las formas de establecer planes de gastos en la nube, asignar presupuestos de nube, supervisar y exigir los presupuestos de nube, detectar anomalías costosas y ajustar el plan de gobernanza en la nube cuando el gasto real no esté alineado.

A continuación, se muestra una lista de herramientas nativas de Azure que pueden ayudar a desarrollar las directivas y los procesos que admiten la disciplina de gobernanza.

| Herramienta | [Azure Portal](https://azure.microsoft.com/features/azure-portal)  | [Azure Cost Management](https://docs.microsoft.com/azure/cost-management/overview-cost-mgt)  | [Paquete de contenido de Azure EA](https://docs.microsoft.com/power-bi/service-connect-to-azure-enterprise)  | [Azure Policy](https://docs.microsoft.com/azure/governance/policy/overview) |
|---------|---------|---------|---------|---------|
|¿Es necesario el Contrato Enterprise?     | No         | No         | Sí         | No         |
|Control del presupuesto     | No         | Sí         | No         | Sí         |
|Supervisión del gasto en un único recurso    | Sí         | Sí         | Sí         | No         |
|Supervisión del gasto en varios recursos    | No         | Sí        | Sí         | No         |
|Control del gasto en un único recurso     | Sí: ajuste de tamaño manual         | Sí         | No         | Sí         |
|Aplicación del gasto en varios recursos    | No         | Sí         | No         | Sí         |
|Aplicar los metadatos de contabilidad a los recursos    | No         | No         | No         | Sí         |
|Supervisión y detección de tendencias     | Sí          | Sí        | Sí         | No         |
|Detección de anomalías en el gasto     | No         | Sí        | Sí         | No        |
|Socialización de desviaciones     | No        | Sí        | Sí        | No        |
