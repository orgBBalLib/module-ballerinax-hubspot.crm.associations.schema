# Companies Association Management

This example demonstrates how to manage HubSpot company association definitions by creating a headquarters-franchise relationship between companies, reading existing association definitions, updating the labels, and then deleting the association definitions.

## Prerequisites

1. **HubSpot Setup**
   > Refer to the [HubSpot setup guide](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/tree/main/ballerina/Package.md) to obtain OAuth2 credentials.

2. **Configuration**
   
   Create a `Config.toml` file in the project root directory with your HubSpot OAuth2 credentials:

   ```toml
   clientId = "<Your Client ID>"
   clientSecret = "<Your Client Secret>"
   refreshToken = "<Your Refresh Token>"
   ```

## Run the Example

Execute the following command to run the example. The script will create a headquarters-franchise association definition between companies, read all association definitions, update the labels, and then delete the created associations.

```shell
bal run
```

Upon successful execution, you will see output similar to:

```
Managing Headquarters-Franchise company association...

Association label created successfully

Association definitions read: 
{results: [...]}

Association label updated successfully

Association definition with ID <id> has been deleted.
```