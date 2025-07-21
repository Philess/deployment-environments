# WebApp-with-SQL Environment Template

This environment template deploys an Azure Web App with an Azure SQL Database.

## Resources Deployed

- **Azure App Service Plan** (Standard S1 tier)
- **Azure Web App** 
- **Azure SQL Server**
- **Azure SQL Database** (Basic tier, 2GB)
- **SQL Server Firewall Rule** (allows Azure services)

## Parameters

- **name**: Name of the Web App (required)
- **sqlAdminLogin**: Administrator username for the SQL Server (required)
- **sqlAdminPassword**: Administrator password for the SQL Server (required, secure)

## Outputs

- **webAppUrl**: The URL of the deployed web app
- **sqlConnectionString**: Connection string for the SQL database
- **sqlServerFqdn**: Fully qualified domain name of the SQL server

## Connection String

The web app is automatically configured with a connection string named `DefaultConnection` that points to the SQL database. This connection string is available in the web app's application settings and can be used by your application code.

## Security Considerations

- The SQL server is configured to allow connections from Azure services
- The SQL admin password should be a strong, secure password
- Consider implementing additional security measures such as:
  - Virtual network integration
  - Private endpoints
  - Azure AD authentication
  - Firewall rules for specific IP ranges

## Usage

Deploy this template through Azure Deployment Environments by providing the required parameters. The template will create all necessary resources and configure the web app with the appropriate connection string to access the SQL database.
