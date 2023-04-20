# Spring Cloud Gateway
The Spring Cloud Gateway is a reverse proxy and load balancer that exposes the Acme Fitness Store demo app externally. It routes incoming requests to the appropriate microservice, based on the URL path and other criteria.

## Routes
The Spring Cloud Gateway is configured using YAML files that define routes for each microservice in the Acme Fitness Store. The following routes are defined:

/api/catalog/**: Routes to the Catalog Service, which provides product catalog data and reviews.
/api/cart/**: Routes to the Cart Service, which manages user shopping carts and orders.
/api/payment/**: Routes to the Payment Service, which handles payments and transactions.
/api/identity/**: Routes to the Identity Service, which handles user authentication and authorization.
/api/recommendation/**: Routes to the Recommendation Service, which provides personalized product recommendations based on user behavior.
In addition to these microservice routes, the Spring Cloud Gateway also provides routes for static assets and other resources:

/css/**, /js/**, /images/**: Routes to static assets used by the frontend web application.
/login, /logout: Routes to the authentication endpoints provided by the Identity Service.
/favicon.ico: Routes to the application icon used in the browser tab.
## Filters
The Spring Cloud Gateway can also apply filters to incoming requests, such as authentication, rate limiting, and caching. The following filters are currently applied:

RewritePath: Rewrites the incoming URL path to remove the /api prefix.
AddRequestHeader: Adds a X-Customer-Id header to the request, based on the customerId query parameter.
Auth: Authenticates the request using JWT tokens provided by the Identity Service.
RateLimiter: Limits the rate of incoming requests, to prevent abuse.
Caching: Caches responses from the microservices, to improve performance.
## Configuration
The Spring Cloud Gateway is configured using YAML files and environment variables. The following files are used:

application.yml: Main configuration file, which sets properties such as server port and logging level.
gateway.yml: Route configuration file, which defines routes to the microservices and other resources.
bootstrap.yml: Bootstrap configuration file, which sets properties such as the application name and configuration server URL.
The following environment variables are supported:

SPRING_APPLICATION_NAME: Name of the Spring Boot application.
SPRING_PROFILES_ACTIVE: Comma-separated list of active profiles, such as dev or prod.
SPRING_CLOUD_CONFIG_URI: URL of the configuration server, which provides externalized configuration.
SPRING_CLOUD_CONFIG_USERNAME: Username for accessing the configuration server, if authentication is required.
SPRING_CLOUD_CONFIG_PASSWORD: Password for accessing the configuration server, if authentication is required.
SPRING_CLOUD_CONFIG_LABEL: Git label or branch for the configuration files.
## Build and Deployment
To build and run the Spring Cloud Gateway locally, you will need to have the following tools installed:

Java JDK (version 8 or higher)
Maven (version 3.2 or higher)
Once you have the prerequisites installed, follow these steps:

Clone the Git repository for the Spring Cloud Gateway.
Set the required environment variables in a .env file, or using your preferred method.
Run mvn spring-boot:run to start the gateway.
To deploy the Spring Cloud Gateway to a Kubernetes cluster, you will need to have the following tools installed:

Docker
Kubernetes CLI (kubectl)
IBM Cloud