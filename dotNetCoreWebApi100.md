# Top 100 .NET Core Web API Interview Questions and Answers for Experienced Developers

Here’s a comprehensive list of **100 .NET Core Web API interview questions and answers** for experienced developers. These questions cover a wide range of topics, including Web API fundamentals, routing, dependency injection, middleware, security, performance optimization, and more.

---

## 1. Web API Fundamentals

1. **What is a Web API?**
   - **Answer**: A Web API is an interface that allows communication between different systems over HTTP using RESTful principles.

2. **What is REST?**
   - **Answer**: REST (Representational State Transfer) is an architectural style that uses HTTP methods (GET, POST, PUT, DELETE) to perform CRUD operations.

3. **What are the advantages of using Web API?**
   - **Answer**: Lightweight, stateless, scalable, and supports multiple data formats (JSON, XML).

4. **What is the difference between Web API and MVC?**
   - **Answer**:
     - **Web API**: Used for building HTTP services, returns data (JSON/XML).
     - **MVC**: Used for building web applications, returns views (HTML).

5. **What is the difference between WCF and Web API?**
   - **Answer**:
     - **WCF**: Supports multiple protocols (HTTP, TCP, MSMQ), more complex.
     - **Web API**: Lightweight, HTTP-only, easier to use.

6. **What is the purpose of [ApiController] attribute?**
   - **Answer**: It enables Web API-specific behaviors like automatic model validation and binding.

7. **What is the difference between [ApiController] and [Controller]?**
   - **Answer**:
     - **[ApiController]**: Used for Web API controllers.
     - **[Controller]**: Used for MVC controllers.

8. **What is the purpose of HttpResponseMessage?**
   - **Answer**: It represents an HTTP response, including status code and content.

9. **What is the difference between IActionResult and ActionResult<T>?**
   - **Answer**:
     - **IActionResult**: Represents an abstract result.
     - **ActionResult<T>**: Represents a result with a specific type.

10. **What is the purpose of ProducesResponseType attribute?**
    - **Answer**: It specifies the possible response types and status codes for an action.

---

## 2. Routing

11. **What is routing in Web API?**
    - **Answer**: Routing maps incoming HTTP requests to controller actions.

12. **What is the difference between convention-based routing and attribute routing?**
    - **Answer**:
      - **Convention-based routing**: Defined in `Startup.cs` using `MapRoute`.
      - **Attribute routing**: Defined directly on controllers and actions using `[Route]`.

13. **How do you define a route in .NET Core Web API?**
    - **Answer**:
      ```csharp
      app.UseEndpoints(endpoints =>
      {
          endpoints.MapControllers();
      });
      ```

14. **What is the purpose of [HttpGet], [HttpPost], [HttpPut], and [HttpDelete]?**
    - **Answer**: They specify the HTTP method (GET, POST, PUT, DELETE) that an action can handle.

15. **What is the difference between MapRoute and MapControllerRoute?**
    - **Answer**:
      - **MapRoute**: Used in older versions of MVC.
      - **MapControllerRoute**: Used in .NET Core Web API.

16. **What is the purpose of the [NonAction] attribute?**
    - **Answer**: It marks a method in a controller as non-actionable, meaning it cannot be called as an action.

17. **What is the difference between Route and RoutePrefix?**
    - **Answer**:
      - **Route**: Defines a route for a specific action.
      - **RoutePrefix**: Defines a common prefix for all routes in a controller.

18. **What is the purpose of the [ActionName] attribute?**
    - **Answer**: It allows you to specify a different name for an action.

19. **What is the difference between MapGet and MapPost?**
    - **Answer**:
      - **MapGet**: Maps a GET request to an action.
      - **MapPost**: Maps a POST request to an action.

20. **What is the purpose of the [FromQuery] and [FromBody] attributes?**
    - **Answer**:
      - **[FromQuery]**: Binds data from query string parameters.
      - **[FromBody]**: Binds data from the request body.

---

## 3. Dependency Injection

21. **What is dependency injection (DI) in .NET Core?**
    - **Answer**: DI is a design pattern that allows objects to receive their dependencies from an external source rather than creating them internally.

22. **What is the difference between AddTransient, AddScoped, and AddSingleton?**
    - **Answer**:
      - **AddTransient**: A new instance is created every time.
      - **AddScoped**: A single instance is created per request.
      - **AddSingleton**: A single instance is shared for the entire application lifetime.

