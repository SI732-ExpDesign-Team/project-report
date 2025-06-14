# Capítulo VIII: Experiment-Driven Development

## 8.1. Experiment Planning

La planificación de experimentos es crucial para definir una visión clara de lo que se busca aprender y cómo se logrará.

### 8.1.1. As-Is Summary

Actualmente, el mercado de remodelación presenta una demanda creciente y un flujo constante de personas interesadas en construir o renovar sus hogares. Sin embargo, existe una problemática significativa: no hay plataformas digitales completas que reúnan a empresas de remodelación, lo que dificulta a los usuarios encontrar servicios adecuados y realizar un seguimiento integral de los proyectos. Los usuarios deben realizar búsquedas manuales, y muchas empresas carecen de un portafolio actualizado, lo que complica la toma de decisiones y la visibilidad para los profesionales. La escasez de soluciones tecnológicas específicas impide una digitalización eficiente del sector.

### 8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims

Esta sección detalla los elementos base que nutren la planificación de los experimentos:

### • Assumptions (Supuestos)

- Los usuarios (contratistas y remodeladores) necesitan una plataforma digital que les permita contactar empresas, gestionar proyectos, acceder a un marketplace de materiales y ampliar su cartera de clientes.
- Existe una creciente demanda en el mercado de remodelación de viviendas, que representa una valiosa oportunidad para la plataforma.
- ReStyle puede diferenciarse de los competidores al ofrecer una plataforma digital que optimiza la experiencia para usuarios y profesionales.
- Los clientes valorarán la facilidad, transparencia y calidad del servicio ofrecido por ReStyle.

### • Knowledge Gaps (Brechas de Conocimiento)

- La efectividad real de las optimizaciones en la búsqueda y comparación de remodeladores para aumentar la recurrencia de usuarios.
- La curva de aprendizaje real de la plataforma y su efecto en la reducción de consultas al soporte.
- El porcentaje exacto de aumento en la contratación de profesionales con mejores valoraciones tras implementar un sistema de evaluaciones.
- La tasa de conversión efectiva de remodeladores a planes premium durante el primer año de lanzamiento.

### • Ideas (Ideas)

- Optimizar el proceso de búsqueda y comparación de remodeladores para mejorar la experiencia del contratista.
- Diseñar una plataforma sencilla y accesible para atraer a una amplia base de usuarios.
- Incorporar un sistema robusto de evaluaciones y comentarios para generar confianza y reflejar la reputación de los remodeladores.
- Ofrecer planes de suscripción premium (mensuales y anuales) a los remodeladores para establecer una fuente de ingresos recurrente y financiar herramientas avanzadas.

### • Claims (Afirmaciones)

- Se proyecta un aumento del 20% en la tasa de recurrencia de usuarios contratistas en los primeros seis meses, con un incremento del 25% en los contratos recurrentes.
- Se espera un incremento del 20% en la satisfacción del cliente y un 15% en la permanencia de los remodeladores en el servicio.
- Se prevé un aumento del 30% en la contratación de profesionales con mejores valoraciones.
- Se busca que al menos el 30% de los remodeladores se suscriban a planes premium durante el primer año.

### 8.1.3. Experiment-Ready Questions

## Preguntas clave para el diseño de experimentos

Basado en las brechas de conocimiento y las ideas, las preguntas clave para el diseño de experimentos son:

- ¿Cómo podemos optimizar el proceso de búsqueda y comparación de remodeladores para incrementar la recurrencia de usuarios en un 20% en los primeros seis meses?
- ¿De qué manera un diseño de plataforma sencillo y accesible atraerá a más visitantes interesados en remodelaciones y profesionales, reduciendo las consultas de soporte en un 30%?
- ¿La incorporación de un sistema de evaluaciones y comentarios dentro de la plataforma aumentará la contratación de profesionales con mejores valoraciones en un 30%?
- ¿La oferta de planes de suscripción premium (mensuales y anuales) para remodeladores resultará en que al menos el 30% de los visitantes de este segmento se suscriban durante el primer año de lanzamiento?

### 8.1.4. Question Backlog

El backlog de preguntas, priorizado según la urgencia de validación para el modelo de negocio, es el siguiente :

