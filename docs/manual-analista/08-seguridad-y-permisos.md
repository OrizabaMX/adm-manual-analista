# 08 — Seguridad y permisos

Casos mínimos de seguridad que el analista debe validar en STAGING.

> No realizar pruebas destructivas ni pentest. Validar únicamente el comportamiento esperado.

## SEC-01 — Ciudadano solo ve sus trámites

- **PASOS**: iniciar sesión como ciudadano DEMO; revisar el listado de trámites.
- **EXPECTED**: solo aparecen los trámites de su propia persona.
- **PASS/FAIL**: ________

## SEC-02 — Ciudadano no ve expediente ajeno

- **PASOS**: intentar abrir un trámite/expediente de otro ciudadano (p. ej. modificando el ID en la URL).
- **EXPECTED**: el sistema niega el acceso (no expone datos de otros).
- **PASS/FAIL**: ________

## SEC-03 — Viewer no modifica

- **PASOS**: iniciar sesión con un rol **Viewer**; intentar cambiar un estado o documento.
- **EXPECTED**: la acción está bloqueada (solo lectura).
- **PASS/FAIL**: ________

## SEC-04 — Capturist no obtiene Administrator

- **PASOS**: iniciar sesión con rol **Capturist**; revisar opciones de administración (catálogo, resoluciones).
- **EXPECTED**: no ve ni ejecuta acciones administrativas.
- **PASS/FAIL**: ________

## SEC-05 — M2M requiere token válido

- **PASOS**: llamar a un endpoint interno M2M sin token o con token inválido.
- **EXPECTED**: `401` (no autorizado); no responde datos.
- **PASS/FAIL**: ________

## SEC-06 — Token humano no sustituye M2M

- **PASOS**: usar un token de usuario humano (no M2M) contra un endpoint M2M.
- **EXPECTED**: rechazo (no se confunde el tipo de credencial).
- **PASS/FAIL**: ________

## SEC-07 — Endpoints protegidos rechazan sesión inválida

- **PASOS**: llamar a un endpoint protegido (p. ej. `/v1/requests/me`) sin sesión.
- **EXPECTED**: `401`.
- **PASS/FAIL**: ________

## SEC-08 — No se confía en personId del cliente

- **PASOS**: verificar que la identidad/persona se resuelve desde el token (issuer+subject) y no desde un campo enviado por el cliente.
- **EXPECTED**: el sistema resuelve server-side; no acepta personId arbitrario.
- **PASS/FAIL**: ________

## Resultados observados en la validación (referencia)

| Caso | Resultado |
|---|---|
| SEC-01 | PASS (el ciudadano DEMO solo ve su trámite 0000061) |
| SEC-05 | PASS (endpoints M2M sin token → 401) |
| SEC-06 | PASS (token humano/fake → 401) |
| SEC-07 | PASS (endpoints protegidos sin sesión → 401) |
