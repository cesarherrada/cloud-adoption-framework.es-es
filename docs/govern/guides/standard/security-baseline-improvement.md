---
title: 'Gobernanza para empresas estándar: Mejora de la materia de línea de base de seguridad'
description: Use Cloud Adoption Framework de Azure para más información sobre la incorporación de controles de seguridad que ayuden al traslado de datos protegidos a la nube.
author: BrianBlanchard
ms.author: brblanch
ms.date: 09/17/2019
ms.topic: guide
ms.service: cloud-adoption-framework
ms.subservice: govern
ms.custom: governance
ms.openlocfilehash: 2e9dbaf3bb92893e4eb737964da3f1b0c3a056ad
ms.sourcegitcommit: af45c1c027d7246d1a6e4ec248406fb9a8752fb5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "77707720"
---
# <a name="standard-enterprise-governance-guide-improve-the-security-baseline-discipline"></a>Guía de gobernanza para empresas estándar: Mejora de la materia de base de referencia de la seguridad

En este artículo se detalla el método de adición de controles de seguridad que ayudan al traslado de datos protegidos a la nube.

## <a name="advancing-the-narrative"></a>Continuación de la historia

TI y la dirección empresarial están satisfechos con los resultados de la experimentación en una fase temprana de los equipos de TI, desarrollo de aplicaciones y BI. Para obtener valores empresariales tangibles de estos experimentos, los equipos deben poder integrar datos protegidos en soluciones. Esto desencadena cambios en la directiva corporativa, pero también requiere una mejora gradual de las implementaciones de gobernanza de la nube antes de que los datos protegidos se puedan colocar en la nube.

### <a name="changes-to-the-cloud-governance-team"></a>Cambios en el equipo de gobernanza de la nube

Dado el efecto del cambio de narración y el respaldo proporcionados hasta ahora, el equipo de gobernanza de la nube se percibe de forma diferente. Los dos administradores del sistema que iniciaron el equipo se ven ahora como arquitectos con experiencia en la nube. A medida que se desarrolla la narración, la percepción que se tiene de ellos se desplazará de administrador de la nube al rol de protector de la nube.

Aunque la diferencia es sutil, es una distinción importante al crear una cultura de TI centrada en la gobernanza. Un administrador de la nube limpia el desorden realizado por los innovadores arquitectos de la nube. La fricción entre los dos roles es natural y sus objetivos son opuestos. Por otro lado, un protector de la nube ayuda a proteger la nube, para que otros arquitectos de la nube puedan moverse más rápidamente, con menos desorden. Además, un protector de la nube está implicado en la creación de plantillas que aceleran la implementación y la adopción, lo que les convierte en un acelerador de la innovación, así como un defensor de las cinco materias de gobernanza de la nube.

### <a name="changes-in-the-current-state"></a>Cambios en el estado actual

Al principio de esta narración, los equipos de desarrollo de aplicaciones aún estaban trabajando en una capacidad de desarrollo y prueba, y el equipo de BI aún estaba en la fase experimental. TI operaba en dos entornos de infraestructura hospedados, denominados Prod y DR.

Desde entonces, han cambiado algunas cosas que afectarán a la gobernanza:

- El equipo de desarrollo de aplicaciones ha implementado una canalización de CI/CD para implementar una aplicación nativa en la nube con una experiencia de usuario mejorada. La aplicación aún no interactúa con los datos protegidos, por lo que no está lista para producción.
- El equipo de inteligencia empresarial de TI mantiene activamente los datos en la nube de terceros, inventario y logística. Estos datos se emplean para impulsar nuevas predicciones, que podrían dar forma a procesos empresariales. Sin embargo, no se puede actuar sobre las predicciones y conclusiones hasta que los datos de cliente y financieros puedan integrarse en la plataforma de datos.
- El equipo de TI hace progresos en los planes del CIO y del director financiero para retirar el centro de datos de DR. Se han retirado o migrado más de 1000 de los 2000 recursos del centro de datos de DR.
- Las directivas definidas de forma flexible con respecto a la información personal y datos financieros se han modernizado. Sin embargo, las nuevas directivas corporativas están supeditadas a la implementación de directivas de seguridad y de gobernanza relacionadas. Así que los equipos siguen estancados.

### <a name="incrementally-improve-the-future-state"></a>Mejora gradual del estado futuro

Los experimentos anteriores de los equipos de desarrollo de aplicaciones y BI muestran posibles mejoras en las experiencias del cliente y las decisiones controladas por datos. Ambos equipos quieren expandir la adopción de la nube en los próximos 18 meses mediante la implementación de estas soluciones en producción.

Durante los seis meses restantes, el equipo de gobernanza de la nube implementará requisitos de seguridad y gobernanza para permitir que los equipos de adopción de la nube puedan migrar los datos protegidos de esos centros de datos.

Los cambios de los estados actual y futuro exponen nuevos riesgos que requieren nuevas instrucciones de directiva.

