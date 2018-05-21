# Ejercicio 2 - Blue Ocean Pipeline
Blue Ocean ha desarrollado un plugin que facilita a pequeños proyectos la definición de un pipeline de forma visual. Mas info: https://jenkins.io/projects/blueocean/ 
## Antes de empezar
- Todo proyecto a incorporar en Jenkins debe ser previamente versionado en Git y debe emplear un software de construcción como Maven en este caso. Trabajaremos sobre un proyecto Java previamente mavenizado. https://github.com/pablotoledo/maven-hello-world.git
- El fichero Jenkinsfile será autogenerado según se parametrice el job con el plugin de BlueOcean.

## Pasos a seguir:

 1. Importar en el GitLab local el proyecto https://github.com/pablotoledo/maven-hello-world.git y darle nombre en GitLab al proyecto como "ejercicio2". *(Botón + en la barra superior de GitLab -> New project -> Import project -> Repo by URL | Es importante tener en cuenta que hay que crear el repositorio con permisos de visibilidad públicos "Public The project can be accessed without any authentication.")* 
 2. Modificamos el pom.xml del repositorio, lo que buscamos es personalizar el nombre del proyecto. El groupId deberá ser "university", el artifactId será "ejercicio2", y el name será "ejercicio2"
 3. Acceder a Jenkins y pulsar Open Blue Ocean
 4. Seleccionamos "Nuevo Pipeline"
 5. En *Where do yo store your code?* seleccionaremos Git
 6. Le pasamos la ruta del repositorio en *Connect to a Git repository* git@gitlab:root/ejercicio2.git y agregamos la clave pública SSH en http://localhost:8030/profile/keys
 7. El primer paso es definir donde se ejecutará el pipeline. Agent tipo node y el label es slave. Como enviroment definiremos la variable JAVA_HOME en la carpeta /usr/
 8. Ahora toca replicar los stages del pipeline del ejercicio 1 con la interfaz gráfica de Blue Ocean, con pasos secuenciales.
	 1. Download Sources en Blue Ocean equivale a un stage tipo git donde añadimos la ruta del repositorio http://gitlab/root/ejercicio2.git 
	 2. UnitTest Source en Blue Ocean equivale a un stage tipo Shell Script y copiaremos el código "mvn clean test" 
	 3. Compile Source en Blue Ocean equivale a un stage tipo Shell Script y copiaremos el código "mvn clean compile package" 
	 4. Package en Blue Ocean equivale a un stage tipo Shell Script y copiaremos el código "mvn install" 
	 5. CoverageTest Source en Blue Ocean equivale a un stage tipo Shell Script y copiaremos el código "mvn scoverage:report sonar:sonar" 
	 6. Publish Artifact Nexus en Blue Ocean equivale a un stage tipo Shell Script y copiaremos el código "mvn deploy" 
9. Ejecutar y comprobar la ejecución del job en Jenkins y revisar la salida en Sonarqube y Nexus.