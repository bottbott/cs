## What is Nest.js?
NestJS is a framework for developing server side Node.js applications. 

## Why Nest.js?
ExpressJS is a barebones framework for designing server side applications. The way that you build an application in NestJS is opinionated and takes on a particular format. This has some pros in that it gives a consistent structure to an application, but can also be a con as soon as your app deviates from this structure.

## App Architecture
### Controllers
Controllers expose routes for the client to connect to the application. The incoming requests are handled by the controller and routed to the appropriate application logic. A controller may have one or more routes.

### Modules
Modules are used to modularize your application. You can abstract your application into different modules which helps prevent you from writing a large monolithic application. You end up with smaller and easier to manage modules. 

### Pipes
Pipes are used to ensure that the right kind of information is flowing into the application. We can control the flow of information into the application by performing validation and transformation of the data.


## Decorators
Classes, methods and parameters are annotated with decorators to provide metadata to NestJS. 
### Class Level
`@Controller('helloWorld')` is an example of a class level decorator. This decorator is used to define a controller. The string passed to the decorator is the route that the controller will be listening on.

### Method Level


### Parameter Level
