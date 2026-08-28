# 02 — Usuarios y roles

## Cuentas DEMO

Las cuentas de prueba de STAGING son sintéticas y dedicadas. **Las credenciales (usuario y
contraseña) se entregan por el responsable de pruebas mediante un canal separado** y no se
incluyen en este repositorio.

| ALIAS | TIPO | ROL | PORTAL | FINALIDAD | ESTADO |
|---|---|---|---|---|---|
| CIUDADANO_DEMO_01 | Ciudadano | Citizen | Portal ciudadano | Prueba completa del flujo ciudadano (login, trámite, seguimiento, expediente, recibo, resolución) | Activa |
| FUNCIONARIO_DEMO_01 | Funcionario | Administrator | Portal funcionarios | Atención ciudadana, revisión documental, pagos, resoluciones | Activo |
| FUNCIONARIO_DEMO_02 | Funcionario | Capturist | Portal funcionarios | Captura de trámites (sin permisos administrativos) | Activo |
| FUNCIONARIO_DEMO_03 | Funcionario | Viewer | Portal funcionarios | Consulta de solo lectura | Activo |
| CAJERO_DEMO_01 | Caja | Cashier | Caja municipal | Apertura de turno, cobro, comprobantes | Activo |

> Los datos demo visibles en el sistema (nombre de persona, CURP enmascarada, teléfono
> enmascarado) pertenecen a **personas sintéticas de prueba**, no a personas reales.

## Cuentas reales / probes

Algunas cuentas de prueba utilizadas internamente corresponden a usuarios reales de la
institución. **No se publican CURP completas ni teléfonos en este manual.**

```
REAL_PROBE_EXCLUDED_FROM_PUBLIC_TEST_MANUAL
```

Para pruebas externas se recomienda usar únicamente las **cuentas DEMO** de la tabla anterior.

## Passwords

> Las credenciales de acceso son entregadas por el responsable de pruebas mediante un canal
> separado y no forman parte del repositorio.

## Matriz de roles

Roles activos en STAGING (confirmados en la configuración de identidad):

| ROL | PORTAL | PERMISOS | RESTRICCIONES |
|---|---|---|---|
| **Citizen** | Portal ciudadano | Ver sus trámites, seguimiento, expediente propio, recibo y resolución; iniciar trámites | Solo sus propios datos; no ve datos de otros ciudadanos |
| **Administrator** | Portal funcionarios | Atención ciudadana, revisión de documentos, generación de pagos, avance de estados, resolución, catálogo | Operación completa de trámites |
| **Capturist** | Portal funcionarios | Captura de trámites, carga documental | No resuelve, no administra |
| **Viewer** | Portal funcionarios | Consulta de trámites y expedientes (solo lectura) | No modifica estados ni documentos |
| **Cashier** | Caja municipal | Apertura de turno, cobro de órdenes, comprobantes | No accede a trámites ni resoluciones |
| **KitDelivery** | Portal funcionarios | Entrega de kits/documentos | Operación limitada a entrega |

## Matriz de permisos por acción

| ACCIÓN | CIUDADANO | CAPTURISTA | ADMIN | VIEWER | CAJERO |
|---|---|---|---|---|---|
| Iniciar trámite | ✅ | ✅ | ✅ | ❌ | ❌ |
| Ver sus trámites | ✅ | ✅ | ✅ | ✅ | ❌ |
| Ver trámites de otros | ❌ | ✅ | ✅ | ✅ | ❌ |
| Cargar documentos | ✅ | ✅ | ✅ | ✅ | ❌ |
| Validar documentos | ❌ | ✅ | ✅ | ❌ | ❌ |
| Generar orden de pago | ❌ | ✅ | ✅ | ❌ | ❌ |
| Cobrar orden | ❌ | ❌ | ❌ | ❌ | ✅ |
| Emitir resolución | ❌ | ❌ | ✅ | ❌ | ❌ |
| Cambiar estados | ❌ | ✅ | ✅ | ❌ | ❌ |
| Administrar catálogo | ❌ | ❌ | ✅ | ❌ | ❌ |

> La matriz refleja la configuración real de STAGING y el comportamiento observado en los
> flujos validados. Los permisos se aplican por **rol (grupo Cognito)** y por **scope**.
