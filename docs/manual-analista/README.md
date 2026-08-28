# ADM — Manual de Validación Funcional

Sistema municipal de atención digital y presencial.

## ¿Qué es ADM?

ADM es una plataforma digital del **H. Ayuntamiento de Orizaba** que permite a la ciudadanía:

- Consultar su **CURP** y validar su identidad.
- **Iniciar trámites** municipales en línea (por ejemplo, Constancia de Alineamiento).
- Dar **seguimiento** al avance de sus trámites por fases.
- Consultar su **expediente ciudadano** y documentos.
- Ver su **orden de pago**, **recibo** y **resolución**.
- Recibir **notificaciones** de cada etapa.

Al mismo tiempo, brinda herramientas a los **funcionarios municipales** (atención ciudadana,
revisión documental, generación de pagos y resoluciones) y a la **caja municipal** (cobro de
derechos y comprobantes).

## ¿Qué prueba el analista?

Este manual permite a un analista funcional recorrer el sistema de **STAGING** paso a paso,
validar los flujos de **Ciudadano**, **Funcionario** y **Caja**, y registrar los resultados
(PASS/FAIL) sin intervención del equipo de desarrollo.

## ¿Qué es STAGING?

**STAGING** es el ambiente de pruebas que replica la funcionalidad del sistema con datos de
prueba (DEMO). Es el lugar correcto para validar funcionalidad.

## ⚠️ Qué NO es PROD

**STAGING NO es PRODUCCIÓN.** No contiene datos reales de la ciudadanía. No debe utilizarse
para trámites reales. Cualquier operación aquí es de **prueba**.

## Portales disponibles (STAGING)

| Portal | URL | Perfiles |
|---|---|---|
| Portal ciudadano | `https://adm-web-citizens-staging.fly.dev` | Ciudadano |
| Portal funcionarios | `https://adm-web-staging.fly.dev/funcionario` | Funcionario (Administrator, Capturist, Viewer, Cashier, KitDelivery) |
| Caja municipal | `https://adm-caja-staging.fly.dev` | Cajero |

## Flujo general

```
CIUDADANO
   ↓
TRÁMITE
   ↓
ATENCIÓN FUNCIONARIO
   ↓
EXPEDIENTE / REQUISITOS
   ↓
ORDEN DE PAGO
   ↓
CAJA / PAGO
   ↓
RESOLUCIÓN
   ↓
NOTIFICACIÓN
   ↓
CONCLUIDO
```

## Índice del manual

| # | Capítulo | Contenido |
|---|---|---|
| 01 | [Acceso y entornos](01-acceso-y-entornos.md) | URLs, entornos, credenciales |
| 02 | [Usuarios y roles](02-usuarios-y-roles.md) | Cuentas demo, roles, matriz de permisos |
| 03 | [Flujo ciudadano](03-flujo-ciudadano.md) | Portal ciudadano paso a paso |
| 04 | [Flujo funcionario](04-flujo-funcionario.md) | Portal funcionario paso a paso |
| 05 | [Expediente](05-expediente.md) | Expediente ciudadano y documental |
| 06 | [Pagos y caja](06-pagos-y-caja.md) | Órdenes de pago, caja, comprobantes |
| 07 | [Notificaciones](07-notificaciones.md) | Avisos del trámite, canales |
| 08 | [Seguridad y permisos](08-seguridad-y-permisos.md) | Aislamiento, roles, autenticación |
| 09 | [Casos de prueba](09-casos-de-prueba.md) | Matriz de casos (30+) |
| 10 | [Reporte de incidencias](10-reporte-de-incidencias.md) | Plantilla de reporte |

## Screenshots

Los screenshots reales del ambiente STAGING están en `screenshots/`:

```
screenshots/
  ciudadano/
  funcionario/
  expediente/
  pagos/
  caja/
  notificaciones/
```

## Aviso de credenciales

Las credenciales de acceso son entregadas por el responsable de pruebas mediante un canal
separado y **no forman parte de este repositorio**.
