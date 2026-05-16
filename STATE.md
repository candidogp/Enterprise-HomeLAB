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

Estado: host principal adquirido, pendiente de recepción.

### Host principal — pve-node01

- Equipo: Lenovo ThinkCentre M920q Tiny
- CPU: Intel Core i5-9500T (6C/6T, 35W)
- RAM: 16 GB DDR4 (ampliable a 64 GB)
- Disco: 256 GB SSD
- Red: 1× NIC Intel Gigabit
- Estado: comprado en Ecoportátil, pendiente de recepción
- Documentación: `hardware/hosts/pve-node01.md`
- Decisión: `docs/architecture/decisions/0001-seleccion-host-virtualizacion.md`

### Próximas acciones de hardware

- [ ] Recepción y verificación física del equipo
- [ ] Rellenar datos pendientes en pve-node01.md (S/N, MAC, BIOS)
- [ ] Fase 2: ampliar RAM a 32 GB
- [ ] Fase 2: añadir SSD SATA 2.5" para backups (posible adelanto por capacidad)

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
