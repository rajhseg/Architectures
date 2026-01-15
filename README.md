# $\textsf{\color{darkblue}{Architecture}}$ 

This repository will discuss about the different architectures in software.
Currently we listed out below items

 $\textsf{\color{darkblue}{1. Layered Architecture}}$ <br />
 $\textsf{\color{darkblue}{2. Onion Architecture}}$   <br />
 $\textsf{\color{darkblue}{3. Hexagonal Architecture}}$ <br />
 $\textsf{\color{darkblue}{4. Clean Architecture}}$ <br />

Solution consists of following projects

```typescript

1. Entities or Domain or Business 
2. UseCase or Application 
3. Infrastructure or DataAccess or Adapters
4. Controller

5. Ports (only for Hexagonal arch project)

```
<br />

<br />

Architecture are differ based on the **RepositoryAndExternalSystems** Interfaces placed

1. For **Layered** Architecture Repository Interfaces placed in $\textsf{\color{blue}{Domain Layer}}$, ExternalSystems interfaces in $\textsf{\color{blue}{Application Layer}}$.
2. For **Hexagonal** Architecture RepositoryAndExternalSystems Interfaces placed in separate project as $\textsf{\color{blue}{Ports Layer}}$.
3. For **Clean** and **Onion** Archtecture RepositoryAndExternalSystems Interfaces is placed in $\textsf{\color{blue}{UseCase Layer}}$ or $\textsf{\color{blue}{Application Layer}}$.
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


