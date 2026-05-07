# Automated Configuration Update

This example demonstrates how to automate the management of HubSpot association definition configurations based on dynamic status changes. The script creates an initial configuration, then enters an interactive loop where users can update the configuration by selecting different status levels (NORMAL, SPECIAL, EMERGENCY, PANDEMIC), each corresponding to different `maxToObjectIds` values.

## Prerequisites

1. **HubSpot Setup**
   > Refer to the [HubSpot setup guide](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/tree/main/ballerina/Package.md#setup-guide) to obtain OAuth2 credentials.

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
1. Create an initial association definition configuration for contacts-to-contacts associations
2. Enter an interactive mode where you can input status changes
3. Display the configuration before and after each update

**Interactive Commands:**
- Enter `1` for NORMAL status (maxToObjectIds: 2)
- Enter `2` for SPECIAL status (maxToObjectIds: 1)
- Enter `3` for EMERGENCY status (maxToObjectIds: 5)
- Enter `4` for PANDEMIC status (maxToObjectIds: 10)
- Enter `x` or `X` to exit the program