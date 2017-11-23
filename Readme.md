## Standard Microsoft .NET Repository

This document provides information about Repository for work project which consists of client applications and/or server applications.

#### Work project
Project for customer, internal or partner -- Not to be confused with .NET project (e.g. `*.csproj`).

#### Client Application
An application that run on user's device. Some client application is able to connect to database directly (e.g. Microsoft SQL Server) such as Database client, Redis client, etc.

#### Server Application
An application that run on server, it is updated and deployed by development team. Server application provides data for client application. However, Some server application is able to work as client and access to other services.

### .NET Solution Structure
- Client -- Folder that holds all files/projects for client application/library. Library in this folder use for client only. 
  - **[Owner]**.Client -- Library for every client applications (Mobile, Windows Application i.e. WPF) and not depend on any client platforms ex. Library for auto update.
  - **[Owner]**.Mobile -- Library for mobile application based on Xamarin project
    - **[Owner]**.Mobile -- Xamarin Portable Class Library (PCL) to share code across platforms
    - **[Owner]**.Mobile.Android -- Xamarin Android
    - **[Owner]**.Mobile.iOS -- Xamarin iOS
    - **[Owner]**.Mobile.UWP -- Xamarin UWP
  - **[Owner]**.Wpf -- Library for WPF application
  - **[Owner]**.**[AppName]** -- Client application
  - **[Owner]**.**[Mobile AppName]** -- Mobile application based on Xamarin Project
    - **[Owner]**.**[Mobile AppName]**
    - **[Owner]**.**[Mobile AppName]**.Android
    - **[Owner]**.**[Mobile AppName]**.iOS
    - **[Owner]**.**[Mobile AppName]**.UWP
- Core -- Folder that holds all files/projects for client/server library.
  - **[Owner]**.Core -- Library for client/server (Owner's library and able to share with other work projects)
  - **[Owner]**.**[Solution Name]** -- Business library for solution
  - **[Owner]**.**[AppName]** *(optional)* -- Business library for application if it use in application only.
- Documentation -- All documents
- Server -- Folder that holds all files/projects for server application/library. Application maybe Web Application, Job Scheduler, Long-run process, etc.
- Tests

Note:
- **[Owner]** is name of owner code, it can be Company Name, Organization Name, Author or Employer.
- **[AppName]** and **[Mobile AppName]** can be solution name if solution has only one application on server/client.
- Folder name is not contain **[Mobile AppName]**, **[Solution Name]** is owner's level and can be use in other work projects.
