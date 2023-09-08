# Service A Readme

Service A consists of a GraphQL backend service with basic authentication endpoints, including Signup and Login. The main purpose of Service A is to provide GraphQL functionality and handle user-related operations. Additionally, Service A maintains a connection with Service B, which is responsible for managing MongoDB schema models and GraphQL type definitions updates.

## Setup Instructions

To set up and run Service A locally or in a deployment environment, follow these instructions:

### Prerequisites

1. Node.js and npm should be installed on your system.

2. MongoDB should be set up and running. You will need the MongoDB connection URI, which you can configure in the `config.js` file.

### Installation

1. Clone the repository and navigate to the Service A directory:

   ```bash
   git clone <repository_url>
   cd service-a
   ```

2. Install the project dependencies:

   ```bash
   npm install
   ```

3. Update the MongoDB connection URI in the `config.js` file:

   ```javascript
   export const MONGODB = "your_mongodb_uri_here";
   ```

4. Ensure that Service B is running and accessible. Service A communicates with Service B to fetch and update GraphQL type definitions and UserModel files.

### Running the Service

To start the GraphQL service and enable communication with Service B `https://github.com/JoshIri360/upddatescheme-service-b`:

```bash
npm start
```

The GraphQL service will be accessible at `http://localhost:4000`.

### Communication with Service B

Service A communicates with Service B to update GraphQL type definitions and UserModel files. This communication is triggered automatically when Service A starts.

- To fetch and update GraphQL type definitions, Service A sends a GET request to `http://localhost:3001/graphql-config`.

- To fetch and update the UserModel file, Service A sends a GET request to `http://localhost:3001/mongodb-config`.

### Local Testing

You can test the GraphQL service locally using tools like Postman or GraphQL clients. The GraphQL schema is defined in the `typeDefs.js` file, and the resolvers are defined in the `userResolvers.js` file. Customize these files to add your own GraphQL operations and logic.

### Deployment

For deployment, you can use platforms like Heroku, AWS, or any other hosting service of your choice. Make sure to configure environment variables for sensitive data, such as database connection details and authentication secrets.

With Service A set up and running, you can build and expand your GraphQL backend while seamlessly updating GraphQL type definitions and database models from Service B.
