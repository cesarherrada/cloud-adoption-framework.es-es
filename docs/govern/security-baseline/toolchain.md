---
title: Herramientas de base de referencia de seguridad
description: Compruebe cómo las herramientas nativas de Azure pueden ayudarle a consolidar directivas y procesos que respalden la materia de gobernanza de la línea de base de seguridad.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 85b0d88d4a275c7215a498b95e0af6717bfac169
ms.sourcegitcommit: af45c1c027d7246d1a6e4ec248406fb9a8752fb5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "77707074"
---
# <a name="security-baseline-tools-in-azure"></a>Herramientas de base de referencia de seguridad

La [base de referencia de seguridad](./index.md) es una de las [cinco materias de gobernanza en la nube](../governance-disciplines.md). Esta materia se centra en formas de establecer directivas que protegen la red, los recursos y, lo que es más importante, los datos que residirán en una solución del proveedor de nube. Dentro de las cinco materias de gobernanza de la nube, la correspondiente a la base de referencia de seguridad implica la clasificación del patrimonio digital y los datos. También implica documentación de estrategias de mitigación, tolerancia empresarial y riesgos que se asocian a la seguridad de los datos, los recursos y las redes. Desde una perspectiva técnica, esta materia también incluye la participación en decisiones sobre el [cifrado](../../decision-guides/encryption/index.md), los [requisitos de red](../../decision-guides/software-defined-network/index.md), las [estrategias de identidad híbrida](../../decision-guides/identity/index.md) y las herramientas para [automatizar la aplicación](../../decision-guides/policy-enforcement/index.md) de directivas de seguridad en los [grupos de recursos](../../decision-guides/resource-consistency/index.md).

La siguiente lista de herramientas de Azure puede contribuir desarrollar las directivas y los procesos que admiten la base de referencia de seguridad.

| Herramienta | [Azure Portal](https://azure.microsoft.com/features/azure-portal) y [Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/resource-group-overview)  | [Azure Key Vault](https://docs.microsoft.com/azure/key-vault)  | [Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-whatis) | [Azure Policy](https://docs.microsoft.com/azure/governance/policy/overview) | [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-intro) | [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) |
|------------------------------------------------------------|---------------------------------|-----------------|----------|--------------|-----------------------|---------------|
| Aplicación de controles de acceso a recursos y creación de recursos   | Sí                             | Sin              | Sí      | Sin           | Sin                    | Sin            |
| Protección de redes virtuales                                    | Sí                             | Sin              | Sin       | Sí          | Sin                    | Sin            |
| Cifrado de discos virtuales                                     | Sin                              | Sí             | Sin       | Sin           | Sin                    | Sin            |
| Cifrado de bases de datos y almacenamiento PaaS                         | Sin                              | Sí             | Sin       | Sin           | Sin                    | Sin            |
| Administración de servicios de identidad híbrida                            | Sin                              | Sin              | Sí      | Sin           | Sin                    | Sin            |
| Restricción de tipos de recurso permitidos                         | Sin                              | Sin              | Sin       | Sí          | Sin                    | Sin            |
| Aplicación de restricciones geográficas regionales                          | Sin                              | Sin              | Sin       | Sí          | Sin                    | Sin            |
| Supervisión del estado de seguridad de redes y recursos          | Sin                              | Sin              | Sin       | Sin           | Sí                   | Sí           |
| Detección de actividad malintencionada                                  | Sin                              | Sin              | Sin       | Sin           | Sí                   | Sí           |
| Detección de vulnerabilidades de forma preventiva                        | Sin                              | Sin              | Sin       | Sin           | Sí                   | Sin            |
| Configuración de copia de seguridad y recuperación ante desastres                     | Sí                             | Sin              | Sin       | Sin           | Sin                    | Sin            |

Para ver una lista completa de servicios y herramientas de seguridad de Azure, consulte [Servicios y tecnologías de seguridad disponibles en Azure](https://docs.microsoft.com/azure/security/azure-security-services-technologies).

También es habitual que los clientes usen herramientas de terceros para facilitar las actividades de base de referencia de seguridad. Para obtener más información, consulte el artículo [Integración de soluciones de seguridad en Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-partner-integration).

Además de las herramientas de seguridad, el [Centro de confianza de Microsoft](https://www.microsoft.com/trustcenter/guidance/risk-assessment) contiene orientación amplia, informes y documentación relacionada que pueden ayudarle a realizar evaluaciones de riesgos como parte de su proceso de planeación de migración.
