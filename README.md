# 024 Global Error Handling

## Lecture

[![# Global Error Handling)](https://img.youtube.com/vi/h8DWSgf2PfM/0.jpg)](https://www.youtube.com/watch?v=h8DWSgf2PfM)

## Instructions

In `HomeEnergyApi/Controllers/HomeController.cs`
- Create a new HTTP GET method with the route "Bang"
    - This method should throw a new `InvalidOperationException` with the message "You caused a loud bang."

In `HomeEnergyApi/Filters/GlobalExceptionFilter.cs`
- Create a new public class `GlobalExceptionFilter` implementing `IExceptionFilter`
    - Create a new public void method `OnException()` taking one argument of type `ExceptionContext`
        - `OnException()` should create a variable `response` with a `message` property set to "An unexpected error occurred." and an `error` property set to the passed `ExceptionContext.Exception.Message`
        - `OnException()` should set the `Result` property on the passed `ExceptionContext` to a new `ObjectResult` with your created `response` variable passed into it's constructor and with it's `StatusCode` property set to 500

In `HomeEnergyApi/Program.cs`
- Pass an option to the existing `AddControllers()` method
    - This option should add a filter of type `GlobalExceptionFilter`

## Additional Information
- Do not remove or modify anything in `HomeEnergyApi.Tests`
- Some Models may have changed for this lesson from the last, as always all code in the lesson repository is available to view
- Along with `using` statements being added, any packages needed for the assignment have been pre-installed for you, however in the future you may need to add these yourself

## Building toward CSTA Standards:
- Develop guidelines that convey systematic troubleshooting strategies that others can use to identify and fix errors (3A-CS-03) https://www.csteachers.org/page/standards
- Recommend security measures to address various scenarios based on factors such as efficiency, feasibility, and ethical impacts (3A-NI-06) https://www.csteachers.org/page/standards
- Document design decisions using text, graphics, presentations, and/or demonstrations in the development of complex programs (3A-AP-23) https://www.csteachers.org/page/standards
- Explain security issues that might lead to compromised computer programs (3B-AP-18) https://www.csteachers.org/page/standards

## Resources
- https://learn.microsoft.com/en-us/aspnet/core/mvc/controllers/filters?view=aspnetcore-9.0#exception-filters

Copyright &copy; 2025 Knight Moves. All Rights Reserved.
