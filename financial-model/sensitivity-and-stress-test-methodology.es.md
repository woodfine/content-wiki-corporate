---
schema: foundry-doc-v1
title: "Cómo Funciona el Análisis de Sensibilidad y Pruebas de Estrés para las Soluciones de Tenencia Directa"
slug: sensitivity-and-stress-test-methodology
aliases: []
short_description: "Cómo las Soluciones de Tenencia Directa modelan el estrés de tasa de interés, ocupación y rendimiento de desarrollo frente al convenio de cobertura de 1.20x."
category: financial-model
index_group: valuation-and-forecasting-methodology
type: topic
content_type: topic
quality: complete
status: active
audience: public
bcsc_class: forward-looking
language_protocol: TRANSLATE-ES
last_edited: 2026-09-06
editor: pointsav-engineering
paired_with: sensitivity-and-stress-test-methodology.md
cites: []
---

Cada Solución de Tenencia Directa se modela frente a una unidad de referencia de preservación de capital de $100,000.00 y un convenio mínimo de cobertura de intereses de 1.20x establecido en las condiciones de financiamiento de sus debentures. Este artículo recorre la metodología de sensibilidad y pruebas de estrés aplicada a ese modelo. Un solo impulsor de cobertura —tasa de interés, ocupación o rendimiento de desarrollo— se ajusta de forma aislada para observar su efecto sobre la cobertura y el ritmo de desarrollo. La palanca adaptativa de desarrollo del emisor está diseñada para sostener el convenio en lugar de incumplirlo. Un choque combinado máximo, calibrado a las recesiones históricas más severas, se absorbe mediante una disposición correctiva de último recurso. Las sensibilidades resultantes se reportan bajo la NIIF 13 §93(h)(ii). El resultado de esta metodología es un conjunto de escenarios modelados e ilustrativos, no una predicción del desempeño futuro — la cobertura, el valor neto de los activos (NAV) y los resultados de distribución reales diferirán de cada uno de los supuestos aquí planteados.

## Antes de leer esto

Este artículo asume familiaridad con el propio convenio de cobertura de intereses — véase [[cre-financial-metrics|Razón de Cobertura de Intereses]] para entender qué es el piso de 1.20x y por qué se establece en ese nivel; este artículo no vuelve a explicar el convenio, sino que recorre cómo se somete a pruebas de estrés. También asume familiaridad con el valor neto de los activos (NAV) y las demás medidas no-NIIF frente a las cuales reporta esta metodología — véase [[non-ifrs-measures-explained|Medidas No-NIIF Explicadas]]. Más allá de esto no se requiere nada: ningún software de modelado ni acceso a cuenta alguna — este artículo describe una metodología, no una herramienta.

## Cómo se construyen los escenarios

La metodología da seguimiento a una unidad de referencia de preservación de capital de $100,000.00 a través de cada escenario, desde el caso base hasta el choque combinado máximo. El caso base es el pronóstico a 10 años sin estrés: la tasa de financiamiento, la ocupación y el rendimiento de desarrollo se mantienen en sus valores esperados, y la cobertura de intereses se verifica frente al convenio de 1.20x en cada punto del horizonte.

A partir de ese caso base, la metodología de escenarios de estrés por impulsor de cobertura ajusta un solo impulsor a la vez —tasa de interés, ocupación o rendimiento de desarrollo— mientras mantiene todos los demás supuestos en su nivel base. Esto aísla el efecto de ese impulsor sobre la cobertura mínima de intereses y sobre el ritmo de desarrollo, antes de que los impulsores se combinen entre sí.

Lo que muestra cada escenario de estrés de un solo impulsor no es una proyección estática, sino la respuesta en tiempo real de la palanca adaptativa de desarrollo del emisor. A medida que los costos de financiamiento o las condiciones operativas empeoran durante la construcción, el emisor restringe la emisión de nuevos debentures y reduce el ritmo del programa de desarrollo para sostener la cobertura de intereses en el nivel del convenio en lugar de permitir su incumplimiento. Una proyección estática, sin respuesta, se considera poco realista en esta metodología, porque un incumplimiento sostenido del convenio transferiría el control del activo a los prestamistas garantizados — la respuesta adaptativa es el comportamiento modelado, no una capa optimista superpuesta.

Una vez que una Solución de Tenencia Directa se estabiliza tras la construcción, la cobertura de intereses se mantiene muy por encima del piso de 1.20x, y los escenarios de estrés de la metodología muestran que se requiere un aumento considerable en el cupón de financiamiento antes de que el umbral del convenio vuelva a acercarse.

