# Automated Configuration Update

This example demonstrates how to automate HubSpot association definition configuration updates based on status changes. The script creates an initial association configuration and then allows interactive status updates (NORMAL, SPECIAL, EMERGENCY, PANDEMIC) that dynamically adjust the `maxToObjectIds` parameter for contact-to-contact associations.

## Prerequisites

1. **HubSpot Setup**
   > Refer to the [HubSpot setup guide](https://github.com/ballerina-platform/ballerina-central-connectors/blob/main/docs/setup/hubspot/crm.associations.schema.md) to obtain your OAuth2 credentials.

2. **Configuration**
   
   Create a `Config.toml` file in the project root directory with your HubSpot OAuth2 credentials:

   ```toml
   clientId = "<Your Client ID>"
   clientSecret = "<Your Client Secret>"
   refreshToken = "<Your Refresh Token>"
   ```

## Run the Example

Execute the following command to run the example. The script will create an initial association configuration and then prompt you to enter status changes interactively.

```shell
bal run
```

Once running, the script will prompt you to enter a status code:
- Enter `1` for NORMAL (maxToObjectIds = 2)
- Enter `2` for SPECIAL (maxToObjectIds = 1)
- Enter `3` for EMERGENCY (maxToObjectIds = 5)
- Enter `4` for PANDEMIC (maxToObjectIds = 10)
- Enter `x` to exit

The script will display the configuration before and after each update, allowing you to observe the changes in real-time.