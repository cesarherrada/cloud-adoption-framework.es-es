---
title: Migración a la nube
description: Aprenda a establecer los procesos iterativos para evaluar, migrar, optimizar, proteger y administrar las cargas de trabajo que desea migrar a la nube.
author: BrianBlanchard
ms.author: brblanch
ms.date: 04/04/2019
ms.topic: landing-page
ms.service: cloud-adoption-framework
ms.subservice: migrate
layout: LandingPage
ms.openlocfilehash: c4ee7491fb5fbfa549dfe82c82e720f51188a25c
ms.sourcegitcommit: 5411c3b64af966b5c56669a182d6425e226fd4f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/13/2020
ms.locfileid: "79312312"
---
# <a name="cloud-migration-in-the-cloud-adoption-framework"></a>Migración a la nube en Cloud Adoption Framework

Cualquier [plan de adopción de nube](../plan/index.md) a escala empresarial incluirá cargas de trabajo que no justifican la realización de inversiones significativas en la creación de la nueva lógica de negocios. Estas cargas de trabajo se pueden mover a la nube mediante diversos métodos: migración mediante lift-and-shift, lift-and-optimize o modernización. Cada uno de estos enfoques se considera una migración. Los ejercicios siguientes le ayudarán a establecer los procesos iterativos para evaluar, migrar, optimizar, proteger y administrar esas cargas de trabajo.

## <a name="getting-started"></a>Introducción

Para prepararse para esta fase del ciclo de vida de adopción de la nube, el marco recomienda los siguientes ejercicios:

<!-- markdownlint-disable MD033 -->
<ul class="panelContent cardsF">
    <li style="display: flex; flex-direction: column;">
        <a href="./azure-migration-guide/index.md">
            <div class="cardSize">
                <div class="cardPadding" style="padding-bottom:10px;">
                    <div class="card" style="padding-bottom:10px;">
                        <div class="cardImageOuter">
                            <div class="cardImage">
                                <img alt="" src="../_images/icons/1.png" data-linktype="external">
                            </div>
                        </div>
                        <div class="cardText" style="padding-left:0px;">
                            <h3>Migración de la primera carga de trabajo</h3>
Aproveche la guía de migración de Azure para familiarizarse con las herramientas nativas de Azure y con la migración.
                        </div>
                    </div>
                </div>
            </div>
        </a>
    </li>
    <li style="display: flex; flex-direction: column;">
        <a href="./expanded-scope/index.md">
            <div class="cardSize">
                <div class="cardPadding" style="padding-bottom:10px;">
                    <div class="card" style="padding-bottom:10px;">
                        <div class="cardImageOuter">
                            <div class="cardImage">
                                <img alt="" src="../_images/icons/2.png" data-linktype="external">
                            </div>
                        </div>
                        <div class="cardText" style="padding-left:0px;">
                            <h3>Escenarios de migración</h3>
Aproveche otras herramientas de migración y enfoques para actuar en escenarios de migración adicionales.
                        </div>
                    </div>
                </div>
            </div>
        </a>
    </li>
    <li style="display: flex; flex-direction: column;">
        <a href="./azure-best-practices/index.md">
            <div class="cardSize">
                <div class="cardPadding" style="padding-bottom:10px;">
                    <div class="card" style="padding-bottom:10px;">
                        <div class="cardImageOuter">
                            <div class="cardImage">
                                <img alt="" src="../_images/icons/3.png" data-linktype="external">
                            </div>
                        </div>
                        <div class="cardText" style="padding-left:0px;">
                            <h3>Procedimientos recomendados</h3>
Aborde las necesidades comunes de migración mediante la aplicación de procedimientos recomendados coherentes.
                        </div>
                    </div>
                </div>
            </div>
        </a>
    </li>
    <li style="display: flex; flex-direction: column;">
        <a href="./migration-considerations/index.md">
            <div class="cardSize">
                <div class="cardPadding" style="padding-bottom:10px;">
                    <div class="card" style="padding-bottom:10px;">
                        <div class="cardImageOuter">
                            <div class="cardImage">
                                <img alt="" src="../_images/icons/4.png" data-linktype="external">
                            </div>
                        </div>
                        <div class="cardText" style="padding-left:0px;">
                            <h3>Mejora de procesos</h3>