23. **How do you register a service in .NET Core?**
    - **Answer**:
      ```csharp
      services.AddTransient<IMyService, MyService>();
      ```

24. **What is the purpose of the IServiceProvider interface?**
    - **Answer**: It provides access to registered services.

25. **What is the difference between constructor injection and method injection?**
    - **Answer**:
      - **Constructor injection**: Dependencies are injected via the constructor.
      - **Method injection**: Dependencies are injected via method parameters.

26. **What is the Options pattern in .NET Core?**
    - **Answer**: It is used to bind configuration settings to strongly-typed classes.

27. **How do you use IOptions<T> in .NET Core?**
    - **Answer**:
      ```csharp
      services.Configure<MyOptions>(Configuration.GetSection("MyOptions"));
      ```

28. **What is the difference between IOptions<T>, IOptionsSnapshot<T>, and IOptionsMonitor<T>?**
    - **Answer**:
      - **IOptions<T>**: Singleton, does not reload changes.
      - **IOptionsSnapshot<T>**: Scoped, reloads changes per request.
      - **IOptionsMonitor<T>**: Singleton, reloads changes dynamically.

29. **What is the purpose of the [FromServices] attribute?**
    - **Answer**: It injects a service directly into an action method.

30. **What is the difference between IServiceCollection and IServiceProvider?**
    - **Answer**:
      - **IServiceCollection**: Used to register services.
      - **IServiceProvider**: Used to resolve services.

---

## 4. Middleware

31. **What is middleware in .NET Core?**
    - **Answer**: Middleware is software components that handle requests and responses in the pipeline.

32. **What is the purpose of Use, Run, and Map in middleware?**
    - **Answer**:
      - **Use**: Adds middleware to the pipeline.
      - **Run**: Terminates the pipeline.
      - **Map**: Branches the pipeline based on the request path.

33. **What is the difference between app.UseMiddleware and app.Use?**
    - **Answer**:
      - **app.UseMiddleware**: Adds a middleware class to the pipeline.
      - **app.Use**: Adds a delegate-based middleware to the pipeline.

34. **What is the purpose of app.UseRouting and app.UseEndpoints?**
    - **Answer**:
      - **app.UseRouting**: Matches incoming requests to routes.
      - **app.UseEndpoints**: Executes the matched route.

35. **What is the difference between app.UseStaticFiles and app.UseFileServer?**
    - **Answer**:
      - **app.UseStaticFiles**: Serves static files.
      - **app.UseFileServer**: Combines static files and directory browsing.

36. **What is the purpose of app.UseExceptionHandler?**
    - **Answer**: It catches exceptions and redirects to an error page or handler.

37. **What is the difference between app.UseHttpsRedirection and app.UseHsts?**
    - **Answer**:
      - **app.UseHttpsRedirection**: Redirects HTTP requests to HTTPS.
      - **app.UseHsts**: Enforces HTTPS using the HSTS header.

38. **What is the purpose of app.UseAuthentication and app.UseAuthorization?**
    - **Answer**:
      - **app.UseAuthentication**: Enables authentication.
      - **app.UseAuthorization**: Enables authorization.

39. **What is the difference between app.UseCors and app.UseResponseCaching?**
    - **Answer**:
      - **app.UseCors**: Enables Cross-Origin Resource Sharing.
      - **app.UseResponseCaching**: Enables response caching.

40. **What is the purpose of app.UseSession?**
    - **Answer**: It enables session state for the application.

---

## 5. Model Binding and Validation

41. **What is model binding in Web API?**
    - **Answer**: Model binding maps HTTP request data to action method parameters or model properties.

42. **What is the purpose of [Bind] attribute?**
    - **Answer**: It specifies which properties should be included or excluded during model binding.

43. **What is the difference between [Bind] and [BindNever]?**
    - **Answer**:
      - **[Bind]**: Specifies properties to include or exclude.
      - **[BindNever]**: Prevents a property from being bound.

44. **What is the purpose of [Required] attribute?**
    - **Answer**: It ensures that a property has a value.

45. **What is the difference between [Required] and [Range]?**
    - **Answer**:
      - **[Required]**: Ensures a value is provided.
      - **[Range]**: Ensures a value falls within a specified range.

46. **What is the purpose of [Compare] attribute?**
    - **Answer**: It compares two properties to ensure they have the same value.