1. ¿Cómo podemos optimizar el proceso de búsqueda y comparación de remodeladores para incrementar la recurrencia de usuarios en un 20% en los primeros seis meses?
2. ¿De qué manera un diseño de plataforma sencillo y accesible atraerá a más visitantes interesados en remodelaciones y profesionales, reduciendo las consultas de soporte en un 30%?
3. ¿La incorporación de un sistema de evaluaciones y comentarios dentro de la plataforma aumentará la contratación de profesionales con mejores valoraciones en un 30%?
4. ¿La oferta de planes de suscripción premium (mensuales y anuales) para remodeladores resultará en que al menos el 30% de los visitantes de este segmento se suscriban durante el primer año de lanzamiento?

### 8.1.5. Experiment Cards

## 8.2. Experiment Design
En esta sección se formulan hipótesis claras, medibles y orientadas a validar los elementos clave del modelo de negocio de reStyle. Estas hipótesis surgen a partir de los supuestos, brechas de conocimiento e ideas definidos en el punto 8.1.2, y se vinculan directamente con las preguntas del backlog priorizado (8.1.4).
### 8.2.1. Hypotheses

#### Hipótesis 1:
  Si optimizamos el proceso de búsqueda y comparación de remodeladores, entonces la tasa de recurrencia de los contratistas aumentará en un 20% durante los primeros seis meses.

- Motivación: Mejorar la experiencia de búsqueda puede fomentar el uso repetido de la plataforma.

- Validación: Un aumento sostenido en el número de sesiones por usuario contratista y contrataciones recurrentes.

#### Hipótesis 2:
Si el diseño de la plataforma es sencillo, claro y accesible, entonces se reducirá el número de consultas al soporte en al menos un 30% en los primeros tres meses tras el rediseño.

- Motivación: Una interfaz clara puede reducir fricciones y dudas al usar el sistema.

- Validación: Reducción del volumen de tickets o mensajes al equipo de soporte, especialmente en categorías de navegación y usabilidad.

#### Hipótesis 3:
Si se incorpora un sistema de evaluaciones y comentarios para remodeladores, entonces la contratación de profesionales con altas valoraciones aumentará en un 30%.

- Motivación: Los usuarios tienden a confiar más en profesionales con buena reputación visible.

- Validación: Mayor porcentaje de contrataciones concentrado en perfiles con calificación ≥ 4 estrellas.

#### Hipótesis 4:
Si se ofrece un plan de suscripción premium con herramientas avanzadas, al menos el 30% de los remodeladores activos en la plataforma se suscribirá en el primer año.

- Motivación: Profesionales que desean destacar y captar más clientes estarán dispuestos a pagar por visibilidad y beneficios adicionales.

- Validación: Porcentaje de remodeladores con cuenta premium vs. total de remodeladores activos.

### 8.2.2. Measures
Esta sección define qué se va a medir para evaluar si las hipótesis formuladas en el punto 8.2.1 son validadas o no. Las métricas seleccionadas deben ser cuantificables, relevantes para el negocio y directamente vinculadas con los cambios esperados.

#### Medidas para la Hipótesis 1 (Optimización de búsqueda → +20% recurrencia de usuarios):
- Tasa de recurrencia de contratistas
(Usuarios que vuelven a contratar dentro de los primeros 6 meses después de su primera contratación).

- Frecuencia de uso de la funcionalidad de búsqueda avanzada
(Número de veces que se utiliza la herramienta de filtrado o comparación).

- Tiempo promedio de búsqueda
(Reducción del tiempo necesario entre el inicio de una búsqueda y la contratación de un remodelador).

#### Medidas para la Hipótesis 2 (Diseño accesible → -30% consultas de soporte):
- Cantidad de tickets o mensajes recibidos por soporte técnico
(Especialmente en las categorías relacionadas con navegación, registro, búsqueda o contratación).

- Tiempo de permanencia en páginas clave
(Mayor claridad se asocia con menor permanencia innecesaria o rebotes).

- Tasa de rebote por sección de la interfaz
(Altas tasas pueden indicar confusión o mal diseño).

#### Medidas para la Hipótesis 3 (Sistema de evaluaciones → +30% contratación de los mejor valorados):
- Porcentaje de contrataciones hechas a remodeladores con 4 estrellas o más

- Número total de evaluaciones publicadas por usuarios
(Para validar si el sistema se está utilizando activamente).

- Tasa de conversión de perfiles mejor valorados frente a los de baja calificación
(Para ver si efectivamente los mejor calificados tienen mayor contratación).

#### Medidas para la Hipótesis 4 (Planes premium → 30% suscripción remodeladores):
- Porcentaje de remodeladores activos que adquieren el plan premium

