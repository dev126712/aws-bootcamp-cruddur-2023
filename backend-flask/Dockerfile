FROM python:3.10-slim-buster

# Container
WORKDIR /backend-flask

# Inside Container to Ouside Container
# This contains the requirements file that lists the libraries we want to install
COPY requirements.txt requirements.txt

# Inside container to outside container
# Install the python libraries used for the app
# This is done by pip3, the python package manager
RUN pip3 install -r requirements.txt

# Outside container to inside container
# This contains the source code of the app
# . means everything current directory<
# First period  means . - /backend-flask (outside container)
# Second period means . - /backend-flask (inside container)
COPY . .

# Set Environment VariablesÊnv vars
# Inside container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# CMD (command) is the command that will be run when the container starts
# python3 -m  flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"] 