# Top 100 .NET Core MVC Interview Questions and Answers for Experienced Developers

Here’s a comprehensive list of **100 .NET Core MVC interview questions and answers** for experienced developers. These questions cover a wide range of topics, including MVC architecture, Razor views, routing, dependency injection, middleware, and more.

---

## 1. MVC Architecture

1. **What is MVC?**
   - **Answer**: MVC (Model-View-Controller) is a design pattern that separates an application into three components: **Model** (data), **View** (UI), and **Controller** (logic).

2. **What are the advantages of using MVC?**
   - **Answer**: Separation of concerns, testability, scalability, and better organization of code.

3. **What is the role of the Model in MVC?**
   - **Answer**: The Model represents the application's data and business logic.

4. **What is the role of the View in MVC?**
   - **Answer**: The View is responsible for displaying the data to the user.

5. **What is the role of the Controller in MVC?**
   - **Answer**: The Controller handles user input, processes requests, and interacts with the Model and View.

6. **What is the difference between MVC and Web Forms?**
   - **Answer**:
     - **MVC**: Uses a separation of concerns, supports testability, and is stateless.
     - **Web Forms**: Uses an event-driven model, has a stateful UI, and is less testable.

7. **What is Razor in .NET Core MVC?**
   - **Answer**: Razor is a markup syntax for embedding server-side code into HTML.

8. **What is the difference between Razor and ASPX?**
   - **Answer**:
     - **Razor**: Lightweight, uses `@` for server-side code, and is more readable.
     - **ASPX**: Uses `<% %>` for server-side code and is more verbose.

9. **What is the ViewBag in MVC?**
   - **Answer**: ViewBag is a dynamic property used to pass data from a controller to a view.

10. **What is the difference between ViewBag and ViewData?**
    - **Answer**:
      - **ViewBag**: Dynamic, uses properties.
      - **ViewData**: Dictionary-based, uses key-value pairs.

---

## 2. Routing

11. **What is routing in MVC?**
    - **Answer**: Routing maps URLs to controller actions.

12. **What is the difference between convention-based routing and attribute routing?**
    - **Answer**:
      - **Convention-based routing**: Defined in `Startup.cs` using `MapRoute`.
      - **Attribute routing**: Defined directly on controllers and actions using `[Route]`.

13. **How do you define a route in .NET Core MVC?**
    - **Answer**:
      ```csharp
      app.UseEndpoints(endpoints =>
      {
          endpoints.MapControllerRoute(
              name: "default",
              pattern: "{controller=Home}/{action=Index}/{id?}");
      });
      ```

14. **What is the purpose of the [HttpGet] and [HttpPost] attributes?**
    - **Answer**: They specify the HTTP method (GET or POST) that an action can handle.

15. **What is the difference between MapRoute and MapControllerRoute?**
    - **Answer**:
      - **MapRoute**: Used in older versions of MVC.
      - **MapControllerRoute**: Used in .NET Core MVC.

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

## 5. Views and Razor

