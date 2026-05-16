# Session Handoff

> Fichero de traspaso de sesión. Registra el trabajo **en curso** para
> poder retomarlo en un chat nuevo sin pérdida de contexto.
>
> **Cuándo actualizar:** al final de cada sesión de trabajo, o cuando un
> chat se esté alargando y exista riesgo de tener que abrir uno nuevo.
>
> **Diferencia con STATE.md:** STATE.md describe el estado *estable* del
> laboratorio (qué hay montado). Este fichero describe el estado *volátil*
> del trabajo en curso (qué se está haciendo ahora mismo).

---

## Cómo retomar el trabajo en un chat nuevo

1. Abrir un chat nuevo en el área temática correspondiente (ver campo
   "Chat activo" más abajo).
2. Pegar el contenido de este fichero.
3. Pegar el contenido de `STATE.md`.
4. Indicar: "Retomamos desde el handoff, continúa con el siguiente paso".

La constitución del proyecto se carga automáticamente desde las
instrucciones del Project, no hace falta pegarla.

---

## Estado de la sesión

**Última actualización:** 2026-05-16
**Fase actual:** 0 — Preparación y fundamentos
**Chat activo:** Linux

---

## Trabajo en curso

Descripción de lo que se está haciendo ahora mismo:

> Fase 0 en marcha. Repositorio montado y configurado. Hardware decidido
> (Lenovo ThinkCentre M920q Tiny) y documentado, pendiente de recepción
> física. Documentación de hardware, ADR y STATE.md completados.

---

## Siguiente paso concreto

El próximo paso a ejecutar cuando se retome el trabajo:

> Refresco de Linux en curso (chat de Linux). Siguiente paso: instalar
> software de virtualización en el PC Windows y crear la primera VM Linux
> para el refresco alineado con LPIC-1. LinkedIn: pendiente un retoque
> rápido de headline esta semana (chat de Documentación y portfolio),
> reescritura completa aplazada hasta tener material.

---

## Decisiones pendientes

Cuestiones abiertas que requieren decisión:

- Ninguna en este momento.

---

## Bloqueos

Cualquier cosa que impida avanzar:

- Recepción física del servidor (no bloquea: hay trabajo en paralelo
  disponible).

---

## Tareas pendientes

- [ ] Documentar en docs/troubleshooting/ nota indicando que "Git: rama da  'not fully merged' tras Squash and merge"

---

## Historial de sesiones

Registro breve de sesiones cerradas (más reciente arriba):

| Fecha | Chat | Resumen |
|-------|------|---------|
| 2026-05-16 | Roadmap | Cierre de fase 0 en Roadmap: sistema de continuidad (SESSION-HANDOFF) en marcha, flujo de PR consolidado. Trabajo se traslada al chat de Linux. |
| 2026-05-15 | Roadmap | Setup completo del repositorio: estructura, Git, SSH, ssh-agent, runbook de setup, protección de main, primer Issue. Decisión y documentación de hardware. |
