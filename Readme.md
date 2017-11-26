## Standard Microsoft .NET Repository

This document provides information about Repository for work project which consists of client applications and/or server applications.

#### Work Project
Project for customer, internal or partner -- Not to be confused with .NET project (e.g. `*.csproj` file).

#### Client Application
An application that run on user's device. Some client application is able to connect to database directly (e.g. Microsoft SQL Server) such as Database client, Redis client, etc.

#### Server Application
An application that run on server, it is updated and deployed by development team. Server application provides data for client application. However, Some server application is able to work as client and access to other services.

### .NET Solution Structure
- `Client` -- Folder that holds all files/projects for client application/library. Library in this folder use for client only (Mobile, Windows Application i.e. WPF). 
  - `[Owner].Client` -- Library for every client applications and not depend on any client platforms ex. Library for auto update.
  - `[Owner].Mobile` -- Library for mobile application based on Xamarin project.
    - `[Owner].Mobile` -- Xamarin Portable Class Library (PCL) to share code across platforms.
    - `[Owner].Mobile.Android` -- Xamarin Android application.
    - `[Owner].Mobile.iOS` -- Xamarin iOS application.
    - `[Owner].Mobile.UWP` -- Xamarin UWP application.
  - `[Owner].Wpf` -- Library for WPF application.
  - `[Owner].[AppName]` -- Client application.
  - `[Owner].[Mobile AppName]` -- Mobile application based on Xamarin project.
    - `[Owner].[Mobile AppName]`
    - `[Owner].[Mobile AppName].Android`
    - `[Owner].[Mobile AppName].iOS`
    - `[Owner].[Mobile AppName].UWP`
- `Config` -- Folder that holds the specific configuration depends on environment ex. dev, test, uat, prod, hotfix.
- `Core` -- Folder that holds all files/projects for client/server library.
  - `[Owner].Core` -- Library for client/server (Owner's library and able to share with other work projects).
  - `[Owner].[Solution Name].Core` -- Business library for solution.
  - `[Owner].[AppName].Core` -- Business library for application if it use in application only.
- `Documentation` -- All documents.
- `packages` -- Folder for libraries (NuGet packages)
- `Server` -- Folder that holds all files/projects for server application/library. Application maybe Web Application, Job Scheduler, Long-run process, etc.
  - `[Owner].Server` -- Library for every server applications and not depend on any server platforms.
  - `[Owner].Web` -- Library for web application only.
  - `[Owner].[AppName].Web` -- Web application.
- `Tests` -- Folder that holds all files/projects for testing.
  - `[(Client|Core|Server)]` -- Folder that holds all files/project to test project in client, core or server respectively.
    - `[Project].IntegrationTest` -- Integration test project ex. Integration test project for `[Owner].Server` is `[Owner].Server.IntegrationTest`.
    - `[Project].UnitTest` -- Unit test project ex. Unit test project for `[Owner].Server` is `[Owner].Server.UnitTest`.
- `.gitignore` -- Git ignore file. See [Git help](https://git-scm.com/docs/gitignore) and [.gitignore for Visual Studio](https://github.com/github/gitignore/blob/master/VisualStudio.gitignore).
- `LICENSE` -- License file. See [Licensing a repository](https://help.github.com/articles/licensing-a-repository/) and [Licenses](https://choosealicense.com/licenses/).
- `README.md` -- README file contains information about work project.
- `[Solution Name].sln` -- Solution contains all projects.
- `[Solution Name].Client.sln` -- Solution contains all client and core projects.
- `[Solution Name].Server.sln` -- Solution contains all server and core projects.

Note:
- `[Owner]` is name of owner work project, it can be Company Name, Organization Name, Author or Employer.
- `[AppName]` and `[Mobile AppName]` can be solution name if solution has only one application on server/client.
- Folder name is not contain `[Mobile AppName]`, `[Solution Name]` is owner's level and can be used in other work projects.
