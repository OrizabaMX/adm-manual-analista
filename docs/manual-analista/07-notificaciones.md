# 07 — Notificaciones

## ¿Qué notifica el sistema?

El sistema despacha avisos al ciudadano en cada etapa relevante de su trámite:

| Evento | Momento |
|---|---|
| **Solicitud enviada** | El ciudadano envía el trámite |
| **En revisión** | El área responsable comienza la revisión |
| **Pago confirmado** | La caja confirma el pago |
| **Resolución emitida** | Se emite la resolución del trámite |
| **Trámite concluido** | El trámite se concluye y entrega el documento |

## Dónde ver el historial

- **Funcionario**: pestaña **Notificaciones** del detalle del trámite → lista de avisos con fecha/hora.
- **Ciudadano**: la actividad del trámite muestra los mismos eventos.

## Canales

- **PUSH** (app móvil con dispositivo activo): canal preferente.
- **SMS**: respaldo cuando no hay dispositivo push activo.

> **PUSH = BLOCKED_EXTERNAL**
>
> La infraestructura externa de notificaciones push (APNs/FCM/SNS) no está configurada en
> STAGING. Esta es una **limitación conocida** y **no es un defecto funcional general**.
> El canal **SMS** y el historial de despacho deben validarse según la configuración actual.

## Screenshot

![Historial de notificaciones](screenshots/notificaciones/01-historial-notificaciones.png)

## Qué validar

- Que cada evento del trámite aparezca en el historial.
- Que el despacho se registre sin errores (sin HTTP 500, sin "Failed" inesperados).
- Que el fallback SMS funcione o quede registrado como pendiente según configuración.
