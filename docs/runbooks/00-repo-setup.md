# Runbook 00 — Configuración inicial del repositorio

> Procedimiento para clonar y empezar a trabajar en este repositorio
> desde una máquina Windows con Git Bash. Equivalente para Linux/macOS
> al final del documento.

**Audiencia:** cualquier persona (incluido el autor en una máquina nueva)
que vaya a contribuir al repositorio.

**Tiempo estimado:** 20-30 minutos si se siguen los pasos en orden.

**Última revisión:** 2026-05-15

---

## 1. Prerrequisitos

- Cuenta en GitHub con permisos para clonar el repositorio.
- Sistema operativo: Windows 10/11 (con Git for Windows) o Linux/macOS.
- Editor de código: VS Code recomendado.
- Acceso a internet.

---

## 2. Instalación de herramientas base

### Windows

1. Descargar e instalar **Git for Windows** desde
   <https://git-scm.com/download/win>. Esto incluye Git Bash.
2. Descargar e instalar **VS Code** desde <https://code.visualstudio.com/>.
3. Verificar instalación en Git Bash:

   ```bash
   git --version
   code --version
   ```

### Linux (Debian/Ubuntu)

```bash
sudo apt update && sudo apt install -y git
```

### macOS

```bash
brew install git
```

---

## 3. Configuración global de Git

Ejecutar una sola vez por máquina. Sustituir los valores entre comillas
por los propios.

```bash
git config --global user.name "Nombre Apellido"
git config --global user.email "email@example.com"
git config --global init.defaultBranch main
git config --global core.editor "code --wait"
git config --global pull.rebase false
git config --global fetch.prune true
git config --global push.default simple
git config --global push.autoSetupRemote true
```

Adicional **solo para Windows** (conversión de finales de línea):

```bash
git config --global core.autocrlf input
```

Verificar:

```bash
git config --global --list
```

---

## 4. Configuración de claves SSH para GitHub

### 4.1 Generar par de claves ed25519

```bash
ssh-keygen -t ed25519 -C "email@example.com"
```

- Aceptar la ruta por defecto (`~/.ssh/id_ed25519`).
- Establecer una passphrase robusta.

### 4.2 Registrar la clave pública en GitHub

1. Mostrar la clave pública:

   ```bash
   cat ~/.ssh/id_ed25519.pub
   ```

2. En GitHub: **Settings → SSH and GPG keys → New SSH key**.
3. Pegar el contenido completo. Asignar un título descriptivo
   (por ejemplo: `Workstation-Casa Windows`).

### 4.3 Verificar conexión

```bash
ssh -T git@github.com
```

Salida esperada:

```
Hi <usuario>! You've successfully authenticated, but GitHub does not provide shell access.
```

### 4.4 Configurar ssh-agent para autostart (Git Bash en Windows)

Añadir al final de `~/.bashrc`:

```bash
# ---------------------------------------------------------------
# SSH agent autostart - load identity once per Git Bash session
# ---------------------------------------------------------------
env=~/.ssh/agent.env

agent_load_env () { test -f "$env" && . "$env" >| /dev/null ; }
agent_start () {
    (umask 077; ssh-agent >| "$env")
    . "$env" >| /dev/null
}

agent_load_env

agent_run_state=$(ssh-add -l >| /dev/null 2>&1; echo $?)

if [ ! "$SSH_AUTH_SOCK" ] || [ $agent_run_state = 2 ]; then
    agent_start
    ssh-add
elif [ "$SSH_AUTH_SOCK" ] && [ $agent_run_state = 1 ]; then
    ssh-add
fi

unset env
```

Crear `~/.bash_profile` para que las sesiones de login fuente `.bashrc`:

```bash
cat > ~/.bash_profile << 'EOF'
if [ -f ~/.bashrc ]; then
    . ~/.bashrc
fi
EOF
```

---

## 5. Clonar el repositorio

```bash
cd /d/proyectos                 # o la carpeta de proyectos en tu sistema
git clone git@github.com:candidogp/enterprise-homelab.git
cd enterprise-homelab
git status
```

Verificar que el remoto usa SSH (no HTTPS):

```bash
git remote -v
```

Debe mostrar `git@github.com:...`. Si aparece `https://`, cambiarlo con:

```bash
git remote set-url origin git@github.com:candidogp/enterprise-homelab.git
```

---

## 6. Estructura del repositorio

```
enterprise-homelab/
├── README.md             Portada y visión general
├── STATE.md              Estado actual del laboratorio (documento vivo)
├── ROADMAP.md            Plan de las cinco fases del proyecto
├── LICENSE               Licencia MIT
├── docs/
│   ├── architecture/     Diagramas y decisiones arquitectónicas (ADR)
│   ├── runbooks/         Procedimientos operativos paso a paso
│   ├── guides/           Guías técnicas extensas
│   └── troubleshooting/  Problemas encontrados y soluciones
├── notes/                Apuntes de estudio
├── hardware/             Inventario y planificación física
├── networking/           Diagramas de red, direccionamiento, configuraciones
├── linux/                Configuraciones, scripts y hardening de Linux
├── virtualization/       Configuraciones de Proxmox y plantillas de VMs
├── docker/               Ficheros docker-compose y configuraciones
├── ansible/              Playbooks de Ansible (fase 4 en adelante)
├── monitoring/           Configuraciones de Prometheus, Grafana, logs
└── security/             Baselines, políticas y configuraciones de hardening
```

---

## 7. Reglas de contribución

### Mensajes de commit

Seguir **Conventional Commits**. Formato:

```
<tipo>(<ámbito opcional>): <descripción imperativa>

<cuerpo opcional: qué y por qué>
```

Tipos en uso: `feat`, `fix`, `docs`, `chore`, `refactor`, `style`.

Ejemplo:

```
docs(runbooks): add initial repo setup procedure

Documents the full bootstrap workflow for a new contributor:
Git installation, global config, SSH key generation,
GitHub registration and repository clone.
```

### Idioma

- **Mensajes de commit, nombres de ramas y nombres de fichero:** inglés.
- **Contenido de documentación (guías, posts, ADR):** español.
- **Configuraciones, comentarios en código:** inglés.

### Ramas

- `main`: rama principal, protegida. No se hace push directo.
- Trabajo en ramas con prefijo según tipo:
  - `feat/<descripcion-corta>`
  - `fix/<descripcion-corta>`
  - `docs/<descripcion-corta>`
- Merge a `main` solo vía Pull Request.

---

## 8. Seguridad

- **NUNCA** subir secretos al repositorio (passwords, API keys, claves
  privadas, ficheros `.env` con datos reales).
- El `.gitignore` cubre patrones comunes pero no es infalible. Revisar
  cada commit antes de hacer push.
- Si por error se sube un secreto: rotarlo inmediatamente, no basta
  con borrarlo en un commit posterior (queda en el historial de Git
  indefinidamente).

---

## 9. Referencias

- Documentación oficial de GitHub sobre SSH:
  <https://docs.github.com/en/authentication/connecting-to-github-with-ssh>
- Conventional Commits: <https://www.conventionalcommits.org/>
- Plantilla MIT License: <https://choosealicense.com/licenses/mit/>
