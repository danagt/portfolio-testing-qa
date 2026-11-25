# BUG-001 — El sistema permite registrarse con una contraseña de 7 caracteres

**Módulo:** Registro de usuarios — Talento Lab  
**Caso relacionado:** TC-002  
**Prioridad:** Alta  
**Severidad:** Alta  
**Estado registrado en la planilla:** Abierto/Asignado

## Descripción

Durante la prueba del límite inferior de longitud de contraseña, el formulario aceptó una contraseña de **7 caracteres**, a pesar de que la regla exige un mínimo de **8 caracteres**.

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
3. Ingresar un correo de prueba no registrado.
4. Introducir la contraseña de ejemplo `Qa12345` (7 caracteres).
5. Adjuntar un CV PDF válido.
6. Aceptar los Términos y Condiciones.
7. Hacer clic en **Registrarse**.

## Resultado esperado

El sistema debe rechazar la contraseña por tener menos de 8 caracteres, mostrar el mensaje de validación correspondiente, no crear la cuenta y permanecer en el formulario de registro.

## Resultado obtenido (registrado en la planilla)

El sistema aceptó la contraseña de 7 caracteres y permitió completar el registro, creando la cuenta.

## Evidencia

La planilla hace referencia a una captura correspondiente a TC-002. **Pendiente de incorporar una copia anonimizada**.

## Técnica utilizada

Análisis de valores límite (BVA): 7 caracteres frente a un mínimo permitido de 8.