47. **What is the difference between [RegularExpression] and [StringLength]?**
    - **Answer**:
      - **[RegularExpression]**: Validates a string against a regex pattern.
      - **[StringLength]**: Validates the length of a string.

48. **What is the purpose of ModelState.IsValid?**
    - **Answer**: It checks if the model passed validation.

49. **What is the difference between client-side and server-side validation?**
    - **Answer**:
      - **Client-side**: Performed in the browser using JavaScript.
      - **Server-side**: Performed on the server to ensure data integrity.

50. **What is the purpose of [Remote] attribute?**
    - **Answer**: It performs remote validation by calling a server-side action.

---

## 6. Advanced Topics

51. **What is the purpose of Tag Helpers in .NET Core Web API?**
    - **Answer**: Tag Helpers generate HTML elements using server-side code.

52. **What is the difference between Tag Helpers and HTML Helpers?**
    - **Answer**:
      - **Tag Helpers**: Use HTML-like syntax.
      - **HTML Helpers**: Use C# syntax.

53. **What is the purpose of View Components?**
    - **Answer**: View Components are reusable UI components that can be invoked from a view.

54. **What is the difference between View Components and Partial Views?**
    - **Answer**:
      - **View Components**: Have their own logic and can be unit tested.
      - **Partial Views**: Are simple reusable views.

55. **What is the purpose of Areas in Web API?**
    - **Answer**: Areas allow you to organize large applications into smaller functional groups.

56. **What is the difference between Areas and Folders?**
    - **Answer**:
      - **Areas**: Have their own controllers, views, and routes.
      - **Folders**: Are just for organizing files.

57. **What is the purpose of Filters in Web API?**
    - **Answer**: Filters allow you to run code before or after specific stages in the request pipeline.

58. **What is the difference between Authorization Filters and Action Filters?**
    - **Answer**:
      - **Authorization Filters**: Handle authorization logic.
      - **Action Filters**: Handle pre- and post-action logic.

59. **What is the purpose of Global Filters?**
    - **Answer**: Global Filters apply to all actions in the application.

60. **What is the difference between Result Filters and Exception Filters?**
    - **Answer**:
      - **Result Filters**: Handle pre- and post-result logic.
      - **Exception Filters**: Handle exceptions.

---

## 7. Testing and Debugging

61. **How do you write unit tests for Web API controllers?**
    - **Answer**: Use a testing framework like xUnit or NUnit and mock dependencies.

62. **What is the purpose of Moq in unit testing?**
    - **Answer**: Moq is a mocking framework used to create test doubles.

63. **What is the difference between unit testing and integration testing?**
    - **Answer**:
      - **Unit Testing**: Tests individual components in isolation.
      - **Integration Testing**: Tests interactions between components.

64. **What is the purpose of TestServer in .NET Core?**
    - **Answer**: TestServer is used to host and test ASP.NET Core applications in memory.

65. **What is the difference between Debug and Release modes?**
    - **Answer**:
      - **Debug**: Includes debugging information and is not optimized.
      - **Release**: Optimized for performance and does not include debugging information.

---

## 8. Security

66. **How do you implement authentication in .NET Core Web API?**
    - **Answer**: Use `AddAuthentication` and configure authentication middleware (e.g., JWT, Cookies).

67. **What is the purpose of [Authorize] attribute?**
    - **Answer**: It restricts access to authenticated users.

68. **What is the difference between [Authorize] and [AllowAnonymous]?**
    - **Answer**:
      - **[Authorize]**: Restricts access.
      - **[AllowAnonymous]**: Allows access to all users.

69. **What is the purpose of AntiForgeryToken?**
    - **Answer**: It prevents Cross-Site Request Forgery (CSRF) attacks.

70. **What is the difference between Authentication and Authorization?**
    - **Answer**:
      - **Authentication**: Verifies identity.
      - **Authorization**: Verifies permissions.

---

## 9. Miscellaneous

71. **What is the purpose of appsettings.json?**
    - **Answer**: It stores configuration settings like connection strings and logging levels.

72. **What is the difference between IConfiguration and IOptions?**
    - **Answer**:
      - **IConfiguration**: Provides access to configuration settings.
      - **IOptions**: Binds configuration settings to strongly-typed classes.

73. **What is the purpose of ILogger in .NET Core?**
    - **Answer**: It provides logging functionality.

74. **What is the difference between ILogger and ILogger<T>?**
    - **Answer**:
      - **ILogger**: Generic logger.
      - **ILogger<T>**: Logger with a category (usually the class name).

