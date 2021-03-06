# Ensure resource name matches pattern

Ensure resource names match the naming pattern.

Sets policy to audit instead of deny.

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/?feature.customportal=false&microsoft_azure_policy=true&microsoft_azure_policy_policyinsights=true&feature.microsoft_azure_security_policy=true&microsoft_azure_marketplace_policy=true#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fgithub.com%2Fanthonyonazure%2Fazure-policy%2Fmaster%2Fsamples%2FTextPatterns%2Fenforce-match-pattern%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzureRmPolicyDefinition -Name "enforce-match-pattern" -DisplayName "Ensure resource names match the naming pattern" -description "Ensure resource names match the naming pattern" -Policy 'https://github.com/anthonyonazure/azure-policy/blob/master/samples/TextPatterns/enforce-match-pattern-audit/azurepolicy.rules.json' -Parameter 'https://github.com/anthonyonazure/azure-policy/blob/master/samples/TextPatterns/enforce-match-pattern-audit/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzureRMPolicyAssignment -Name <assignmentname> -Scope <scope> -PolicyDefinition $definition
$assignment 
````

## Try with CLI

````cli
az policy definition create --name 'enforce-match-pattern' --display-name 'Ensure resource names match the naming pattern' --description 'Ensure resource names match the naming pattern' --rules '
https://github.com/anthonyonazure/azure-policy/blob/master/samples/TextPatterns/enforce-match-pattern-audit/azurepolicy.rules.json' --params 'https://github.com/anthonyonazure/azure-policy/blob/master/samples/TextPatterns/enforce-match-pattern-audit/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "enforce-match-pattern"
````
