
# Ejercicio 1 - CD con Jenkinsfile - Pipeline
En este primer ejercicio el objetivo es definir un Job en Jenkins que ejecute un Jenkinsfile donde esté definido todo un ciclo de Continuous Delivery (GitLab -> Jenkins [ Compilación, Test, SonarQube, Empaquetado, Deploy a Nexus ]). 
## Antes de empezar
- Todo proyecto a incorporar en Jenkins debe ser previamente versionado en Git y debe emplear un software de construcción como Maven en este caso. Trabajaremos sobre un proyecto Java previamente mavenizado. https://github.com/pablotoledo/maven-hello-world.git
- Disponemos de un fichero Jenkinsfile que os evitará definir desde cero los pasos a ejecutar por Jenkins. Conviene que lo reviséis. 

## Pasos a seguir:

 1. Importar en el GitLab local el proyecto https://github.com/pablotoledo/maven-hello-world.git y darle nombre en GitLab al proyecto como "ejercicio1". *(Botón + en la barra superior de GitLab -> New project -> Import project -> Repo by URL | Es importante tener en cuenta que hay que crear el repositorio con permisos de visibilidad públicos "Public The project can be accessed without any authentication.")* 
 2. El fichero Jenkinsfile ubicado en el escritorio o en () lo incorporaremos a la raíz del repositorio "ejercicio1" en GitLab. Podemos emplear conocimientos de Git o usar la interfaz gráfica de GitLab. *(Dentro del repositorio en GitLab, Botón + -> New file -> Copiamos el contenido del Jenkinsfile y lo guardamos con el nombre de Jenkinsfile)*
 3. Modificamos el pom.xml del repositorio, lo que buscamos es personalizar el nombre del proyecto. El groupId deberá ser "university", el artifactId será "ejercicio1", y el name será "ejercicio1"
 4. Crear un job en Jenkins (Nueva Tarea -> nombramos y seleccionamos Multibranch Pipeline -> en Branch Sources seleccionamos "Add source" y una vez se despliega elegimos Git -> completamos el campo de Project Repository con http://gitlab/root/ejercicio1.git 
 5. Ejecutar y comprobar la ejecución del job en Jenkins y revisar la salida en Sonarqube y Nexus.

