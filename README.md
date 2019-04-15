# DevExpress UI for Razor Components

This demo application is a preview of the [DevExpress UI for Razor Components](https://www.devexpress.com/products/blazor-razor-components/).

The DevExpress UI components featured in this demo are available for free download and can be used in your next Razor Components/Blazor app.* 

> \* Like any software preview, the DevExpress UI for Razor Components is not without fault. You should not use these products in production environments or in mission-critical applications.

# Included Demo Modules

* Data Grid
  * Column Types
  * Templates
  * Large Datasets
* Pivot Grid
  * Data Binding Basics
  * Templates
  * Large Datasets
* Data Editors
  * Combo Box – Business Object List
  * Combo Box – Cascading Lists
  * Date Edit
  * Spin Edit
  * Text Box
* Pager

# Live Demo
 
Check out the [published demo website](https://demos.devexpress.com/razor-components/).

# Set up your environment

1. Install Visual Studio 2019
2. Ensure that you have .NET Core 3 installed.
3. If you use Visual Studio 2019 release version, enable the "Use previews of the .NET Core SDK" option.

![Enable SDK preview in VS 2019 Release"](https://raw.githubusercontent.com/DevExpress/RazorComponents/master/media/VS2019Release-EnablePreviewSDK.png)

# How to run the demo on your machine

1. Download the "**demo**" directory from this repository.
2. Open **demo/Demo.RazorComponents.sln** in Visual Studio 2019.
3. Start the application.

See also: 

[Introduction to Razor Components](https://docs.microsoft.com/aspnet/core/razor-components/?view=aspnetcore-3.0)

[Get started with Razor Components](https://docs.microsoft.com/ru-ru/aspnet/core/razor-components/get-started?view=aspnetcore-3.0&tabs=visual-studio)

# How to create a new project

Follow the steps below to try our Razor Components in your own application. 

1. Create a new solution using the "Razor Components" or "Blazor" template in Visual Studio 2019.

In the "Create a new project" dialog, select "ASP.NET Core Web Application" (C# language).

![Create New ASP.NET Core Web Application Project"](https://raw.githubusercontent.com/DevExpress/RazorComponents/master/media/VisualStudio2019CreateNewProject_AspNetCoreWebApp.png)

In the next step select "ASP.NET Core 3.\*" framework and "Razor Components" project template.

![Create New ASP.NET Core Web Application Project"](https://raw.githubusercontent.com/DevExpress/RazorComponents/master/media/VisualStudio2019CreateNewProject_RazorComponents.png)

2. Register the *DevExpress Early Access* feed in Visual Studio's NuGet Package Manager.

Select "Package Manager Settings" in the Visual Studio menu.

![Open the "Package Manager Settings"](https://raw.githubusercontent.com/DevExpress/RazorComponents/master/media/NuGetPackageManagerSettings.png)

Add a new NuGet source:

```https://nuget.devexpress.com/early-access/api```

![Add new NuGet source](https://raw.githubusercontent.com/DevExpress/RazorComponents/master/media/DevExpressEarlyAccessNuGetSource.png)

3. Install the "DevExpress.RazorComponents" NuGet package.
4. Download all files from the *client-runtime* directory in this  GitHub repository. Move the downloaded files into the "wwwroot" directory of your project. Include the files into your start page.
5. Register our tag namespace and helper in /Components/\_ViewImports.cshtml: 

```
@using DevExpress.RazorComponents
@addTagHelper *, DevExpress.RazorComponents
```

6. Your application is ready to use DevExpress Razor Components.

# Troubleshooting

## 1. DxDataGrid in Blazor

If you use Blazor (client-side hosting via MonoWASM) with DxDataGrid, you may see the following exception in your browser:

![Troubleshooting - No Generic Method 'Take' On Type System.Linq.Queryable](https://raw.githubusercontent.com/DevExpress/RazorComponents/master/media/Troubleshooting-NoGenericMethodTakeOnTypeSystemLinqQueryable.png)

> "System.InvalidOperationException: No generic method 'Take' on type 'System.Linq.Queryable' is compatible with the supplied type arguments and arguments."

Please refer the [original mono issue in GitHub](https://github.com/mono/mono/issues/12917#issuecomment-462925005) to resolve the issue.

Alternatively, your can simply turn off the linker. To do this, locate the <ProjectName>.Client.csproj file and add the following line:

```
<BlazorLinkOnBuild>false</BlazorLinkOnBuild>
```

Project content should look like this:

```
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
  ...
    <BlazorLinkOnBuild>false</BlazorLinkOnBuild>
  </PropertyGroup>
  ...
</Project>
```




