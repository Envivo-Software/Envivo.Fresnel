# Fresnel Domain Model Explorer

<picture id="fresnel_logo">
  <source media="(prefers-color-scheme: dark)" srcset="https://www.envivo.co.uk/images/white_fg_transparent_bg_for_docs.png">
  
  <img alt="Fresnel for .NET" src="https://www.envivo.co.uk/images/color_fg_transparent_bg_for_docs.png">
</picture>

Fresnel is a .NET library that accelerates the discovery, analysis, and design phase of projects using **Domain Driven Design**.

Build .NET domain models that run as interactive prototypes, then use those prototypes to explore the domain model with your team and your Domain Experts.

Fresnel is built using Blazor on .NET 8 and Visual Studio 2022.

## Getting Started

<!-- Copy this from Fresnel.Wiki/getting-started.md -->
## Requirements

- Windows 10 or above
- .NET 8
### Supported IDEs:
- Visual Studio 2022, with workloads for:
  - .NET Desktop Development
  - .NET Multi-platform App UI Development
- Visual Studio Code with:
  - C# Dev Kit
- JetBrains Rider

<!-- Copy this from Fresnel.Wiki/create-a-new-prototype.md -->
### Install the template
```
> cd <my repo folder>
> dotnet new install Envivo.Fresnel.Templates
> dotnet new fresnel-prototype-winforms  👈 // For Windows project
> dotnet new fresnel-prototype-webserver 👈 // For non-Windows project
``` 

### Sample projects

- **Starting a new DDD project?** Use this sample project as a starting point:
  - [Fresnel.Sample.ShoppingProject](https://github.com/Envivo-Software/Fresnel.Sample.ShoppingProject)

- **Want to see the various capabilities and features of Fresnel?** Use this sample project and the Developer documentation to guide you:
  - [Fresnel.Sample.Features](https://github.com/Envivo-Software/Fresnel.Sample.Features)

### Documentation
The Developer's guide can be found at https://github.com/Envivo-Software/Envivo.Fresnel/wiki

*Copyright 2022-2025 Envivo Software*