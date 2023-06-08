# Jenkins

Instalación de Jenkins en un host de Windows


## Instalación

Descarga las imágenes y crea el contenedor

```
docker-compose up -d
```

- El fichero **docker-compose.yaml** está configurado para ser utilizado para entornos formativo donde en su interior se tendrá un tomcat que ejecutará aplicaciones.

- El fichero **docker-compose.original.yaml** es el docker-compose que se debe utilizar para ejecutar exclusivamente jenkins

### Configuracion inicial
1. Introduce la clave que aparece en la instalación
2. Selecciona "Install suggested plugins"
3. Introduce los datos de un usuario diferente a admin.
4. Puedes entrar con: http://localhost:8080/ 


### Jenkins-cli

Descarga el jar de jenkins-cli
http://jenkins.loc:8080/jnlpJars/jenkins-cli.jar


Ejecuta en línea de comando de esta forma:

```
java -jar jenkins-cli.jar -s http://192.168.56.101:8080/ -auth myuser:mypass -webSocket help
```


## Referencias
* https://hub.docker.com/r/jenkins/jenkins
* https://www.jenkins.io/doc/book/installing/docker/
* https://www.cloudbees.com/blog/how-to-install-and-run-jenkins-with-docker-compose
* https://medium.com/indigoit/instalar-y-configurar-jenkins-en-un-servidor-para-integraci%C3%B3n-continua-parte-1-78b1a8a749c4

