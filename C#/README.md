# Standard Microsoft .NET Repository

This document provides information about Repository for work project which consists of client applications and/or server applications.

### Work Project
Project for customer, internal or partner -- Not to be confused with .NET project (e.g. `*.csproj` file).

### Client Application
An application that run on user's device. Some client application is able to connect to database directly (e.g. Microsoft SQL Server) such as Database client, Redis client, etc.

### Server Application
An application that run on server, it is updated and deployed by development team. Server application provides data for client application. However, Some server application is able to work as client and access to other services.

## .NET Solution Structure
Solution structure consists of 2 logical parts, but physical path is the same folder.
1. Owner's library that can use in other work projects, it maybe included in the repository to custom or it's implementing.
2. Work project source code.

### Owner's Library
- `Client` -- Folder to store all files/projects for client library. Library in this folder use for client only (Mobile, Windows Application i.e. WPF). 
  - `[Owner].Client` -- Library for every client applications and not depend on any client platforms ex. Library for auto update.
  - `[Owner].Mobile` -- Library for mobile application based on Xamarin project.
    - `[Owner].Mobile` -- Xamarin Portable Class Library (PCL) to share code across platforms.
    - `[Owner].Mobile.Android` -- Xamarin Android application.
    - `[Owner].Mobile.iOS` -- Xamarin iOS application.
    - `[Owner].Mobile.UWP` -- Xamarin UWP application.
  - `[Owner].Wpf` -- Library for WPF application.
- `Core` -- Folder to store all files/projects for client library.
  - `[Owner].Core` -- Library for client/server.
  - `[Owner].[Module]` -- Other libraries for client/server ex. `[Owner].Net`.
- `Server` -- Folder to store all files/projects for server library.
  - `[Owner].Server` -- Library for every server applications and not depend on any server platforms.
  - `[Owner].Web` -- Library for web application only.

### Work Project Source Code
- `Client` -- Folder to store all files/projects for client application.
  - `[Owner].[AppName]` -- Client application.
  - `[Owner].[Mobile AppName]` -- Mobile application based on Xamarin project.
    - `[Owner].[Mobile AppName]`
    - `[Owner].[Mobile AppName].Android`
    - `[Owner].[Mobile AppName].iOS`
    - `[Owner].[Mobile AppName].UWP`
- `Config` -- Folder to store the specific configuration depends on environment ex. dev, test, uat, prod, hotfix.
- `Core` -- Folder to store all files/projects for client/server library.
  - `[Owner].[Solution Name]` -- Business library for solution.
  - `[Owner].[AppName]` -- Business library for application if it use in application only.
- `Documentation` -- All documents that related with how to coding, setting/configuration project or make project to debug or run locally.
- `packages` -- Folder for libraries (NuGet packages)
- `Server` -- Folder to store all files/projects for server application. Application maybe Web Application, Job Scheduler, Long-run process, etc.
  - `[Owner].[AppName].Web` -- Web application.
  - `[Owner].[AppName].WebJobs` -- Web jobs application.
- `Tests` -- Folder to store all files/projects for testing.
  - `[Project].IntegrationTest` -- Integration test project ex. Integration test project for `[Owner].Server` is `[Owner].Server.IntegrationTest`.
  - `[Project].UnitTest` -- Unit test project ex. Unit test project for `[Owner].Server` is `[Owner].Server.UnitTest`.
- `.gitignore` -- Git ignore file. See [Git help](https://git-scm.com/docs/gitignore) and [.gitignore for Visual Studio](https://github.com/github/gitignore/blob/master/VisualStudio.gitignore).
- `[Solution Name].sln` -- Solution contains all projects.
- `[Solution Name].Client.sln` -- Solution contains all client and core projects.
- `[Solution Name].Server.sln` -- Solution contains all server and core projects.

#### Note:
- `[Owner]` is name of owner work project, it can be Company Name, Organization Name, Author or Employer.
- `[AppName]` and `[Mobile AppName]` can be solution name if solution has only one application on server/client.
- In Client, `[AppName]` suffix is *App*, `[Mobile AppName]` suffix is *Mobile*.
- Folder name is not contain `[Mobile AppName]`, `[Solution Name]` is owner's level and can be used in other work projects.
