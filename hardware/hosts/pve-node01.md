# pve-node01 — Lenovo ThinkCentre M920q Tiny

Ficha técnica del host principal de virtualización del homelab.

Última actualización: 2026-05-16
Estado: **Pendiente de recepción**

## Identificación

| Campo                  | Valor                              |
|------------------------|------------------------------------|
| Hostname previsto      | pve-node01                         |
| Fabricante / Modelo    | Lenovo ThinkCentre M920q Tiny      |
| Machine Type Model     | _(rellenar al recibir)_            |
| Número de serie        | _(rellenar al recibir)_            |
| Formato                | Tiny (1 litro)                     |

## Especificaciones

| Componente      | Detalle                                       |
|-----------------|-----------------------------------------------|
| CPU             | Intel Core i5-9500T — 6C/6T, 2.2 GHz, 35W TDP |
| RAM instalada   | 16 GB DDR4 SODIMM                             |
| RAM — slots     | _(rellenar: nº ocupados / nº totales)_        |
| RAM — máxima    | 64 GB (2 × 32 GB)                             |
| Almacenamiento  | 256 GB SSD NVMe M.2                           |
| Slots de disco  | 1× M.2 2280 NVMe + 1× bahía SATA 2.5"         |
| Red             | 1× Intel Gigabit Ethernet (integrada)         |
| MAC address NIC | _(rellenar al recibir)_                       |
| BIOS/UEFI       | _(rellenar: versión al recibir)_              |

## Red

| Campo            | Valor                          |
|------------------|--------------------------------|
| IP de gestión    | _(se asignará al instalar Proxmox)_ |
| VLAN de gestión  | _(se definirá en fase de Networking)_ |

## Histórico de cambios físicos

Registro de toda modificación de hardware (ampliaciones, sustituciones).

| Fecha      | Cambio                                  |
|------------|-----------------------------------------|
| 2026-05-XX | Recepción del equipo. Configuración de fábrica. |

## Deuda técnica conocida

## Deuda técnica conocida

Ver ADR-0001 para el detalle y la justificación.

- RAM a 16 GB: suficiente para fases 0-1; ampliación a 32 GB prevista en fase 2.
- Almacenamiento de 256 GB en disco único: capacidad ajustada y sin
  redundancia. Es la principal limitación del equipo. La incorporación de un
  segundo disco (SSD SATA 2.5") podría adelantarse si la capacidad se vuelve
  un cuello de botella al desplegar las primeras VMs.
- NIC única: la segmentación de red se hará por VLANs con switch gestionable,
  no por interfaces físicas.