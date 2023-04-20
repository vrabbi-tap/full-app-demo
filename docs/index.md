# Acme Fitness Store
The Acme Fitness Store is a demo e-commerce application that showcases how to build a microservices-based architecture using Spring Boot and other open source technologies.

The application consists of several microservices, each responsible for a specific set of features, such as product catalog, shopping cart, payments, authentication, and recommendations. The microservices communicate with each other using REST APIs, and are deployed independently, allowing for scalability and fault tolerance.

In addition to the microservices, the application also includes a frontend web application, which provides a user interface for browsing products, adding them to the shopping cart, and completing orders. The frontend is built using React and communicates with the backend microservices using REST APIs.

## Microservices
The following microservices are included in the Acme Fitness Store:

Catalog Service: Provides product catalog data and reviews.
Cart Service: Manages user shopping carts and orders.
Payment Service: Handles payments and transactions.
Identity Service: Handles user authentication and authorization.
Recommendation Service: Provides personalized product recommendations based on user behavior.
Each microservice has its own README file, which provides detailed information on how to build, run, and deploy the service.

## Frontend
The frontend web application is built using React and communicates with the backend microservices using REST APIs. The following features are included:

Browse products by category and search for specific products.
Add products to the shopping cart and view the cart contents.
Complete orders and view order history.
View product details and reviews.
Sign in or create a new user account.
View personalized product recommendations based on previous purchases.
The frontend also includes several static assets, such as CSS stylesheets, JavaScript files, and images. These assets are served by the Spring Cloud Gateway, which is used to expose the Acme Fitness Store externally.

## Spring Cloud Gateway
The Spring Cloud Gateway is a reverse proxy and load balancer that exposes the Acme Fitness Store demo app externally. It routes incoming requests to the appropriate microservice, based on the URL path and other criteria. See the gateway folder for more information on how to build, run, and deploy the gateway.

## Build and Deployment
To build and run the Acme Fitness Store locally, you will need to have the following tools installed:

Java JDK (version 8 or higher)
Maven (version 3.2 or higher)
Node.js (version 10 or higher)
npm (version 6 or higher)
Docker (version 19 or higher)
Once you have the prerequisites installed, follow these steps:

Clone the Git repository for the Acme Fitness Store.
Build and start each microservice using Maven and Spring Boot.
Build and start the frontend using Node.js and npm.
Build and start the Spring Cloud Gateway using Maven and Spring Boot.
To deploy the Acme Fitness Store to a Kubernetes cluster, you will need to have the following tools installed:

Kubernetes CLI (kubectl)
IBM Cloud CLI (ibmcloud)
IBM Cloud Container Registry Plugin (ibmcloud cr)
IBM Cloud Kubernetes Service Plugin (ibmcloud ks)
Once you have the prerequisites installed, follow these steps:

Create a Kubernetes cluster on IBM Cloud.
Build and push each microservice and the frontend to the IBM Cloud Container Registry.
Deploy each microservice and the frontend to the Kubernetes cluster using kubectl and YAML files.
Deploy the Spring Cloud Gateway to the Kubernetes cluster using kubectl and YAML files.