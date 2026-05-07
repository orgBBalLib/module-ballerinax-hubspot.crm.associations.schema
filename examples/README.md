# Examples

The `hubspot.crm.associations.schema` connector provides practical examples illustrating usage in various scenarios. Explore these [examples](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/tree/main/examples), covering use cases like companies association management, association analytics report, and automated configuration update.

1. [Companies association management](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/tree/main/examples/companies_association_management) - Manage and configure associations between company records in HubSpot CRM.

2. [Association analytics report](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/tree/main/examples/association_analytics_report) - Generate analytical reports on association schemas and their usage across CRM objects.

3. [Automated configuration update](https://github.com/ballerina-platform/module-ballerinax-hubspot.crm.associations.schema/tree/main/examples/automated_configuration_update) - Automate the update of association schema configurations in HubSpot CRM.

## Prerequisites

1. Generate HubSpot credentials to authenticate the connector as described in the [Setup guide](https://central.ballerina.io/ballerinax/hubspot.crm.associations.schema/latest#setup-guide).

2. For each example, create a `Config.toml` file the related configuration. Here's an example of how your `Config.toml` file should look:

    ```toml
    token = "<Access Token>"
    ```

## Running an Example

Execute the following commands to build an example from the source:

* To build an example:

    ```bash
    bal build
    ```

* To run an example:

    ```bash
    bal run
    ```