# Change Log

This file contains all the notable changes done to the Ballerina connector through the releases.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- New 'hapikey' field added to ApiKeysConfig
- New 'WORK' enum value added to category fields across multiple types
- Added documentation comments to all types and fields
- Added class-level documentation comment 'Basepom for all HubSpot Projects'

### Changed
- ApiKeysConfig type changed: field 'privateAppLegacy' was previously first field, now 'hapikey' field added and field order changed - existing code using positional initialization breaks
- ApiKeysConfig now requires 'hapikey' field which did not exist before, making it a breaking addition to a required config type
- Enum value ordering changed in multiple types (e.g., 'PENDING|PROCESSING|CANCELED|COMPLETE' changed to 'CANCELED|COMPLETE|PENDING|PROCESSING') - while values are same, Ballerina union type ordering can affect compatibility
- Category enum values expanded: 'HUBSPOT_DEFINED|USER_DEFINED|INTEGRATOR_DEFINED' changed to 'HUBSPOT_DEFINED|INTEGRATOR_DEFINED|USER_DEFINED|WORK' in multiple types (AssociationSpecWithLabel, PublicAssociationDefinitionUserConfiguration, PublicAssociationDefinitionConfigurationUpdateResult, PublicAssociationDefinitionConfigurationUpdateRequest, PublicAssociationDefinitionConfigurationCreateRequest) - adding 'WORK' value and reordering
- API key authentication no longer injects private-app and private-app-legacy headers automatically in resource functions - breaking change for clients relying on API key auth
- Resource function 'get definitions/configurations/all' comment changed from 'Retrieve all association definitions and configurations' to 'Retrieve all association limits' - functional behavior may differ

### Fixed
- Simplified auth config handling in init() by removing type cast and using direct variable
- Removed redundant header manipulation code for API key injection in resource functions
- Code refactoring to reduce duplication in resource function implementations
