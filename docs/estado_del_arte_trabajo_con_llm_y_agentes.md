# Estado del arte del trabajo con LLM y agentes

**Tipo:** Transcripción de una conversación con GPT  
**Propósito:** insumo para definir el objetivo de Conjecture 56  
**Fecha indicada en la respuesta:** 25 de octubre de 2026

> Esta transcripción se conserva como material de referencia. Las afirmaciones y menciones de fuentes todavía no fueron verificadas de manera independiente en este repositorio.

## Prompt

De que formas un desarrollador, ingeniero de software, data scientist trabajan hoy con llm y agentes? Me refiero al mas alto nivel, quiero saber como se trabaja en los mas grandes proyectos opensource, empresas, freelance, startups. Mencione llm y agentes pero si hay mas cosas tambien me interesa saberlo, quiero conocer el estado del arte, con referencias verificables

## Respuesta de GPT

### Estado del arte: cómo trabajan los profesionales de software, datos e IA en 2026

Investigación actualizada al 25 de octubre de 2026 · Ingeniería de software, ciencia de datos, agentes y organizaciones tecnológicas

La transformación más importante que está ocurriendo en el desarrollo de software es el paso de utilizar la IA como asistente para escribir código a utilizarla como sistema de ejecución de tareas de ingeniería.

En los equipos más avanzados ya encontramos ingenieros que delegan investigaciones, implementaciones completas, pruebas, refactorizaciones y revisiones a agentes, mientras se concentran en especificar problemas, diseñar sistemas, establecer restricciones y evaluar resultados.

Esto no significa que todas las empresas hayan adoptado esa forma de trabajar ni que sea siempre más eficiente. Hay diferencias importantes entre lo que ya se utiliza en producción, lo que se está experimentando y lo que los proveedores anuncian como próximo avance.

Un caso particularmente interesante es el de OpenAI: en febrero de 2026 publicó un experimento de ingeniería donde un equipo desarrolló un producto interno con aproximadamente un millón de líneas de código generado por Codex, incluyendo pruebas, CI y observabilidad. Los ingenieros se concentraron en diseñar el entorno y los mecanismos de retroalimentación. La empresa estimó que necesitó una décima parte del tiempo de una implementación manual, aunque se trata de una estimación interna, no de un ensayo independiente.

**Fuente mencionada:** OpenAI.

Este caso representa una de las fronteras más avanzadas del trabajo con agentes, pero es importante contrastarlo con estudios independientes. Por ejemplo, un experimento aleatorizado de METR encontró que, con herramientas disponibles a comienzos de 2025, desarrolladores experimentados tardaban un 19 % más al usarlas en proyectos open source que conocían bien. Es un resultado histórico y contextual, no una medición universal de las herramientas de 2026.

**Fuente mencionada:** METR.

Voy a separar el panorama en cuatro dimensiones: cómo se trabaja, qué tecnologías se utilizan, qué hacen las organizaciones reales y cómo distinguir un flujo avanzado de uno simplemente llamativo.

## 1. Los principales modelos de trabajo

Actualmente pueden distinguirse cinco modalidades. No son etapas que necesariamente deba atravesar una organización: muchas las combinan según el riesgo, la complejidad y el tipo de tarea.

### 1. Desarrollo asistido

El profesional escribe código y utiliza LLM para consultar documentación, autocompletar, explicar errores, generar funciones y discutir alternativas. Conserva el control continuo de la implementación.

### 2. Agentic coding interactivo

Un agente inspecciona el repositorio, edita varios archivos, ejecuta comandos, instala dependencias, corre pruebas y corrige problemas. El ingeniero guía la sesión y revisa los resultados. Es el tipo de trabajo que ofrecen Claude Code, OpenAI Codex y OpenCode.

### 3. Delegación asíncrona de tareas

El profesional asigna una issue o especificación al agente. Este trabaja en un entorno aislado, implementa cambios, verifica resultados y prepara una pull request para revisión posterior. GitHub Copilot cloud agent documenta oficialmente este flujo.

**Fuente mencionada:** GitHub Docs.

### 4. Orquestación de múltiples agentes

Se ejecutan varios agentes con contextos y espacios de trabajo separados. Pueden encargarse simultáneamente de investigación, implementación, pruebas, migraciones o revisión. Un orquestador administra tareas, dependencias y resultados.

