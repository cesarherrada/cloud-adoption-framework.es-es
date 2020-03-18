---
title: Habilitación de los servicios de administración de servidores en una máquina virtual
description: Use Cloud Adoption Framework para Azure con el fin de aprender a habilitar los servicios de administración de servidores de Azure en una sola máquina virtual.
author: BrianBlanchard
ms.author: brblanch
ms.date: 05/10/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: d79539e6708a46a905e1b69a4d6bd186eaff2d0f
ms.sourcegitcommit: 0ea426f2f471eb7310c6f09478be1306cf7bf0d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "78341698"
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
