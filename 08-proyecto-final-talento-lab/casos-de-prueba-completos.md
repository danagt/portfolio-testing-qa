# Talento Lab — Casos de prueba completos

**Proyecto:** Testing QA – Registro de usuarios de Talento Lab  
**Fuente:** hoja `TCs` de *Testing QA - Plantilla TC Dana Grecco*  
**Técnicas:** pruebas funcionales, partición de equivalencia, análisis de valores límite (BVA)  
**Gestión:** Jira / Zephyr Essential

> **Nota de trazabilidad:** los estados de este documento proceden de la columna «Estado» de la planilla original. Representan las ejecuciones manuales registradas allí; **no son una exportación ni una comprobación de estados del ciclo de Zephyr**. Los datos de personas, correos y contraseñas han sido reemplazados por referencias ficticias para publicación pública. Las evidencias se mencionan tal como figuran en la planilla, pero no se adjuntan aquí.

## Resumen de resultados documentados en la planilla

| ID de diseño | Caso Zephyr | Escenario | Prioridad | Severidad consignada | Estado documentado |
| --- | --- | --- | --- | --- | --- |
| TC-001 | TL-T2 | Registro exitoso con CV PDF de 2 MB | Alta | Alta | Pasado/Exitoso |
| TC-002 | TL-T3 | Contraseña de 7 caracteres | Alta | Media | Fallido (BUG-001) |
| TC-003 | TL-T4 | CV PDF de 5,01 MB | Alta | Media | Pasado/Exitoso |
| TC-004 | TL-T5 | Correo ya registrado | Alta | Media | Pasado/Exitoso |
| TC-005 | TL-T6 | Apellido obligatorio vacío | Media | Media | Pasado/Exitoso |
| TC-006 | TL-T7 | Contraseña con espacio | Alta | Media | Fallido (BUG-002) |
| TC-007 | TL-T8 | Registro sin CV | Alta | Alta | Pasado/Exitoso |
| TC-008 | TL-T9 | CV PDF de exactamente 5,00 MB | Alta | Media | Pasado/Exitoso |

**Resultado según la hoja TCs:** 8 casos con resultado registrado: **6 exitosos y 2 fallidos**. La planilla registra esos resultados; no se han comprobado mediante capturas de ejecución en este archivo.

**Entorno reportado:** Linux Mint 22.3 MATE de 64 bits; Google Chrome; ambiente Test.  
**Aplicación bajo prueba:** https://talento-lab-test-web.netlify.app/register

## TC-001 / TL-T2 — Registro exitoso con datos válidos y CV PDF de 2 MB

**Objetivo:** comprobar el registro exitoso con información válida y un archivo admitido.  
**Precondiciones:** navegador abierto en el formulario; correo de prueba nuevo; archivo PDF de 2 MB disponible.  
**Datos de prueba públicos:** nombre y apellido ficticios; correo único de prueba; contraseña válida; `CV_prueba_2MB.pdf`.

**Pasos:**
1. Abrir el formulario de registro.
2. Completar Nombre.
3. Completar Apellido.
4. Completar Email.
5. Completar Contraseña.
6. Cargar un CV PDF de 2 MB.
7. Aceptar Términos y Condiciones.
8. Hacer clic en «Registrarse».

**Esperado:** registro completado sin errores.  
**Observado según la hoja:** se completó el registro y no aparecieron errores.  
**Estado documentado:** Pasado/Exitoso. **Evidencia:** la hoja indica que no se adjuntó evidencia.

## TC-002 / TL-T3 — Contraseña de 7 caracteres (límite inferior −1)

**Objetivo:** comprobar el rechazo de una contraseña menor al mínimo permitido.  
**Precondiciones:** formulario abierto; correo de prueba nuevo; CV PDF de 2 MB disponible.  
**Datos públicos:** contraseña ficticia de **7 caracteres** que cumple las demás clases requeridas; datos personales ficticios; CV PDF válido.

**Pasos:**
1. Abrir el formulario de registro.
2. Completar Nombre, Apellido y Email.
3. Ingresar la contraseña de 7 caracteres.
4. Cargar el CV.
5. Aceptar Términos y Condiciones.
6. Hacer clic en «Registrarse».

**Esperado:** mensaje de longitud permitida (8–16 caracteres), sin creación de cuenta y permanencia en el formulario.  
**Observado según la hoja:** el sistema aceptó la contraseña de 7 caracteres y creó la cuenta.  
**Estado documentado:** Fallido. **Defecto relacionado:** BUG-001. **Técnica:** BVA.

## TC-003 / TL-T4 — CV PDF de 5,01 MB

**Objetivo:** comprobar el rechazo de un CV que supera el límite.  
**Precondiciones:** formulario abierto; correo de prueba nuevo; PDF de 5,01 MB disponible.  
**Datos públicos:** datos válidos ficticios; `CV_prueba_5_01MB.pdf`.

**Pasos:**
1. Abrir el formulario de registro.
2. Completar Nombre, Apellido, Email y Contraseña.
3. Seleccionar el CV PDF de 5,01 MB.
4. Aceptar Términos y Condiciones.
5. Hacer clic en «Registrarse».

**Esperado:** archivo rechazado, mensaje de error, cuenta no creada, permanencia en el formulario.  
**Observado según la hoja:** CV rechazado y registro impedido.  
**Estado documentado:** Pasado/Exitoso. **Técnica:** BVA. **Evidencia:** no adjunta en la hoja.