- Retención de remodeladores premium vs. estándar
(¿Se quedan más tiempo los usuarios de pago?).

- Número de funciones premium utilizadas por remodeladores suscritos
(Para validar el uso real del valor agregado ofrecido).
### 8.2.3. Conditions
Esta sección establece las condiciones bajo las cuales se llevarán a cabo los experimentos para asegurar que los resultados sean válidos, confiables y estén alineados con los objetivos de negocio. Las condiciones incluyen el entorno del experimento, la segmentación de usuarios, las variables a controlar y los plazos estimados.

#### Condiciones generales para todos los experimentos
- Entorno controlado: Los experimentos se realizarán en la plataforma web y app de ReStyle, asegurando un entorno digital estable y funcional.

- Usuarios reales: Los datos se recopilarán de usuarios reales (contratistas y remodeladores) dentro de un entorno de producción o en pruebas A/B.

- Segmentación geográfica: Los primeros experimentos estarán enfocados en una región piloto (por ejemplo, Lima Metropolitana) antes de expandirse.

- Período de prueba: Cada experimento se ejecutará inicialmente durante 8 semanas, para observar tanto efectos inmediatos como tendencias sostenidas.

### Condiciones específicas por hipótesis
  #### Hipótesis 1 – Optimización del buscador
  - Se habilitará una nueva versión del buscador a un grupo de usuarios A (50%) y se comparará con el grupo B (con versión antigua).
  - Ambos grupos deben tener perfiles similares en antigüedad y nivel de actividad.

#### Hipótesis 2 – Interfaz sencilla y accesible
- Se realizará un rediseño parcial (wireframes de baja carga cognitiva) que se mostrará a nuevos usuarios y se comparará con la versión anterior.
- Se controlará la fuente del tráfico (redes sociales, Google Ads, tráfico orgánico) para reducir sesgos.

#### Hipótesis 3 – Sistema de evaluaciones
- Se activará el sistema de valoraciones solo en ciertos tipos de servicios o categorías durante el primer test (ej: cocina y baño).
- Se incentivará a los usuarios a dejar una evaluación tras completar un proyecto.

#### Hipótesis 4 – Planes premium
- Se ofrecerá la opción premium a remodeladores registrados con más de 2 contratos exitosos.
- Se usará una landing especial para mostrar beneficios exclusivos a este grupo y comparar con remodeladores sin exposición a esta oferta.

### 8.2.4. Scale Calculations and Decisions
Esta sección define el tamaño mínimo de muestra requerido para validar estadísticamente las hipótesis planteadas y las decisiones clave sobre cómo escalar cada experimento a mayor número de usuarios si se observan resultados positivos.

### Tamaño mínimo de muestra (Sample Size)
Para que los resultados de los experimentos sean estadísticamente significativos, necesitamos calcular cuántos usuarios deben participar en cada grupo (control y experimental). Utilizaremos las siguientes condiciones estándar para pruebas A/B:

- Nivel de confianza (Confidence level): 95%

  Esto significa que hay un 95% de probabilidad de que los resultados reflejen una diferencia real y no un error aleatorio.

- Poder estadístico (Statistical power): 80%

  Esto indica que si realmente existe un efecto (por ejemplo, una mejora en contrataciones), hay un 80% de probabilidad de detectarlo.

- Tasa de conversión base esperada (Baseline conversion rate): 10%

  Por ejemplo, si actualmente el 10% de los visitantes contratan un servicio, este será nuestro punto de comparación.

- Diferencia mínima detectable (Minimum Detectable Effect, MDE): 10%

  Esperamos ver al menos un 10% de mejora (por ejemplo, pasar de 10% a 11%).

Utilizando una calculadora estadística estándar (por ejemplo, Evan Miller’s Sample Size Calculator), se obtiene lo siguiente:

- Para detectar una diferencia del 10% con 95% de confianza y 80% de poder estadístico, partiendo de una tasa base del 10%:

  Resultado: Se requieren aproximadamente 385 usuarios por grupo, es decir:

  770 usuarios en total por experimento A/B.

### Escalamiento por hipótesis
Hipótesis 1 – Optimización del proceso de búsqueda y comparación.

- Tamaño de muestra inicial: 770 usuarios (385 grupo A y 385 grupo B)

- Criterio de éxito: aumento significativo ≥10% en la tasa de recurrencia.

