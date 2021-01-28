# Deploy a WordPress Web App

## Overview

Deploy a customised version of WordPress designed to work run in an Azure Web App and link to an Azure Database for MySQL resource with SSL enforced and TLS 1.2 enabled.

**Please check certificate expiry before deployment.**

Link: [Azure WordPress repo](https://github.com/Hamilton-Brown-Digital/WordPress-On-Azure-Web-App-MySQL-TLS-SSL)

Certificate source: [Baltimore CyberTrust Root](https://www.digicert.com/kb/digicert-root-certificates.htm)

## Prerequisites
- An existing Linux based App Service Plan
- An existing Azure Database for MySQL resource with SSL enforced and TLS 1.2 enabled
- A schema already created with an associated user and password

## Deployment:

Click the button below to deploy a new WordPress instance.

This will:
- Create a new Azure Web App, linking it to the existing App Service Plan. The database details will be set as Application Settings. The code will be pulled from the [Six Degrees Azure WordPress repo](https://github.com/sixdegreesazure/WordPress-On-Azure-Web-App-MySQL-TLS-SSL).

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FHamilton-Brown-Digital%2FDeploy_wordpress_site_azure%2Fmain%2Farm%2Ftemplate.json" target="_blank">
  <img src="https://aka.ms/deploytoazurebutton"/>
</a>



<!-- 

https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/deploy-to-azure-button

-->
