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

You can run the application directly in the VS Code interface using the '''run -> Start Debugging''' click sequence. 

The application will run on '''https://localhost:5001/'''

### Standalone Snippets

#### Run ARM Templates in Azure Shell

Assumes the arm template files are stored within the shell storage, so is not applicable for any CI/CD etc. Though this could work on an azure CLI.

'''az deployment group create --resource-group opt-vm-rg --template-file template.json --parameters parameters.json'''






## Note

- You can export to an ARM template a given resource group, which might be useful in certain scenarios: https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/export-template-portal



## TODO

- I committed a lot of .net junk (debug et al) files. I am not a c# expert, so I committed everything given the application itself is not the critical part of my learning for this project.




