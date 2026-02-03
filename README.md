# $\textsf{\color{darkblue}{Architecture}}$ 

This repository will discuss about the different architectures in software.
Currently we listed out below items

 $\textsf{\color{darkblue}{1. Layered Architecture}}$ <br />
 $\textsf{\color{darkblue}{2. Onion Architecture}}$   <br />
 $\textsf{\color{darkblue}{3. Hexagonal Architecture}}$ <br />
 $\textsf{\color{darkblue}{4. Clean Architecture}}$ <br />
 $\textsf{\color{darkblue}{5. CQRS Architecture}}$ <br />

Solution consists of following projects

```typescript

1. Entities or Domain or Business 
2. UseCase or Application 
3. Infrastructure or DataAccess or Adapters
4. Controller

5. Ports (only for Hexagonal arch project)
6. ApplicationModels (only for CQRS arch project)
7. Commands (only for CQRS arch project)
8. Queries (only for CQRS arch project)

```
<br />

<br />

Architecture are differ based on the **RepositoryAndExternalSystems** Interfaces placed

1. For **Layered** Architecture Repository Interfaces placed in $\textsf{\color{blue}{Domain Layer}}$, ExternalSystems interfaces are placed
   <br /> in $\textsf{\color{blue}{Application Layer}}$.
3. For **Hexagonal** Architecture RepositoryAndExternalSystems Interfaces are placed in separate project as $\textsf{\color{blue}{Ports Layer}}$
   <br /> and its implementation are in $\textsf{\color{blue}{Adapter Layer}}$.
4. For **Clean** Archtecture RepositoryAndExternalSystems Interfaces is placed in $\textsf{\color{blue}{UseCase Layer}}$
   or $\textsf{\color{blue}{Application Layer}}$.
6. For **Onion** Archtecture Repository Interfaces are in Domain Layer And ExternalSystems Interfaces are placed
   <br /> in $\textsf{\color{blue}{UseCase Layer}}$ or $\textsf{\color{blue}{Application Layer}}$.
8. For **CQRS** Architecture RepositoryAndExternalSystems Interfaces is placed in $\textsf{\color{blue}{UseCase Layer}}$ or $\textsf{\color{blue}{Application Layer}}$.
   <br /> Additionally we have $\textsf{\color{blue}{Commands Project}}$ is for commands model and $\textsf{\color{blue}{Queries Project}}$ is for queries model
   <br /> and $\textsf{\color{blue}{UseCaseModels Project}}$ is for Models require for UseCase Project, Command Project and Queries Project.
   
<br />
<br />

What are the interfaces present in **RepositoryAndExternalSystems** Interfaces

```typescript

Repository Interfaces

1. IUnitOFWork
2. ITransaction
3. IRepository
4. I{Entity}Repository

ExternalSystems Interfaces

5. IEmailService
6. ILoggingService
7. IPaymentService
8. IExternalSystemInterfaces

```


