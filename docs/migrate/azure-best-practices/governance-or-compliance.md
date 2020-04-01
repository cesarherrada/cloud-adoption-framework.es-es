---
title: Estrategia de cumplimiento o de gobernanza
description: Estrategia de cumplimiento o de gobernanza
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 0526b85e52e203163942050716e5cabd4fc84ff3
ms.sourcegitcommit: ea63be7fa94a75335223bd84d065ad3ea1d54fdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80355572"
---
# <a name="governance-or-compliance-strategy"></a>Estrategia de cumplimiento o de gobernanza

Cuando se requiere gobernanza o cumplimiento a lo largo de un esfuerzo de migración, se necesita un ámbito adicional. En la siguiente guía se amplía el ámbito de la [guía de migración de Azure](../azure-migration-guide/index.md) para abarcar los distintos enfoques de los requisitos de cumplimiento o de gobernanza.

## <a name="general-scope-expansion"></a>Ampliación del ámbito general

La mayor parte de las actividades de requisitos previos se ven afectadas cuando están implicados la gobernanza y el cumplimiento. Pueden ser necesarios ajustes adicionales durante la evaluación, migración y optimización.

## <a name="suggested-prerequisites"></a>Requisitos previos sugeridos

La configuración del entorno base de Azure podría cambiar significativamente al integrar los requisitos de cumplimiento o gobernanza. Para entender cómo cambian los requisitos previos, es importante comprender su naturaleza. Antes de comenzar cualquier migración que requiera gobernanza o cumplimiento, se debe elegir e implementar un enfoque en el entorno de nube. A continuación se muestran algunos enfoques de alto nivel que se suelen observar durante las migraciones:

**Enfoque de gobernanza común:** Para la mayoría de las organizaciones, el [modelo de gobernanza de Cloud Adoption Framework](../../govern/guides/index.md) es un enfoque suficiente que consiste en la implementación de un producto mínimo viable, seguido de iteraciones específicas de madurez de la gobernanza para abordar los riesgos tangibles identificados en el plan de adopción. Este enfoque proporciona las herramientas mínimas necesarias para establecer una gobernanza coherente, de modo que el equipo pueda comprender las herramientas. Después se expande en esas herramientas para abordar los problemas comunes de gobierno.