### 5. Ingeniería centrada en agentes (agent-first)

El equipo diseña repositorios, arquitecturas, pruebas, herramientas y políticas para que los agentes puedan ejecutar gran parte del trabajo. Los humanos se concentran en objetivos, diseño, restricciones, calidad y responsabilidad sobre el sistema. Es una frontera de experimentación avanzada, no un estándar universal.

## 2. Cómo se desarrolla una funcionalidad en un flujo avanzado

El siguiente es un flujo de referencia que sintetiza prácticas documentadas por OpenAI, Anthropic y GitHub. Representa una arquitectura de trabajo posible, no una metodología obligatoria de la industria.

1. **Ingeniero / Product Owner:** define el problema, criterios de aceptación y restricciones.
2. **Planificador / Coordinador:** examina el repositorio, propone tareas y asigna recursos.
3. **Agente A:** implementación.
4. **Agente B:** pruebas.
5. **Agente C:** investigación y revisión.
6. **Validación automatizada:** tests, lint, tipos, seguridad, integración y CI.
7. **Pull request y aprobación:** revisión del cambio, evidencia de pruebas y autorización humana según el riesgo.
8. **Despliegue y observabilidad:** métricas, registros, alertas, rollback y retroalimentación.

Las prácticas que hacen que este flujo sea confiable son más importantes que la cantidad de agentes:

- **Specification-first:** documentar qué debe lograrse y cómo determinar que está bien.
- **Context engineering:** proporcionar a los agentes arquitectura, convenciones y fuentes de información relevantes.
- **Trabajo aislado:** separar cambios mediante ramas, git worktree, contenedores o entornos remotos.
- **Verification-driven development:** dar al agente pruebas y herramientas para comprobar su propio resultado.
- **Revisión independiente:** contrastar implementación y requisitos, buscando errores que el ejecutor puede no haber detectado.
- **Observabilidad:** conservar evidencia de acciones, resultados, errores y consumo de recursos.

Anthropic destaca específicamente la verificación como la práctica más importante de su guía avanzada de Claude Code.

**Fuente mencionada:** Claude Help Center.

## 3. Casos reales: empresas que están publicando sus prácticas

### OpenAI — Harness Engineering y Symphony

El caso más interesante para estudiar orquestación. En abril de 2026 publicaron Symphony: un sistema que transforma un tablero de gestión de tareas, como Linear, en un mecanismo de coordinación de agentes.

Cada tarea puede dar lugar a un agente y los humanos revisan los resultados. OpenAI reportó un aumento del 500 % en pull requests integradas en algunos equipos; es una cifra interna, no un resultado generalizable.

**Fuentes mencionadas:** OpenAI, *Harness Engineering* y *Symphony*.

### GitHub — Agentes integrados en el proceso de contribución

GitHub permite asignar tareas a Copilot cloud agent, iniciar investigaciones, producir implementaciones y revisar cambios sobre el repositorio. El agente puede trabajar sobre varias issues en paralelo, y una de las modalidades consiste en producir draft pull requests para revisión humana.

**Fuentes mencionadas:** GitHub Docs y guía de adopción empresarial.

### Ramp — Revisión de código y operaciones

Ramp documentó en mayo de 2026 el uso de Codex para revisar código y construir herramientas internas que ayudan a gestionar tareas de guardia (on-call). Es un ejemplo de IA utilizada en el mantenimiento y operación de sistemas existentes, además del desarrollo de funcionalidades.

**Fuentes mencionadas:** OpenAI y caso de ingeniería de Ramp.

## 4. Cómo trabajan los grandes proyectos open source

Aquí aparece una diferencia importante respecto de los laboratorios que experimentan con autonomía casi total: los mantenedores priorizan la calidad, la responsabilidad y el tiempo que cuesta revisar una contribución.

### Kubernetes: un ejemplo verificable de 2026

En junio de 2026, la comunidad de Kubernetes publicó cómo está adaptándose al desarrollo asistido por IA.

Su enfoque incluye declarar el uso de IA en las pull requests, exigir responsabilidad al contribuyente humano, verificar los cambios y responder personalmente a las revisiones. También describe experimentos con herramientas de revisión automatizada en proyectos relacionados con Kubernetes, como Kueue, JobSet y Agent-Sandbox.

En particular, los mantenedores esperan que quien presenta una contribución pueda explicarla y mantenerla.

