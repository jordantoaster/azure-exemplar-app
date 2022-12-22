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

##### Catalog & Inventory

You can run the a given application directly in the VS Code interface using the '''run -> Start Debugging''' click sequence. 

The catalog (for example) application will run on '''https://localhost:5001/'''

##### Cart

- Run the Dockerfile to create an image.
- Launch the image into a container
- Visit '''http://localhost:5004/'''

You can do these actions in VSCode or via cli as desired. 

#### Order

- Download azure functions core tools.
- Install vs code azure functions extension.
- Run -> Run Without Debugging, terminal will show two urls for locally hosted functions:
	- e.g. http://localhost:7071/api/ProcessOrderStorage
- You can also use the Azure extension UI in the workspace tab to use the functions. 


### Resources

- Catalog + Weather VM creds: jordanadmin + 4YSG4wDaJb2tSC!
- Catalog IP: Public: 13.80.251.88 Private: 10.0.0.5
- Port for Catalog and weather app is 8080.
- Weather IP: 52.236.132.250

### Standalone Snippets

#### Run ARM Templates in Azure Shell

Assumes the arm template files are stored within the shell storage, so is not applicable for any CI/CD etc. Though this could work on an azure CLI.

'''az deployment group create --resource-group opt-vm-rg --template-file template.json --parameters parameters.json'''

#### Publish a Dot Net App Artifact

You can create a deployable application artifact using the command '''dotnet publish -o publish''' in the terminal for a given application folder, whether catalog, inventory or other.

#### Pushing to Azure container registry

Once you have an azure registry created, you can push images to it using VS Code docker extension or the cli using the typical commands for pushing images to registries.

#### Running image on ASK clusters

Note: Assumes an image exists in ACR.

- Create an AKS cluster using the Azure Kubernetes Service, export an arm template if desired. Ensure it has an ACR integration setup in the relevant tab to your registry.  
- Ensure Azure AKS cli tools installed - '''az aks install-cli'''
- Set azure AKS cli tools to the path '''set PATH=%PATH%;"c:\Users\<USERNAME>\.azure-kubectl"'''
- Get AKS cluster credentials - '''aks get-credentials --resource-group readit-app-rg --name cart-aks'''
- Deploy container to AKS - '''kubectl apply -f deployment.yaml'''
- From Azure ASK portal, in your deployed AKS app you can grab and view the app on the external ip. 



## Note

- You can export to an ARM template a given resource group, which might be useful in certain scenarios: https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/export-template-portal

- RDP connecting to a VM can be a bit odd, where the password used does not actually allow access. I resolved this by resetting the password to a more secure, random sequence of letters, casing, numbers and symbols. 

- When accesiong Ubuntu Machine via Putty, the password needs to be typed not copied. 

- Azure app service is a fantastic tool for rapid deployment of web apps, see here for a Python example: https://learn.microsoft.com/en-us/azure/app-service/quickstart-python?tabs=flask%2Cwindows%2Cazure-cli%2Cvscode-deploy%2Cdeploy-instructions-azportal%2Cterminal-bash%2Cdeploy-instructions-zip-azcli#1---sample-application
	- It is such a fantastic service that its almost free from requiring infrastructure as code, with easy CI processes and lite azure commands if done via CLI.

- ARM templates can be downloaded when/during a resource is being created via the Export Template tab on the left panel of the Azure UI for a resource. 
	- This is possible at the level of a resource group overall as well. 
	- You can then use the same template in a different resource group to act as a different environment if desired. 


## TODO




