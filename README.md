# azure-exemplar-app

Based on the course linked blow, sections 6 onwards:

https://www.udemy.com/course/microsoft-azure-from-zero-to-hero-the-complete-guide

## Working Notes

### Installation & Setup

#### Required Install

- .NET Core 6 SDK
- VS Code

Installed in the same drive, which has to be the C drive for .NET Core. 

#### Required VS Code Extensions

- Azure App Services
- C#
- Azure Accounts

During setup, I got a few errors related to "OmniSharp" in the output window - '''OmniSharp.MSBuild.ProjectManager Attempted to update project that is not loaded'''. I chose to ignore this error and the application ran as expected without resolving it. 

### Running the App

#### Locally

You can run the application directly in the VS Code interface using the '''run -> Start Debugging''' click sequence. 

The application will run on '''https://localhost:5001/'''

#### Publish Catalog App to an Azure VM

- https://www.udemy.com/course/microsoft-azure-from-zero-to-hero-the-complete-guide/learn/lecture/24413374#overview
- Highly manual and reflects an approach I would never repeat. 


### Resources

PENDING - add here connection strings etc. 

- Catalog + Weather VM creds: jordanadmin + 4YSG4wDaJb2tSC!
- Catalog IP: Public: 13.80.251.88 Private: 10.0.0.5
- Port for Catalog and weather app is 8080.
- Weather IP: 52.236.132.250

### Standalone Snippets

#### Run ARM Templates in Azure Shell

Assumes the arm template files are stored within the shell storage, so is not applicable for any CI/CD etc. Though this could work on an azure CLI.

'''az deployment group create --resource-group opt-vm-rg --template-file template.json --parameters parameters.json'''


## Note

- You can export to an ARM template a given resource group, which might be useful in certain scenarios: https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/export-template-portal

- RDP connecting to a VM can be a bit odd, where the password used does not actually allow access. I resolved this by resetting the password to a more secure, random sequence of letters, casing, numbers and symbols. 

- When accesiong Ubuntu Machine via Putty, the password needs to be typed not copied. 

## TODO




