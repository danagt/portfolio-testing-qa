# BUG-002 — El campo de contraseña acepta espacios en blanco

**Módulo:** Registro de usuarios — Talento Lab  
**Caso relacionado:** TC-006  
**Prioridad:** Alta  
**Severidad:** Media  
**Estado registrado en la planilla:** Abierto/Asignado

## Descripción

Durante la validación de contraseñas, el formulario permitió continuar con una contraseña que contenía un **espacio en blanco**, incumpliendo la regla que prohíbe espacios.

## Entorno documentado

- Sistema operativo: Linux Mint 22.3 MATE (64 bits).
- Navegador: Google Chrome 153.0.
- Ambiente: Test.
- Aplicación: https://talento-lab-test-web.netlify.app/register

## Precondiciones

- Estar en la página de registro.
- Disponer de un correo de prueba no registrado previamente.
- Tener un archivo CV PDF válido de 2 MB.

## Pasos para reproducir

1. Abrir el formulario de registro.
2. Completar Nombre y Apellido con datos válidos.
3. Ingresar un correo válido y no registrado.
4. Introducir la contraseña de ejemplo `Qa 123456` (con un espacio).
5. Adjuntar un CV válido.
6. Aceptar los Términos y Condiciones.
7. Hacer clic en **Registrarse**.

## Resultado esperado

El sistema debe rechazar la contraseña e informar que **no se permiten espacios en blanco**.

## Resultado obtenido (registrado en la planilla)

El sistema aceptó la contraseña con espacio en blanco y permitió continuar con el registro.

## Evidencia

La planilla refiere a una captura relacionada con TC-006. **Pendiente de incorporar una copia anonimizada**.

## Técnica utilizada

Partición de equivalencia inválida: contraseña que contiene un espacio no permitido.
