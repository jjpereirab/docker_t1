Fundamentos de Docker
https://platzi.com/cursos/docker-fundamentos/


----------------------------- html_simple_nginx
ver Dockerfile***

construir imagen
    docker build -t webclaire:latest .

una vez existe la imagen, crear el contenedor
	docker run -it --rm -d -p 8080:80 --name web webclaire

ejecutar url
    http://localhost:8080/linktree.html


----------------------------- api_python_flask
iniciar servidor local con flask
    python -m flask run

luego la url va con el metodo de la api definido en app.py
    <localhost>/getMyInfo

en docker hub  https://hub.docker.com/ se puede buscar que version de python usar para el contenedor

ver Dockerfile***

    FROM python:3.12-alpine3.17 establece una imagen base ligera de Python 3.12 sobre Alpine Linux 3.17. 
    WORKDIR /app define el directorio de trabajo dentro del contenedor, todos los comandos posteriores se ejecutarán dentro de /app.
    COPY requirements.txt requirements.txt copia el archivo de dependencias, 
    RUN pip install -r requirements.txt instala los paquetes necesarios con pip. 
    COPY . . copia todo el código y archivos del proyecto al contenedor. 
    CMD [ "python", "-m", "flask", "run", "--host=0.0.0.0" ] ejecuta Flask y lo expone en la dirección 0.0.0.0 para que sea accesible desde cualquier IP dentro de la red del contenedor.

CMD define el proceso que se ejecutará cuando el contenedor inicie, mientras que RUN se usa para ejecutar comandos durante la construcción de la imagen y su resultado se guarda en la capa de la imagen.

