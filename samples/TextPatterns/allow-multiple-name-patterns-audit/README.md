# Specify multiple name patterns for resources

Allow one of many name patterns to be used for resources.  

Sets policy to audit instead of deny.

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/?feature.customportal=false&microsoft_azure_policy=true&microsoft_azure_policy_policyinsights=true&feature.microsoft_azure_security_policy=true&microsoft_azure_marketplace_policy=true#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fgithub.com%2Fanthonyonazure%2Fazure-policy%2Fmaster%2Fsamples%2FTextPatterns%2Fallow-multiple-name-patterns%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzureRmPolicyDefinition -Name "allow-multiple-name-patterns-audit" -DisplayName "Allow one of many name patterns to be used for resources." -description "Allow one of many name patterns to be used for resources." -Policy 'https://github.com/anthonyonazure/azure-policy/blob/master/samples/TextPatterns/allow-multiple-name-patterns-audit/azurepolicy.rules.json' -Parameter 'https://github.com/anthonyonazure/azure-policy/blob/master/samples/TextPatterns/allow-multiple-name-patterns-audit/azurepolicy.parameters.json' -Mode All
$definition
$assignment = New-AzureRMPolicyAssignment -Name <assignmentname> -Scope <scope> -PolicyDefinition $definition
$assignment
````

## Try with CLI

````cli

az policy definition create --name 'allow-multiple-name-patterns-audit' --display-name 'Allow one of many name patterns to be used for resources.' --description 'Allow one of many name patterns to be used for resources.' --rules 'https://github.com/anthonyonazure/azure-policy/blob/master/samples/TextPatterns/allow-multiple-name-patterns-audit/azurepolicy.rules.json' --params 'https://github.com/anthonyonazure/azure-policy/blob/master/samples/TextPatterns/allow-multiple-name-patterns-audit/azurepolicy.parameters.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "allow-multiple-name-patterns" 
