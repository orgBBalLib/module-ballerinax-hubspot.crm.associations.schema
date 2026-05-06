# Change Log

This file contains all the notable changes done to the Ballerina connector through the releases.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- Added class-level documentation comment 'Basepom for all HubSpot Projects'
- Added 'WORK' as a valid category enum value across multiple types
- Added 'hapikey' field to ApiKeysConfig
- Extensive documentation comments added to all types and their fields
- Improved auth config handling using typed variable instead of type cast

### Changed
- ApiKeysConfig record changed: 'privateAppLegacy' field removed and replaced with 'hapikey' field added, and field ordering changed - this breaks existing code using ApiKeysConfig
- Enum value ordering changed in multiple types: 'PENDING|PROCESSING|CANCELED|COMPLETE' changed to 'CANCELED|COMPLETE|PENDING|PROCESSING' - while functionally equivalent, this is a type definition change
- Category enum values updated to include 'WORK' in multiple types (PublicAssociationDefinitionConfigurationUpdateResult, PublicAssociationDefinitionConfigurationUpdateRequest, PublicAssociationDefinitionConfigurationCreateRequest, AssociationSpecWithLabel, PublicAssociationDefinitionUserConfiguration) - existing pattern matching may break
- API key header injection removed from all resource functions - requests using ApiKeysConfig will no longer have private-app and private-app-legacy headers automatically injected, breaking authentication for API key users
- ApiKeysConfig now requires 'hapikey' field which did not exist before, breaking existing ApiKeysConfig instantiations

### Fixed
- Simplified auth config assignment using typed variable to avoid unnecessary type casting
- Removed redundant header map creation for API key injection in resource functions
