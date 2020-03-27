---
title: Preparación de las aptitudes para la supervisión de la nube
description: Preparación de las aptitudes para la supervisión de la nube
author: BrianBlanchard
ms.author: magoedte
ms.date: 03/23/2020
ms.topic: article
ms.service: cloud-adoption-framework
ms.subservice: migrate
ms.openlocfilehash: 7e078bbeea12c71997474d372b0b6b838ed5f4a3
ms.sourcegitcommit: a1209c9dab369171e1fe0cdc6a58e3f6ae6a8f22
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80261560"
---
# <a name="skills-readiness-for-cloud-monitoring"></a>Preparación de las aptitudes para la supervisión de la nube

Durante la fase de planeamiento del recorrido de migración, el objetivo es desarrollar los planes necesarios para guiar la implementación. Los planes también deben prever cómo funcionarán estas cargas de trabajo antes de que se realice la transición a producción, y no posteriormente. Las partes interesadas de la empresa esperan servicios valiosos y los esperan sin interrupciones. Los miembros del personal de TI son conscientes de que necesitan aprender nuevas aptitudes y adaptarse para estar preparados y emplear con confianza los servicios de Azure integrados para supervisar eficazmente los recursos en Azure y en entornos híbridos. 

Es posible acelerar el desarrollo de las aptitudes necesarias con las siguientes rutas de aprendizaje:

