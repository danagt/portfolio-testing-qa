# Informe final de Testing QA – Talento Lab

## 1. Resumen ejecutivo

Se realizaron pruebas funcionales sobre el formulario de registro de usuarios de Talento Lab, con el objetivo de verificar el cumplimiento de los requisitos y criterios de aceptación definidos.

Se diseñaron y ejecutaron ocho casos de prueba, aplicando técnicas de caja negra, partición de equivalencia y análisis de valores límite.

Los resultados fueron:

| Indicador | Resultado |
|---|---:|
| Casos diseñados | 8 |
| Casos ejecutados | 8 |
| Casos aprobados | 6 |
| Casos fallidos | 2 |
| Casos bloqueados | 0 |
| Cobertura de ejecución | 100% |
| Tasa de aprobación | 75% |
| Tasa de fallos | 25% |

## 2. Estrategia de pruebas

**Tipo de testing:** funcional manual.

**Alcance:** validación del formulario de registro, campos obligatorios, reglas de contraseña, correo electrónico duplicado y carga de archivos CV.

**Técnicas utilizadas:**
- Partición de equivalencia.
- Análisis de valores límite.
- Pruebas positivas y negativas.

**Herramientas:** Jira, Zephyr Essential, Google Sheets y Google Chrome.

**Ambiente:** Test, sobre Linux Mint 22.3 MATE y Google Chrome.

## 3. Gestión de defectos

Durante las pruebas se identificaron dos defectos:

**BUG-001 – Registro con contraseña de 7 caracteres**

- Severidad: Alta.
- Prioridad: Alta.
- Resultado observado: el sistema permite el registro con una contraseña inferior al mínimo requerido de ocho caracteres.

**BUG-002 – Contraseña con espacios en blanco**

- Severidad: Media.
- Prioridad: Alta.
- Resultado observado: el sistema acepta una contraseña que contiene espacios en blanco, incumpliendo la regla establecida.

Ambos defectos figuran como Abierto/Asignado en la planilla de seguimiento utilizada para este informe.

## 4. Análisis de riesgos

La matriz de riesgo registra:

| Categoría | Cantidad |
|---|---:|
| Críticos | 0 |
| Mayores | 1 |
| Menores / Estéticos | 1 |

Aunque la cobertura de ejecución alcanzó el 100%, la existencia de un defecto de severidad Alta incumple la regla establecida para autorizar el lanzamiento.

La ejecución completa de los casos de prueba no implica que el producto esté libre de defectos.

## 5. Recomendación de lanzamiento

**Veredicto profesional: NO-GO.**

Se recomienda no autorizar la salida a producción del módulo en las condiciones evaluadas.

Esta decisión se fundamenta en la existencia de un defecto de severidad Alta que afecta las reglas de validación de contraseñas.

Se recomienda corregir los defectos identificados, volver a ejecutar los casos afectados y realizar pruebas de regresión antes de reconsiderar el lanzamiento.

La decisión final corresponde a los responsables del proyecto, considerando los riesgos documentados.

## 6. Conclusión

La práctica permitió aplicar el proceso de Testing QA desde el análisis de requerimientos y el diseño de casos hasta la ejecución, identificación de defectos, elaboración de métricas y comunicación de resultados.

El proyecto demuestra la importancia de fundamentar las decisiones de calidad en evidencias verificables y criterios de aceptación previamente definidos.

## 7. Documentación complementaria

- [Casos de prueba](../01-casos-de-prueba/README.md)
- [Reportes de bugs](../02-reportes-de-bugs/README.md)
- [Evidencias de ejecución en Zephyr](../03-evidencias-zephyr/README.md)
- [Métricas y cobertura](../04-metricas/README.md)

---

**Proyecto:** Talento Lab – Testing funcional del formulario de registro.

**Formación:** Talento Tech – Testing QA.

**Estado:** Informe de cierre elaborado a partir de las ejecuciones y defectos documentados.
