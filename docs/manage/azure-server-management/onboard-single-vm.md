---
title: Habilitar los servicios de administración en una única VM para su evaluación
description: Habilitar los servicios de administración en una única VM para su evaluación
author: BrianBlanchard
ms.author: brblanch
ms.date: 05/10/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: d73b9f5a13150b0c3b13feff3f21a765a36ac4a8
ms.sourcegitcommit: 2362fb3154a91aa421224ffdb2cc632d982b129b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76808046"
---
# <a name="enable-server-management-services-on-a-single-vm-for-evaluation"></a>Habilitar los servicios de administración en una única VM para su evaluación

Obtenga información sobre cómo habilitar los servicios de administración en una única VM para su evaluación.

> [!NOTE]
> Cree el [área de trabajo de Log Analytics y la cuenta de Azure Automation](./prerequisites.md#create-a-workspace-and-automation-account) necesarias antes de implementar servicios de administración de Azure en una VM.

La incorporación de servicios de administración de servidores de Azure a máquinas virtuales individuales es sencilla en Azure Portal. Puede familiarizarse con estos servicios antes de incorporarlos. Al seleccionar una instancia de VM, todas las soluciones que se describen en la lista de [herramientas y servicios de administración](./tools-services.md) aparecen en el menú **Operaciones** o en el menú **Supervisión**. Debe seleccionar una solución y seguir el asistente para incorporarla.

![Captura de pantalla de configuración de máquina virtual en Azure Portal](./media/onboarding-single-vm.png)

## <a name="related-resources"></a>Recursos relacionados

Para obtener más información sobre cómo incorporar estas soluciones a VM individuales, consulte:

- [Incorporación de las soluciones Update Management, Change Tracking e Inventario desde una máquina virtual de Azure](https://docs.microsoft.com/azure/automation/automation-onboard-solutions-from-vm)
- [Incorporar Azure Monitor para VM](https://docs.microsoft.com/azure/azure-monitor/insights/vminsights-enable-single-vm)

## <a name="next-steps"></a>Pasos siguientes

Aprenda a usar Azure Policy para incorporar máquinas virtuales de Azure a escala.

> [!div class="nextstepaction"]
> [Configuración de servicios de administración de Azure para una suscripción](./onboard-at-scale.md)