La migración es una actividad de proceso intensivo. A medida que se escalan los esfuerzos de migración, utilice estas mejoras de procesos para evaluar y consolidar diversos aspectos de la migración.
                        </div>
                    </div>
                </div>
            </div>
        </a>
    </li>
</ul>
<!-- markdownlint-enable MD033 -->

Esta metodología y los pasos anteriores se basan en los siguientes supuestos:

- Antes de migrar las cargas de trabajo, se ha identificado, configurado e implementado al menos una [zona de aterrizaje](../ready/index.md) para satisfacer las necesidades del plan de adopción de la nube a corto plazo.
- La migración se asocia normalmente con los términos _lift-and-shift_ o _rehospedaje_. Esta metodología y los pasos anteriores se basan en la creencia de que no se debe migrar ningún centro de datos (y muy pocas cargas de trabajo) mediante un enfoque de rehospedaje puro. Aunque se pueden rehospedar muchas cargas de trabajo, los clientes suelen optar por modernizar recursos específicos dentro de cada carga de trabajo. Durante este proceso iterativo, el equilibrio entre velocidad y modernización es un punto de debate común.

## <a name="iterative-migration-process"></a>Proceso de migración iterativo

En esencia, la migración a la nube consta de cuatro fases simples: Evaluación, Migración, Optimización y Seguridad y administración. Esta sección de Cloud Adoption Framework enseña a los lectores cómo maximizar el rendimiento de cada fase del proceso y cómo alinear esas fases al plan de adopción de la nube. El siguiente gráfico ilustra esas fases en un enfoque iterativo:

![Modelo de migración de Cloud Adoption Framework](../_images/migrate/methodology.png)

## <a name="create-a-balanced-cloud-portfolio"></a>Creación de una cartera equilibrada en la nube

Cualquier cartera de tecnología equilibrada tiene una mezcla de recursos en varios estados. Algunas aplicaciones están programadas para la retirada y reciben un soporte técnico mínimo. Se admiten otras aplicaciones o recursos en estado de mantenimiento, pero las características de esas soluciones son estables. Para los procesos empresariales más recientes, es probable que las condiciones cambiantes del mercado estimulen mejoras o modernizaciones continuas de las características. Cuando surgen oportunidades para impulsar nuevas fuentes de ingresos, se introducen nuevas aplicaciones o recursos en el entorno. En cada fase del ciclo de vida de un recurso, el impacto de cualquier inversión en los ingresos y las ganancias cambiará. Cuanto más avanzada sea la fase del ciclo de vida, menos probable es que una nueva característica o un esfuerzo de modernización produzcan una fuerte rentabilidad de la inversión.

La nube proporciona varios mecanismos de adopción, cada uno con grados similares de inversión y rentabilidad. La creación de aplicaciones nativas de la nube puede reducir significativamente los gastos operativos. Una vez que una aplicación nativa de la nube se publica, el desarrollo de nuevas características y soluciones puede iterar más rápido. La modernización de una aplicación puede producir beneficios similares al quitar las restricciones heredadas asociadas con los modelos de desarrollo local. Desafortunadamente, estos dos enfoques requieren mucha mano de obra y dependen del tamaño, aptitudes y experiencia de los equipos de desarrollo de software. A menudo, la mano de obra está mal alineada &mdash;las personas con las aptitudes y el talento para modernizar aplicaciones preferirían crear nuevas aplicaciones. En un mercado con limitaciones de mano de obra, los proyectos de modernización a gran escala pueden verse afectados por un problema de satisfacción y talento de los empleados. En una cartera equilibrada, este enfoque debería reservarse a las aplicaciones que recibirían mejoras significativas de las funciones si permanecieran en las instalaciones.

## <a name="envision-an-end-state"></a>Previsión de un estado final

Un viaje efectivo necesita un destino. Establezca una visión aproximada del estado final antes de dar el primer paso. Esta infografía describe un punto inicial que consiste en aplicaciones, datos e infraestructura existentes, que definen el patrimonio digital. Durante el proceso de migración, cada recurso se envía a través de una de las opciones de la derecha.