## <a name="changes-in-tangible-risks"></a>Cambios en riesgos tangibles

**Vulneración de datos:** Al adoptar una nueva plataforma de datos, hay un aumento inherente de las responsabilidades en relación con las posibles vulneraciones de datos. Los técnicos que adoptan las tecnologías de la nube tienen mayores responsabilidades para implementar soluciones que puedan reducir este riesgo. Para asegurarse de que los técnicos cumplen con estas responsabilidades se debe implementar una estrategia eficaz de seguridad y gobernanza.

Este riesgo empresarial puede ampliarse a algunos riesgos técnicos:

1. Se podrían implementar aplicaciones críticas o datos protegidos de forma no intencionada.
2. Los datos protegidos podrían exponerse durante el almacenamiento debido a decisiones de cifrado deficiente.
3. Usuarios no autorizados podrían tener acceso a datos protegidos.
4. Podrían producirse intrusiones externas en el acceso a datos protegidos.
5. Intrusiones externas o ataques por denegación de servicio podrían provocar una interrupción del negocio.
6. Los cambios de la organización o empleo podrían permitir el acceso no autorizado a los datos protegidos.
7. Nuevas vulnerabilidades podrían crear nuevas oportunidades de intrusión o acceso.
8. Procesos incoherentes de implementación podrían dar lugar a brechas de seguridad y estas, a su vez, a pérdidas de datos o interrupciones.
9. El desfase de configuración o la falta revisiones podrían dar lugar a brechas de seguridad y estas, a su vez, a pérdidas de datos o interrupciones.

## <a name="incremental-improvement-of-the-policy-statements"></a>Mejora gradual de las declaraciones de las directivas

Los siguientes cambios en la directiva le ayudarán a corregir los nuevos riesgos y le guiarán en la implementación. La lista parece larga, pero la adopción de estas directivas puede ser más fácil de lo que parece.

1. Todos los recursos implementados deben categorizarse por importancia y clasificación de datos. El equipo de gobernanza de la nube y el propietario de la aplicación deben revisar las clasificaciones antes de la implementación en la nube.
2. Las aplicaciones que almacenan o acceden a datos protegidos se deben administrar de manera diferente de las demás. Como mínimo, deben segmentarse para evitar el acceso no intencionado de los datos protegidos.
3. todos los datos protegidos deben estar cifrados cuando están en reposo. Aunque este es el valor predeterminado para todas las cuentas de Azure Storage, es posible que se necesiten estrategias de cifrado adicionales, incluido el cifrado de los datos de la cuenta de almacenamiento, el cifrado de las máquinas virtuales y el cifrado en el nivel de bases de datos cuando se usa SQL en una máquina virtual (cifrado de datos transparente y de columnas).
4. Los permisos elevados en los segmentos que contienen datos protegidos deben ser una excepción. Estas excepciones se registrarán con el equipo de gobernanza de la nube y se auditarán periódicamente.
5. las subredes que contengan datos protegidos deben aislarse de las otras subredes. El tráfico de red entre subredes de datos protegidos se auditará periódicamente.
6. No se podrá tener acceso a ninguna subred que contenga datos protegidos directamente a través de Internet o entre centros de datos. El acceso a esas subredes debe enrutarse a través de subredes intermedias. Todo acceso a esas subredes debe realizarse a través de una solución de firewall que pueda realizar funciones de análisis y bloqueo de paquetes.
7. Las herramientas de gobernanza deben auditar y aplicar los requisitos de configuración de red definidos por el equipo de administración de seguridad.
8. Las herramientas de gobernanza deben limitar la implementación de máquina virtual a solo las imágenes aprobadas.
9. Siempre que sea posible, la administración de configuración de nodos debe aplicar los requisitos de directiva a la configuración de cualquier sistema operativo invitado.
10. Las herramientas de gobernanza deben exigir que las actualizaciones automáticas estén habilitadas en todos los recursos implementados. Las infracciones deben revisarse con los equipos de administración de operaciones y corregirse de acuerdo con las directivas de operaciones. Los recursos que no se actualicen automáticamente deben incluirse en procesos que sean propiedad del departamento de operaciones de TI.
11. La creación de nuevas suscripciones o grupos de administración para las aplicaciones críticas o datos protegidos requiere una revisión del equipo de gobernanza de la nube para garantizar que se ha asignado el plano técnico correcto.
12. Un modelo de acceso con privilegios mínimos se aplicará a cualquier grupo de administración o suscripción que contenga aplicaciones críticas o datos protegidos.
13. El equipo de seguridad debe revisar periódicamente las tendencias y vulnerabilidades que podrían afectar a implementaciones en la nube para proporcionar actualizaciones a las herramientas de administración de seguridad utilizadas en la nube.
14. El equipo de gobernanza de la nube debe aprobar las herramientas de implementación para garantizar la gobernanza en curso de los recursos implementados.
15. Los scripts de implementación deben conservarse en un repositorio central accesible para el equipo de gobernanza de la nube, y que así se puedan revisar y se realicen auditorías periódicas.
16. Los procesos de gobernanza deben incluir auditorías en el punto de implementación y en ciclos regulares para garantizar la coherencia entre todos los recursos.
17. la implementación de las aplicaciones que requieren autenticación de cliente debe usar un proveedor de identidades aprobado que sea compatible con el proveedor de identidades principal para usuarios internos.
18. Los procesos de gobernanza en la nube deben incluir revisiones trimestrales con equipos de administración de identidades. Estas revisiones pueden ayudar a identificar actores malintencionados o patrones de uso que deben evitarse en la configuración de recursos en la nube.

