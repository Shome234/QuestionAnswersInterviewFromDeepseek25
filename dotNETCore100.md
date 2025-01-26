# Top 100 .NET Core Interview Questions and Answers for Experienced Developers

Here are the **answers** to the **top 100 .NET Core interview questions** for experienced developers. These answers are concise and to the point, covering the key concepts and practical aspects of .NET Core.

---

## 1. .NET Core Fundamentals

1. **What is .NET Core, and how is it different from .NET Framework?**
   - **.NET Core** is a cross-platform, high-performance, open-source framework for building modern applications. Unlike **.NET Framework**, which is Windows-only, .NET Core supports Windows, Linux, and macOS.

2. **Explain the architecture of .NET Core.**
   - .NET Core consists of:
     - **CoreCLR**: The runtime for executing .NET applications.
     - **CoreFX**: A set of libraries for common functionality.
     - **Roslyn**: The compiler for C# and VB.NET.
     - **CLI Tools**: Command-line tools for building and running applications.

3. **What are the key features of .NET Core?**
   - Cross-platform, high performance, modular, dependency injection, built-in support for microservices, and cloud-native development.

4. **What is the difference between .NET Core and .NET 5/6/7/8?**
   - Starting with **.NET 5**, Microsoft unified .NET Core, .NET Framework, and Xamarin into a single platform called **.NET**. .NET 5/6/7/8 are successors to .NET Core 3.1, with additional features and improvements.

5. **What is the role of Program.cs and Startup.cs in .NET Core?**
   - **Program.cs**: The entry point of the application, where the host is configured.
   - **Startup.cs**: Configures services and the request pipeline (in ASP.NET Core).

6. **What is the difference between IHost and IWebHost in .NET Core?**
   - **IHost**: Used for generic hosting (e.g., console apps).
   - **IWebHost**: Used for hosting web applications (ASP.NET Core).

7. **What is the purpose of appsettings.json in .NET Core?**
   - It stores configuration settings like connection strings, logging levels, and custom settings.

8. **How does dependency injection work in .NET Core?**
   - It is built into the framework. Services are registered in Startup.cs and injected into constructors or methods.

9. **What is the difference between AddTransient, AddScoped, and AddSingleton?**
   - **AddTransient**: A new instance is created every time.
   - **AddScoped**: A single instance is created per request.
   - **AddSingleton**: A single instance is shared for the entire application lifetime.

10. **What is middleware in .NET Core, and how does it work?**
    - Middleware is software components that handle requests and responses. They are executed in the order they are added to the pipeline.

---

## 2. ASP.NET Core

11. **What is ASP.NET Core, and how is it different from ASP.NET?**
    - ASP.NET Core is a cross-platform, high-performance framework for building web applications. Unlike ASP.NET, it is modular and supports modern web development practices.

12. **Explain the request pipeline in ASP.NET Core.**
    - The request pipeline consists of middleware components that process HTTP requests and responses in sequence.

13. **What is the role of UseRouting and UseEndpoints in ASP.NET Core?**
    - **UseRouting**: Matches incoming requests to routes.
    - **UseEndpoints**: Executes the matched route.

14. **How do you configure routing in ASP.NET Core?**
    - Use `app.UseEndpoints` with `MapControllerRoute` or attribute routing.

15. **What is the difference between Map, MapGet, and MapPost?**
    - **Map**: Maps a route to a delegate.
    - **MapGet**: Maps a GET request to a delegate.
    - **MapPost**: Maps a POST request to a delegate.

16. **How do you handle errors in ASP.NET Core?**
    - Use `app.UseExceptionHandler` for global error handling.

17. **What is the purpose of UseExceptionHandler?**
    - It catches exceptions and redirects to an error page or handler.

18. **How do you implement logging in ASP.NET Core?**
    - Use `ILogger<T>` and configure logging providers in `appsettings.json`.

19. **What is the difference between ILogger and ILogger<T>?**
    - `ILogger<T>` is a generic version of `ILogger` that includes the category (usually the class name).

20. **How do you implement authentication and authorization in ASP.NET Core?**
    - Use `AddAuthentication` and `AddAuthorization` in `Startup.cs` and apply `[Authorize]` attributes.

---

## 3. Dependency Injection

21. **What is dependency injection, and why is it important?**
    - It is a design pattern that promotes loose coupling by injecting dependencies rather than creating them.

22. **How do you register services in .NET Core?**
    - Use `services.AddTransient`, `services.AddScoped`, or `services.AddSingleton` in `Startup.cs`.

23. **What is the difference between IServiceCollection and IServiceProvider?**
    - **IServiceCollection**: Used to register services.
    - **IServiceProvider**: Used to resolve services.

24. **How do you resolve services manually in .NET Core?**
    - Use `GetService<T>` or `GetRequiredService<T>` from `IServiceProvider`.

25. **What is the difference between constructor injection and method injection?**
    - **Constructor injection**: Dependencies are injected via the constructor.
    - **Method injection**: Dependencies are injected via method parameters.

