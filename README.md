# OAuthDemo

A demonstration **ASP.NET Core MVC application** showcasing user authentication with **ASP.NET Core Identity** and **Google OAuth 2.0**.

The project demonstrates how to integrate an external identity provider with an ASP.NET Core application, allowing users to authenticate using their Google accounts alongside the application's built-in identity system.

## Overview

**OAuthDemo** is a learning and demonstration project focused on implementing modern authentication workflows in an ASP.NET Core MVC application.

The application combines:

* ASP.NET Core MVC
* ASP.NET Core Identity
* Google OAuth 2.0
* External authentication
* User account management
* Cookie-based authentication

The project provides a practical example of how applications can delegate authentication to an external provider while still managing authenticated users through ASP.NET Core Identity.

## Features

* User registration and login
* User logout
* ASP.NET Core Identity integration
* Google account authentication
* External OAuth authentication
* Authentication cookie management
* MVC architecture
* Google OAuth configuration
* Integration between Identity and an external authentication provider

## Technology Stack

| Technology                | Purpose                            |
| ------------------------- | ---------------------------------- |
| **C#**                    | Primary programming language       |
| **ASP.NET Core**          | Application framework              |
| **ASP.NET Core MVC**      | Web application architecture       |
| **ASP.NET Core Identity** | User and authentication management |
| **OAuth 2.0**             | External authentication            |
| **Google OAuth**          | Google account authentication      |
| **Entity Framework Core** | Identity data persistence          |
| **SQL Server**            | Database                           |

## Authentication Flow

The Google OAuth authentication flow follows this general process:

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

This allows users to authenticate through Google without the application directly handling their Google password.

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
* A Google Cloud project with OAuth credentials configured

### Clone the Repository

```bash
git clone https://github.com/BrianAhuga/OAuthDemo.git
```

Navigate into the project:

```bash
cd OAuthDemo
```

### Restore Dependencies

```bash
dotnet restore
```

## Configure Google OAuth

To enable Google authentication, create OAuth credentials through the **Google Cloud Console**.

You will need:

* **Client ID**
* **Client Secret**

Once you have your credentials, add them to the `appsettings.json` file:

```json
{
  "Authentication": {
    "Google": {
      "ClientId": "YOUR_CLIENT_ID",
      "ClientSecret": "YOUR_CLIENT_SECRET"
    }
  }
}
```

Replace `YOUR_CLIENT_ID` and `YOUR_CLIENT_SECRET` with the credentials generated for your Google OAuth application.

You will also need to configure the appropriate **Authorized redirect URI** in your Google Cloud OAuth application.

For local development, the redirect URI will typically follow the format:

```text
https://localhost:PORT/signin-google
```

Replace `PORT` with the HTTPS port used by your application.

> **Security Note:** For local learning and demonstration purposes, the credentials can be configured in `appsettings.json`. However, for production applications, sensitive credentials should be stored using environment variables, User Secrets, Azure Key Vault, or another secure secrets-management solution. Never commit real client secrets to a public GitHub repository.

## Run the Application

Start the application using:

```bash
dotnet run
```

Alternatively, open the solution in Visual Studio and run the `OAuthDemo` project.

Once the application is running, navigate to the authentication page and select the **Google Login** option.

## OAuth Concepts Demonstrated

### Authentication vs Authorization

**Authentication** determines who the user is, while **authorization** determines what an authenticated user is allowed to access.

### OAuth 2.0

OAuth 2.0 provides a standardized framework that allows applications to authenticate users through an external identity provider.

### External Authentication

The project demonstrates how an ASP.NET Core application can integrate an external provider such as Google for user authentication.

### ASP.NET Core Identity

ASP.NET Core Identity provides the application's user-management infrastructure, including user accounts, authentication state, and identity-related data.

## Security Considerations

This project is intended primarily for learning and demonstration purposes.

When adapting the implementation for production:

* Store secrets outside source control.
* Use HTTPS.
* Configure OAuth redirect URIs carefully.
* Use secure production connection strings.
* Apply appropriate authorization policies.
* Keep dependencies updated.
* Protect authentication cookies.
* Avoid exposing sensitive configuration publicly.
* Use environment-specific configuration.

## Learning Objectives

This project demonstrates practical implementation of:

* ASP.NET Core MVC
* ASP.NET Core Identity
* OAuth 2.0
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
* Additional external identity providers

## Author

**Brian Ahuga**

Software Engineer specializing in scalable backend systems, enterprise web applications, secure authentication, and modern software development.

GitHub: [BrianAhuga](https://github.com/BrianAhuga)

## License

This project is intended for learning, experimentation, and portfolio demonstration.