## <a name="incremental-improvement-of-governance-practices"></a>Mejora incremental de las prácticas de gobernanza

El diseño de un producto viable mínimo de gobernanza cambiará para incluir nuevas directivas de Azure y una implementación de Azure Cost Management. Juntos, estos dos cambios de diseño cumplirán con las nuevas declaraciones de directiva corporativa.

1. Los equipos de redes y seguridad de TI definirán los requisitos de la red. El equipo de gobernanza de la nube admitirá la conversación.
2. Los equipos de identidad y de seguridad de TI definirán los requisitos de identidad y realizarán los cambios necesarios en la implementación local de Active Directory. El equipo de gobernanza de la nube revisará los cambios.
3. Cree un repositorio en Azure DevOps para almacenar y edite todas las plantillas de Azure Resource Manager pertinentes y configuraciones con script.
4. Implementación de Azure Security Center:
    1. Configure Azure Security Center para cualquier grupo de administración que contenga clasificaciones de datos protegidos.
    2. Active de forma predeterminada el aprovisionamiento automático para garantizar el cumplimiento de la aplicación de revisiones.
    3. Establezca configuraciones de seguridad del sistema operativo. El equipo de seguridad de TI definirá la configuración.
    4. Admita el equipo de seguridad de TI en el uso inicial de Security Center. Realice la transición del uso de Security Center al equipo de seguridad de TI, pero conserve el acceso con el fin de mejorar continuamente la gobernanza.
    5. Cree una plantilla de Resource Manager que refleje los cambios necesarios para la configuración de Security Center dentro de una suscripción.
5. Actualice las directivas de Azure para todas las suscripciones:
    1. Audite y exija la clasificación de datos y la importancia en todos los grupos de administración y suscripciones, para identificar las suscripciones con clasificaciones de datos protegidos.
    2. Audite y exija el uso de imágenes aprobadas únicamente.
6. Actualice las directivas de Azure para todas las suscripciones que contengan clasificaciones de datos protegidos:
    1. Audite y exija el uso de roles RBAC de Azure únicamente.
    2. Audite y exija el cifrado para todas las cuentas de almacenamiento y los archivos en reposo en nodos individuales.
    3. Audite y exija la aplicación de un NSG a todos los NIC y subredes. Los equipos de redes y seguridad de TI definirán los NSG.
    4. Audite y exija el uso de la subred de red aprobada y vNet por interfaz de red.
    5. Audite y exija que se aplique la limitación de las tablas de enrutamiento que defina el usuario.
    6. Aplique las directivas integradas para la configuración de invitado de la manera siguiente:
        1. Confirme que los servidores web de Windows usan protocolos de comunicación segura.
        2. Confirme que la configuración de seguridad de contraseñas es correcta en máquinas de Linux y Windows.
7. Configuración del firewall:
    1. Identifique una configuración de Azure Firewall que cumpla los requisitos de seguridad necesarios. También puede identificar un dispositivo de terceros compatible, que sea compatible con Azure.
    2. Cree una plantilla de Resource Manager para implementar el firewall con las configuraciones necesarias.
8. Plano técnico de Azure:
    1. Cree un nuevo plano técnico denominado `protected-data`.
    2. Agregue el firewall y las plantillas de Azure Security Center al plano técnico.
    3. Agregue las nuevas directivas para suscripciones de datos protegidos.
    4. Publique el plano técnico en cualquier grupo de administración que planee actualmente el hospedaje de datos protegidos.
    5. Aplique el nuevo plano técnico a cada suscripción afectada, además de los planos técnicos existentes.

## <a name="conclusion"></a>Conclusión

La adición de los procesos anteriores y los cambios realizados en el producto viable mínimo de gobernanza ayudarán a corregir muchos de los riesgos asociados con controles de seguridad. Juntos, agregan herramientas de supervisión de red, así como la identidad y la seguridad necesarias para proteger los datos.

## <a name="next-steps"></a>Pasos siguientes

A medida que avanza la adopción de la nube y aporta valores empresariales adicionales, también cambian los riesgos y necesidades de gobernanza de la nube. En cuanto a la empresa ficticia de esta guía, el paso siguiente es dar servicio a las cargas de trabajo críticas. En este punto son necesarios los controles de coherencia de recursos.

> [!div class="nextstepaction"]
> [Mejora de la coherencia de los recursos](./resource-consistency-improvement.md)
