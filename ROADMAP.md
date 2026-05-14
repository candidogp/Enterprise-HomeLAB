# Roadmap — Enterprise Homelab (12 meses)

> Plan de evolución del homelab y de la transición profesional.  
> Dedicación estimada: 8-10 horas/semana.

---

## Fase 0 — Preparación y fundamentos
**Duración:** Semanas 1-3 (~25h)  
**Objetivo:** entorno de trabajo, documentación y refresco Linux antes 
de tocar infraestructura compleja.

**Entregables:**
- [ ] Repositorio GitHub público con estructura inicial.
- [ ] Hardware del servidor decidido y/o adquirido.
- [ ] VM Debian/Ubuntu funcional en PC personal con Linux refrescado.
- [ ] LinkedIn actualizado con posicionamiento de transición.

**Lo que no se toca:** Docker, Kubernetes, cloud.

---

## Fase 1 — Linux serio + Networking fundacional
**Duración:** Meses 2-3 (~70h)  
**Objetivo:** Linux a nivel administrador y base teórico-práctica de redes.

**Entregables:**
- [ ] Primera VM Linux configurada de cero con SSH endurecido, firewall, usuarios.
- [ ] Diagrama de red objetivo del homelab.
- [ ] Apuntes organizados de LPIC-1.
- [ ] Decisión sobre router/switch propio para fase 2.

**Lo que no se toca:** Docker, Ansible, cloud.

---

## Fase 2 — Virtualización y red real
**Duración:** Meses 4-5 (~80h)  
**Objetivo:** hipervisor productivo y red segmentada con VLANs reales.

**Entregables:**
- [ ] Proxmox VE instalado y documentado.
- [ ] pfSense/OPNsense como firewall del lab.
- [ ] VLANs reales: management, servers, DMZ, lab.
- [ ] DNS interno funcional.
- [ ] Post técnico: "Montando un homelab con Proxmox + pfSense + VLANs".

**Lo que no se toca:** servicios "divertidos" (Plex, *arr) hasta tener la base.

---

## Fase 3 — Servicios reales + Contenedores
**Duración:** Meses 6-8 (~110h)  
**Objetivo:** servicios fundamentales y Docker como herramienta de despliegue.

**Entregables:**
- [ ] Active Directory (Samba AD o Windows Server) con clientes Linux y Windows.
- [ ] Reverse proxy con gestión de certificados.
- [ ] Stack Docker Compose para servicios secundarios.
- [ ] Estrategia 3-2-1 de backups implementada y probada.
- [ ] Post técnico sobre AD híbrido.

**Lo que no se toca:** Kubernetes.

---

## Fase 4 — Observabilidad + Automatización + Seguridad aplicada
**Duración:** Meses 9-11 (~110h)  
**Objetivo:** prácticas de sysadmin senior y capa de seguridad aplicada.

**Entregables:**
- [ ] Prometheus + Grafana + Alertmanager funcionando.
- [ ] Logs centralizados (Loki o equivalente).
- [ ] Playbooks Ansible para provisionar VMs y servicios.
- [ ] Hardening CIS básico aplicado y documentado.
- [ ] Gestión de secretos implementada.
- [ ] Backups cifrados con restauración probada.

---

## Fase 5 — Cloud básico + Portfolio + Búsqueda activa
**Duración:** Mes 12 (~50h)  
**Objetivo:** cierre del proyecto y entrada al mercado.

**Entregables:**
- [ ] Despliegue mínimo en AWS Free Tier o Azure.
- [ ] Portfolio README maestro completo.
- [ ] LinkedIn actualizado con proyectos y resultados.
- [ ] CV reorientado a sysadmin/infra.
- [ ] Aplicaciones a ofertas reales en curso.
