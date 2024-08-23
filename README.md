***
<p align="center">
  <a href="https://shoonya.ai4bharat.org"><img src="https://github.com/AI4Bharat/Shoonya/blob/master/docs/shoonya/logos/shoonya-logo.png" alt="Shoonya" width="550" height="110"></a>
</p>

<p align="center">
    <em>An open source platform to annotate and label data at scale</em>
</p>

<p align="center">
    <a href="https://opensource.org/licenses/MIT" target="_blank">
        <img src="https://img.shields.io/badge/License-MIT-green.svg" alt="License: MIT">
    </a>
</p>

***

*[Shoonya](http://shoonya.ai4bharat.org/)* is an open source platform to annotate and label data at scale, built with a vision to enhance digital presence of under-represented languages in India. 

Shoonya offers support for multiple data types (Ex : parallel datasets, OCR, ASR, TTS etc) and labeling tasks (Ex : parallel datasets, OCR, ASR, TTS etc).

_Shoonya, referring to zero, represents the start. It also represents universality in the sense that several cultures have a similar symbol for zero. We believe that the language resources that we collect in Shoonya will start a valuable open-source movement for Indian language technologies that will be available universally for all to adopt and improve upon._

<br>

## Qualities of a good Data Collection Ecosystem
<p align="center">
  <img src="https://github.com/AI4Bharat/Shoonya/blob/master/docs/shoonya/images/data-collection-ecosystem.png"  width="800" height="350">
</p>

## Challenges faced by Annotators
<p align="center">
  <img src="https://github.com/AI4Bharat/Shoonya/blob/master/docs/shoonya/images/annotator-challenges.png"  width="800" height="420">
</p>

## Why Shoonya?
_The National Language Translation Mission (NLTM) has been announced in the budget by the Honorable Finance Minister in the backdrop of growing demand for accessing online services in local Indian languages. This will enable the wealth of governance-and-policy related knowledge on the Internet being made available in major Indian languages. The Ministry of Electronics and Information Technology (MeitY) has launched 'Bhashini' to help ensure that digital content is readily available to all citizens, in their preferred languages._

_The goal of Bhashini is to develop an ecosystem of innovative practices for data collection, curation, develop technology for speech to speech translation and deliver solutions powered by open data, apps and services. Bhashini shall act as an orchestrator to bring contributions (like data, models etc.) received from government, industry, academia and society into an open “Hundi” or “Repository”. All contributions to Bhashini shall be validated and standardized using a Unified Language Contribution API (ULCA)._
<br>


<p align="center">
  <img src="https://github.com/AI4Bharat/Shoonya/blob/master/docs/shoonya/images/nltm-architecture.png"  width="800" height="450">
</p>
  
[Reference : Bhashini Whitepaper](https://www.meity.gov.in/writereaddata/files/Bhashini%20Whitepaper%20ver%206.0.pdf)

Also read [Bhashini Data Report](https://indicnlp.ai4bharat.org/static/documents/DMU_Data_Report_May_2022.pdf) 

Naturally, data collection/curation becomes the core of building state-of-the-art NLP ML models. This is where Shoonya comes into picture. Shoonya provides the platform for the Annotators/Translators to create such large datasets with highest quality.


<p align="center">
  <img src="https://github.com/AI4Bharat/Shoonya/blob/master/docs/shoonya/images/shoonya-layer.png"  width="600" height="400">
</p>


## Goals
* Support all possible data types and labeling tasks
* Build a reliable & scalable platform beneath Shoonya
* Keep the UI simple and intuitive

## Features of Shoonya
<p align="center">
  <img src="https://github.com/AI4Bharat/Shoonya/blob/master/docs/shoonya/images/shoonya-features.png"  width="800" height="350">
</p>

## Overview and Demo Video
[![Shoonya Overview & Demo](https://img.youtube.com/vi/N4PBSB2fQto/0.jpg)](https://www.youtube.com/watch?v=N4PBSB2fQto)

## Cloning this master repo

```
git clone --recurse-submodules https://github.com/AI4Bharat/Shoonya
```

## Backend Setup

### Clone the Shoonya-Backend repository from GitHub to your local machine.
    git clone https://github.com/AI4Bharat/Shoonya-Backend.git

### Create a virtual environment for the project. Replace  with your preferred environment name.
    python3 -m venv 

### Activate the virtual environment. This ensures that the packages you install are isolated from the global Python environment.
    source /bin/activate

### Install all required Python packages listed in the requirements-dev.txt file.
    pip install -r deploy/requirements-dev.txt

### Set up the environment variables needed for the project by copying the example environment file.
    cp .env.example ./backend/.env

### Generate a new secret key for Django (within the virtual environment):
### Open a Python shell.
    python backend/manage.py shell

    # Import the utility function to generate a secret key.
    >> from django.core.management.utils import get_random_secret_key

    # Generate and print a new secret key.
    >> get_random_secret_key()

#### Copy the generated secret key and paste it into the .env file as the value for SECRET_KEY.

### Docker Installation
### Build the Docker containers as defined in the docker-compose-local.yml file.
    docker-compose -f docker-compose-local.yml build

### Run the containers in detached mode (-d flag). This will start up all the services defined in the Docker Compose file.
    docker-compose -f docker-compose-local.yml up -d

### Run Migrations
#### The following steps are required only when you run the project for the first time or after making changes to the models.

    # Check if there are any pending migrations.
    docker-compose exec web python backend/manage.py makemigrations 

    # Apply all pending migrations to the database.
    docker-compose exec web python backend/manage.py migrate

### Create a superuser for accessing the Django admin interface (required only once).
    docker-compose exec web python backend/manage.py createsuperuser

### Run the Django development server within the Docker container.
    docker-compose exec web python backend/manage.py runserver


## Frontend Setup

### Clone the Shoonya-Frontend repository from GitHub to your local machine.
    git clone https://github.com/AI4Bharat/Shoonya-Frontend.git

### Change directory to the newly cloned Shoonya-Frontend folder.
    cd Shoonya-Frontend

### Install the necessary dependencies for the project. 
#### The --force flag is used to bypass conflicts with the existing dependencies.
    npm i --force

### Start the development server. This will run the frontend application on a local server.
    npm start

## Communication Forum
Any information/help/discussion required, can be taken up using the following link :
https://github.com/AI4Bharat/Shoonya/discussions


## Code of Conduct
This project adheres to the Contributor Covenant [code of conduct](CODE_OF_CONDUCT.md).
By participating, you are expected to uphold this code. Please report unacceptable behavior to opensource@ai4bharat.org.