---

## 4. Entity Framework Core

31. **What is Entity Framework Core, and how is it different from Entity Framework?**
    - EF Core is a lightweight, cross-platform ORM. It is more modular and extensible than EF.

32. **How do you configure a DbContext in EF Core?**
    - Override `OnConfiguring` or use `AddDbContext` in `Startup.cs`.

33. **What is the difference between DbSet and DbQuery?**
    - **DbSet**: Represents a table.
    - **DbQuery**: Represents a query (removed in EF Core 3.0).

34. **How do you perform migrations in EF Core?**
    - Use `Add-Migration` and `Update-Database` commands.

35. **What is the difference between Add-Migration and Update-Database?**
    - **Add-Migration**: Creates a migration file.
    - **Update-Database**: Applies migrations to the database.

---

## 5. REST APIs and Web APIs

41. **How do you create a REST API in .NET Core?**
    - Use `[ApiController]` and `[Route]` attributes with action methods.

42. **What is the difference between [HttpGet], [HttpPost], [HttpPut], and [HttpDelete]?**
    - They define the HTTP method for the action.

43. **How do you version a REST API in .NET Core?**
    - Use URL-based versioning, query string versioning, or header versioning.

44. **What is the purpose of [FromBody], [FromQuery], and [FromRoute]?**
    - They specify where to bind the action method parameters.

45. **How do you implement pagination in a REST API?**
    - Use `Skip` and `Take` methods with query parameters.

---

## 6. Performance Optimization

51. **How do you optimize the performance of a .NET Core application?**
    - Use asynchronous programming, caching, and efficient database queries.

52. **What is the difference between async and sync programming in .NET Core?**
    - **async**: Non-blocking, improves scalability.
    - **sync**: Blocking, simpler but less scalable.

53. **How do you use Task and ValueTask in .NET Core?**
    - **Task**: Represents an asynchronous operation.
    - **ValueTask**: A lightweight alternative for high-performance scenarios.

---

## 7. Testing and Debugging

61. **How do you write unit tests in .NET Core?**
    - Use xUnit, NUnit, or MSTest with mocking frameworks like Moq.

62. **What is the difference between xUnit, NUnit, and MSTest?**
    - They are testing frameworks with similar functionality but different syntax and features.

63. **How do you mock dependencies in unit tests?**
    - Use Moq to create mock objects.

64. **What is the purpose of Moq in .NET Core?**
    - It is a mocking library for creating test doubles.

65. **How do you debug a .NET Core application?**
    - Use Visual Studio or VS Code with breakpoints and debugging tools.

---

## 8. Security

71. **How do you implement JWT authentication in .NET Core?**
    - Use `AddJwtBearer` and configure JWT options.

72. **What is the difference between authentication and authorization?**
    - **Authentication**: Verifies identity.
    - **Authorization**: Verifies permissions.

73. **How do you use [Authorize] and [AllowAnonymous] in ASP.NET Core?**
    - **[Authorize]**: Restricts access to authenticated users.
    - **[AllowAnonymous]**: Allows access to all users.

74. **What is the purpose of ClaimsPrincipal in .NET Core?**
    - It represents the user's identity and claims.

75. **How do you implement role-based authorization in .NET Core?**
    - Use `[Authorize(Roles = "Admin")]` or Policy-based authorization.

---

## 9. Advanced Concepts

81. **What is the purpose of BackgroundService in .NET Core?**
    - It is used to implement long-running background tasks.

82. **How do you implement a hosted service in .NET Core?**
    - Create a class that implements `IHostedService` or inherits from `BackgroundService`.

83. **What is the difference between IHostedService and BackgroundService?**
    - **BackgroundService**: A base class for implementing long-running tasks.
    - **IHostedService**: An interface for hosted services.

84. **How do you use SignalR in .NET Core?**
    - Use `AddSignalR` and `MapHub` to enable real-time communication.

85. **What is the purpose of gRPC in .NET Core?**
    - It is a high-performance RPC framework for microservices.

---

## 10. Deployment and DevOps

91. **How do you deploy a .NET Core application?**
    - Use `dotnet publish` to create a deployment package and deploy to a server or cloud.

92. **What is the difference between self-contained and framework-dependent deployments?**
    - **Self-contained**: Includes the .NET runtime.
    - **Framework-dependent**: Requires the .NET runtime to be installed.

93. **How do you use Docker with .NET Core?**
    - Create a Dockerfile and use `docker build` and `docker run`.

94. **What is the purpose of Dockerfile in .NET Core?**
    - It defines the steps to build and run a .NET Core application in a Docker container.

95. **How do you configure CI/CD pipelines for .NET Core applications?**
    - Use Azure DevOps, GitHub Actions, or Jenkins to automate builds and deployments.

---

These answers should help you prepare for your .NET Core interview. Let me know if you need further clarification on any topic!
