# CI-Service Virtual Machine

Este proyecto es una continuación de CI-Service y tiene como objetivo definir una máquina virtual para facilitar el entorno docente necesario para un curso de DevOps básico.

# Cómo empezar!
Será necesario contar con una máquina x64 con al menos 2 cores y 8 GB de RAM.

## Obtener Virtualbox y copia de vm
Para ejecutar la máquina virtual será imprescindible instalar las siguientes herramientas de virtualización:

	- Virtualbox 5.2.8: http://download.virtualbox.org/virtualbox/5.2.8/VirtualBox-5.2.8-121009-Win.exe
	- Virtualbox Extension Pack: http://download.virtualbox.org/virtualbox/5.2.8/Oracle_VM_VirtualBox_Extension_Pack-5.2.8.vbox-extpack
	- Obtener una copia del disco duro virtual para la máquina virtual

## Configurar máquina virtual en Virtualbox
Los pasos a ejecutar para configurar la máquina virtual en Virtualbox serían:

- Abrir VirtualBox y seleccionar New
- En la ventana de "Create Virtual Machine"
    - Name: Darle un nombre a la máquina virtualbox
    - Type: Seleccionar "Linux"
    - Version: Seleccionar "Ubuntu 64"
    - Memory size: **4096 MB como mínimo** siendo recomendable poner más memoria
    - Hard Disk: Seleccionar "Use an existing virtual hard disk file" y buscamos el fichero .vdi que se proporciona en el curso.
- Una vez creada la máquina virtual podremos iniciarla seleccionándola en VirtualBox y pulsando la opción de start.

## Datos adicionales de la VM
En caso de precisar la contraseña en algún momento para el uso de la máquina virtual:
|Usuario|Password|
|--|--|
|ciservice|ciservice|

# Que encontramos en la máquina virtual

 - **Entorno DevOps**: en el escritorio de la máquina virtual encontraremos enlaces a los distintos servicio que corren en la misma:
	 - GitLab - como solución para la gestión de código fuente
	 - Jenkins - orquestador de WF para CI/CD
		 - Agente o esclavo Centos donde ejecutar las tareas de CI
	 - Nexus - como repositorio de binarios
	 - SonarQube - como herramienta para el análisis de calidad de código
		 - Postgresql
	 - Portainer: Portal que nos permitirá administrar y monitorizar desde un dashboard todo el Docker Engine en ejecución.

 - **Material de estudio**: el material de estudio presente en este repositorio está disponible en el escritorio de la máquina virtual.

----------
# Recuerda
Este proyecto es una variante de https://github.com/pablotoledo/CI-Service que ejecuta sobre una máquina Ubuntu la solución dockerizada por CI-Service pero con algunas diferencias.

## Listado de servicios y puertos

|Servicio|Ruta Host:Puerto|Docker Hostname|
|--|--|--|
|Portainer|http://localhost:9000/ |portainer|
|GitLab|http://localhost:8030/ |gitlab|
|Jenkins|http://localhost:8080/ |jenkins|
|Nexus|http://localhost:8081/nexus/ |nexus|
|SonarQube|http://localhost:8020/ |sonarqube|

## Usuarios y contraseñas
Los usuarios siempre son de administración y puede ser: **root** ó **admin**
Las contraseñas siempre es la misma: **ciservice**

En el caso de Sonar el token creado para acceder a este servicio desde otras aplicaciones es: 5f94f7762e88a8559fbc618abc02d4685dabc4b9


----------

### Autor
    Pablo Toledo