## TC-004 / TL-T5 — Registro con correo ya existente

**Objetivo:** comprobar la validación de duplicados.  
**Precondiciones:** una cuenta con el correo de prueba ya debe existir; formulario abierto; CV PDF válido disponible.  
**Datos públicos:** correo ficticio previamente registrado; datos personales ficticios; contraseña válida; CV PDF de 2 MB.

**Pasos:**
1. Abrir el formulario de registro.
2. Completar Nombre, Apellido y un Email ya registrado.
3. Completar Contraseña.
4. Cargar el CV.
5. Aceptar Términos y Condiciones.
6. Hacer clic en «Registrarse».

**Esperado:** mensaje «Este email ya está en uso», enlace al inicio de sesión y ninguna cuenta nueva.  
**Observado según la hoja:** se detectó el email duplicado, se presentó el mensaje y no se creó una cuenta.  
**Estado documentado:** Pasado/Exitoso. **Evidencia:** no adjunta.  
**Nota de consistencia:** en la planilla original, el correo citado en la precondición y en el resultado obtenido no coincide exactamente con el que figura en «Datos de Prueba». Antes de repetir este caso, unificar el correo de referencia.

## TC-005 / TL-T6 — Campo obligatorio Apellido vacío

**Objetivo:** verificar la obligatoriedad del apellido.  
**Precondiciones:** formulario abierto, correo de prueba nuevo, CV PDF válido.  
**Datos públicos:** nombre ficticio, apellido vacío, correo nuevo de prueba, contraseña válida y CV PDF de 2 MB.

**Pasos:**
1. Abrir el formulario de registro.
2. Completar Nombre y dejar Apellido vacío.
3. Completar Email y Contraseña.
4. Cargar el CV.
5. Aceptar Términos y Condiciones.
6. Hacer clic en «Registrarse».

**Esperado:** indicación de que Apellido es obligatorio, sin crear cuenta.  
**Observado según la hoja:** el sistema validó el campo vacío e impidió el registro.  
**Estado documentado:** Pasado/Exitoso. **Evidencia:** no adjunta.

## TC-006 / TL-T7 — Contraseña con espacio en blanco

**Objetivo:** comprobar el rechazo de contraseñas con espacios.  
**Precondiciones:** formulario abierto, correo de prueba nuevo y CV válido.  
**Datos públicos:** contraseña de prueba con un espacio interior; identidad ficticia; CV de 2 MB.

**Pasos:**
1. Abrir el formulario de registro.
2. Completar Nombre y Apellido.
3. Ingresar un Email válido.
4. Ingresar una contraseña que contenga un espacio.
5. Cargar un CV válido.
6. Aceptar Términos y Condiciones.
7. Hacer clic en «Registrarse».

**Esperado:** rechazo de la contraseña e información de que no se permiten espacios en blanco.  
**Observado según la hoja:** el sistema aceptó la contraseña con espacio y permitió continuar.  
**Estado documentado:** Fallido. **Defecto relacionado:** BUG-002. **Técnica:** partición de equivalencia inválida.

## TC-007 / TL-T8 — Registro sin CV adjunto

**Objetivo:** verificar que el CV sea obligatorio.  
**Precondiciones:** formulario abierto y correo nuevo de prueba.  
**Datos públicos:** datos personales ficticios y válidos; **ningún archivo CV**.

**Pasos:**
1. Abrir el formulario de registro.
2. Completar Nombre y Apellido.
3. Ingresar Email válido.
4. Ingresar Contraseña válida.
5. No adjuntar ningún CV.
6. Aceptar Términos y Condiciones.
7. Hacer clic en «Registrarse».

**Esperado:** impedir registro, informar que el CV es obligatorio, no crear cuenta.  
**Observado según la hoja:** se bloqueó el registro sin CV y se mostró validación.  
**Estado documentado:** Pasado/Exitoso. **Evidencia:** no adjunta.

## TC-008 / TL-T9 — CV PDF de exactamente 5,00 MB

**Objetivo:** comprobar el rechazo del límite superior exacto.  
**Precondiciones:** formulario abierto; correo nuevo; archivo PDF de exactamente 5,00 MB disponible.  
**Datos públicos:** datos válidos ficticios; `CV_prueba_5MB.pdf` de exactamente 5,00 MB.

**Pasos:**
1. Abrir el formulario de registro.
2. Completar Nombre y Apellido.
3. Ingresar Email válido.
4. Ingresar Contraseña válida.
5. Cargar el CV PDF de exactamente 5,00 MB.
6. Aceptar Términos y Condiciones.
7. Hacer clic en «Registrarse».

**Esperado:** rechazo, mensaje de error y ninguna cuenta creada.  
**Observado según la hoja:** el archivo se rechazó y el registro no se completó.  
**Estado documentado:** Pasado/Exitoso. **Técnica:** BVA. **Evidencia:** no adjunta.

**Regla de negocio confirmada por el Product Owner:** el archivo debe pesar **estrictamente menos de 5 MB**; por ello un archivo de 5,00 MB se rechaza.

---

## Próximos pasos de documentación
- Incorporar capturas de los bugs únicamente después de anonimizar su contenido.
- Publicar exportaciones y métricas del ciclo Zephyr cuando estén disponibles y verificadas.
- Conservar una distinción explícita entre resultados documentados en la planilla y resultados confirmados desde Zephyr.
