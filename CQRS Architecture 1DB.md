# $\textsf{\color{darkblue}{CQRS - Architecture with 1DB}}$ 

This repository will explain about CQRS architecture by using technology Asp.Net Core and Angular.
<br /> <br />
CQRS is a Architectural pattern that segregates the read and write operations for DB, 
<br /> Here we have 1DB for both read and write.
<br /> <br />
Solution consists of following $\textsf{\color{darkblue}{Projects}}$.
 

1. Entities
2. UseCaseModels or ApplicationModels
3. Commands
4. Queries
5. UseCase or Application
6. Infrastructure
7. Controller

CQRS Architecture Dependency travels towards inwards

# $\textsf{\color{darkblue}{CQRS - Routing}}$ 

```nginx

 Controller
    |
 IMediator
    |
 CommandHandler
    |
 CommandService
    |
 IUnitOfWork
    |
 Repository1
    |
 Repository2
    |
  Commit

```

<br/>

# $\textsf{\color{darkblue}{Dependency Layer}}$ 
```nginx

   Entities

   UseCaseModels

   Commands --> Entities
            --> UseCaseModels

   Queries --> Entities
           --> UseCaseModels

   UseCase  --> Entities
            --> UseCaseModels
            --> Commands
            --> Queries

   Infrastructure --> Entities
                  --> UseCase

   Controller --> Refers UseCase only for Composition Root and use IMediator for Publish "Commands and Queries"
              --> Refers Infrastrucure only for Composition Root.

```

<br />


```nginx

1. Entities or Domain project

      will have only about Entities or Domain

      Value Objects

      Aggregate Root

```

<br />
<br />

```nginx

2. UseCaseModels or ApplicationModels Project

      will have Models needed for UseCase

      that models refer in Commands

      that models refer in Queries

```

<br />
<br />

```nginx

3. Commands Project

      will have only Commands and ICommand with public access.

```

<br />
<br />

```nginx

4. Queries Project

      will have only Queries and IQuery with public access.

```

<br />
<br />

```nginx

5. UseCase or Application project
      
      will have infrastructure interfaces like Repository interfaces
            (ex IRepository, IAuthorRepository)

      unitofwork interfaces (ex IUnitOfWork)

      transaction interfaces (ex ITransaction)

      will have External System Services interfaces (ex IEmailService)

      will have External System Contracts or interfaces (ex IPaymentServiceGateway
            or IAddressValidate)

      will have usecase interfaces (ex IAuthorService)

      will have usecase implementation with internal access specifiers
           (ex internal class AuthorService)

      will have ICommandHandler and CommandHandlers for Command with
           internal access specifier

      will have IQueryHandler and QueryHandler for Queries with
           internal access specifier

      will have IMediator with Public access specifier

      will have implementation for IMediator with internal access specifier

      expose only interfaces and composition root using public access specifiers
            (ex IMediator, RegistorService())

      usecase (AuthorService) implementation should have transactions implemented
         using IUnitOFWork interface

```


```nginx

6. Infrastructure Project

      Should have implementation for Repositories. (ex AuthorRepository)

      Should have implementation for Transaction. (ex EFTransaction)

      Should have implementation for UnitOfWork. (ex UnitOfWork)

      Should have implementation for External Services. (ex EmailService)

      Should have implementation for UseCaseExternalSystemInterfaces.
         (ex PaymentServiceGateway or AddressValidate) 

      All the above four are with internal access specifiers.

      Expose CompositeRoot to register the Dependency injection. (RegisterRepositories() method)

```

```nginx

7. Controller Project

       Should register the services in program.cs

       refer the usecase IMediator and call it to publish command
         and queries.

       Refers UseCase only for Composition Root Register and IMediator.

       Refers Infrastrucure only for Composition Root Register.

```

<br />