**Planos técnicos de cumplimiento ISO 27001:** En el caso de los clientes que deben cumplir los estándares de cumplimiento ISO, los [ejemplos de planos técnicos de los servicios compartidos ISO 27001](https://docs.microsoft.com/azure/governance/blueprints/samples/iso27001-shared/index) pueden servir como un producto mínimo viable más eficaz para producir restricciones de gobernanza más ricas al principio del proceso iterativo. El [ejemplo de App Service Environment/SQL Database ISO 27001](https://docs.microsoft.com/azure/governance/blueprints/samples/iso27001-ase-sql-workload) se expande en el plano técnico para asignar los controles e implementar una arquitectura común para un entorno de aplicación. A medida que se publiquen otros planos técnicos de cumplimiento, también se hará referencia a ellos.

**Centro de datos virtual:** Es posible que se requiera un punto de partida de gobernanza más sólido. En estos casos, considere el uso de [Centro de datos virtual de Azure](../../reference/vdc.md). Este enfoque se suele recomendar durante los esfuerzos de adopción de escala empresarial y, especialmente, los esfuerzos que superan los 10 000 recursos. También es la elección de facto para los escenarios complejos de gobernanza cuando no se necesita ninguno de los elementos siguientes: requisitos de cumplimiento normativo de terceros ampliados, conocimiento profundo de los dominios o paridad con los requisitos de cumplimiento normativo y las directivas de gobernanza de TI madurados.

### <a name="partnership-option-to-complete-prerequisites"></a>Opción de asociación para completar los requisitos previos

**Servicios de Microsoft:** Servicios de Microsoft proporciona ofertas de soluciones que se pueden alinear con el modelo de gobernanza de Cloud Adoption Framework, los planos técnicos de cumplimiento o las opciones del centro de datos virtual para garantizar el modelo de gobernanza o cumplimiento más adecuado. Use la oferta de la solución [Secure Cloud Insights (SCI)](https://download.microsoft.com/download/C/7/C/C7CEA89D-7BDB-4E08-B998-737C13107361/Secure_Cloud_Insights_Datasheet_EN_US.pdf) para establecer una imagen controlada por datos de la implementación de un cliente en Azure y validar la madurez de la implementación del cliente año de Azure mientras se identifica la optimización de las arquitecturas de implementación existentes y se eliminan los riesgos de disponibilidad y seguridad de gobernanza. En función de la información del cliente, debe llevar a cabo los siguientes enfoques:

- **Cloud Foundation:** Establezca los diseños, patrones y arquitecturas de gobernanza básicos del cliente con la oferta de la solución [Hybrid Cloud Foundation (HCF)](https://download.microsoft.com/download/D/8/7/D872DFD0-1C46-4145-95E4-B5EAB2958B96/Hybrid_Cloud_Foundation_Datasheet_EN_US.pdf). Asignar los requisitos del cliente a la arquitectura de referencia más adecuada. Implemente un producto mínimo viable que conste de servicios compartidos y cargas de trabajo de IaaS.
- **Modernización de la nube:** Use la oferta de la solución de [modernización de la nube](https://download.microsoft.com/download/3/7/3/373F90E3-8568-44F3-B096-CD9C1CD28AB7/Cloud_Modernization_Datasheet_EN_US.pdf) como un enfoque integral para migrar aplicaciones, datos e infraestructura a una nube preparada para la empresa, así como para la optimización y la modernización tras la implementación en la nube.
- **Innovación con la nube:** Interactúe con el cliente mediante el enfoque de la solución innovadora y única [Centro de excelencia en la nube (CCoE)](https://download.microsoft.com/download/F/8/B/F8BBE4BD-E5F8-4DFB-82F7-C0A4E17051BB/Cloud_Center_of_Excellence_Datasheet_EN_US.pdf) que crea una organización de TI moderna para habilitar la agilidad a escala con DevOps mientras se mantiene el control. Implementa un enfoque ágil para capturar los requisitos empresariales, volver a usar los paquetes de implementación alineados con las directivas de seguridad, cumplimiento y administración de servicios, y mantener la plataforma de Azure alineada con los procedimientos operativos.

## <a name="assess-process-changes"></a>Evaluación de los cambios en el proceso

Durante la evaluación, se necesitan decisiones adicionales para alinearse con el enfoque de gobernanza requerido. El equipo de gobernanza de la nube debe proporcionar a todos los miembros del equipo de adopción de la nube instrucciones, pautas arquitectónicas o requisitos de gobernanza o cumplimiento antes de evaluar una carga de trabajo.

### <a name="suggested-action-during-the-assess-process"></a>Acción sugerida durante el proceso de evaluación

Los requisitos de evaluación de gobernanza y cumplimiento son demasiado específicos del cliente para proporcionar instrucciones generales sobre los pasos reales que se llevan a cabo durante la evaluación. Sin embargo, el proceso debe incluir tareas y asignaciones de tiempo para la "alineación con los requisitos de cumplimiento y gobernanza". Para más información sobre estos requisitos, consulte los vínculos siguientes:

Para una comprensión más profunda de la gobernanza, consulte el artículo [Las cinco disciplinas de la gobernanza de la nube](../../govern/governance-disciplines.md). En esta sección de Cloud Adoption Framework también se incluyen plantillas para documentar las directivas, las instrucciones y los requisitos de cada una de las cinco secciones:

- [Cost Management](../../govern/cost-management/template.md)
- [Línea de base de seguridad](../../govern/security-baseline/template.md)
- [Coherencia de recursos](../../govern/resource-consistency/template.md)
- [Línea de base de identidad](../../govern/identity-baseline/template.md)
- [Aceleración de la implementación](../../govern/deployment-acceleration/template.md)

Para obtener instrucciones sobre el desarrollo de instrucciones de gobierno basadas en el modelo de gobernanza de Cloud Adoption Framework, consulte [Implementación de una estrategia de gobernanza en la nube](../../govern/corporate-policy.md).

## <a name="optimize-and-promote-process-changes"></a>Optimización y promoción de los cambios del proceso

Durante los procesos de optimización y promoción, el equipo de gobernanza de la nube debe emplear tiempo en probar y validar si se respetan los estándares de gobernanza y cumplimiento. Además, este paso es un buen momento para insertar procesos para el equipo de gobernanza de la nube con el fin de ajustar plantillas que podrían proporcionar [aceleración de implementación](../../govern/deployment-acceleration/index.md) adicional para proyectos futuros.

### <a name="suggested-action-during-the-optimize-and-promote-process"></a>Acción sugerida durante el proceso de optimización y promoción

Durante este proceso, el plan del proyecto debe incluir asignaciones de tiempo para que el equipo de gobernanza de la nube pueda ejecutar una revisión de cumplimiento para cada carga de trabajo planeada para la promoción de producción.

## <a name="next-steps"></a>Pasos siguientes

Como último elemento de la [lista de comprobación de ámbito expandido](./index.md), vuelva a la lista de comprobación y evalúe de nuevo los requisitos de ámbito adicionales para el trabajo de migración.

> [!div class="nextstepaction"]
> [Lista de comprobación del ámbito ampliado](./index.md)
