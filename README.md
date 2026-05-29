# Proyecto Semestral Backend

## Descripción

Backend compuesto por dos microservicios:

* Ventas
* Despachos

Los servicios fueron desarrollados con Spring Boot y desplegados mediante contenedores Docker sobre AWS.

## Tecnologías Utilizadas

* Java
* Spring Boot
* MySQL
* Docker
* Docker Compose
* GitHub Actions
* Docker Hub
* AWS EC2
* AWS Systems Manager (SSM)

## Arquitectura

La solución utiliza una arquitectura de tres capas:

### Capa Web

Frontend React desplegado en EC2 Web.

### Capa Aplicación

EC2 App con los contenedores:

* ventas-api
* despacho-api

### Capa Datos

EC2 Datos con:

* mysql-db

Base de datos:

* ventasdb

## Puertos Utilizados

| Servicio     | Puerto |
| ------------ | ------ |
| Frontend     | 80     |
| Ventas API   | 8080   |
| Despacho API | 8081   |
| MySQL        | 3306   |

## Ejecución Local

### Clonar repositorio

```bash
git clone https://github.com/BertaSoto/proyecto-semestral-backend.git
cd proyecto-semestral-backend
```

### Ejecutar servicios

```bash
docker compose up -d
```

### Verificar contenedores

```bash
docker ps
```

## CI/CD

La automatización se realiza mediante GitHub Actions.

Flujo:

1. Push a rama deploy.
2. Build de imágenes Docker.
3. Publicación en Docker Hub.
4. Ejecución de comandos remotos mediante AWS Systems Manager.
5. Actualización automática de contenedores en EC2.

## Imágenes Docker

* bertasotoj/despacho-backend
* bertasotoj/ventas-backend

## Autoras

* Daniela Gómez Palacios
* Berta Soto

