# Companies Association Management

This example demonstrates how to manage HubSpot company-to-company association definitions by creating a headquarters-franchise relationship, reading existing associations, updating the association labels, and then cleaning up by deleting the created definitions.

## Prerequisites

1. **HubSpot Setup**
   > Refer to the [HubSpot CRM Associations Schema setup guide](https://central.ballerina.io/ballerinax/hubspot.crm.associations.schema/latest) to obtain OAuth2 credentials.

2. **Configuration**
   
   Create a `Config.toml` file in the project root directory with your HubSpot OAuth2 credentials:

   ```toml
   clientId = "<Your Client ID>"
   clientSecret = "<Your Client Secret>"
   refreshToken = "<Your Refresh Token>"
   ```

## Run the Example

Execute the following command to run the example. The script will print its progress to the console as it creates, reads, updates, and deletes the company association definitions.

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