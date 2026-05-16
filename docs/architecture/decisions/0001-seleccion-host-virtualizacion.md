# ADR-0001: Selección del host de virtualización del homelab

## Estado

Aceptada — 2026-05-16

## Contexto

El proyecto requiere un host físico para ejecutar un hipervisor (Proxmox VE)
sobre el que se desplegarán entre 5 y 10 máquinas virtuales a lo largo de las
fases 2 y 3 del roadmap (firewall virtualizado, Active Directory de laboratorio,
servidores Linux, host de contenedores y, más adelante, stack de observabilidad).

Restricciones del proyecto:

- Presupuesto contenido: gasto sostenible de ~200 €/mes, sin desembolsos
  excesivos en una sola pieza.
- Entorno doméstico: prioridad a bajo consumo (<30W en reposo) y bajo ruido.
- Ubicación en Tenerife: clima cálido (disipación) y mercado local de segunda
  mano muy limitado; las compras dependen de proveedores peninsulares con
  envío a Canarias.
- Mentalidad enterprise: se prioriza hardware empresarial real frente a
  soluciones de consumo, por su valor formativo para una transición
  profesional a administración de sistemas.

## Opciones consideradas

### Opción A — Mini PC empresarial reacondicionado (Lenovo/HP/Dell)

Equipos tipo Lenovo ThinkCentre M920q, HP EliteDesk 800 Mini o Dell OptiPlex
Micro, de 8ª-9ª generación Intel.

- A favor: hardware empresarial real, NIC Intel fiable con hipervisores,
  RAM ampliable en 2 slots SODIMM hasta 64 GB, formato Tiny silencioso y de
  bajo consumo (CPU con sufijo "T", 35W), precio contenido, valor formativo.
- En contra: sin garantía de fabricante (sí garantía del reacondicionador),
  generación de hardware no reciente.

### Opción B — Mini PC nuevo de bajo consumo (Intel N100/N305)

Equipos nuevos con SoC Intel de la serie N.

- A favor: garantía completa, consumo en reposo muy bajo (6-15W), silencio.
- En contra: NIC Realtek frecuente (peor comportamiento con VLANs y trunk
  802.1Q), memoria a menudo monocanal o limitada a 32 GB, sin HyperThreading,
  ecosistema menos representativo de un entorno empresarial real.

### Opción C — Compra escalonada (equipo modesto ahora, host serio en fase 2)

- A favor: menor desembolso inicial.
- En contra: duplica el gasto total, complica la trazabilidad del laboratorio
  e incumple el principio de no introducir complejidad innecesaria.

## Decisión

Se selecciona la **Opción A**: un **Lenovo ThinkCentre M920q Tiny** con CPU
**Intel Core i5-9500T** (6C/6T, 35W), 16 GB de RAM DDR4 y SSD de 256 GB,
adquirido reacondicionado en Ecoportátil por 272,69 € con 2 años de garantía
y envío a Canarias.

Motivos principales:

- Cumple todos los requisitos no negociables: CPU de 4C/8T o superior,
  2 slots SODIMM con ampliación hasta 64 GB, slot M.2 NVMe más bahía SATA 2.5",
  NIC Intel y consumo en reposo previsto por debajo de 30W.
- El i5-9500T ofrece margen suficiente para 5-10 VMs con sobre-suscripción
  razonable de CPU.
- Es hardware empresarial representativo del que se gestiona en el puesto
  profesional objetivo.
- El precio deja presupuesto disponible para el resto del roadmap (ampliación
  de RAM, almacenamiento, switch gestionable, SAI).

## Consecuencias

### Positivas

- Base estable para las fases 2-4 del roadmap sin necesidad de sustituir el host.
- NIC Intel: sin fricción esperada con Proxmox, VLANs ni trunking.
- Formato Tiny: bajo consumo, bajo ruido y espacio mínimo en escritorio.

### Negativas / deuda técnica conocida

- **RAM inicial de 16 GB**: suficiente para fases 0-1, pero insuficiente para
  el objetivo de 5-10 VMs. Se planifica ampliación a 32 GB en fase 2.
  El equipo admite hasta 64 GB, por lo que la deuda es resoluble sin
  sustituir hardware.
- **Almacenamiento en disco único de 256 GB**: es la limitación más relevante
  del equipo. Tras instalar Proxmox, el espacio disponible para discos de VM
  es ajustado para el objetivo de 5-10 VMs. Se planifica añadir un SSD SATA
  2.5" en fase 2 para separar almacenamiento de VMs y backups y dar
  cumplimiento a la estrategia 3-2-1; esta incorporación podría adelantarse
  si la capacidad se convierte en cuello de botella antes de lo previsto.
- **NIC física única**: no permite separar tráfico por interfaces físicas.
  Se asume de forma deliberada: la segmentación de red se implementará
  mediante VLANs y un switch gestionable (router-on-a-stick), topología
  válida y representativa de entornos reales. Revisable en fases 4-5 si
  se decide un firewall en appliance físico dedicado.
- Hardware de 9ª generación: ciclo de vida útil más corto que un equipo nuevo;
  asumible para los objetivos del proyecto.

## Notas

- Decisión tomada en el chat especializado de Hardware del proyecto.
- La ficha técnica del equipo se mantiene en `hardware/hosts/pve-node01.md`.