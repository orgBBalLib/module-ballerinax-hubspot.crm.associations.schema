
# Ballerina hubspot.crm.associations.schema connector

[![Build](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/actions/workflows/ci.yml/badge.svg)](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/actions/workflows/ci.yml)
[![Trivy](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/actions/workflows/trivy-scan.yml/badge.svg)](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/actions/workflows/trivy-scan.yml)
[![GraalVM Check](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/actions/workflows/build-with-bal-test-graalvm.yml/badge.svg)](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/actions/workflows/build-with-bal-test-graalvm.yml)
[![GitHub Last Commit](https://img.shields.io/github/last-commit/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema.svg)](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/commits/master)
[![GitHub Issues](https://img.shields.io/github/issues/ballerina-platform/ballerina-library/module/hubspot.crm.associations.schema.svg?label=Open%20Issues)](https://github.com/ballerina-platform/ballerina-library/labels/module%hubspot.crm.associations.schema)

## Overview

[HubSpot](https://www.hubspot.com/) is a cloud-based customer relationship management (CRM) platform that helps businesses grow by connecting marketing, sales, content management, and customer service tools in one unified solution.

The `ballerinax/hubspot.crm.associations.schema` package offers APIs to connect and interact with [HubSpot CRM Associations Schema API](https://developers.hubspot.com/docs/api/crm/associations) endpoints, specifically based on [HubSpot CRM API v4](https://developers.hubspot.com/docs/api/crm/associations/v4).
## Setup guide

To use the HubSpot CRM Associations Schema connector, you must have access to the HubSpot API through a [HubSpot developer account](https://developers.hubspot.com/) and obtain an API access token. If you do not have a HubSpot account, you can sign up for one [here](https://app.hubspot.com/signup-hubspot/crm).

### Step 1: Create a HubSpot Account

1. Navigate to the [HubSpot website](https://www.hubspot.com/) and sign up for an account or log in if you already have one.

2. If you intend to use private apps for API access, note that while HubSpot offers free tools, certain API features and scopes may require a Professional or Enterprise plan subscription depending on the endpoints you need to access.

### Step 2: Generate an API Access Token

1. Log in to your HubSpot account.

2. In the main navigation bar, click the settings icon (gear icon) in the top right corner.

3. In the left sidebar menu, navigate to Integrations, then select Private Apps.

4. Click Create a private app.

5. On the Basic Info tab, provide a name and description for your app.

6. Navigate to the Scopes tab and select the required scopes for CRM associations schema access (e.g., `crm.schemas.contacts.read`, `crm.schemas.contacts.write`, or other relevant schema scopes).

7. Click Create app in the top right corner, then review the information and click Continue creating.

8. Once the private app is created, your access token will be displayed. Click Show token to reveal it.

> **Tip:** You must copy and store this key somewhere safe. It won't be visible again without clicking "Show token," and for security reasons, you should treat it like a password and never expose it publicly.
## Quickstart

To use the `HubSpot CRM Associations Schema` connector in your Ballerina application, update the `.bal` file as follows:

### Step 1: Import the module

```ballerina
import ballerina/oauth2;
import ballerinax/hubspot.crm.associations.schema as hsassocschema;
```

### Step 2: Instantiate a new connector

1. Create a `Config.toml` file and configure the obtained credentials:

```toml
clientId = "<Your_Client_Id>"
clientSecret = "<Your_Client_Secret>"
refreshToken = "<Your_Refresh_Token>"
```

2. Create a `hsassocschema:ConnectionConfig` and initialize the client:

```ballerina
configurable string clientId = ?;
configurable string clientSecret = ?;
configurable string refreshToken = ?;

final hsassocschema:Client hsassocschemaClient = check new ({
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

#### Retrieve all association limits

```ballerina
public function main() returns error? {
    hsassocschema:CollectionResponsePublicAssociationDefinitionUserConfigurationNoPaging response = check hsassocschemaClient->/definitions/configurations/all.get();
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
## Build from the source

### Setting up the prerequisites

1. Download and install Java SE Development Kit (JDK) version 21. You can download it from either of the following sources:

    * [Oracle JDK](https://www.oracle.com/java/technologies/downloads/)
    * [OpenJDK](https://adoptium.net/)

    > **Note:** After installation, remember to set the `JAVA_HOME` environment variable to the directory where JDK was installed.

2. Download and install [Ballerina Swan Lake](https://ballerina.io/).

3. Download and install [Docker](https://www.docker.com/get-started).

    > **Note**: Ensure that the Docker daemon is running before executing any tests.

4. Export Github Personal access token with read package permissions as follows,

    ```bash
    export packageUser=<Username>
    export packagePAT=<Personal access token>
    ```

### Build options

Execute the commands below to build from the source.

1. To build the package:

    ```bash
    ./gradlew clean build
    ```

2. To run the tests:

    ```bash
    ./gradlew clean test
    ```

3. To build the without the tests:

    ```bash
    ./gradlew clean build -x test
    ```

4. To run tests against different environments:

    ```bash
    ./gradlew clean test -Pgroups=<Comma separated groups/test cases>
    ```

5. To debug the package with a remote debugger:

    ```bash
    ./gradlew clean build -Pdebug=<port>
    ```

6. To debug with the Ballerina language:

    ```bash
    ./gradlew clean build -PbalJavaDebug=<port>
    ```

7. Publish the generated artifacts to the local Ballerina Central repository:

    ```bash
    ./gradlew clean build -PpublishToLocalCentral=true
    ```

8. Publish the generated artifacts to the Ballerina Central repository:

    ```bash
    ./gradlew clean build -PpublishToCentral=true
    ```

## Contribute to Ballerina

As an open-source project, Ballerina welcomes contributions from the community.

For more information, go to the [contribution guidelines](https://github.com/ballerina-platform/ballerina-lang/blob/master/CONTRIBUTING.md).

## Code of conduct

All the contributors are encouraged to read the [Ballerina Code of Conduct](https://ballerina.io/code-of-conduct).


## Useful links

* For more information go to the [`hubspot.crm.associations.schema` package](https://central.ballerina.io/ballerinax/hubspot.crm.associations.schema/latest).
* For example demonstrations of the usage, go to [Ballerina By Examples](https://ballerina.io/learn/by-example/).
* Chat live with us via our [Discord server](https://discord.gg/ballerinalang).
* Post all technical questions on Stack Overflow with the [#ballerina](https://stackoverflow.com/questions/tagged/ballerina) tag.
