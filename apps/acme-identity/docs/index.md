# Identity Service
The Identity Service is responsible for managing user authentication and authorization in the Acme Fitness Store. It provides a REST API that allows clients to create and authenticate user accounts, as well as manage user roles and permissions.

## API Endpoints
The following endpoints are available:

POST /register: Creates a new user account.
POST /login: Authenticates a user and generates a JWT (JSON Web Token) for subsequent requests.
GET /users/{id}: Returns details for a specific user, identified by their ID.
PUT /users/{id}: Updates an existing user, identified by their ID.
DELETE /users/{id}: Deletes a user, identified by their ID.
POST /roles: Creates a new user role.
GET /roles/{id}: Returns details for a specific user role, identified by its ID.
PUT /roles/{id}: Updates an existing user role, identified by its ID.
DELETE /roles/{id}: Deletes a user role, identified by its ID.
## Data Model
The Identity Service stores user and role data in a PostgreSQL database. The data model consists of the following tables:

users: Contains user account information, including email, password (hashed), and role ID.
roles: Contains user role information, including name and permissions.
## Configuration
The Identity Service is configured using environment variables. The following variables are supported:

DATABASE_URL: URL of the PostgreSQL database used to store user and role data. Defaults to postgres://localhost:5432/identity.
JWT_SECRET: Secret key used to sign and verify JWT tokens. Defaults to a randomly generated value.
## Build and Deployment
To build and run the Identity Service locally, you will need to have the following tools installed:

Go (version 1.16 or higher)
PostgreSQL (version 10.0 or higher)
Once you have the prerequisites installed, follow these steps:

Clone the Git repository for the Identity Service.
Run go build to compile the application.
Set the DATABASE_URL environment variable to point to your local PostgreSQL instance.
Set the JWT_SECRET environment variable to a secret key of your choice.
Run the compiled binary.
To deploy the Identity Service to a Kubernetes cluster, you will need to have the following tools installed:

Docker
Kubernetes CLI (kubectl)
IBM Cloud CLI
Once you have the prerequisites installed, follow these steps:

Build a Docker image for the Identity Service.
Push the Docker image to a container registry, such as Docker Hub or IBM Cloud Container Registry.
Create a Kubernetes deployment and service for the microservice, using the provided YAML files.
Configure Istio service mesh to secure communication between microservices.