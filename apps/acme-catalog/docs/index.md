# Product Catalog Microservice
The Product Catalog Microservice is responsible for managing the products available in the Acme Fitness Store. It provides a REST API that allows clients to perform CRUD (Create, Read, Update, Delete) operations on products.

## API Endpoints
The following endpoints are available:

GET /products: Returns a list of all products in the catalog.
GET /products/{id}: Returns details for a specific product, identified by its ID.
POST /products: Creates a new product in the catalog.
PUT /products/{id}: Updates an existing product, identified by its ID.
DELETE /products/{id}: Deletes a product from the catalog, identified by its ID.
## Data Model
The Product Catalog Microservice stores product data in a MongoDB database. The data model consists of the following fields:

id: Unique identifier for the product.
name: Name of the product.
description: Description of the product.
price: Price of the product.
image: URL of an image representing the product.
## Configuration
The Product Catalog Microservice is configured using environment variables. The following variables are supported:

MONGODB_URL: URL of the MongoDB database used to store product data. Defaults to mongodb://localhost:27017/products.
## Build and Deployment
To build and run the Product Catalog Microservice locally, you will need to have the following tools installed:

Go (version 1.16 or higher)
MongoDB (version 4.0 or higher)
Once you have the prerequisites installed, follow these steps:

Clone the Git repository for the Product Catalog Microservice.
Run go build to compile the application.
Set the MONGODB_URL environment variable to point to your local MongoDB instance.
Run the compiled binary.
To deploy the Product Catalog Microservice to a Kubernetes cluster, you will need to have the following tools installed:

Docker
Kubernetes CLI (kubectl)
IBM Cloud CLI
Once you have the prerequisites installed, follow these steps:

Build a Docker image for the Product Catalog Microservice.
Push the Docker image to a container registry, such as Docker Hub or IBM Cloud Container Registry.
Create a Kubernetes deployment and service for the microservice, using the provided YAML files.
Configure Istio service mesh to secure communication between microservices.