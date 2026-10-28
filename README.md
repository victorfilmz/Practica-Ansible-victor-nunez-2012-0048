# Práctica: Automatización de Servidores con Ansible y Docker

## Descripción
Esta práctica consiste en aprovisionar y gestionar múltiples servidores Ubuntu simulados mediante contenedores Docker usando Docker Compose, y configurarlos de manera automatizada utilizando Ansible.

## Objetivo
- Desplegar 5 nodos Ubuntu con servicio SSH activo mediante Docker Compose.
- Gestionar los nodos usando un inventario de Ansible.
- Ejecutar un playbook automatizado que actualice el sistema, cree usuarios, cree directorios/archivos e instale paquetes (`htop`, `cowsay`).

## Requisitos
- Docker Desktop
- Ansible (en Linux/WSL o máquina de control)

## Pasos para ejecutar el proyecto

### 1. Levantar los contenedores de prueba
```bash
docker compose up -d --build
```

Comprobar que los 5 contenedores estén activos:
```bash
docker compose ps
```

### 2. Probar conectividad con Ansible (Ping)
```bash
ansible servidores -m ping
```

### 3. Ejecutar el Playbook de configuración
```bash
ansible-playbook playbooks/configurar-servidores.yml
```

### 4. Detener el entorno
```bash
docker compose down
```

## Autor
Víctor Núñez - Matrícula: 2012-0048
