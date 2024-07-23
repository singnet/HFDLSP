# Hugging Face Datasets Library to SingularityNET Pipeline

## Table of Contents
1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Installation](#installation)
4. [Usage](#usage)
5. [API Endpoints](#api-endpoints)
6. [Configuration](#configuration)
7. [Database](#database)
8. [Security](#security)
9. [Deployment](#deployment)
10. [Contributing](#contributing)
11. [License](#license)

## Project Overview

This project implements a foundational pipeline to integrate the Hugging Face Datasets library into a technological system. It creates a seamless pipeline for accessing and utilizing Knowledge Graph Question-Answer datasets, fostering efficient integration with Hugging Face's extensive NLP resources. The framework serves as a robust backbone for subsequent integration of specific Hugging Face datasets, enhancing capabilities in the realm of augmenting Artificial General Intelligence (AGI) research.

## Features

- Data retrieval from Hugging Face Datasets library
- Data transformation and schema mapping
- Integration with Neo4j graph database
- RESTful API for dataset access and querying
- Support for multiple datasets:
  - Tree of Knowledge
  - HotpotQA
  - TimeQA
- Security measures including API key authentication
- Deployment on AWS infrastructure

## Installation

1. Clone the repository:
`git clone https://github.com/singnet/HFDLSP.git`

2. Install the required dependencies:
`pip install -r requirements.txt`

3. Set up the environment variables:
- Copy the `.env.example` file to `.env`
- Fill in the necessary environment variables in the `.env` file

4. Set up the Neo4j database (see [Database](#database) section for details)

5. Run database migrations:
`python manage.py migrate`

## Usage

To start the development server:

The API will be available at `http://localhost:8000/`.

## API Endpoints

- `/answer/`: Get answers from the dataset
- `/fetch_dataset/`: Fetch and insert datasets into Neo4j
- `/schema/`: OpenAPI schema
- `/swagger-ui/`: Swagger UI for API documentation

For detailed API documentation, visit the Swagger UI at `/swagger-ui/` when the server is running.

## Configuration

The project uses environment variables for configuration. Key settings include:

- `SECRET_KEY`: Django secret key
- `DEBUG`: Debug mode (set to 0 for production)
- `DJANGO_ALLOWED_HOSTS`: Allowed hosts for Django
- `NEO4J_DATABASE_URL`: URL for the Neo4j database
- `API_KEY`: API key for authentication

Refer to `settings.py` for all available configuration options.

## Database

This project uses Neo4j as its primary database. Ensure you have Neo4j installed and running. Update the `NEOMODEL_NEO4J_BOLT_URL` in `settings.py` or set the `NEO4J_DATABASE_URL` environment variable to point to your Neo4j instance.

## Security

The API is secured using API key authentication. Ensure you set the `API_KEY` environment variable and include it in the `Authorization` header when making requests to the API.

## Deployment

The project is deployed on AWS, but is designed to be deployed on any Cloud service. Key components of the deployment include:

- EC2 instances for hosting the application
- Load balancing and auto-scaling configurations
- CI/CD pipeline for automated testing and deployment

Refer to the deployment documentation for detailed instructions on setting up the AWS infrastructure.

## Contributing

Contributions to this project are welcome. Please follow these steps:

1. Fork the repository
2. Create a new branch for your feature
3. Commit your changes
4. Push to the branch
5. Create a new Pull Request

## License

Apache-2.0 License: http://www.apache.org/licenses/