**Fuente mencionada:** publicación oficial de Kubernetes.

### ¿Qué ocurre en el resto del ecosistema?

Una investigación publicada en septiembre de 2026 analizó 281 políticas de contribución con IA en proyectos open source populares.

- **83,3 %:** de las políticas analizadas permiten o promueven contribuciones de código asistidas por IA.
- **67,3 %:** exigen un nivel elevado de participación humana.

Porcentajes sobre las políticas estudiadas, no sobre la totalidad de repositorios GitHub. Investigación académica de 2026.

**Fuente mencionada:** arXiv.

Esto ayuda a comprender una distinción fundamental: generar más código no equivale necesariamente a contribuir mejor.

En proyectos como Apache Flink, las políticas documentadas desalientan contribuciones generadas sin suficiente refinamiento humano. Otros proyectos exigen acordar cambios grandes antes de presentar una implementación extensa.

La competencia profesional relevante aquí es entregar cambios pequeños, justificados, reproducibles, revisables y mantenibles, independientemente de quién haya escrito inicialmente el código.

## 5. Cómo trabaja hoy un data scientist con LLM y agentes

La ciencia de datos está cambiando de manera parcialmente distinta a la ingeniería de software. Un agente puede generar un programa correcto desde el punto de vista sintáctico y, aun así, producir conclusiones analíticas equivocadas.

Un flujo avanzado de trabajo puede organizarse así:

| Actividad | Trabajo delegado al agente | Responsabilidad del profesional |
|---|---|---|
| Exploración | Consultas SQL, EDA, gráficos y perfiles de datos | Comprender fuentes, sesgos y significado de variables |
| Preparación | Limpieza, transformaciones, pipelines y validaciones | Definir calidad, evitar fugas de información y preservar linaje |
| Modelado | Baselines, entrenamiento, búsqueda de hiperparámetros | Diseñar experimentos y métricas apropiadas |
| Evaluación | Ejecutar pruebas y comparar experimentos | Determinar validez estadística y capacidad de generalización |
| Producción | Crear APIs, pipelines, monitoreo y alertas | Aprobar despliegues y controlar degradación |
| Investigación | Revisar literatura, replicar métodos y generar informes | Verificar evidencia, reproducibilidad y conclusiones |

El informe *State of Analytics Engineering 2026* de dbt Labs aporta una referencia cuantitativa: el 72 % de los encuestados prioriza programación asistida por IA, pero solamente el 24 % prioriza su aplicación a la gestión de pipelines, pruebas, observabilidad y controles de calidad. Es una señal de que la generación de código está avanzando más rápido que los mecanismos de validación.

**Fuente mencionada:** dbt Labs.

### Herramientas y prácticas

#### MLflow — Experimentación, trazabilidad y evaluación

Registra experimentos de ML y, con sus capacidades GenAI, permite rastrear ejecuciones de agentes, llamadas a herramientas, salidas y métricas de evaluación. Es especialmente interesante por ser open source y poder ejecutarse sobre infraestructura propia.

**Fuentes mencionadas:** MLflow AI Platform y documentación de tracing.

#### dbt — Analytics engineering

Permite estructurar transformaciones SQL, dependencias, pruebas y documentación dentro de proyectos versionables. Los agentes pueden participar en la construcción y mantenimiento de estos activos, sujetos a sus validaciones.

**Fuente mencionada:** documentación de dbt.

#### Databricks — Plataforma integrada de datos y ML

Integra herramientas de preparación de datos, notebooks, procesamiento distribuido, experimentación, gobernanza y evaluación de agentes. Su documentación describe flujos que combinan asistentes, ingeniería de características y entrenamiento.

**Fuentes mencionadas:** Databricks, evaluación y monitoreo.

También se investiga la automatización completa de tareas científicas. El benchmark académico DSAgentBench (EMNLP 2026) evalúa agentes sobre 275 tareas que requieren interacción con entornos informáticos y herramientas de análisis. El estudio encuentra limitaciones importantes para completar de forma autónoma procesos integrales de ciencia de datos.

**Fuente mencionada:** ACL Anthology.

Por eso, para un data scientist avanzado, saber utilizar un agente es solo una parte de la capacidad profesional. Diseñar una evaluación rigurosa, detectar resultados engañosos y garantizar reproducibilidad siguen siendo capacidades decisivas.

