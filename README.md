# Jenkins Lab

## Ejecutar Docker Compose

Para ejecutar Docker Compose, asegúrate de que tengas Docker Compose instalado en tu sistema. Luego, sigue estos pasos:

1. Navega a la ubicación donde se encuentra tu archivo `docker-compose.yml`.

    Asegúrate de que el archivo docker-compose.yml tenga las siguientes especificaciones:
    ```yaml
    version: '3.7'

    services:
      jenkins:
        image: jenkins/jenkins:lts
        ports:
          - "8080:8080"
          - "3000:3000"
        volumes:
          - jenkins_data:/var/jenkins_home

    volumes:
      jenkins_data:
        name: jenkins_data
    ```
    

2. Ejecuta el siguiente comando en tu terminal para iniciar los contenedores definidos en el archivo `docker-compose.yml`:

```bash
docker-compose up -d
```
![Ejemplo de imagen](evidences/jenkins.png)

3. Extraer passwords

```bash
docker logs id_container
```

```bash
docker exec id_container cat /var/jenkins_home/secrets/initialAdminPassword
```
