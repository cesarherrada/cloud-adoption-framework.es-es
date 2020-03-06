---
title: Introducción a los servicios de administración de servidores de Azure
description: Conozca el plan normativo que esta sección de Cloud Adoption Framework para Azure ofrece un para la implementación de los servicios de administración de servidores en su entorno.
author: BrianBlanchard
ms.author: brblanch
ms.date: 05/10/2019
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: operate
ms.openlocfilehash: c6afdfe05a9245d729b17d1d56f3c64ffa6107bd
ms.sourcegitcommit: 0ea426f2f471eb7310c6f09478be1306cf7bf0d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2020
ms.locfileid: "78341681"
---
# <a name="overview-of-azure-server-management-services"></a>Introducción sobre los servicios de administración de servidores de Azure

Los servicios de administración de servidores de Azure proporcionan una experiencia coherente para administrar sus servidores a escala. Estos servicios abarcan los sistemas operativos Linux y Windows. Se pueden usar en entornos de producción, desarrollo y pruebas. Los servicios de administración de servidores pueden admitir máquinas virtuales IaaS de Azure, servidores físicos y máquinas virtuales hospedados de forma local o en otros entornos de hospedaje.

El conjunto de servicios de administración de servidores de Azure incluye los servicios del siguiente diagrama: ![Diagrama del modelo de operaciones de Azure](./media/operations-diagram.png)

En esta sección de Microsoft Cloud Adoption Framework se ofrece un plan preceptivo y viable para la implementación de los servicios de administración de servidores en su entorno. Este plan le ayuda a orientarse rápidamente en estos servicios y le guía a través de un conjunto progresivo de fases de administración para entornos de todos los tamaños.

Para simplificar, se han clasificado las instrucciones en tres fases:

![Las tres fases de incorporación de los servicios de administración de servidores de Azure](./media/operations-stages.png)

<!-- markdownlint-disable MD026 -->

## <a name="why-use-azure-server-management-services"></a>¿Por qué usar los servicios de administración de servidores de Azure?

Los servicios de administración de servidores de Azure ofrecen las siguientes ventajas:

- **Nativos de Azure:** Los servicios de administración de servidores están integrados de forma nativa con Azure Resource Manager. Estos servicios se mejoran continuamente para proporcionar funcionalidades y características nuevas.
- **Windows y Linux:** Las máquinas Windows y Linux obtienen la misma experiencia de administración coherente.
- **Híbrido:** Los servicios de administración de servidores abarcan máquinas virtuales IaaS de Azure, así como servidores físicos y virtuales hospedados en el entorno local o en otros entornos de hospedaje.
- **Seguridad:** Microsoft dedica bastantes recursos a todo lo que aporte seguridad. Esta inversión no solo protege la infraestructura de Azure, sino que también extiende las tecnologías y conocimientos resultantes para proteger los recursos de los clientes allá donde se encuentren.

## <a name="next-steps"></a>Pasos siguientes

Familiarícese con las [herramientas, servicios y planeamiento](./prerequisites.md) relacionados con la adopción del paquete de administración de servidores de Azure.

> [!div class="nextstepaction"]
> [Requisitos previos de herramientas y planeamiento](./prerequisites.md)