- Escalamiento: Si se valida, se aplicará la mejora a todos los usuarios activos.

Hipótesis 2 – Diseño sencillo y accesible.

- Tamaño de muestra inicial: 600 usuarios (300 por grupo), nuevos visitantes.

- Criterio de éxito: reducción ≥30% en consultas a soporte y mayor retención en primera semana.

- Escalamiento: Publicación completa del diseño tras dos ciclos exitosos.

Hipótesis 3 – Evaluaciones y comentarios.

- Tamaño de muestra inicial: 500 usuarios (centrados en proyectos de cocina/baño)

- Criterio de éxito: incremento ≥25-30% en contratación de profesionales con alta puntuación.

- Escalamiento: Activación del sistema de reseñas en toda la plataforma.

Hipótesis 4 – Planes de suscripción premium.

- Tamaño de muestra inicial: 400 remodeladores activos

- Criterio de éxito: ≥30% de suscripciones en el primer mes.

- Escalamiento: Lanzamiento completo de los planes premium y nuevas funcionalidades asociadas.

### Decisiones clave sobre escalamiento

- El escalamiento nacional (fuera de Lima) solo ocurrirá si se valida primero con éxito en la región piloto (Lima Metropolitana).

- Se utilizarán experimentos iterativos (por ejemplo, cada 2 semanas) para ajustes rápidos y detección de mejoras marginales.

- Los grupos de control se mantendrán en producción para comparar resultados a largo plazo (especialmente en métricas de retención y satisfacción).

- En caso de baja significancia estadística o efecto nulo, se replanteará la hipótesis o se ajustará el diseño de la solución.

### 8.2.5. Methods Selection
En esta sección se detallan los métodos a utilizar para validar las hipótesis planteadas, considerando el tipo de datos necesarios, el nivel de fidelidad requerido y la etapa de desarrollo del producto.

### Métodos Cuantitativos

Estos métodos permitirán validar hipótesis relacionadas con comportamiento, métricas de conversión y patrones de uso a mayor escala.

| Método                                   | Justificación                                                                                                                                                                                                                                                                 |
| ---------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **A/B Testing**                          | Ideal para comparar variantes de funcionalidades como el buscador optimizado, presentación de remodeladores, o la incorporación de filtros. Permite medir con precisión el impacto de un cambio en métricas clave como tasa de conversión o tiempo promedio en la plataforma. |
| **Análisis de Cohortes**                 | Útil para analizar el comportamiento de grupos de usuarios (p. ej., contratistas nuevos vs. recurrentes) a lo largo del tiempo, validando hipótesis sobre retención y recurrencia.                                                                                            |
| **Funnel Analysis**                      | Ayuda a identificar en qué etapa del flujo de uso (registro, búsqueda, contratación, contacto) se producen los mayores abandonos, y así validar hipótesis sobre mejoras UX o accesibilidad.                                                                                   |
| **Encuestas con escala Likert (en app)** | Cuantifica la percepción del usuario sobre facilidad de uso, confianza en los evaluadores y satisfacción general.                                                                                                                                                             |
| **Segmentación por comportamiento**      | Permite analizar si ciertos segmentos (p. ej., usuarios frecuentes vs. esporádicos) reaccionan de manera diferente a las mejoras, especialmente útil para el sistema de suscripciones.                                                                                        |
### Métodos Cualitativos
Complementan los datos cuantitativos para entender los "porqués" detrás del comportamiento del usuario.

| Método                                  | Justificación                                                                                                                                                                              |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Entrevistas en profundidad**          | Ideal en etapas tempranas para validar supuestos y detectar insights sobre cómo los usuarios perciben la plataforma, qué barreras tienen, o qué funcionalidades valoran más.               |
| **Pruebas de usabilidad (think aloud)** | Esenciales para identificar problemas en el diseño y navegación del sistema antes o durante los experimentos. Permiten mejorar la experiencia sin esperar datos a gran escala.             |
| **Diarios de usuario (User Diaries)**   | Sirven para recolectar experiencias más ricas y contextuales durante periodos prolongados de uso de la plataforma. Especialmente útiles para evaluar la percepción del valor en el tiempo. |


