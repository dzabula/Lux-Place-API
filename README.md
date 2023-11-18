# Lux-Place-API
link to view app: 

The application is intended for renting apartments to users for a certain period.


The project consists of 5 layers (Domain, DataAccess, Application, Implementation and API).
The domain is the highest layer, which does not depend on any other layer. Represents database tables, code first approach was used.
DataAccess is another layer, which depends on the "Domain" layer. It is responsible for connecting to the database and configuring the database tables.
Application is the third layer. which depends on "Domain" and "DataAccess" layer. It is responsible for software abstraction. It indicates how it will be done
functionality to implement
Implementation is the fourth layer, which depends on the previous three layers. It is responsible for the specific implementation, executes queries against the database,
processes data etc.
The API is the lowest layer and depends on all higher layers. He is responsible for serving the client with data. Defines dependency container, endpoints, controllers, middleware.
It is responsible for user authentication as well as exception management.

During the development of the software, all SOLID principles were respected.

Used design patterns: facades, strategy, Singleton,
Template Method, Composite, Observer...

Used technical and architectural concepts: Dependency Injection and CQRS (Command and Query Responsibility Segregation).

DBMS used: Microsoft SQL Server

Data transfer is in JSON format.

Authentication is performed using a JWT token
There are 3 basic roles for users: authorized, authorized, administrators
Each user, regardless of the role, can individually add or remove rights to perform a useCase operation.
Each UseCase has its own ID, each user has an array of UseCase IDs that they can execute.
Exception management is implemented at the global level - Global Exception Handler class.
The log of each operation is performed in the Implementation layer (UseCaseHangler), where when performing any operation, data about it, the user and the time are recorded in the database.