## 6. Tecnologías que conforman un entorno de ingeniería de vanguardia

Los LLM son solamente una parte. La capacidad de un equipo depende también de la infraestructura que rodea al modelo.

| Capa | Tecnologías y prácticas relevantes |
|---|---|
| Agentes de programación | Claude Code, Codex, GitHub Copilot, OpenCode, OpenHands |
| Contexto persistente | AGENTS.md, CLAUDE.md, instrucciones por repositorio, documentación de arquitectura |
| Herramientas externas | MCP, CLI, SDK, APIs, herramientas propias |
| Orquestación | Symphony, LangGraph, Temporal, agentes especializados |
| Evaluación | Pytest, pruebas de integración, property-based testing, MLflow Evals, evaluaciones propias |
| Observabilidad | OpenTelemetry, MLflow Tracing, LangSmith |
| Entornos de ejecución | Contenedores, sandboxes, worktrees, entornos efímeros de CI |
| Calidad y seguridad | Análisis estático, escaneo de dependencias, controles de acceso, aprobación humana |
| Datos y ML | dbt, MLflow, pipelines versionados, catálogos de datos, registros de modelos |
| Infraestructura | CI/CD, infraestructura como código, despliegue progresivo, rollback |

Algunas tecnologías merecen especial atención.

### Context engineering

La ingeniería de contexto consiste en seleccionar y estructurar la información que recibe el agente para ejecutar una tarea.

Por ejemplo, un repositorio puede incluir un AGENTS.md que explique la arquitectura, las convenciones, cómo ejecutar pruebas y qué operaciones están prohibidas.

GitHub documenta el uso de archivos de instrucciones para personalizar el comportamiento de agentes. Thoughtworks también publicó una investigación específica sobre *Context Engineering for Coding Agents* en febrero de 2026.

**Fuentes mencionadas:** GitHub Docs y *Context Engineering for Coding Agents*.

### MCP y comunicación entre agentes

#### Model Context Protocol (MCP)

Facilita que agentes accedan a herramientas y fuentes de datos mediante interfaces comunes. La especificación publicada el 28 de julio de 2026 incorpora mejoras de autorización, enrutamiento y funcionamiento sin estado.

**Fuente mencionada:** Model Context Protocol Blog.

#### Agent2Agent (A2A)

Define una forma de comunicación entre aplicaciones de agentes potencialmente desarrolladas con diferentes frameworks y proveedores.

**Fuente mencionada:** A2A Protocol.

MCP conecta agentes con herramientas y datos; A2A aborda la interoperabilidad entre agentes. Son capacidades complementarias.

### Orquestación duradera

Una diferencia entre una demostración y un sistema de producción es qué sucede cuando un agente falla a mitad de un proceso.

Temporal ofrece mecanismos de ejecución duradera para reanudar workflows después de fallos, administrar esperas de aprobación y recuperar procesos largos.

**Fuentes mencionadas:** Temporal Documentation y *Temporal: Durable AI*.

### Evaluación continua

Los agentes que producen resultados variables necesitan evaluaciones especializadas. En un sistema avanzado se estudian la exactitud, los errores, las acciones ejecutadas, el tiempo, el costo y el cumplimiento de restricciones.

El estudio *State of Agent Engineering*, publicado por LangChain en junio de 2026 y basado en más de 1.300 profesionales encuestados, encontró que el 89 % de los participantes utilizaba alguna forma de observabilidad, frente a un 52 % que había implementado evaluaciones. La muestra corresponde a participantes del ecosistema de agentes y no representa necesariamente a toda la industria.

**Fuente mencionada:** LangChain.

## 7. Cómo cambia el trabajo según el entorno profesional

La organización influye mucho en qué nivel de automatización resulta conveniente.

| Entorno | Organización del trabajo y uso de agentes |
|---|---|
| Grandes empresas | Integración con repositorios corporativos, controles de acceso, CI/CD, revisiones, observabilidad y operaciones. El control del riesgo es determinante. |
| Proyectos open source grandes | Contribuciones trazables, políticas de IA, tests reproducibles, revisión de mantenedores y responsabilidad humana. |
| Startups | Prototipos, desarrollo de funcionalidades, experimentos de producto y automatización de tareas repetitivas. La prioridad suele ser validar valor rápidamente. |
| Freelance | Un profesional puede utilizar agentes para investigación, implementación, pruebas y documentación, dedicando más atención a requisitos, comunicación y entrega. |
| Investigación y ciencia de datos | Automatización de experimentos y pipelines, preservando controles metodológicos, reproducibilidad y evaluación independiente. |

