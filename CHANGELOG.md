# Change Log

This file contains all the notable changes done to the Ballerina connector through the releases.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Added 'WORK' category value to association category enums
- Added 'hapikey' field to ApiKeysConfig
- Added documentation comments to all public types and fields
- Added class-level doc comment 'Basepom for all HubSpot Projects' to Client class
- Simplified auth handling in init function using typed variable instead of type cast

### Changed
- ApiKeysConfig record changed: removed 'privateAppLegacy' and 'privateApp' fields and replaced with 'hapikey', 'privateApp', 'privateAppLegacy' - field order changed and 'hapikey' added as new required field, breaking existing ApiKeysConfig instantiations
- API key authentication headers removed from all resource functions - private-app and private-app-legacy headers are no longer injected, breaking authentication for API key users
- Enum value ordering changed in multiple types (e.g., 'PENDING|PROCESSING|CANCELED|COMPLETE' changed to 'CANCELED|COMPLETE|PENDING|PROCESSING'), which may break pattern matching in dependent code
- New enum value 'WORK' added to category fields in AssociationSpecWithLabel, PublicAssociationDefinitionUserConfiguration, PublicAssociationDefinitionConfigurationUpdateResult, PublicAssociationDefinitionConfigurationUpdateRequest, PublicAssociationDefinitionConfigurationCreateRequest - existing exhaustive match expressions will fail
- Resource function 'get definitions/configurations/all' description changed from 'Retrieve all association definitions and configurations' to 'Retrieve all association limits' indicating semantic behavior change
- ApiKeysConfig now requires 'hapikey' as a mandatory field, breaking existing instantiations that don't include it

### Fixed
- Simplified header handling by removing redundant headerValues map construction
- Improved type safety in auth config handling by using typed variable instead of type cast
