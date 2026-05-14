# Enterprise Homelab

> Homelab progresivo orientado a transición profesional desde IT Support 
> hacia Sysadmin Linux / Infraestructura on-prem, con base de networking 
> y seguridad aplicada.

## Estado actual

**Fase:** 0 — Preparación y fundamentos  
**Última actualización:** YYYY-MM-DD

Ver [`STATE.md`](./STATE.md) para el estado técnico actual del laboratorio.

## Objetivo del proyecto

Construir, documentar y mantener un homelab que simule un entorno empresarial 
real, cubriendo:

- Linux como administrador (no como usuario).
- Networking segmentado con VLANs y firewall.
- Virtualización con Proxmox VE.
- Servicios fundamentales (AD, DNS, ficheros, reverse proxy).
- Contenedores con Docker.
- Automatización con Ansible.
- Observabilidad con Prometheus + Grafana.
- Seguridad aplicada: hardening, backups cifrados, gestión de secretos.

## Roadmap

Ver [`ROADMAP.md`](./ROADMAP.md) para el plan completo de 12 meses dividido 
en 5 fases.

| Fase | Periodo | Foco |
|------|---------|------|
| 0 | Semanas 1-3 | Preparación, repo, refresco Linux |
| 1 | Meses 2-3 | Linux serio + Networking fundacional |
| 2 | Meses 4-5 | Proxmox + pfSense + VLANs reales |
| 3 | Meses 6-8 | AD, servicios base, Docker, backups 3-2-1 |
| 4 | Meses 9-11 | Observabilidad + Ansible + Seguridad |
| 5 | Mes 12 | Cloud básico + Portfolio + Búsqueda activa |

## Estructura del repositorio

docs/             Documentación técnica, decisiones, runbooks, troubleshooting
notes/            Apuntes de estudio (LPIC, networking, etc.)
hardware/         Inventario y planificación física
networking/       Diagramas, plan de direccionamiento, configuraciones
linux/            Configs, scripts, hardening
virtualization/   Configs de Proxmox, plantillas de VMs
docker/           docker-compose.yml de servicios
ansible/          Playbooks (a partir de fase 4)
monitoring/       Configuraciones de Prometheus, Grafana, logs
security/         Baselines, políticas, hardening

## Filosofía

1. **Enterprise mindset desde el día 1**: segmentación, nomenclatura, 
   backups, documentación, seguridad.
2. **Tecnología empresarial real**, no la última de moda.
3. **Documentación en caliente**: si no está documentado, no existe.
4. **No saltar fases**: cada capa se construye sobre una base sólida.
5. **Cada fase produce un entregable** demostrable.

## Sobre el autor

[Tu nombre] — IT Support Specialist en transición hacia Systems 
Administration. Tenerife, España.

- LinkedIn: [URL]
- Email: [opcional]

## Licencia

Documentación y configuraciones bajo licencia MIT. Ver [`LICENSE`](./LICENSE).
