# Instrucciones para uso del entorno de desarrollo

Este documento proporciona las instrucciones necesarias para configurar y utilizar el entorno de desarrollo para el proyecto.

## Requisitos previos

Antes de comenzar, asegúrate de tener instalados los siguientes programas en tu máquina:

- **Git**: Para gestionar el código fuente.
- **Docker**: Para crear entornos aislados mediante contenedores.
- **Docker Compose**: Para orquestar múltiples contenedores de Docker.

## Instalación

### 1. Clonar el repositorio

Primero, clona el repositorio en tu máquina local:

```bash
git clone https://github.com/ramonmoralb/proyecto_final_daw
```
### 2. Configuración del entorno

El proyecto contiene dos carpetas principales: films-backend para el backend y films-frontend para el frontend. Cada una de estas carpetas contiene un archivo de configuración de Docker Compose (docker-compose-dev.yml) para levantar los contenedores de desarrollo correspondientes.
### 3. Levantar los contenedores
## Backend

Para iniciar el contenedor de desarrollo del backend, navega a la carpeta films-backend y ejecuta el siguiente comando:

```bash
cd films-backend
docker-compose -f docker-compose-dev.yml up -d
```
Este comando descargará las imágenes necesarias, construirá los contenedores y pondrá en marcha el backend de la aplicación.


### Frontend

Para iniciar el contenedor de desarrollo del frontend, navega a la carpeta films-frontend y ejecuta el siguiente comando:

```bash
cd films-frontend
docker-compose -f docker-compose-dev.yml up -d
```

Este comando descargará las imágenes necesarias, construirá los contenedores y pondrá en marcha el frontend de la aplicación.
### 4. Acceder a la aplicación

Una vez que ambos contenedores estén en funcionamiento, puedes acceder a la aplicación a través de los siguientes enlaces:

    Backend: Accede al backend en http://films.api.dev.com:8080/  
    Frontend: Accede al frontend en http://films.dev.com:8081/ 

## Para que el navegador de tú máquina pueda resolver el dominio se debe añadir las siguientes instrucciones en el archivo hosts:

```plaintext
127.0.0.1 films.api.dev.com
127.0.0.1 films.dev.com
```
# Ubicacón del archivo hosts:

- **Windows:** `C:\Windows\System32\drivers\etc\hosts`
- **Linux/macOS:** `/etc/hosts`

#### 5. Parar los contenedores

Para detener los contenedores, puedes usar el siguiente comando en cada carpeta (frontend y backend):

```bash
docker-compose -f docker-compose-dev.yml down
```