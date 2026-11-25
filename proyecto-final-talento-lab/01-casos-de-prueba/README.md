# Casos de prueba — Talento Lab

## Objetivo

Documentar el diseño de pruebas funcionales para el formulario de registro de Talento Lab, utilizando escenarios positivos y negativos, partición de equivalencia y análisis de valores límite (BVA).

**Aplicación bajo prueba:** https://talento-lab-test-web.netlify.app/register  
**Herramientas de gestión:** Jira y Zephyr Essential  
**Estado de este documento:** casos diseñados e importados; no equivale a ejecución aprobada.

## Casos diseñados

| ID en Zephyr | Escenario | Técnica principal | Resultado esperado |
| --- | --- | --- | --- |
| TL-T2 | Registro exitoso con datos válidos y CV PDF de 2 MB | Partición válida | Se completa el registro sin errores. |
| TL-T3 | Contraseña de 7 caracteres | Valor límite inferior inválido | Se rechaza la contraseña y se informa el requisito de longitud (8 a 16 caracteres). |
| TL-T4 | CV PDF de 5,01 MB | Valor límite superior inválido | Se rechaza el archivo por superar el tamaño permitido y no se crea la cuenta. |
| TL-T5 | Registro con correo ya existente | Partición inválida | Se informa que el correo ya está en uso y no se crea una cuenta duplicada. |
| TL-T6 | Campo Apellido vacío | Campo obligatorio / partición inválida | Se informa que Apellido es obligatorio y no se crea la cuenta. |
| TL-T7 | Contraseña con espacio en blanco | Partición inválida | Se rechaza la contraseña y se informa que no se permiten espacios. |
| TL-T8 | Registro sin CV | Campo obligatorio / partición inválida | Se impide el registro y se informa que el CV es obligatorio. |
| TL-T9 | CV PDF de exactamente 5,00 MB | Valor límite superior inválido | Se rechaza el archivo y se impide el registro. |

> **Criterio de aceptación aclarado por el Product Owner:** el archivo CV debe pesar **estrictamente menos de 5 MB**. Por eso 5,00 MB y 5,01 MB deben rechazarse; 4,99 MB cumple la condición de tamaño.

## Trazabilidad y alcance

Los ocho casos se importaron en la biblioteca de Zephyr Essential del proyecto de prácticas y se revisaron sus pasos y resultados esperados. El ciclo de prueba preparado es **TL-R3 — Ciclo 01: Validaciones del formulario de registro**, con ambiente **QA — Talento Lab**.

Este documento presenta el **diseño de pruebas**, no resultados de ejecución. Los estados reales (*Passed*, *Failed* o *Blocked*) deben incorporarse después de ejecutar y verificar cada caso.

## Evidencias que se incorporarán

- Exportación de casos de prueba sin datos personales sensibles.
- Capturas anonimizadas del diseño en Zephyr Essential.
- Evidencias de ejecución y reportes de defectos, una vez obtenidos.

## Protección de datos

Se utilizan datos de prueba ficticios. Antes de subir capturas o exportaciones, ocultar contraseñas, correos personales, identificadores privados, tokens y cualquier información interna no autorizada.
