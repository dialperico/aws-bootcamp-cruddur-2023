FROM python:3.10-slim-buster

# Inside Container
# Make a new folder inside container
WORKDIR /backend-flask

# Outside Container -> Inside Container
# This containd the libraries want to install to run the app
COPY requirements.txt requirements.txt

# Inside Container
# Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Container
# . means everything in the current directory
# first period . /backend-flask (outside the container)
# scond period . /backend-flask (inside the container)
COPY . .

# Inside Container and will remain set when the container is running
# Set Enviroment Variables (Env Vars)
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
#python 3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]