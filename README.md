# Boomi AKS Molecule Quickstart ARM Template

AKS Cluster Recommendation

| Environment   | AKS VM Size      | vCPU | Memory: GiB   | No. of System Node   | No. of user Node   |
| ------------- | ---------------- | ---- | ------------- | -------------------- | ------------------ |
| Development   | Standard_D4_v4   | 4    | 16            | 1                    | 1                  |
| Test      | Standard_D16_v4   | 16    | 64            | 2                    | 3                  |
| **Production**    | Standard_D16_v4  | 16   | 64            | 2                    | 3                  |
| **High Throughput Production**    | Standard_D32_v4  | 32   | 128           | 2                    | 3                  |


## Step 1: Enable AKS Preview

The following ‘az’ commands require you to install the [Azure command-line interface (CLI)](https://docs.microsoft.com/en-us/cli/azure/) on your personal computer, or you can use https://shell.azure.com/.

### Install the extension
`az extension add -n aks-preview`

### Update the extension to ensure the latest version is installed
`az extension update -n aks-preview`

## Step 2: Register the AKS-IngressApplicationGatewayAddon feature

`az feature register --name AKS-IngressApplicationGatewayAddon --namespace Microsoft.ContainerService`

Enter the following command to verify that the Azure Resource Feature has been registered.(Check registrationState parameter value is showing "Registered" in the result).


`az feature show --name AKS-IngressApplicationGatewayAddon --namespace Microsoft.ContainerService`

## Step 3: Register for Azure NetApp files
Follow the 7 steps from below link to register for NetApp files

https://docs.microsoft.com/en-us/azure/azure-netapp-files/azure-netapp-files-register

## Step 4: Deploy Azure ARM Template

[![Deploy To Azure](https://raw.githubusercontent.com/Azure/azure-quickstart-templates/master/1-CONTRIBUTION-GUIDE/images/deploytoazure.svg?sanitize=true)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FGanesh-Yeole%2Fquickstart-aks-boomi-molecule%2Fmain%2FmainTemplate.json/createUIDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2FGanesh-Yeole%2Fquickstart-aks-boomi-molecule%2Fmain%2FcreateUiDefinition.json)

`Note: If you delete the resources created by the quickstart template, you should be aware that Azure keeps deleted key vaults for 3 months. You should purge the Azure KeyVault to avoid a naming conflict should you run the quickstart again.`