### Selección basada en la hipótesis
| Hipótesis clave                              | Métodos sugeridos                                          |
| -------------------------------------------- | ---------------------------------------------------------- |
| Optimización de búsqueda mejora recurrencia  | A/B testing + análisis de cohorte + entrevistas            |
| Diseño sencillo reduce consultas de soporte  | Pruebas de usabilidad + funnel analysis + encuestas        |
| Sistema de evaluaciones aumenta contratación | A/B testing + segmentación de comportamiento + entrevistas |
| Planes premium generan suscripciones         | Funnel analysis + encuestas + entrevistas a remodeladores  |

### 8.2.6. Data Analytics: Goals, KPIs and Metrics Selection

El objetivo de esta sección es definir con claridad qué se va a medir, por qué se mide y cómo se utilizarán esos datos para evaluar el éxito de los experimentos y tomar decisiones informadas.

### Goals (Objetivos Analíticos)
- Incrementar la recurrencia de usuarios contratistas.<br>
  Validar si las mejoras en la búsqueda y experiencia de usuario logran que los contratistas regresen y contraten más de una vez.

- Reducir la fricción de uso y dependencia del soporte.<br>
  Verificar si el diseño intuitivo disminuye el número de consultas, tickets o errores reportados.

- Incrementar la contratación de remodeladores con mejores valoraciones.<br>
  Medir si el sistema de evaluaciones incide directamente en decisiones de contratación.

- Validar viabilidad del modelo de monetización mediante suscripciones premium.<br>
  Medir la aceptación, conversión y retención de remodeladores en planes pagos.

### KPIs (Indicadores Clave de Rendimiento)

| Objetivo                                | KPI Principal                                 | Fórmula / Descripción                                                                  |
| --------------------------------------- | --------------------------------------------- | -------------------------------------------------------------------------------------- |
| Recurrencia de usuarios                 | **Tasa de Retención**                         | % de usuarios que regresan y contratan en un período definido (ej. dentro de 30 días). |
| Facilidad de uso                        | **Número de tickets de soporte**              | Total de consultas o incidencias reportadas durante el uso de la plataforma.           |
| Efectividad del sistema de evaluaciones | **Tasa de contratación de top remodeladores** | % de contrataciones que se hacen a remodeladores con calificación ≥ 4.5/5.             |
| Viabilidad del plan premium             | **Tasa de conversión a plan premium**         | % de remodeladores activos que se suscriben a un plan pago.                            |

### Otras Métricas Complementarias
| Métrica                                 | Descripción                                                                                                                          |
| --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **Tiempo medio en búsqueda**            | Tiempo promedio que toma a un contratista filtrar, explorar y contactar a un remodelador. Idealmente debe disminuir con las mejoras. |
| **Net Promoter Score (NPS)**            | Evalúa la satisfacción general y probabilidad de recomendación. Se obtiene a través de encuestas.                                    |
| **Customer Satisfaction (CSAT)**        | Calificación del usuario luego de una contratación o interacción, típicamente medida en escala 1–5.                                  |
| **Tasa de rebote**                      | % de usuarios que abandonan sin interactuar con el sistema de búsqueda. Un indicador de experiencia poco atractiva o confusa.        |
| **Churn Rate de remodeladores premium** | % de remodeladores premium que cancelan su suscripción. Ayuda a evaluar sostenibilidad del modelo de ingresos.                       |



### 8.2.7. Web and Mobile Tracking Plan

## 8.3. Experimentation

### 8.3.1. To-Be User Stories

En esta sección, se identifican y refinan las historias de usuario clave del proyecto **Restyle**, enfocadas en facilitar la interacción entre contratistas y empresas remodeladoras. Estas historias han sido analizadas y ajustadas respecto a versiones anteriores, incorporando mejoras de usabilidad y funcionalidades técnicas necesarias para lograr una experiencia más eficiente, confiable y satisfactoria para los usuarios.


---
#### **US007 - Búsqueda de empresas remodeladoras**

- **Historia de Usuario:**  
  *Como visitante del segmento contratista, quiero poder buscar remodeladoras por ubicación o expertise para obtener un resultado más personalizado.*

- **Estado Inicial:**  
  La búsqueda arrojaba resultados genéricos sin posibilidad de filtrado específico por tipo de servicio o zona geográfica.

- **Cambios:**  
  Se implementaron filtros por especialidad, puntuación y ubicación, permitiendo a los usuarios encontrar empresas más alineadas con sus necesidades concretas.

- **Estado Final:**  
  La búsqueda se ha vuelto más precisa y eficiente, permitiendo una mejor experiencia de descubrimiento y comparación entre proveedores de servicios.

---

#### **US009 - Agregar críticas y opiniones**