75. **What is the purpose of IHttpContextAccessor?**
    - **Answer**: It provides access to the current HTTP context.

76. **What is the difference between HttpContext and IHttpContextAccessor?**
    - **Answer**:
      - **HttpContext**: Represents the current HTTP context.
      - **IHttpContextAccessor**: Provides access to the HTTP context in non-controller classes.

77. **What is the purpose of IMemoryCache?**
    - **Answer**: It provides in-memory caching functionality.

78. **What is the difference between IMemoryCache and IDistributedCache?**
    - **Answer**:
      - **IMemoryCache**: Stores data in memory.
      - **IDistributedCache**: Stores data in a distributed cache (e.g., Redis).

79. **What is the purpose of ResponseCaching?**
    - **Answer**: It caches HTTP responses to improve performance.

80. **What is the difference between ResponseCaching and OutputCaching?**
    - **Answer**:
      - **ResponseCaching**: Caches HTTP responses.
      - **OutputCaching**: Caches the output of actions (not available in .NET Core).

---

## 10. Advanced Web API Concepts

81. **What is the purpose of Model Binding in Web API?**
    - **Answer**: It maps HTTP request data to action method parameters or model properties.

82. **What is the difference between Model Binding and Model Validation?**
    - **Answer**:
      - **Model Binding**: Maps request data to model properties.
      - **Model Validation**: Ensures the model data is valid.

83. **What is the purpose of Custom Model Binders?**
    - **Answer**: They allow you to define custom logic for binding request data to models.

84. **What is the difference between Custom Model Binders and Default Model Binders?**
    - **Answer**:
      - **Custom Model Binders**: User-defined logic.
      - **Default Model Binders**: Built-in logic provided by Web API.

85. **What is the purpose of Model Metadata?**
    - **Answer**: It provides metadata about model properties (e.g., display name, data type).

86. **What is the difference between Model Metadata and Data Annotations?**
    - **Answer**:
      - **Model Metadata**: Provides metadata about model properties.
      - **Data Annotations**: Attributes used to define validation rules and display properties.

87. **What is the purpose of Custom Validation Attributes?**
    - **Answer**: They allow you to define custom validation logic.

88. **What is the difference between Custom Validation Attributes and Data Annotations?**
    - **Answer**:
      - **Custom Validation Attributes**: User-defined validation logic.
      - **Data Annotations**: Built-in validation attributes.

89. **What is the purpose of Globalization and Localization in Web API?**
    - **Answer**: They enable support for multiple languages and cultures.

90. **What is the difference between Globalization and Localization?**
    - **Answer**:
      - **Globalization**: Designing applications to support multiple cultures.
      - **Localization**: Adapting an application for a specific culture.

---

## 11. Performance Optimization

91. **How do you optimize the performance of a Web API?**
    - **Answer**: Use caching, asynchronous programming, and efficient database queries.

92. **What is the purpose of IHttpClientFactory?**
    - **Answer**: It manages HttpClient instances to improve performance and reliability.

93. **What is the difference between IHttpClientFactory and HttpClient?**
    - **Answer**:
      - **IHttpClientFactory**: Manages HttpClient instances and handles connection pooling.
      - **HttpClient**: A class for sending HTTP requests.

94. **What is the purpose of Response Compression?**
    - **Answer**: It reduces the size of HTTP responses to improve performance.

95. **What is the difference between Response Compression and Response Caching?**
    - **Answer**:
      - **Response Compression**: Reduces response size.
      - **Response Caching**: Stores responses to reduce server load.

96. **What is the purpose of Health Checks?**
    - **Answer**: It monitors the health of the application and its dependencies.

97. **What is the difference between Health Checks and Diagnostics?**
    - **Answer**:
      - **Health Checks**: Monitors application health.
      - **Diagnostics**: Provides detailed information about application performance.

98. **What is the purpose of Application Insights?**
    - **Answer**: It provides monitoring and diagnostics for .NET Core applications.

99. **What is the difference between Application Insights and Serilog?**
    - **Answer**:
      - **Application Insights**: Cloud-based monitoring and diagnostics.
      - **Serilog**: A logging library for .NET.

100. **What is the purpose of Distributed Tracing?**
    - **Answer**: It tracks requests across multiple services to diagnose performance issues.

---

These questions and answers should help you prepare for .NET Core Web API interviews at an experienced level. Let me know if you need further clarification!