El escenario de choque combinado máximo se aparta del enfoque de un solo impulsor al aplicar movimientos adversos simultáneos a la tasa de financiamiento, la tasa de capitalización y la ocupación a la vez. Está calibrado a la evidencia histórica de recesiones severas —movimientos de expansión de tasas de capitalización de oficinas y de tasas de refinanciamiento a la escala de 2008-09 y 2022-23— y se utiliza para dimensionar el caso a la baja para la preservación de capital. Bajo este choque combinado, se vende una fracción mínima de la cartera a su valor de transacción ordenada bajo condiciones de estrés, para restablecer la cobertura de intereses al nivel del convenio — una venta a valor de mercado diseñada para preservar el NAV por unidad mientras comprime, sin eliminar, las distribuciones.

Junto a estos escenarios por impulsor de cobertura, la metodología de presentación da seguimiento a las trayectorias del NAV por unidad bajo un caso base, un caso pesimista (tasa de capitalización y ocupación adversas) y un caso optimista (tasa de capitalización favorable), todos medidos frente a la referencia de preservación de capital de $100,000.00 a lo largo del horizonte de pronóstico a 10 años.

Por separado, la tabla de sensibilidad de la NIIF 13 §93(h)(ii) aplica una sensibilidad unidireccional de ±25 puntos base a través de la tasa de capitalización, la tasa de interés, la ocupación y el rendimiento de desarrollo, medida frente al NAV por unidad, el rendimiento de ingresos y la cobertura mínima del Año 8. Esta tabla es un requisito de divulgación de medición a valor razonable, distinto de los escenarios prospectivos descritos anteriormente.

## Cómo distinguir qué escenario se está leyendo

Cualquier ejemplo de esta metodología puede ubicarse correctamente verificando dos cosas. Primero, cuál de los tres impulsores de cobertura se está ajustando, y si el ejemplo corresponde a un estrés de un solo impulsor o al choque combinado máximo. Esto se resuelve verificando si dos de los tres impulsores se mantienen en su nivel base (estrés de un solo impulsor) o si la tasa de financiamiento, la tasa de capitalización y la ocupación se mueven todas a la vez (choque combinado).

Segundo, de qué lado del límite de divulgación se encuentra el ejemplo. Los ejemplos de respuesta de la administración y de disposición correctiva descritos anteriormente son escenarios ilustrativos y prospectivos, mientras que la tabla de la NIIF 13 es una divulgación de sensibilidad de medición a valor razonable. Ambos se preparan conforme a normas distintas — los ejemplos prospectivos incorporan un lenguaje de advertencia coherente con el NI 51-102 y la ISAE 3400, y la tabla de la NIIF 13 sigue la propia convención de esa norma de supuestos alternativos razonablemente posibles de ±25 puntos base. Una cifra que no pueda ubicarse en uno u otro lado de ese límite no ha sido correctamente localizada dentro de la metodología.

Todos los escenarios de estrés y de choque de esta metodología son modelados e ilustrativos. Ninguna de las cifras de cobertura, NAV o distribución que produce constituye una predicción, una garantía ni una promesa de desempeño futuro real; los resultados reales diferirán de cada uno de los supuestos utilizados para construir estos escenarios.

## Lo que esto no es

Ninguna cifra de cobertura, NAV o distribución de esta metodología es un pronóstico. Cada escenario se construye a partir de supuestos declarados; los resultados reales diferirán. La metodología aún no se ha aplicado a una cartera en operación — ninguna Solución de Tenencia Directa ha emitido un debenture ni alcanzado la fase estabilizada que describen los escenarios, de modo que el caso base es un conjunto de supuestos, no un historial. La respuesta adaptativa de desarrollo y la disposición correctiva de último recurso son comportamientos modelados, no compromisos de actuar. La tabla de sensibilidad de la NIIF 13 es una convención de divulgación a valor razonable, no una estimación de resultados probables.

## Consulte también

- [[cre-financial-metrics|Razón de Cobertura de Intereses]] — el convenio que esta metodología somete a pruebas de estrés
- [[non-ifrs-measures-explained|Medidas No-NIIF Explicadas]] — cómo se definen el NAV y las demás medidas complementarias utilizadas en esta metodología, y cómo se concilian con las NIIF
- [[forward-looking-statements-advisory|Aviso sobre Declaraciones Prospectivas]] — el lenguaje de advertencia que rige cada escenario ilustrativo de este artículo