- **Historia de Usuario:**  
  *Como visitante del segmento contratista, quiero agregar un review para poder compartir mi experiencia con otros usuarios sobre el remodelador con el que realicé un proyecto.*

- **Estado Inicial:**  
  La funcionalidad no estaba disponible en etapas tempranas de desarrollo, lo que limitaba el feedback colaborativo en la plataforma.

- **Cambios:**  
  Se desarrolló un módulo para registrar comentarios, calificaciones con estrellas y retroalimentación textual, vinculado al perfil del remodelador.

- **Estado Final:**  
  Ahora, los usuarios pueden compartir sus experiencias, ayudando a otros a tomar decisiones informadas y fomentando la confianza en el ecosistema de la aplicación.


---
#### **US016 - Programar consulta con un remodelador**

- **Historia de Usuario:**  
  *Como propietario de vivienda interesado en remodelar, quiero poder programar una consulta con un remodelador a través de la plataforma para discutir mis necesidades y obtener recomendaciones.*

- **Estado Inicial:**  
  No existía una forma clara para coordinar citas o reuniones con los remodeladores desde la aplicación.

- **Cambios:**  
  Se añadió una funcionalidad de agendamiento, incluyendo un formulario con calendario, opciones de horarios disponibles y confirmación por correo electrónico.

- **Estado Final:**  
  Los usuarios ahora pueden gestionar consultas directamente con los profesionales, facilitando el inicio del proceso de remodelación y generando una interacción más fluida.




### 8.3.2. To-Be Product Backlog

A continuación, se presenta el Product Backlog actualizado del proyecto **Restyle**. Estas historias representan funcionalidades clave para brindar una experiencia personalizada y eficiente a los usuarios interesados en servicios de remodelación.

| N°  | ID     | Título                                     | Descripción                                                                                                                                    | Story Points |
|-----|--------|--------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------|--------------|
| 7   | US007  | Búsqueda de empresas remodeladoras         | Como visitante del segmento contratista, quiero poder buscar remodeladoras por ubicación o expertise para obtener un resultado más personalizado. | 4            |
| 9   | US009  | Agregar críticas y opiniones               | Como visitante del segmento contratista, quiero agregar un review para poder compartir mi experiencia con otros usuarios sobre el remodelador con el que realicé un proyecto. | 3            |
| 16  | US016  | Programar consulta con un remodelador      | Como propietario de vivienda interesado en remodelar, quiero poder programar una consulta con un remodelador a través de la plataforma para discutir mis necesidades y obtener recomendaciones. | 5            |



### 8.3.3. Pipeline-supported, Experiment-Driven To-Be Software Platform Lifecycle

#### 8.3.3.1. To-Be Sprint Backlogs

#### 8.3.3.2. Implemented To-Be Landing Page Evidence

#### 8.3.3.3. Implemented To-Be Frontend-Web Application Evidence

#### 8.3.3.4. Implemented To-Be Native-Mobile Application Evidence

#### 8.3.3.5. Implemented To-Be RESTful API and/or Serverless Backend Evidence

#### 8.3.3.6. Team Collaboration Insights

### 8.3.4. To-Be Validation Interviews

#### 8.3.4.1. Diseño de Entrevistas

#### 8.3.4.2. Registro de Entrevistas

## 8.4. Experiment Aftermath & Analysis

### 8.4.1. Analysis and Interpretation of Results

### 8.4.2. Re-scored and Re-prioritized Question Backlog

## 8.5. Continuous Learning

### 8.5.1. Shareback Session Artifacts: Learning Workflow

## 8.6. To-Be Software Platform Pre-launch

### 8.6.1. About-the-Product Intro Video

# Capítulo IX: Conclusiones 

## 9.1. Conclusiones y recomendaciones

- La plataforma ReStyle surge como respuesta a una necesidad real en el mercado peruano, respaldada por datos estadísticos del INEI e IPSOS que muestran un crecimiento tanto en el sector de remodelación (7% de personas con planes para remodelar su vivienda) como en la adopción tecnológica por parte de las PYMES (94% han invertido en tecnología recientemente).

- La aplicación de metodologías Lean UX y Design Thinking permitió una comprensión profunda de los segmentos objetivos (contratistas y remodeladores), evidenciada en las entrevistas realizadas y en el desarrollo de User Personas, User Journey Mapping y Empathy Mapping, que revelan puntos de dolor específicos como la falta de transparencia y dificultad para encontrar profesionales confiables.

