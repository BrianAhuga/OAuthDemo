# OAuthDemo

A demonstration **ASP.NET Core MVC application** showcasing user authentication with **ASP.NET Core Identity** and **Google OAuth 2.0**.

The project explores how to integrate an external identity provider with an ASP.NET Core application, allowing users to authenticate using their Google accounts alongside the application's built-in identity system.

## Overview

**OAuthDemo** is a learning and demonstration project focused on implementing modern authentication workflows in an ASP.NET Core MVC application.

The application combines:

* ASP.NET Core MVC
* ASP.NET Core Identity
* Google OAuth 2.0
* External authentication
* User account management
* Cookie-based authentication

The project is intended to provide a practical example of how applications can delegate authentication to an external provider while still managing authenticated users through ASP.NET Core Identity.

## Features

* User registration and login
* User logout
* ASP.NET Core Identity integration
* Google account authentication
* External OAuth authentication
* Authentication cookie management
* MVC architecture
* Secure configuration of OAuth credentials
* Integration between Identity and an external authentication provider

## Technology Stack

| Technology                         | Purpose                            |
| ---------------------------------- | ---------------------------------- |
| **C#**                             | Primary programming language       |
| **ASP.NET Core**                   | Application framework              |
| **ASP.NET Core MVC**               | Web application architecture       |
| **ASP.NET Core Identity**          | User and authentication management |
| **OAuth 2.0**                      | External authentication            |
| **Google OAuth**                   | Google account authentication      |
| **Entity Framework Core**          | Identity data persistence          |
| **SQL Server / Database Provider** | User data storage                  |

## Authentication Flow

The Google OAuth authentication flow follows the general process:

```text
User
  │
  ▼
ASP.NET Core Application
  │
  │ Sign in with Google
  ▼
Google Authorization Server
  │
  │ User authenticates
  │ Grants permission
  ▼
Application Callback
  │
  ▼
ASP.NET Core Identity
  │
  │ Creates or associates user
  ▼
Authenticated Session
```

This allows users to authenticate through Google without the application needing to directly handle their Google password.

## Project Structure

```text
OAuthDemo/
│
├── OAuthDemo/
│   ├── Controllers/
│   ├── Data/
│   ├── Models/
│   ├── Views/
│   ├── Areas/
│   ├── wwwroot/
│   ├── Program.cs
│   └── appsettings.json
│
├── OAuthDemo.sln
└── README.md
```

## Getting Started

### Prerequisites

Make sure you have the following installed:

* [.NET SDK](https://dotnet.microsoft.com/download)
* Visual Studio 2022 or Visual Studio Code
* Git
* A Google account
* Google Cloud project with OAuth credentials configured

### Clone the Repository

```bash
git clone https://github.com/BrianAhuga/OAuthDemo.git
```

Navigate to the project:

```bash
cd OAuthDemo
```

### Restore Dependencies

```bash
dotnet restore
```

### Configure Google OAuth

To enable Google authentication, create OAuth credentials through the **Google Cloud Console**.

You will need:

* Client ID
* Client Secret
* Authorized redirect URI

Store OAuth credentials securely using **User Secrets**, environment variables, or another secure configuration mechanism.

For local development, User Secrets can be initialized with:

```bash
dotnet user-secrets init
```

Then configure the credentials:

```bash
dotnet user-secrets set "Authentication:Google:ClientId" "YOUR_CLIENT_ID"
dotnet user-secrets set "Authentication:Google:ClientSecret" "YOUR_CLIENT_SECRET"
```

**Never commit Google OAuth client secrets to GitHub.**

### Run the Application

```bash
dotnet run
```

Alternatively, open the solution in Visual Studio and run the `OAuthDemo` project.

## OAuth Concepts Demonstrated

This project provides practical exposure to several important authentication concepts.

### Authentication vs Authorization

Authentication determines **who the user is**, while authorization determines **what the authenticated user is allowed to access**.

### OAuth 2.0

OAuth 2.0 provides a standardized framework that allows applications to obtain authorized access through an external identity provider.

### External Authentication

The application demonstrates how an ASP.NET Core application can integrate an external provider such as Google for user authentication.

### ASP.NET Core Identity

Identity provides the application's user-management infrastructure, including user accounts, authentication state, and associated identity data.

## Security Considerations

This project is intended for learning and demonstration purposes.

When adapting the implementation for production:

* Store secrets outside source control.
* Use HTTPS.
* Validate OAuth redirect URIs carefully.
* Configure appropriate cookie security settings.
* Use secure production connection strings.
* Apply appropriate authorization policies.
* Keep dependencies updated.
* Avoid exposing authentication configuration publicly.
* Use environment-specific configuration.

## Learning Objectives

This project demonstrates:

* ASP.NET Core MVC
* ASP.NET Core Identity
* OAuth 2.0 fundamentals
* Google authentication
* External login providers
* Authentication middleware
* User account management
* Secure application configuration
* Dependency injection
* Authentication and authorization concepts

## Future Improvements

Potential extensions include:

* Microsoft authentication
* GitHub authentication
* Facebook authentication
* JWT-based API authentication
* Role-based authorization
* Custom authorization policies
* Two-factor authentication
* Account linking
* Email confirmation
* Password recovery
* Authentication audit logging
* API integration

## Author

**Brian Ahuga**

Software Engineer specializing in scalable backend systems, enterprise web applications, secure authentication, and modern software development.

GitHub: [BrianAhuga](https://github.com/BrianAhuga)

## License

This project is intended for learning, experimentation, and portfolio demonstration.
