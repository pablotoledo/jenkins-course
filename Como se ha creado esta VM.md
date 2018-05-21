# Partiendo de contar con el siguiente software:
	- VirtualBox
	- VirtualBox Extension Pack 

	http://download.virtualbox.org/virtualbox/5.2.8/

# Se virtualiza Ubuntu 16.04
	- Se emplea la siguiente Box: Ubuntu 16.04.4 Xenial
	  https://www.osboxes.org/ubuntu/
	- Características de la VM:
		- 4096 MB RAM
		- 2 vCPUs

# Se instala el siguiente software de base
	- openjdk-8jdk
	- htop
	- git
	- curl 
	- atom 
	- build-essentials
	- Docker CE : Script - curl -sSL https://get.docker.com | sudo sh
	- pip
		- docker-compose

 
# Se instala manualmente el entorno	
DevOps de github.com/pablotoledo/CI-Service

	- Se interpretan los comandos necesarios de aprovisionamiento del Vagrantfile
	- Se ejecuta el fichero docker-compose
