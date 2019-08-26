# devops-technoscreen-workshops
Workshops relacionadas a las diferentes areas a tratar en la consultoria de DEVOPS, a continuación los temas que estaremos tratando.

### Descargar imagenes desde un repositorio
```bash
docker pull image-name:tag
docker pull nginx:latest
```

### Listar imagenes en el host
```bash
docker image ls
```
### run
Estructura general de comando docker run
```bash
docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]
```
Ejemplo>>
```bash
docker run -d --name workshop-nginx-01 -p 8080:80 nginx:latest 
```
### Opciones comunmente utilizadas.
- -d
- -p
- --name
- -i
- -t 