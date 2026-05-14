# State of the Lab

> Documento vivo. Refleja el estado **real** del homelab en cada momento.  
> Actualizar tras cada cambio significativo.

**Última actualización:** YYYY-MM-DD  
**Fase actual:** 0 — Preparación y fundamentos

---

## Resumen ejecutivo

Laboratorio en **fase de preparación**. Sin hardware dedicado todavía. 
Documentación y planificación en curso.

---

## Hardware

| Elemento | Modelo | Estado | Notas |
|----------|--------|--------|-------|
| Servidor principal | _Pendiente_ | No adquirido | Decisión en curso en chat de Hardware |
| Router | Router Digi (ISP) | En producción | Sin control avanzado |
| Switch | _Ninguno gestionable_ | — | A evaluar en fase 1-2 |
| PC personal | [Tu PC] | Operativo | Usado para VMs temporales en fase 0 |

---

## Red

**Estado:** sin segmentación. Red plana del router del ISP.

Plan de direccionamiento futuro: pendiente de definir en chat de Networking 
(fase 1-2).

---

## Virtualización

**Estado:** sin hipervisor. Se usará VirtualBox/VMware Workstation en el PC 
personal durante fase 0 para refresco de Linux.

---

## Servicios desplegados

Ninguno todavía.

---

## Backups

No aplica todavía.

---

## Monitorización

No aplica todavía.

---

## Riesgos y deuda técnica conocida

- Router del ISP sin control avanzado: limitará networking hasta que se 
  introduzca firewall propio (fase 2).
- Sin segunda ubicación física: backup 3-2-1 requerirá pensar estrategia 
  off-site (fase 3).

---

## Próximos hitos

- [ ] Definir y adquirir hardware del servidor principal.
- [ ] Instalar entorno de virtualización temporal en PC personal.
- [ ] Refrescar Linux en VM (Debian o Ubuntu Server).
- [ ] Primer commit del repositorio con estructura inicial.
