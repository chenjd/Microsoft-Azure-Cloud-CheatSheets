## DevOps

###  [#1 Bicep CheatSheet](./1.BicepCheatSheet.png)

<a href="https://github.com/chenjd/Microsoft-Azure-Cloud-CheatSheets/blob/main/DevOps/1.BicepCheatSheet.png"><img src="https://github.com/chenjd/Microsoft-Azure-Cloud-CheatSheets/blob/main/DevOps/1.BicepCheatSheet.png"  height="256px" align="right"></a>


#### ๐ช Whatโs Azure Bicep?
Azure Bicep is a domain-specific language (DSL) that uses declarative syntax to deploy Azure resources and offers a first-class authoring experience for your infrastructure-as-code (IaC) solutions in Azure.

In addition, although Azureโs Resource Manager still operates based on the JSON format, and your Azure Bicep templates will be converted to Json format when you submit them, it is clear that Azure Bicep templates are more readable and easier to maintain for developers than Json-based Azure Resource Manager (ARM) templates.

#### ๐ช ๐ง๐ต๐ฒ ๐๐๐ฟ๐๐ฐ๐๐๐ฟ๐ฒ ๐ผ๐ณ ๐ฎ ๐ฏ๐ฎ๐๐ถ๐ฐ ๐๐ถ๐ฐ๐ฒ๐ฝ ๐ณ๐ถ๐น๐ฒ

##### Parameters
A parameter lets you bring in values from outside the bicep file. Itโs usually a good idea to use parameters for things that will change between each deployment.

You can declare a new parameter as follows:

```
๐ฝ๐ฎ๐ฟ๐ฎ๐บ <๐ฝ๐ฎ๐ฟ๐ฎ๐บ_๐ป๐ฎ๐บ๐ฒ> <๐ฝ๐ฎ๐ฟ๐ฎ๐บ_๐๐๐ฝ๐ฒ>
```

- **๐ฝ๐ฎ๐ฟ๐ฎ๐บ** tells Bicep that youโre defining a parameter.
- **<๐ฝ๐ฎ๐ฟ๐ฎ๐บ_๐ป๐ฎ๐บ๐ฒ>** is the name of the parameter.
- **<๐ฝ๐ฎ๐ฟ๐ฎ๐บ_๐๐๐ฝ๐ฒ>** is the type of the parameter.


##### Variables
Variables let you store important information in one place and refer to it throughout the template without having to copy and paste it.

You can declare a new variable as follows:
```
var <var_name> = <var_value>
```

- **var** tells Bicep that youโre defining a variable.
- You do not need to provide the type of the variable but you must provide the value for the variable.


##### Resources
The main thing youโll do with Bicep templates is define your Azure resources. This example defines two resources, App Service plan and App Service.

You can declare a new resource as follows:
```
resource <symbolic_name> โ<resource_type>@<API_version>โ
```
- **resource** tells Bicep that youโre defining a resource.
- **<symbolic_name>** is used within Bicep to refer to the resource.
- **<resource_type>** tells Bicep what resource type you want to create.
- **<API_version>** is the version of the resource API that Bicep will use when it creates the resource.


#### ๐ช What Tools Do You Need to Install?
##### Development Tools
Letโs start with development tools that can be used to create Bicep files:

- **Visual Studio Code**, also commonly referred to as VS Code, is a source-code editor made by Microsoft for Windows, Linux and macOS.
- **The Bicep VS Code extension** provides language support and resource autocompletion and helps you create and validate Bicep files.

##### Deployment Tools
In addition to the development tools, you will also need to install the **Bicep CLI** and one of the following two tools for your deployment environment:

- **Azure CLI (version 2.20.0 or later)** will automatically install the Bicep CLI when a command is executed that needs it.
- **Azure PowerShell (version 5.6.0 or later)** doesnโt automatically install the Bicep CLI.

### Ref:
https://docs.microsoft.com/en-nz/azure/azure-resource-manager/bicep/install?WT.mc_id=DT-MVP-5001664#vs-code-and-bicep-extension

https://docs.microsoft.com/en-us/learn/paths/fundamentals-bicep/?WT.mc_id=DT-MVP-5001664
