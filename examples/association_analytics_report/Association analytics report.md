# Association Analytics Report

This example demonstrates how to generate an analytics report for HubSpot CRM association definitions and configurations. The script connects to HubSpot's Association Schema API to count and categorize different types of association configurations (HubSpot-defined, user-defined, and integrator-defined) and provides a summary analysis.

## Prerequisites

1. **HubSpot Setup**
   > Refer to the [HubSpot setup guide](https://central.ballerina.io/ballerinax/hubspot.crm.associations.schema/latest#setup-guide) to obtain OAuth2 credentials.

2. **Configuration**
   
   Create a `Config.toml` file in the project root directory with your HubSpot OAuth2 credentials:

   ```toml
   clientId = "<Your Client ID>"
   clientSecret = "<Your Client Secret>"
   refreshToken = "<Your Refresh Token>"
   ```

## Run the Example

Execute the following command to run the example. The script will analyze your HubSpot association configurations and definitions, then print the categorized counts to the console.

```shell
bal run
```

Upon successful execution, you will see output similar to:

```
Total Configurations: 15
HubSpot Defined: 10
User Defined: 3
Integrator Defined: 2

Total Association Definitions: 8
HubSpot Defined: 5
User Defined: 2
Integrator Defined: 1
```