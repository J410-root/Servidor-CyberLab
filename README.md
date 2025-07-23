# Servidor-CyberLab
# Servidor de Laboratorio de Ciberseguridad y Administración de Sistemas

Este repositorio contiene todos los detalles sobre la creación y configuración de un **servidor de laboratorio** utilizando Proxmox, Kubernetes y diversas herramientas de seguridad y monitoreo. El objetivo es crear un entorno virtualizado y seguro para aprender sobre administración de sistemas, redes, ciberseguridad y automatización.

## Descripción del Proyecto

Este proyecto tiene como objetivo montar un laboratorio de ciberseguridad y administración de sistemas sobre una infraestructura virtualizada utilizando **Proxmox VE**. A través de diversas máquinas virtuales, se desplegarán servicios, aplicaciones y herramientas como Kubernetes, herramientas de seguridad, monitoreo, y más.

## Objetivos del Proyecto

- **Administración de Servidores**: Crear y gestionar un servidor virtualizado con Proxmox.
- **Orquestación con Kubernetes**: Desplegar un clúster de Kubernetes con múltiples nodos para ejecutar servicios y aplicaciones.
- **Seguridad**: Implementar firewalls, IDS/IPS (Suricata), y otras prácticas de ciberseguridad.
- **Monitoreo**: Configurar herramientas de monitoreo como Grafana y Prometheus para asegurar la infraestructura.
- **Automatización**: Usar herramientas como Ansible para la automatización de tareas.
  
## Requisitos del Proyecto

### Hardware:

- **Procesador**: Xeon E5-2680 v4
- **Memoria RAM**: 16 GB DDR4 3200 MHz
- **Almacenamiento**: SSD de 250 GB + HDDs grandes para almacenamiento secundario
- **Tarjeta Gráfica**: GT 710 2GB
- **Red**: Switch básico para conectar varias máquinas

### Software:

- **Proxmox VE**: Para gestionar las máquinas virtuales.
- **Kubernetes**: Usando `k3s` o `kubeadm` para la orquestación de contenedores.
- **Suricata**: Para detección y prevención de intrusiones (IDS/IPS).
- **Wazuh**: SIEM para la centralización de logs y alertas.
- **Grafana y Prometheus**: Para monitoreo de la infraestructura.
- **Ansible**: Para la automatización de configuraciones.

## Instalación

### 1. Instalación de Proxmox VE

1. Descargue la ISO de **Proxmox VE** desde el [sitio oficial](https://www.proxmox.com/en/proxmox-ve).
2. Cree un USB booteable usando **Ventoy** o **Rufus**.
3. Instale Proxmox VE en un SSD de 250 GB y configure el sistema en modo **UEFI**.
4. Realice las configuraciones iniciales (usuario administrador, hostname, etc.).

### 2. Configuración de Red en Proxmox

1. Cree los **puentes de red**:
   - `vmbr0` para la LAN interna.
   - `vmbr1` para el acceso a internet (NAT o puente físico).
   - `vmbr2` (opcional) para una red aislada para pruebas de seguridad.

### 3. Despliegue de Máquinas Virtuales

#### pfSense / OPNsense
1. Cree una VM con 2 vCPUs y 2 GB de RAM.
2. Configure pfSense/OPNsense para manejar el firewall, NAT, y DHCP.
3. Habilite **Suricata** para la detección y prevención de intrusiones (IDS/IPS).

#### Kubernetes
1. Cree las VMs para el clúster de Kubernetes:
   - `kubemaster` con 4 vCPUs y 4 GB de RAM.
   - `kubeworker1` y `kubeworker2` con 2 vCPUs y 2-4 GB de RAM.
2. Instale **k3s** o **kubeadm** para la orquestación de contenedores.
3. Despliegue el **dashboard** y un servicio de prueba (como nginx o una app simple).

#### SIEM y Monitoreo
1. Instale **Wazuh** o **Security Onion** para la centralización de logs.
2. Configure **Grafana** y **Prometheus** para monitoreo de la infraestructura.

#### Seguridad Ofensiva
1. Cree máquinas virtuales con **Metasploitable1** y **Metasploitable2** para realizar pruebas de penetración.
2. Instale aplicaciones de pruebas como **DVWA**, **Juice Shop**, y **WebGoat**.

#### Automatización
1. Cree una VM para **Ansible Controller**.
2. Configure **GitLab CI** o **Jenkins** para automatizar tareas y despliegues.

## Documentación de Configuración

Cada paso y configuración realizada está documentada en los archivos de este repositorio. Si tienes alguna pregunta o sugerencia, no dudes en abrir un **issue**.

## Formación y Certificaciones

Este proyecto también forma parte de mi proceso de aprendizaje en el ámbito de la **ciberseguridad** y la **administración de sistemas**. Las siguientes certificaciones están en proceso:

- **CC (ISC2)**: Preparación para la certificación **Certified Cloud Security Professional (CCSP)**.
- **ACP 120 y 620**: Certificación en Google Cloud.

## Licencia

Este proyecto está bajo la **Licencia MIT**. Puedes usarlo, modificarlo y distribuirlo, siempre y cuando se dé el crédito adecuado.

---

Si tienes alguna duda o deseas contribuir, no dudes en abrir un **issue** o hacer un **pull request**.
![image](https://github.com/user-attachments/assets/cc6c5955-1012-4f91-a574-6c7a9f14e65e)
