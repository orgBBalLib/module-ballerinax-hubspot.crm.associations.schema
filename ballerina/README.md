## Overview

[HubSpot](https://www.hubspot.com/) is a cloud-based customer relationship management (CRM) platform that helps businesses manage marketing, sales, content, and customer service operations through a unified suite of tools designed to drive growth and enhance customer relationships.

The `ballerinax/hubspot.crm.associations.schema` package offers APIs to connect and interact with [HubSpot CRM Associations Schema API](https://developers.hubspot.com/docs/reference/api/crm/associations/association-schema) endpoints, specifically based on [HubSpot CRM API v4](https://developers.hubspot.com/docs/reference/api/crm/associations/association-schema).
## Setup guide

To use the HubSpot CRM Associations Schema connector, you must have access to the HubSpot API through a [HubSpot developer account](https://developers.hubspot.com/) and obtain an API access token. If you do not have a HubSpot account, you can sign up for one [here](https://app.hubspot.com/signup-hubspot/crm).

### Step 1: Create a HubSpot Account

1. Navigate to the [HubSpot website](https://www.hubspot.com/) and sign up for an account or log in if you already have one.

2. If you intend to use private apps for API access, note that while HubSpot offers free tools, certain API features and scopes may require a Professional or Enterprise plan subscription depending on the endpoints you need to access.

### Step 2: Generate an API Access Token

1. Log in to your HubSpot account.

2. In the main navigation bar, click the settings icon (gear icon) in the top right corner.

3. In the left sidebar menu, navigate to Integrations > Private Apps.

4. Click Create a private app.

5. On the Basic Info tab, enter a name and description for your app.

6. Navigate to the Scopes tab and select the required scopes for CRM associations schema access (such as `crm.schemas.associations.read` and `crm.schemas.associations.write`).

7. Click Create app in the top right corner, then review the information and click Continue creating.

8. Once the private app is created, copy the access token displayed on the screen.

> **Tip:** You must copy and store this key somewhere safe. It won't be visible again after you navigate away from the page for security reasons.
## Quickstart

To use the `HubSpot CRM Associations Schema` connector in your Ballerina application, update the `.bal` file as follows:

### Step 1: Import the module

```ballerina
import ballerina/oauth2;
import ballerinax/hubspot.crm.associations.schema as hscrmschema;
```

### Step 2: Instantiate a new connector

1. Create a `Config.toml` file and configure the obtained credentials:

```toml
clientId = "<Your_Client_Id>"
clientSecret = "<Your_Client_Secret>"
refreshToken = "<Your_Refresh_Token>"
```

2. Create a `hscrmschema:ConnectionConfig` and initialize the client:

```ballerina
configurable string clientId = ?;
configurable string clientSecret = ?;
configurable string refreshToken = ?;

final hscrmschema:Client hscrmschemaClient = check new ({
    auth: {
        clientId,
        clientSecret,
        refreshToken,
        credentialBearer: oauth2:POST_BODY_BEARER
    }
});
```

### Step 3: Invoke the connector operation

Now, utilize the available connector operations.

#### Create an association label

```ballerina
public function main() returns error? {
    hscrmschema:PublicAssociationDefinitionCreateRequest newLabel = {
        name: "partner_relationship",
        label: "Partner",
        inverseLabel: "Partner Of"
    };

    hscrmschema:CollectionResponseAssociationSpecWithLabelNoPaging response = check hscrmschemaClient->/["contacts"]/["companies"]/labels.post(newLabel);
}
```

### Step 4: Run the Ballerina application

```bash
bal run
```
## Examples

The `hubspot.crm.associations.schema` connector provides practical examples illustrating usage in various scenarios. Explore these [examples](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/tree/main/examples), covering the following use cases:

1. [Companies association management](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/tree/main/examples/companies_association_management) - Demonstrates how to manage and configure associations between company records in HubSpot CRM.
2. [Association analytics report](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/tree/main/examples/association_analytics_report) - Illustrates generating analytics reports based on association schema data.
3. [Automated configuration update](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/tree/main/examples/automated_configuration_update) - Shows how to automate the update of association schema configurations programmatically.