Esta tabla es una síntesis práctica de los modelos de trabajo, no una encuesta que afirme que todos los profesionales de cada categoría trabajan igual.

### ¿Cómo trabajaría un profesional independiente muy avanzado?

Por ejemplo, ante el desarrollo de una aplicación para un cliente, podría convertir los requisitos en una especificación verificable, delegar investigaciones sobre dependencias, encargar al agente la implementación de un módulo y utilizar otro proceso para crear pruebas y buscar defectos.

Mientras eso ocurre, el profesional puede trabajar sobre un segundo módulo o verificar los resultados anteriores. El objetivo es mantener varias actividades productivas en curso, siempre que no aumenten demasiado los conflictos ni el esfuerzo de revisión.

La habilidad central deja de ser exclusivamente escribir código rápido. Se vuelve importante seleccionar tareas delegables, controlar dependencias, establecer buenos criterios de aceptación y detectar errores antes de entregar.

En una startup pequeña, ese mismo profesional podría incorporar experimentos de producto, análisis de métricas y automatización de operaciones. En una empresa grande, tendría que integrar además las políticas corporativas de seguridad, despliegue y auditoría.

## 8. ¿Qué evidencia tenemos sobre productividad real?

Este punto es esencial para distinguir el estado del arte de las afirmaciones comerciales.

| Investigación | Evidencia y limitaciones |
|---|---|
| Microsoft Research, 2025 | Tres experimentos de campo con 4.867 desarrolladores encontraron un incremento combinado del 26,08 % en tareas completadas utilizando asistentes de código. Evaluaban principalmente asistencia, no orquestación autónoma avanzada. |
| METR, 2025 | Experimento controlado: los desarrolladores experimentados tardaron un 19 % más utilizando herramientas de IA de comienzos de 2025 en repositorios que conocían. |
| DORA / Google, 2025 | Investigación sobre casi 5.000 profesionales: la IA actúa como amplificador de las capacidades y problemas existentes en las organizaciones. |
| Anthropic Research, junio de 2026 | Estudio de unas 400.000 sesiones de Claude Code: los usuarios suelen tomar más decisiones de planificación y los agentes más decisiones de ejecución. La experiencia en el dominio se asocia con mejores resultados. |
| METR, febrero de 2026 | La continuación del experimento encontró dificultades metodológicas por la selección de participantes y no produjo una estimación confiable del efecto actual de las herramientas. |

Estas investigaciones miden cosas distintas: tareas completadas, tiempo empleado, patrones de uso y desempeño organizacional.

No sería correcto concluir que todos los agentes aumentan la productividad un porcentaje determinado.

Incluso los benchmarks de código necesitan una lectura crítica. En 2026 se identificaron problemas importantes en SWE-bench Verified y SWE-bench Pro, lo que impulsó revisiones y nuevas versiones de evaluación.

**Fuente mencionada:** Epoch AI.

La medida más útil para un equipo real es el trabajo correcto y mantenible que consigue entregar por unidad de tiempo, costo y riesgo, considerando también las tareas de revisión y corrección.

## 9. Seguridad: una condición para trabajar con autonomía real

En agentes que acceden a repositorios, terminales, bases de datos y servicios, los riesgos ya no se limitan a respuestas incorrectas.

Un agente puede ejecutar operaciones destructivas, filtrar secretos o procesar instrucciones maliciosas introducidas en una issue, documento o herramienta externa.

OWASP publicó durante 2026 análisis de ataques e investigaciones donde entradas manipuladas y privilegios excesivos permitieron abusos en workflows con agentes.

Por eso, un flujo de producción debe contemplar permisos mínimos, credenciales acotadas, aislamiento, límites de ejecución, registro de acciones, validación de entradas y aprobaciones para operaciones de alto impacto.

**Fuentes mencionadas:** OWASP Gen AI Security Project, *Excessive Agency* y materiales de seguridad y gobernanza de agentes de 2026.

## 10. Qué estudiaría para trabajar en ese nivel

