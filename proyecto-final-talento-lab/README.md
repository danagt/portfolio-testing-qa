
# Talento Lab — Testing funcional del formulario de registro

## Contexto
Práctica de testing funcional del formulario de registro de usuarios en Talento Lab, realizada durante la formación en Testing QA de Talento Tech.

**Aplicación bajo prueba:** https://talento-lab-test-web.netlify.app/register

## Objetivo
Verificar reglas de registro, campos obligatorios, validaciones de contraseña y requisitos de carga del CV, a partir de criterios de aceptación.

## Alcance de los casos diseñados
Se diseñaron e importaron **8 casos de prueba** en Zephyr Essential:

| Caso | Escenario |
| --- | --- |
| TL-T2 | Registro exitoso con datos válidos y CV PDF de 2 MB |
| TL-T3 | Contraseña de 7 caracteres: límite inferior inválido |
| TL-T4 | CV PDF de 5,01 MB: tamaño inválido |
| TL-T5 | Registro con correo ya existente |
| TL-T6 | Campo Apellido obligatorio vacío |
| TL-T7 | Contraseña con espacio en blanco |
| TL-T8 | Registro sin CV adjunto |
| TL-T9 | CV PDF de exactamente 5,00 MB: límite superior inválido |

**Criterio confirmado por el Product Owner:** el CV debe pesar **estrictamente menos de 5 MB**. Un archivo de exactamente 5,00 MB se debe rechazar.

## Técnicas y herramientas
- Partición de equivalencia y análisis de valores límite (EP/BVA).
- Pruebas funcionales positivas y negativas.
- Jira y Zephyr Essential para casos, ciclos y seguimiento.
- Google Sheets para matriz de cobertura y riesgo.
- Chrome DevTools para inspección y pruebas responsive.

## Avance del proyecto

- [x] Análisis de requisitos y criterios de aceptación.
- [x] Diseño de ocho casos de prueba.
- [x] Importación y revisión de casos en Zephyr Essential.
- [x] Ejecución de los ocho casos en el ciclo TL-R1.
- [x] Documentación de dos defectos.
- [x] Elaboración de métricas de cobertura y matriz de riesgo.
- [x] Publicación de evidencias de ejecución.
- [x] Elaboración del informe final con recomendación NO-GO.

**Estado:** Proyecto de práctica documentado y con informe de cierre.

## Estado final del proyecto

El proyecto de práctica se encuentra documentado, incluyendo el diseño y ejecución de ocho casos de prueba, dos defectos identificados y el informe de cierre con recomendación NO-GO.

Los casos fueron diseñados originalmente con los identificadores TC-001 a TC-008 y posteriormente gestionados en Zephyr Essential. Las ejecuciones finales se documentaron en el proyecto T1PF.

Las evidencias, métricas y conclusiones están disponibles en las carpetas correspondientes de este repositorio.



