# our base image
 FROM alpine:latest

 # Install python and pip
 RUN apk add --update --no-cache curl py-pip

 # install Python modules needed by the Python app
 COPY requirements.txt /usr/src/app/
 RUN pip install --no-cache-dir -r /usr/src/app/requirements.txt

 # copy files required for the app to run
 COPY app.py /usr/src/app/
 COPY templates/about.html /usr/src/app/templates/
 COPY templates/home.html /usr/src/app/templates/
 COPY templates/template.html /usr/src/app/templates/
 COPY static/css/template.css /usr/src/app/static/css/

 # tell the port number the container should expose
 EXPOSE 5000
 
 # run the application
 CMD [ "python3", "/usr/src/app/app.py" ]