Hay una distinción útil de Martin Fowler: en mayo de 2026 diferenció *vibe coding* —generar software mediante indicaciones sin preocuparse necesariamente por inspeccionar el código— de *agentic engineering*, donde los ingenieros siguen siendo responsables del comportamiento y la calidad del software y evalúan el trabajo de los agentes.

Para adquirir capacidades de ingeniería avanzada, organizaría el aprendizaje alrededor de estos dominios:

### Ingeniería de agentes

Dominio de herramientas de terminal, administración de contexto, delegación de tareas, herramientas especializadas, integración con APIs y límites de ejecución.

### Ingeniería de software y plataformas

Arquitectura, Git, automatización, pruebas, integración continua, contenedores, infraestructura, observabilidad y revisión de código.

### Ingeniería experimental

Benchmarks propios, hipótesis, evaluación automatizada, estudios de errores, comparación de modelos y análisis de costos.

### Seguridad, gobernanza y confiabilidad

Sandboxing, aislamiento, autorización, auditoría, protección de datos, controles ante prompt injection y recuperación ante fallos.

### Ingeniería de producto y dominio

Comprender necesidades reales, convertirlas en requisitos precisos, desarrollar soluciones mantenibles y evaluar resultados tangibles.

### Un experimento concreto de ingeniería avanzada

Para ponerlo a prueba, propondría utilizar un proyecto real de tamaño moderado y comparar tres modalidades de desarrollo en tareas similares.

**Diseñar una comparación reproducible:** seleccionar las modalidades a comparar. El experimento debe usar tareas equivalentes, condiciones documentadas y criterios definidos antes de ejecutarlo.

- [x] **Asistido:** desarrollador con LLM para consultas y sugerencias.
- [x] **Agente individual:** agente que implementa y ejecuta pruebas bajo supervisión.
- [x] **Agentes coordinados:** planificación, ejecución y revisión con contextos separados.
- **Cantidad de tareas por modalidad:** 6.
- [x] Registrar costo de modelos e infraestructura.

Este tipo de estudio permite aprender a utilizar agentes y, al mismo tiempo, investigar si realmente aportan valor frente a otros métodos de ingeniería.

## 11. Referencias que priorizaría para profundizar

Seleccioné publicaciones con evidencia, documentación operativa o experiencias directas de equipos reales.

- **Agentic Engineering — Martin Fowler.** Mayo de 2026. Marco conceptual para comprender el cambio de responsabilidades del ingeniero.
- **Harness Engineering — OpenAI.** Febrero de 2026. Caso profundo de diseño de repositorios, herramientas, verificaciones y agentes.
- **Symphony — OpenAI.** Abril de 2026. Orquestación de agentes integrada con tableros de trabajo.
- **DORA: State of AI-assisted Software Development — Google.** 2025. Investigación sobre desempeño, prácticas de equipo y adopción de IA. Incluye versión resumida en español latinoamericano.
- **Agentic Coding and Persistent Returns to Expertise — Anthropic Research.** Junio de 2026. Estudio de uso real que investiga cómo se reparten las decisiones entre profesionales y agentes.
- **Open Source Maintainership in the Age of AI — Kubernetes.** Junio de 2026. Caso de gobernanza y revisión de contribuciones asistidas por agentes.
- **State of Analytics Engineering 2026 — dbt Labs.** Panorama específico de prácticas de datos, adopción y calidad.

## Conclusión

A octubre de 2026, la frontera del trabajo profesional está en la combinación de agentes capaces de ejecutar tareas complejas e infraestructura de ingeniería que permita controlar, verificar y mantener sus resultados.

Los casos de OpenAI muestran hasta dónde puede llegar un equipo que diseña su organización alrededor de agentes. Kubernetes ilustra cómo un gran ecosistema open source equilibra esas capacidades con responsabilidad humana. Los estudios académicos muestran que todavía existen diferencias considerables entre herramientas, tareas y condiciones de uso.

Para alguien que busca dominar la ingeniería de software, la ciencia de datos y la IA al máximo nivel, investigaría especialmente tres temas: harness engineering, orquestación de agentes y evaluación reproducible de su desempeño. Son líneas que permiten construir productos reales, participar en proyectos exigentes y también producir investigación técnica verificable.

Y hay una idea que atraviesa todas las referencias: la capacidad de generar código se está abaratando; la capacidad de definir correctamente un problema y demostrar que una solución funciona sigue siendo extraordinariamente valiosa.
