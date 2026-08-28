# 09 — Casos de prueba

Matriz de casos de prueba funcionales para STAGING.

**Cómo usar**: copia este archivo o crea una rama propia; completa la columna **RESULTADO**
con `PASS`, `FAIL`, `BLOCKED_EXTERNAL` o `NOT_APPLICABLE` y agrega observaciones.

> El analista puede editar una copia propia de este documento sin modificar el original.

| ID | MÓDULO | ROL | CASO | EXPECTED | RESULTADO | OBSERVACIONES |
|---|---|---|---|---|---|---|
| AUTH-01 | Autenticación | Ciudadano | Login con credenciales DEMO correctas | Acceso al portal | ⬜ PENDIENTE ANALISTA | |
| AUTH-02 | Autenticación | Ciudadano | Login con contraseña incorrecta | Error de credenciales, sin acceso | ⬜ PENDIENTE ANALISTA | |
| AUTH-03 | Autenticación | Funcionario | Login Workforce con CURP+password DEMO | Acceso según rol | ⬜ PENDIENTE ANALISTA | |
| AUTH-04 | Autenticación | Cajero | Login caja DEMO | Pantalla de caja | ⬜ PENDIENTE ANALISTA | |
| AUTH-05 | Autenticación | Todos | Cerrar sesión | Regreso al login, sin sesión residual | ⬜ PENDIENTE ANALISTA | |
| CIU-01 | Ciudadano | Ciudadano | Iniciar trámite desde el portal | Formulario de trámite | ⬜ PENDIENTE ANALISTA | |
| CIU-02 | Ciudadano | Ciudadano | Capturar información del trámite | Datos guardados correctamente | ⬜ PENDIENTE ANALISTA | |
| CIU-03 | Ciudadano | Ciudadano | Cargar documento obligatorio | Documento subido y marcado | ⬜ PENDIENTE ANALISTA | |
| CIU-04 | Ciudadano | Ciudadano | Enviar trámite | Folio asignado; estado enviado | ⬜ PENDIENTE ANALISTA | |
| CIU-05 | Ciudadano | Ciudadano | Ver seguimiento (timeline) | Fases y eventos visibles | ⬜ PENDIENTE ANALISTA | |
| CIU-06 | Ciudadano | Ciudadano | Consultar estatus | Estado/fase correctos | ⬜ PENDIENTE ANALISTA | |
| CIU-07 | Ciudadano | Ciudadano | Ver orden de pago | Número, referencia, monto | ⬜ PENDIENTE ANALISTA | |
| CIU-08 | Ciudadano | Ciudadano | Ver recibo | Recibo descargable | ⬜ PENDIENTE ANALISTA | |
| CIU-09 | Ciudadano | Ciudadano | Ver resolución | Número y documento | ⬜ PENDIENTE ANALISTA | |
| EXP-01 | Expediente | Ciudadano | Consultar expediente propio | Documentos propios visibles | ⬜ PENDIENTE ANALISTA | |
| EXP-02 | Expediente | Ciudadano | Cargar documento faltante | Estado pasa a "Cargado" | ⬜ PENDIENTE ANALISTA | |
| EXP-03 | Expediente | Funcionario | Ver documentos del trámite | Documentos con estado de validación | ⬜ PENDIENTE ANALISTA | |
| EXP-04 | Expediente | Funcionario | Validar documento | Estado VALIDADO | ⬜ PENDIENTE ANALISTA | |
| EXP-05 | Expediente | Ciudadano | Ver documento (PDF) | PDF abre correctamente | ⬜ PENDIENTE ANALISTA | |
| CAT-01 | Catastro | Funcionario | Consultar predio por clave | Datos del predio | ⬜ PENDIENTE ANALISTA | |
| PAG-01 | Pagos | Funcionario | Generar orden de pago | Orden emitida (Pending) | ⬜ PENDIENTE ANALISTA | |
| PAG-02 | Pagos | Funcionario | Ver estado de orden | Estado reflejado correctamente | ⬜ PENDIENTE ANALISTA | |
| PAG-03 | Pagos | Caja | Buscar orden pendiente | Orden localizada | ⬜ PENDIENTE ANALISTA | |
| CAJ-01 | Caja | Cajero | Abrir turno | TURNO ABIERTO | ⬜ PENDIENTE ANALISTA | |
| CAJ-02 | Caja | Cajero | Cobrar orden DEMO | Orden pasa a Pagado; comprobante | ⬜ PENDIENTE ANALISTA | |
| CAJ-03 | Caja | Cajero | Reimprimir comprobante | Comprobante reimpreso | ⬜ PENDIENTE ANALISTA | |
| CAJ-04 | Caja | Cajero | Consultar orden ya pagada | Mensaje ORDEN YA PAGADA | ⬜ PENDIENTE ANALISTA | |
| RES-01 | Resolución | Funcionario | Emitir resolución (Administrator) | Resolución emitida | ⬜ PENDIENTE ANALISTA | |
| RES-02 | Resolución | Funcionario | Ver resolución del trámite | Número y documento | ⬜ PENDIENTE ANALISTA | |
| NOT-01 | Notificaciones | Funcionario | Ver historial de avisos | Eventos listados con fecha | ⬜ PENDIENTE ANALISTA | |
| NOT-02 | Notificaciones | Ciudadano | Ver avisos en actividad del trámite | Eventos visibles | ⬜ PENDIENTE ANALISTA | |
| NOT-03 | Notificaciones | — | Push móvil | (ver nota) | ⬜ BLOCKED_EXTERNAL | APNs/FCM/SNS sin configurar |
| ROL-01 | Roles | Funcionario | Viewer intenta modificar | Bloqueado | ⬜ PENDIENTE ANALISTA | |
| ROL-02 | Roles | Funcionario | Capturist accede a administración | Bloqueado | ⬜ PENDIENTE ANALISTA | |
| AIS-01 | Aislamiento | Ciudadano | Ver trámite de otro ciudadano | Negado | ⬜ PENDIENTE ANALISTA | |
| AIS-02 | Aislamiento | Ciudadano | Ver expediente ajeno | Negado | ⬜ PENDIENTE ANALISTA | |
| ERR-01 | Errores | Todos | Sesión expirada en endpoint protegido | 401, redirección a login | ⬜ PENDIENTE ANALISTA | |
| ERR-02 | Errores | Todos | M2M con token inválido | 401 | ⬜ PENDIENTE ANALISTA | |
| ERR-03 | Errores | Ciudadano | Trámite inexistente en URL | 404 / mensaje de no encontrado | ⬜ PENDIENTE ANALISTA | |
