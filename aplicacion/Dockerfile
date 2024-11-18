FROM python:3.10-alpine

# Establecer el directorio de trabajo en el contenedor
WORKDIR /aplicacion

#Instala las herramientas necesarias
RUN apk add --no-cache --update make curl

#Copia requirements.txt desde el directorio padre
COPY requirements.txt requirements.txt

#Instala las dependencias
RUN pip install -r requirements.txt

#Copia el resto de los archivos al contenedor
COPY . /aplicacion

#Comando para ejecutar la aplicacion
CMD ["gunicorn", "flask_app:app", "--bind", "0.0.0.0:5000"]


