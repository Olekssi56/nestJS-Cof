NestJS project example
=====

This repository is an example application for the [NestJS framework](https://nestjs.com/) in Typescript that exposes a REST API and interacts with both [PostgreSQL](https://www.postgresql.org/) and [MongoDB](https://www.mongodb.com/). The project covers a wide range of topics such as creating controllers, services, entities, data transfer objects, handling request and response data, error handling, input data validation, configuration management, middleware, guards, interceptors, testing, creating a Mongoose model, using it to access MongoDB, adding pagination, and implementing transactions.


Topics
---

This repository has two branches: `main` and `mongodb`. 
The `main` branch focuses on developing a web application using the NestJS framework with a particular emphasis on creating controllers, services, entities, and data transfer objects. It also covers a wide range of other topics such as handling request and response data, error handling, input data validation, configuration management, middleware, guards, interceptors, and testing. Furthermore it provides a solid foundation for building a robust and scalable web application using NestJS, which is a popular Node.js framework for building server-side applications.
The `mongodb` branch is primarily focused on implementing MongoDB functionalities and covers topics such as creating a Mongoose model, using it to access MongoDB, adding pagination, and implementing transactions. It also covers adding indexes to schemas for better performance.

The main branch
--

The `main` branch covers the following topics:

- Create controllers with route parameters
- Request body handling
- Implement response status codes and pagination
- Create services
- Create user-friendly error messages
- Use data transfer objects for input data validation
- Auto-transform payloads to DTO instances
- Handle malicious request data
- Create entities
- Use repositories to access the database
- Establish relations between entities
- Retrieve entities with their relations
- Use cascading inserts and updates
- Add pagination
- Use transactions
- Add indexes to entities and set up migrations
- Use custom environment file paths
- Use schema validation
- Use the Config Service and custom configuration files
- Work with configuration namespaces and partial registration
- Configure dynamic modules asynchronously
- Use binding techniques
- Catch exceptions with filters
- Protect routes with guards
- Use metadata to build generic guards or interceptors
- Add pointcuts with interceptors
- Handle timeouts with interceptors
- Create custom pipes
- Add request logging with middleware
- Create custom param decorators
- Implement URI Versioning
- Use ClassSerializerInterceptor
- Implement a role-based access control
- Use Helmet, Express cors, and rate limiting
- Use the Swagger Module
- Enable CLI plugin
- Decorate model properties
- Add example responses
- Use tags to group resources in the OpenAPI specification
- Create and run test suites in Jest
- Add unit tests
- Create an end-to-end test
- Implement end-to-end test logic


The mongodb branch
--


The `mongodb` branch covers the following additional topics:

- Create a Mongoose Model
- Use a Mongoose Model to Access MongoDB
- Adding Pagination
- Use Transactions
- Adding Indexes to Schemas



Endpoints
---

The REST API is about coffees and includes a few endpoints. Some examples follow.

```
POST http://localhost:3000/v1/auth/login
with JSON data in the request body:
{
    "username": "user",
    "password": "user"
}
or
{
    "username": "admin",
    "password": "admin"
}
This will return an authorization token.
```
```
GET http://localhost:3000/v1/auth/profile
with authorization token.
```
```
GET http://localhost:3000/v1/coffees/flavors?limit={limit}&offset={offset}
with authorization token.
```
```
GET http://localhost:3000/v1/coffees/{id}
with authorization token.
```
```
POST http://localhost:3000/v1/coffees/ 
with authorization token and a user having admin privileges
with JSON data in the request body:
{
  "name": "name",
  "brand": "brand",
  "flavors": [
    "flavor1",
    "flavor2"
  ]
}
```
```
PATCH http://localhost:3000/v1/coffees/{id} 
with authorization token and a user having admin privileges
with JSON data in the request body:
{
  "name": "new_name"
}
```
```
DELETE http://localhost:3000/v1/coffees/{id}
with authorization token and a user having admin privileges.
```


Getting Started
---

To get started with this project, clone the repository to your local machine and install the required dependencies:
```
git clone https://github.com/vittorioexp/NestJS-project-example.git

cd NestJS-project-example

docker-compose up -d

npm install
```

Then rename the `.env.template` file to `.env` and, if necessary, edit it.

To run the application, use the following command:
```
npm run start:dev
```
This will start the application in development mode with hot reloading enabled.

Then connect to the database and enter the following SQL statements to create one admin, one user, and a two coffees:
```
insert into "user" ("username", "password", "role") values ('admin', '8c6976e5b5410415bde908bd4dee15dfb167a9c873fc4bb8a81f6f2ab448a918', 'admin');
insert into "user" ("username", "password", "role") values ('user', '04f8996da763b7a969b1028ee3007569eaf3a635486ddab211d512c85b9df8fb', 'user');
insert into "coffee" ("name", "brand", "inventorId") values ('star trucks coffee', 'star trucks ltd', 1);
insert into "coffee" ("name", "brand", "inventorId") values ('cheap coffee', 'cheap ltd', 2);
```
Now you're ready to hit the endpoints of the application! See the section above for details.


To run unit tests, run the following command:
```
npm run test:watch
```
To run e2e tests, run the following command:
```
npm run test:e2e
```


Contributing
---

If you'd like to contribute to this project, please create a pull request with your changes.
