# 023 Custom Validation

## Lecture

[![# Custom Validation (Part 1)](https://img.youtube.com/vi/grDY0iQW74w/0.jpg)](https://www.youtube.com/watch?v=grDY0iQW74w)
[![# Custom Validation (Part 2)](https://img.youtube.com/vi/YswTsa3CVJ4/0.jpg)](https://www.youtube.com/watch?v=YswTsa3CVJ4)

## Instructions

In `HomeEnergyApi/Validations/HomeStreetAddressValidAttribute.cs`
- Create a public class `HomeStreetAddressValidAttribute`, implementing `ValidationAttribute`
    - Create a protected override method `IsValid()` 
        - `IsValid()` should return a result of type `ValidationResult?`
        - `IsValid()` should take two arguments of types `object?` and `ValidationContext`
        - `IsValid()` should return a new `ValidationResult` with the message "Invalid home data." if the passed `object?` is not of type `HomeDto`
        - `IsValid()` should return a new `ValidationResult` with the message "Street Address must contain a number and have fewer than 64 characters" if..
            - The `StreetAddress` on the passed `HomeDto` does not contain a digit(numeric characters 0-9)
            - OR The `StreetAddress` on the passed `HomeDto` is longer than 64 characters
        - If no prior return conditions were met, `IsValid()` should return `ValidationResult.Success`

In `HomeEnergyApi/Dtos/HomeDto.cs`
- Add the newly constructed `HomeStreetAddressValidAttribute` as an attribute on `HomeDto`

## Additional Information
- Do not remove or modify anything in `HomeEnergyApi.Tests`
- Some Models may have changed for this lesson from the last, as always all code in the lesson repository is available to view
- Along with `using` statements being added, any packages needed for the assignment have been pre-installed for you, however in the future you may need to add these yourself

## Building toward CSTA Standards:
- Decompose problems into smaller components through systematic analysis, using constructs such as procedures, modules, and/or objects (3A-AP-17) https://www.csteachers.org/page/standards
- Create artifacts by using procedures within a program, combinations of data and procedures, or independent but interrelated programs (3A-AP-18) https://www.csteachers.org/page/standards
- Evaluate and refine computational artifacts to make them more usable and accessible (3A-AP-21) https://www.csteachers.org/page/standards
- Systematically design and develop programs for broad audiences by incorporating feedback from users (3A-AP-19) https://www.csteachers.org/page/standards
- Develop and use a series of test cases to verify that a program performs according to its design specifications (3B-AP-21) https://www.csteachers.org/page/standards

## Resources
- https://learn.microsoft.com/en-us/aspnet/core/mvc/models/validation?view=aspnetcore-9.0#custom-attributes
- https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/is

Copyright &copy; 2025 Knight Moves. All Rights Reserved.