- En la introducción a [Azure Resource Manager](https://docs.microsoft.com/azure/azure-resource-manager/management/overview) se describen los conceptos básicos de administración e implementación de recursos de Azure. El personal de TI que administra la experiencia de supervisión en la empresa debe comprender los ámbitos de administración y el control de acceso basado en roles (RBAC) mediante plantillas de Azure Resource Manager, y la administración de recursos mediante la CLI de Azure y Azure PowerShell.

- Para aprender a proteger los recursos mediante directivas, control de acceso basado en roles y otros servicios de Azure, vea [Implementación de la seguridad de administración de recursos en Azure](https://docs.microsoft.com//learn/paths/implement-resource-mgmt-security/). 

- La introducción a [Azure Policy](https://docs.microsoft.com/azure/governance/policy/overview) le ayuda a usar Azure Policy para crear, asignar y administrar directivas. Azure Policy puede implementar y configurar los agentes de Azure Monitor, habilitar la supervisión con Azure Monitor para VM y Azure Security Center, implementar la configuración de diagnóstico, auditar la configuración de invitados, etc.

- Revise la introducción a la [interfaz de la línea de comandos (CLI) de Azure](https://docs.microsoft.com/cli/azure/get-started-with-azure-cli?view=azure-cli-latest), la experiencia de línea de comandos multiplataforma para administrar recursos de Azure. Revise también la introducción a [Azure PowerShell](https://docs.microsoft.com/powershell/azure/?view=azps-3.6.1). LinkedIn ofrece, como parte de su curso de nivel básico denominado [Aprendizaje de las herramientas de administración de Azure](https://www.linkedin.com/learning/learning-azure-management-tools), sesiones que tratan sobre la CLI de Azure y los lenguajes de programación de PowerShell:

   - [Uso de la CLI de Azure](https://www.linkedin.com/learning/learning-azure-management-tools/use-the-azure-cli).
   
   - [Introducción a Azure PowerShell](https://www.linkedin.com/learning/learning-azure-management-tools/understand-azure-powershell) 

- Aprenda a escribir [consultas de registro en Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/log-query/get-started-queries).  El lenguaje de consulta Kusto es el recurso principal para escribir consultas de registro de Azure Monitor para explorar y analizar los datos de registro entre los datos recopilados de Azure y las dependencias de las aplicaciones de recursos híbridos, incluida la aplicación activa.

- Vea cómo [Azure Monitor](https://docs.microsoft.com/azure/azure-monitor/overview) le ayuda a visualizar la disponibilidad y el rendimiento de las aplicaciones y servicios en un solo lugar. Pluralsight ofrece los siguientes cursos de ayuda:

   - [Administración y supervisión de IaaS en Microsoft Azure](https://www.pluralsight.com/courses/azure-iaas-monitoring-management-getting-started) le ayuda a usar Azure Monitor para realizar una supervisión básica de las cargas de trabajo que se ejecutan en IaaS.

   - [Supervisión de recursos y cargas de trabajo de Microsoft Azure](https://www.pluralsight.com/courses/microsoft-azure-resources-workloads-monitoring) le ayuda a usar herramientas de supervisión de Microsoft Azure para supervisar los recursos de red de Azure (así como los locales).

   - [Microsoft Azure DevOps Engineer: Optimización de los mecanismos de comentarios](https://www.pluralsight.com/courses/microsoft-azure-optimize-feedback-mechanisms) le ayuda a prepararse para usar Azure Monitor, incluido Application Insights y Log Analytics para supervisar y optimizar las aplicaciones web.

   - El [cuaderno de estrategias de supervisión de bases de datos de Microsoft Azure](https://www.pluralsight.com/courses/microsoft-azure-database-playbook-monitoring) le ayuda a implementar y usar la supervisión de Azure SQL Database, Azure SQL Data Warehouse y Azure Cosmos DB.

- Con [Azure Arc para servidores](https://docs.microsoft.com/azure/azure-arc/servers/overview), aprenda a administrar las máquinas Windows y Linux hospedadas fuera de Azure de forma parecida a como administra máquinas virtuales nativas de Azure.

## <a name="deeper-skills-exploration"></a>Exploración en profundidad de las aptitudes

Además de estas opciones iniciales para desarrollar las aptitudes, hay una variedad de opciones de aprendizaje disponibles.

### <a name="typical-mappings-of-cloud-it-roles"></a>Asignaciones típicas de roles de TI en la nube

Microsoft y sus asociados ofrecen una variedad de opciones para todo tipo de público con el fin de desarrollar las aptitudes con los servicios de Azure:

- [Microsoft IT Pro Career Center](https://www.microsoft.com/itpro): Actúa como un recurso en línea gratuito para ayudar a asignar su trayectoria profesional en la nube. Conozca lo que expertos del sector sugieren para su rol en la nube y las aptitudes para conseguirlo. Siga un plan de estudios de aprendizaje a su propio ritmo para desarrollar las aptitudes que más necesita para mantenerse al día.

Convierta su conocimiento de Azure en un reconocimiento oficial con los [exámenes y aprendizaje para obtener la certificación de Microsoft Azure]( https://www.microsoft.com/learning/azure-certification.aspx).

## <a name="azure-devops-and-project-management"></a>Azure DevOps y administración de proyectos

El entorno de nube híbrida supone un obstáculo para TI ya que presenta roles, responsabilidades y actividades no definidos. Las organizaciones deben evolucionar a unos procedimientos más modernos de administración de servicios, entre los que se incluyen las metodologías Agile y DevOps, para satisfacer mejor las necesidades de transformación y optimización de las empresas actuales de una manera simplificada y eficaz. 

Como parte de la migración a una plataforma de supervisión en la nube, el equipo de TI responsable de administrar la supervisión en la empresa debe incluir entrenamiento y participación ágiles en actividades de DevOps. Esto también incluye el *desarrollo* en DevOps que toma los requisitos y los convierte en requisitos ágiles organizados con el fin de ofrecer soluciones de supervisión mínimamente viables que se refinan de manera iterativa y en línea con las necesidades empresariales. Para que el control de código fuente administre los paquetes de la solución de supervisión iterativa y cualquier otro material relacionado, conecte el proyecto de Azure DevOps Server a un repositorio de GitHub Enterprise Server. Esto proporciona un vínculo entre las confirmaciones de GitHub y las solicitudes de incorporación de cambios en los elementos de trabajo. Puede usar GitHub Enterprise para el desarrollo con el fin de apoyar la integración e implementación continuas de la supervisión al tiempo que usa Azure Boards para planear y realizar un seguimiento de su trabajo.

Para más información, consulte lo siguiente:

- [Introducción a Azure DevOps](https://docs.microsoft.com/learn/modules/get-started-with-devops/) 

- [Más información acerca de DevOps Dojo White Belt Foundation](https://docs.microsoft.com/learn/paths/devops-dojo-white-belt-foundation/)

- [Logre que sus prácticas de DevOps evolucionen](https://docs.microsoft.com/learn/paths/evolve-your-devops-practices/)

- [Automatización de las implementaciones con Azure DevOps](https://docs.microsoft.com/learn/paths/automate-deployments-azure-devops/)

## <a name="other-considerations"></a>Otras consideraciones

A menudo, los clientes tienen dificultades para administrar, mantener y ofrecer los resultados empresariales esperados, al igual que la organización de TI con respecto a los servicios que TI tiene obligación de proporcionar. La supervisión se considera fundamental para administrar la infraestructura y el negocio, ya que se centra en la medición de la calidad del servicio y la experiencia del cliente.  Con el fin de lograr estos objetivos, siente las bases mediante el uso de ITSM junto con DevOps, los cuales ayudarán al equipo de supervisión a consolidar la forma en que administran, entregan y apoyan al servicio de supervisión. La adopción de un marco de ITSM permite al equipo de supervisión funcionar como proveedor y obtener reconocimiento como un facilitador empresarial de confianza mediante la alineación con los objetivos estratégicos y las necesidades de la organización.

Repase lo siguiente para conocer las actualizaciones realizadas en el marco de trabajo de ITSM más popular, las [notas del producto ITIL v4 y la informática en la nube](https://www.axelos.com/case-studies-and-white-papers/itil-4-and-the-cloud), que se centra en combinar la guía de ITIL existente con los procedimientos recomendados de DevOps, Agile y Lean. Tenga en cuenta también la [arquitectura de referencia de IT4IT](https://www.opengroup.org/it4it) que proporciona un plano técnico alternativo sobre como transformar TI mediante un marco independiente de los procesos.

## <a name="learn-more"></a>Más información

Para conocer más rutas de aprendizaje, eche un vistazo al [catálogo de Microsoft Learn](https://docs.microsoft.com/learn/browse). Use el filtro Roles para alinear las rutas de aprendizaje con su rol.