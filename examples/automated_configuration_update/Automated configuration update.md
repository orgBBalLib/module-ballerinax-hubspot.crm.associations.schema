# Automated Configuration Update

This example demonstrates how to automate HubSpot association definition configuration updates based on status changes. The script creates an initial association configuration between contacts and then allows interactive updates to the configuration's `maxToObjectIds` value based on different status levels (NORMAL, SPECIAL, EMERGENCY, PANDEMIC).

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

Execute the following command to run the example:

```shell
bal run
```

The script will:
1. Create an initial association definition configuration between contacts
2. Enter an interactive loop where you can input status changes
3. Display the configuration before and after each update

When prompted, enter one of the following options:
- `1` - Set status to NORMAL (maxToObjectIds = 2)
- `2` - Set status to SPECIAL (maxToObjectIds = 1)
- `3` - Set status to EMERGENCY (maxToObjectIds = 5)
- `4` - Set status to PANDEMIC (maxToObjectIds = 10)
- `x` - Exit the program