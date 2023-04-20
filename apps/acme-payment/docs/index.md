# Payment Service
The Payment Service is responsible for handling payments and transactions in the Acme Fitness Store. It provides a REST API that allows clients to initiate and confirm payments, as well as view transaction history.

## API Endpoints
The following endpoints are available:

POST /payments: Initiates a new payment transaction.
POST /payments/confirm: Confirms a previously initiated payment transaction.
GET /transactions: Retrieves a list of all completed transactions.
GET /transactions/{id}: Retrieves details for a specific transaction, identified by its ID.
## Data Model
The Payment Service stores transaction data in a PostgreSQL database. The data model consists of the following table:

transactions: Contains information about each completed transaction, including user ID, payment method, amount, and status.
## Configuration
The Payment Service is configured using environment variables. The following variables are supported:

DATABASE_URL: URL of the PostgreSQL database used to store transaction data. Defaults to postgres://localhost:5432/payment.
STRIPE_API_KEY: Secret API key for Stripe, the payment processing provider used by the Payment Service.
## Build and Deployment
To build and run the Payment Service locally, you will need to have the following tools installed:

Go (version 1.16 or higher)
PostgreSQL (version 10.0 or higher)
Stripe account with an API key
Once you have the prerequisites installed, follow these steps:

Clone the Git repository for the Payment Service.
Run go build to compile the application.
Set the DATABASE_URL environment variable to point to your local PostgreSQL instance.
Set the STRIPE_API_KEY environment variable to your Stripe API key.
Run the compiled binary.
To deploy the Payment Service to a Kubernetes cluster, you will need to have the following tools installed:

Docker
Kubernetes CLI (kubectl)
IBM Cloud CLI
Once you have the prerequisites installed, follow these steps:

Build a Docker image for the Payment Service.
Push the Docker image to a container registry, such as Docker Hub or IBM Cloud Container Registry.
Create a Kubernetes deployment and service for the microservice, using the provided YAML files.
Configure Istio service mesh to secure communication between microservices.