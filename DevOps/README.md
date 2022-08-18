## DevOps
---
###  [#1 Bicep CheatSheet](./1.BicepCheatSheet.png)

#### 💪 What’s Azure Bicep?
Azure Bicep is a domain-specific language (DSL) that uses declarative syntax to deploy Azure resources and offers a first-class authoring experience for your infrastructure-as-code (IaC) solutions in Azure.

In addition, although Azure’s Resource Manager still operates based on the JSON format, and your Azure Bicep templates will be converted to Json format when you submit them, it is clear that Azure Bicep templates are more readable and easier to maintain for developers than Json-based Azure Resource Manager (ARM) templates.

#### 💪 𝗧𝗵𝗲 𝘀𝘁𝗿𝘂𝗰𝘁𝘂𝗿𝗲 𝗼𝗳 𝗮 𝗯𝗮𝘀𝗶𝗰 𝗕𝗶𝗰𝗲𝗽 𝗳𝗶𝗹𝗲

##### Parameters
A parameter lets you bring in values from outside the bicep file. It’s usually a good idea to use parameters for things that will change between each deployment.

You can declare a new parameter as follows:

```
𝗽𝗮𝗿𝗮𝗺 <𝗽𝗮𝗿𝗮𝗺_𝗻𝗮𝗺𝗲> <𝗽𝗮𝗿𝗮𝗺_𝘁𝘆𝗽𝗲>
```

- **𝗽𝗮𝗿𝗮𝗺** tells Bicep that you’re defining a parameter.
- **<𝗽𝗮𝗿𝗮𝗺_𝗻𝗮𝗺𝗲>** is the name of the parameter.
- **<𝗽𝗮𝗿𝗮𝗺_𝘁𝘆𝗽𝗲>** is the type of the parameter.


##### Variables
Variables let you store important information in one place and refer to it throughout the template without having to copy and paste it.

You can declare a new variable as follows:
```
var <var_name> = <var_value>
```

- **var** tells Bicep that you’re defining a variable.
- You do not need to provide the type of the variable but you must provide the value for the variable.


##### Resources
The main thing you’ll do with Bicep templates is define your Azure resources. This example defines two resources, App Service plan and App Service.

You can declare a new resource as follows:
```
resource <symbolic_name> ‘<resource_type>@<API_version>’
```
- **resource** tells Bicep that you’re defining a resource.
- **<symbolic_name>** is used within Bicep to refer to the resource.
- **<resource_type>** tells Bicep what resource type you want to create.
- **<API_version>** is the version of the resource API that Bicep will use when it creates the resource.


#### 💪 What Tools Do You Need to Install?
##### Development Tools
Let’s start with development tools that can be used to create Bicep files:

- **Visual Studio Code**, also commonly referred to as VS Code, is a source-code editor made by Microsoft for Windows, Linux and macOS.
- **The Bicep VS Code extension** provides language support and resource autocompletion and helps you create and validate Bicep files.

##### Deployment Tools
In addition to the development tools, you will also need to install the **Bicep CLI** and one of the following two tools for your deployment environment:

- **Azure CLI (version 2.20.0 or later)** will automatically install the Bicep CLI when a command is executed that needs it.
- **Azure PowerShell (version 5.6.0 or later)** doesn’t automatically install the Bicep CLI.

### Ref:
https://docs.microsoft.com/en-nz/azure/azure-resource-manager/bicep/install?WT.mc_id=DT-MVP-5001664#vs-code-and-bicep-extension

https://docs.microsoft.com/en-us/learn/paths/fundamentals-bicep/?WT.mc_id=DT-MVP-5001664