- El análisis competitivo identificó ventajas claras frente a competidores como ARAM, Remodela tu casa y Timbrit, centrándose en la conexión directa entre clientes y profesionales, la transparencia en el seguimiento de proyectos y un modelo de monetización basado en suscripciones premium para remodeladores.

- La definición de guías de estilo de código, convenciones de nomenclatura y el uso de GitFlow como sistema de control de versiones demuestran un enfoque profesional que facilita la colaboración entre los miembros del equipo y asegura la calidad del producto final.

- El proyecto no solo se centra en el desarrollo técnico, sino que contempla todos los aspectos del ciclo de vida del producto, desde la investigación inicial y definición de requerimientos hasta la implementación, despliegue y promoción, evidenciado en la landing page funcional y el video promocional del producto.

## 9.2. Video About-the-Team

# Capítulo X: Bibliografía 

Instituto Nacional de Estadística e Informática. (2018). En el país existen más de diez millones de viviendas particulares censadas. https://m.inei.gob.pe/prensa/noticias/en-el-pais-existen-mas-de-diez-millones-de-viviendas-particulares-censadas-10893/

Instituto Nacional de Estadística e Informática. (2018). Informe Técnico N° 02: Demografía empresarial - I Trimestre 2018. https://www.inei.gob.pe/media/MenuRecursivo/boletines/02-informe-tecnico-n-02-demografia-empresarial-i-trim2018_may2018.pdf

Interaction Design Foundation. (s.f.). A simple introduction to Lean UX. https://www.interaction-design.org/literature/article/a-simple-introduction-to-lean-ux

Ipsos. (2019). Planes para la vivienda y el mejoramiento del hogar 2019. https://www.ipsos.com/es-pe/planes-para-la-vivienda-y-el-mejoramiento-del-hogar-2019

Microsoft. (2022). Aceleración digital: Más del 94% de las pymes peruanas invirtió en tecnología en el último año [Comunicado de prensa]. https://news.microsoft.com/es-xl/aceleracion-digital-mas-del-94-de-las-pymes-peruanas-invirtio-en-tecnologia-en-el-ultimo-ano/

Terrel, E. (2023). Cinco razones por las que los peruanos eligen remodelar su vivienda. Peru Construye. https://peruconstruye.net/2023/08/03/cinco-razones-eligen-remodelar-vivienda/

# Capítulo XI: Anexos 

<table>
  <tr>
    <th>Sección</th>
    <th>Características del video</th>
    <th>Sobre el contenido</th>
    <th>Integración y entrega</th>
  </tr>
  <!--PRIMERA FILA-->
  <tr>
    <td>Entrevistas</td>
    <td>
      Cantidad de videos: 1<br>
      Nomenclatura: upc-pre-202501-1asi0732-4430-estrellados-needfinding-sprint-1<br>
      Formato: .mp4<br>
      Duración: 28:27 min
    </td>
    <td>Consolida todas las entrevistas realizadas, incluyendo en cada entrevista títulos con información del entrevistado, el segmento objetivo y la fecha de la entrevista.</td>
    <td>Enlace: <a href="https://upcedupe-my.sharepoint.com/:v:/g/personal/u202118315_upc_edu_pe/ET1QS27QI8FIp31HoL_PQVoB4ZOZMMzHz00ElPWsFPpE1Q?e=t2hWIb&nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D">Link de entrevistas</a>
    <br>Captura:<br> <img src="../assets/img/chapter-II/needfinding-tb1.png" alt="Foto de entrevista" width=200px></td>
  </tr>
  <!--SEGUNDA FILA-->
  <tr>
    <td>About the Product</td>
    <td>      
      Cantidad de videos: 1<br>
      Nomenclatura: upc-pre-202501-1asi0732-4430-estrellados-about-the-product-sprint-1<br>
      Formato: .mp4<br>
      Duración: 1:00 min</td>
    <td>
    Orientación promocional, resumiendo el modelo de negocio, las características y beneficios del producto, incluyendo algunas escenas de interacción con el producto y al menos una opinión por cada segmento objetivo.</td>
    <td>Enlace: <a href="https://www.youtube.com/embed/T2M434QKT4k">Link de Youtube</a>
    <br>Captura:<br> <img src="../assets/img/chapter-V/video-about-the-product.png" alt="" width=200px></td>
  </tr>
  <!--TERCERA FILA-->
  <tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
</table>