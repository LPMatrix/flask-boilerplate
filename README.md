# Flask Boilerplate

[![The MIT License](https://img.shields.io/badge/license-MIT-orange.svg?style=flat-square)](LICENSE)

  Flask Boilerplate to quickly get started with production grade flask application with some additional packages and configuration prebuilt.

  You can find an in-depth article on this implementation [here](https://dev.to/idrisrampurawala/flask-boilerplate-structuring-flask-app-3kcd).

# Contributing
  We encourage you to contribute to Flask Boilerplate! Please check out the [Contributing](CONTRIBUTING.md) guidelines about how to proceed.

# Getting Started

### Prerequisites

- Python 3.8.2 or higher
- Up and running Redis client

### Project setup
```sh
# clone the repo
$ git clone https://github.com/idris-rampurawala/flask-boilerplate.git
# move to the project folder
$ cd flask-boilerplate
```

### Creating virtual environment

- Install `pipenv` a global python project `pip install pipenv`
- Create a `virtual environment` for this project
```shell
# creating pipenv environment for python 3
$ pipenv --three
# activating the pipenv environment
$ pipenv shell
# install all dependencies (include -d for installing dev dependencies)
$ pipenv install -d
```
### Configuration

- There are 3 configurations `development`, `staging` and `production` in `config.py`. Default is `development`
- Create a `.env` file from `.env.example` and set appropriate environment variables before running the project

### Running app

- Run flask app `python run.py`
- Logs would be generated under `log` folder

### Running celery workers

- Run redis locally before running celery worker
- Celery worker can be started with following command
```sh
# run following command in a separate terminal
$ celery worker -A celery_worker.celery -l=info  
# (append `--pool=solo` for windows)
```


# Preconfigured Packages
Includes preconfigured packages to kick start flask app by just setting appropriate configuration.

| Package 	| Usage 	|
|-----	|-----	|
| [celery](https://docs.celeryproject.org/en/stable/getting-started/introduction.html) 	| Running background tasks 	|
| [redis](https://redislabs.com/lp/python-redis/) 	| A Python Redis client for caching 	|
| [flask-cors](https://flask-cors.readthedocs.io/) 	| Configuring CORS 	|
| [python-dotenv](https://pypi.org/project/python-dotenv/) 	| Reads the key-value pair from .env file and adds them to environment variable. 	|
| [marshmallow](https://marshmallow.readthedocs.io/en/stable/) 	| A package for creating Schema, serialization, deserialization 	|
| [webargs](https://webargs.readthedocs.io/) 	| A Python library for parsing and validating HTTP request objects 	|

## app
The app directory is the home of your application logic.

It’s autoloaded under the namespace App.

## config
The config directory is used to define the configuration of your application.

It ships with a number of config files, but feel free to create your own.

## database
The database directory is used to store all database related files.

## public
The public directory is used to serve static assets over HTTP.

This directory is mapped to the root of your website:

## resources
The resources directory is used to store presentational files for your application like view templates, LESS/SASS files, uncompiled JavaScript, or even images.

## test
The test directory is used to store all your application tests. The testing package is not included by default – you can install it following the instructions defined here.

# License
 This program is free software under MIT license. Please see the [LICENSE](LICENSE) file in our repository for the full text.