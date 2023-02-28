FROM python:3.10-slim-buster

# Inside Container
# Make a new folder inside container
WORKDIR /backend-flask

# Outside Container -> Inside Container
# This contains the libraries you want to install to run the app
COPY requirements.txt requirements.txt

# Inside Container
# 1. Install the python library used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Container
# . means everything in the current directory
# First period . - /backend-flask (outside container)
# Second period . / backend-flask (Inside Container)
COPY . .

# Set Environment Variables (Env Vars)
# Inside Container and will remain set when the container is run
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (Command)
# 2. python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]