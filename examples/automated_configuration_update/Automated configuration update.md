# Automated Configuration Update

This example demonstrates how to automate HubSpot association definition configuration updates based on status changes. The script creates an initial association configuration and then allows interactive status updates (NORMAL, SPECIAL, EMERGENCY, PANDEMIC), automatically adjusting the `maxToObjectIds` parameter accordingly.

## Prerequisites

1. **HubSpot Setup**
   > Refer to the [HubSpot setup guide](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/blob/main/ballerina/Package.md#setup-guide) to obtain OAuth2 credentials.

2. **Configuration**
   
   Create a `Config.toml` file in the project root directory with your HubSpot OAuth2 credentials:

   ```toml
   clientId = "<Your Client ID>"
   clientSecret = "<Your Client Secret>"
   refreshToken = "<Your Refresh Token>"
   ```

## Run the Example

Execute the following command to run the example:

```shell
bal run
```

The script will:
1. Create an initial association definition configuration between contacts
2. Enter an interactive loop where you can input status codes:
   - `1` - NORMAL (maxToObjectIds: 2)
   - `2` - SPECIAL (maxToObjectIds: 1)
   - `3` - EMERGENCY (maxToObjectIds: 5)
   - `4` - PANDEMIC (maxToObjectIds: 10)
   - `x` - Exit the program

When you change the status, the script will display the configuration before and after the update.