## <a name="migration-implementation"></a>Implementación de la migración

Estos artículos describen dos recorridos, cada uno con un objetivo similar: migrar un gran porcentaje de los recursos existentes a Azure. Sin embargo, los resultados empresariales y el estado actual influirán de manera significativa en los procesos necesarios para conseguirlo. Esas sutiles desviaciones dan como resultado dos enfoques radicalmente diferentes para alcanzar un estado final similar.

![Modelo de migración de Cloud Adoption Framework](../_images/migrate/methodology.png)

Para guiar la ejecución incremental durante la transición al estado final, este modelo separa la migración en dos áreas de enfoque.

**Preparación de la migración:** Establecer un trabajo pendiente de migración aproximado basado en gran medida en el estado actual y en los resultados deseados.

- **Resultados empresariales:** Los principales objetivos empresariales que promueven esta migración.
- **Estimación del patrimonio digital:** Una estimación aproximada del número y la condición de cargas de trabajo que se van a migrar.
- **Roles y responsabilidades:** Una definición clara de la estructura del equipo, la separación de responsabilidades y los requisitos de acceso.
- **Cambio de los requisitos de administración:** La cadencia, los procesos y la documentación necesarios para revisar y aprobar los cambios.

Estas entradas iniciales conforman el trabajo pendiente de la migración. El resultado del trabajo pendiente de la migración es una lista clasificada por orden de prioridad de las aplicaciones que se van a migrar a la nube. Esta lista da forma a la ejecución del proceso de migración a la nube. Con el tiempo, también crecerá para incluir gran parte de la documentación necesaria para administrar el cambio.

**Proceso de migración:** Cada actividad de migración a la nube está contenida en uno de los siguientes procesos, ya que se relaciona con el trabajo pendiente de la migración.

- **Evaluación:** Evalúe un recurso existente y establezca un plan para la migración del recurso.
- **Migración:** Replique la funcionalidad de un recurso en la nube.
- **Optimización:** Equilibre el rendimiento, el costo, el acceso y la capacidad operativa de un recurso en la nube.
- **Protección y administración:** Asegúrese de que un recurso en la nube está listo para las operaciones en curso.

La información recopilada durante el desarrollo de un trabajo pendiente de migración determina la complejidad y el nivel de esfuerzo requerido dentro del proceso de migración de la nube durante cada iteración y para cada etapa de funcionalidad.

## <a name="transition-to-the-end-state"></a>Transición al estado final

El objetivo es una migración suave y parcialmente automatizada a la nube. El proceso de migración utiliza las herramientas proporcionadas por un proveedor de nube para replicar y escalonar rápidamente los recursos en la nube. Una vez comprobado, un simple cambio de red redirecciona a los usuarios a la solución en la nube. Para muchos casos de uso, la tecnología para lograr este objetivo está ampliamente disponible. Hay casos de ejemplo que demuestran la velocidad a la que se pueden replicar 10 000 máquinas virtuales en Azure.

Sin embargo, sigue siendo necesario un enfoque de migración incremental. En la mayoría de los entornos, la larga lista de máquinas virtuales que se van a migrar debe descomponerse en unidades de trabajo más pequeñas para que la migración se realice correctamente. Hay muchos factores que limitan el número de máquinas virtuales que se pueden migrar en un período determinado. La velocidad de la red de salida es uno de los pocos límites técnicos; la mayoría de los límites se imponen a la capacidad de la empresa para validar y adaptarse al cambio.

El enfoque de migración incremental de Cloud Adoption Framework ayuda a crear un plan incremental que refleja y documenta las limitaciones técnicas y culturales. El objetivo de este modelo es maximizar la velocidad de migración y minimizar la sobrecarga de TI y de la empresa. A continuación se presentan dos ejemplos de ejecución de una migración incremental basada en el trabajo pendiente de la migración.

## <a name="next-steps"></a>Pasos siguientes

Empiece por familiarizarse con la [guía de migración de Azure](./azure-migration-guide/index.md).

> [!div class="nextstepaction"]
> [Guía de migración a Azure](./azure-migration-guide/index.md)
