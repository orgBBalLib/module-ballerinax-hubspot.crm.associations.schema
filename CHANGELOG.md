# Change Log

This file contains all the notable changes done to the Ballerina connector through the releases.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Added 'hapikey' field to ApiKeysConfig for additional API key authentication option
- Added 'WORK' as a new valid enum value for category fields across multiple types
- Added doc comment 'Basepom for all HubSpot Projects' to Client class
- Added comprehensive documentation comments to all types and their fields

### Changed
- ApiKeysConfig type changed: field 'privateAppLegacy' was the first field, now a new field 'hapikey' was added and field order changed - existing code using positional initialization would break
- API key authentication removed from individual resource functions - apiKeyConfig headers are no longer injected into requests, breaking private-app authentication for all endpoints
- Enum value ordering changed in multiple types (e.g., 'PENDING|PROCESSING|CANCELED|COMPLETE' changed to 'CANCELED|COMPLETE|PENDING|PROCESSING') which may affect pattern matching
- New enum value 'WORK' added to category fields in AssociationSpecWithLabel, PublicAssociationDefinitionUserConfiguration, PublicAssociationDefinitionConfigurationUpdateResult, PublicAssociationDefinitionConfigurationUpdateRequest, PublicAssociationDefinitionConfigurationCreateRequest - existing exhaustive match expressions would break
- Resource function order changed (batch/purge and batch/update moved before labels endpoints) - while functionally equivalent, this is a structural change
- Private-app and private-app-legacy headers no longer automatically injected when ApiKeysConfig is used, breaking authentication for all API calls using API key auth

### Fixed
- Simplified auth configuration handling in init() by using typed variable instead of type casting
- Removed redundant header map creation in resource functions, passing headers directly