41. **What is a Razor view?**
    - **Answer**: A Razor view is a file that contains HTML and server-side code (C#) to generate dynamic content.

42. **What is the difference between @Html.Partial and @Html.RenderPartial?**
    - **Answer**:
      - **@Html.Partial**: Returns a partial view as a string.
      - **@Html.RenderPartial**: Writes the partial view directly to the response.

43. **What is the purpose of @Html.Action and @Html.RenderAction?**
    - **Answer**:
      - **@Html.Action**: Invokes a controller action and returns the result as a string.
      - **@Html.RenderAction**: Invokes a controller action and writes the result directly to the response.

44. **What is the difference between View and PartialView?**
    - **Answer**:
      - **View**: Renders a full view.
      - **PartialView**: Renders a partial view (a portion of a view).

45. **What is the purpose of @Html.BeginForm?**
    - **Answer**: It generates an HTML form tag.

46. **What is the difference between @Html.TextBox and @Html.TextBoxFor?**
    - **Answer**:
      - **@Html.TextBox**: Creates a text box with a specified name.
      - **@Html.TextBoxFor**: Creates a text box bound to a model property.

47. **What is the purpose of @Html.ValidationSummary?**
    - **Answer**: It displays a summary of validation errors.

48. **What is the difference between @Html.EditorFor and @Html.DisplayFor?**
    - **Answer**:
      - **@Html.EditorFor**: Generates an input element for editing a model property.
      - **@Html.DisplayFor**: Generates a display element for a model property.

49. **What is the purpose of @Html.AntiForgeryToken?**
    - **Answer**: It generates a hidden form field to prevent Cross-Site Request Forgery (CSRF) attacks.

50. **What is the difference between @section and @RenderSection?**
    - **Answer**:
      - **@section**: Defines a section in a view.
      - **@RenderSection**: Renders a section in a layout.

---

## 6. Model Binding and Validation

51. **What is model binding in MVC?**
    - **Answer**: Model binding maps HTTP request data to action method parameters or model properties.

52. **What is the purpose of [Bind] attribute?**
    - **Answer**: It specifies which properties should be included or excluded during model binding.

53. **What is the difference between [Bind] and [BindNever]?**
    - **Answer**:
      - **[Bind]**: Specifies properties to include or exclude.
      - **[BindNever]**: Prevents a property from being bound.

54. **What is the purpose of [Required] attribute?**
    - **Answer**: It ensures that a property has a value.

55. **What is the difference between [Required] and [Range]?**
    - **Answer**:
      - **[Required]**: Ensures a value is provided.
      - **[Range]**: Ensures a value falls within a specified range.

56. **What is the purpose of [Compare] attribute?**
    - **Answer**: It compares two properties to ensure they have the same value.

57. **What is the difference between [RegularExpression] and [StringLength]?**
    - **Answer**:
      - **[RegularExpression]**: Validates a string against a regex pattern.
      - **[StringLength]**: Validates the length of a string.

58. **What is the purpose of ModelState.IsValid?**
    - **Answer**: It checks if the model passed validation.

59. **What is the difference between client-side and server-side validation?**
    - **Answer**:
      - **Client-side**: Performed in the browser using JavaScript.
      - **Server-side**: Performed on the server to ensure data integrity.

60. **What is the purpose of [Remote] attribute?**
    - **Answer**: It performs remote validation by calling a server-side action.

---

## 7. Advanced Topics

61. **What is the purpose of Tag Helpers in .NET Core MVC?**
    - **Answer**: Tag Helpers generate HTML elements using server-side code.

62. **What is the difference between Tag Helpers and HTML Helpers?**
    - **Answer**:
      - **Tag Helpers**: Use HTML-like syntax.
      - **HTML Helpers**: Use C# syntax.

63. **What is the purpose of View Components?**
    - **Answer**: View Components are reusable UI components that can be invoked from a view.

64. **What is the difference between View Components and Partial Views?**
    - **Answer**:
      - **View Components**: Have their own logic and can be unit tested.
      - **Partial Views**: Are simple reusable views.

65. **What is the purpose of Areas in MVC?**
    - **Answer**: Areas allow you to organize large applications into smaller functional groups.

66. **What is the difference between Areas and Folders?**
    - **Answer**:
      - **Areas**: Have their own controllers, views, and routes.
      - **Folders**: Are just for organizing files.

67. **What is the purpose of Filters in MVC?**
    - **Answer**: Filters allow you to run code before or after specific stages in the request pipeline.

68. **What is the difference between Authorization Filters and Action Filters?**
    - **Answer**:
      - **Authorization Filters**: Handle authorization logic.
      - **Action Filters**: Handle pre- and post-action logic.

69. **What is the purpose of Global Filters?**
    - **Answer**: Global Filters apply to all actions in the application.

70. **What is the difference between Result Filters and Exception Filters?**
    - **Answer**:
      - **Result Filters**: Handle pre- and post-result logic.
      - **Exception Filters**: Handle exceptions.

---

## 8. Testing and Debugging

71. **How do you write unit tests for MVC controllers?**
    - **Answer**: Use a testing framework like xUnit or NUnit and mock dependencies.

72. **What is the purpose of Moq in unit testing?**
    - **Answer**: Moq is a mocking framework used to create test doubles.

73. **What is the difference between unit testing and integration testing?**
    - **Answer**:
      - **Unit Testing**: Tests individual components in isolation.
      - **Integration Testing**: Tests interactions between components.

74. **What is the purpose of TestServer in .NET Core?**
    - **Answer**: TestServer is used to host and test ASP.NET Core applications in memory.

75. **What is the difference between Debug and Release modes?**
    - **Answer**:
      - **Debug**: Includes debugging information and is not optimized.
      - **Release**: Optimized for performance and does not include debugging information.

---

## 9. Security

76. **How do you implement authentication in .NET Core MVC?**
    - **Answer**: Use `AddAuthentication` and configure authentication middleware (e.g., JWT, Cookies).

77. **What is the purpose of [Authorize] attribute?**
    - **Answer**: It restricts access to authenticated users.

78. **What is the difference between [Authorize] and [AllowAnonymous]?**
    - **Answer**:
      - **[Authorize]**: Restricts access.
      - **[AllowAnonymous]**: Allows access to all users.

79. **What is the purpose of AntiForgeryToken?**
    - **Answer**: It prevents Cross-Site Request Forgery (CSRF) attacks.

80. **What is the difference between Authentication and Authorization?**
    - **Answer**:
      - **Authentication**: Verifies identity.
      - **Authorization**: Verifies permissions.

---

## 10. Miscellaneous

81. **What is the purpose of appsettings.json?**
    - **Answer**: It stores configuration settings like connection strings and logging levels.

82. **What is the difference between IConfiguration and IOptions?**
    - **Answer**:
      - **IConfiguration**: Provides access to configuration settings.
      - **IOptions**: Binds configuration settings to strongly-typed classes.

83. **What is the purpose of ILogger in .NET Core?**
    - **Answer**: It provides logging functionality.

84. **What is the difference between ILogger and ILogger<T>?**
    - **Answer**:
      - **ILogger**: Generic logger.
      - **ILogger<T>**: Logger with a category (usually the class name).

85. **What is the purpose of IHttpContextAccessor?**
    - **Answer**: It provides access to the current HTTP context.

86. **What is the difference between HttpContext and IHttpContextAccessor?**
    - **Answer**:
      - **HttpContext**: Represents the current HTTP context.
      - **IHttpContextAccessor**: Provides access to the HTTP context in non-controller classes.

87. **What is the purpose of IMemoryCache?**
    - **Answer**: It provides in-memory caching functionality.

88. **What is the difference between IMemoryCache and IDistributedCache?**
    - **Answer**:
      - **IMemoryCache**: Stores data in memory.
      - **IDistributedCache**: Stores data in a distributed cache (e.g., Redis).

89. **What is the purpose of ResponseCaching?**
    - **Answer**: It caches HTTP responses to improve performance.

90. **What is the difference between ResponseCaching and OutputCaching?**
    - **Answer**:
      - **ResponseCaching**: Caches HTTP responses.
      - **OutputCaching**: Caches the output of actions (not available in .NET Core).

---

## 11. Advanced MVC Concepts

91. **What is the purpose of Model Binding in MVC?**
    - **Answer**: It maps HTTP request data to action method parameters or model properties.

92. **What is the difference between Model Binding and Model Validation?**
    - **Answer**:
      - **Model Binding**: Maps request data to model properties.
      - **Model Validation**: Ensures the model data is valid.

93. **What is the purpose of Custom Model Binders?**
    - **Answer**: They allow you to define custom logic for binding request data to models.

94. **What is the difference between Custom Model Binders and Default Model Binders?**
    - **Answer**:
      - **Custom Model Binders**: User-defined logic.
      - **Default Model Binders**: Built-in logic provided by MVC.

95. **What is the purpose of Model Metadata?**
    - **Answer**: It provides metadata about model properties (e.g., display name, data type).

96. **What is the difference between Model Metadata and Data Annotations?**
    - **Answer**:
      - **Model Metadata**: Provides metadata about model properties.
      - **Data Annotations**: Attributes used to define validation rules and display properties.

97. **What is the purpose of Custom Validation Attributes?**
    - **Answer**: They allow you to define custom validation logic.

98. **What is the difference between Custom Validation Attributes and Data Annotations?**
    - **Answer**:
      - **Custom Validation Attributes**: User-defined validation logic.
      - **Data Annotations**: Built-in validation attributes.

99. **What is the purpose of Globalization and Localization in MVC?**
    - **Answer**: They enable support for multiple languages and cultures.

100. **What is the difference between Globalization and Localization?**
    - **Answer**:
      - **Globalization**: Designing applications to support multiple cultures.
      - **Localization**: Adapting an application for a specific culture.

---

These questions and answers should help you prepare for .NET Core MVC interviews at an experienced level. Let me know if you need further clarification!
