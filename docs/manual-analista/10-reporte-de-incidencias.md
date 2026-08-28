# 10 — Reporte de incidencias

Plantilla para registrar incidencias encontradas durante la validación funcional en STAGING.

## Severidad

| Severidad | Descripción |
|---|---|
| **P0** | Bloqueante (impide la prueba o el flujo completo) |
| **P1** | Alta (funcionalidad afectada sin workaround) |
| **P2** | Media (funcionalidad afectada con workaround) |
| **P3** | Baja / UI (problema cosmético o menor) |

## Plantilla

```
INCIDENTE:
FECHA:
ANALISTA:
AMBIENTE: STAGING
ROL:
URL:
CASO DE PRUEBA:
PRIORIDAD: (P0/P1/P2/P3)

PASOS PARA REPRODUCIR:
1.
2.
3.

RESULTADO ESPERADO:

RESULTADO OBTENIDO:

SCREENSHOT:

CORRELATION ID:

OBSERVACIONES:
```

## Notas

- Registrar siempre el **CASO DE PRUEBA** (ID de [09-casos-de-prueba.md](09-casos-de-prueba.md)).
- Incluir el **CORRELATION ID** de la petición cuando el sistema lo muestre o lo proporcione el
  equipo de soporte.
- No incluir credenciales, tokens ni datos personales reales en el reporte.
