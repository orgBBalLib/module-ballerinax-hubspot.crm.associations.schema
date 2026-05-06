# Change Log

This file contains all the notable changes done to the Ballerina connector through the releases.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- New 'hapikey' field added to ApiKeysConfig
- New 'WORK' category enum value added across multiple association definition types
- Added documentation comments to Client class and all public types
- Simplified auth configuration handling in init function

### Changed
- ApiKeysConfig type changed: removed 'privateAppLegacy' and 'privateApp' fields and replaced with 'hapikey', 'privateApp', 'privateAppLegacy' (reordered, and 'hapikey' added as new required field - existing code using ApiKeysConfig without 'hapikey' will break)
- API key headers no longer automatically injected into requests - removed apiKeyConfig-based header injection logic from all resource functions, breaking private-app authentication flow
- Enum value ordering changed in multiple types (e.g., 'PENDING|PROCESSING|CANCELED|COMPLETE' changed to 'CANCELED|COMPLETE|PENDING|PROCESSING'), which may break pattern matching in some Ballerina contexts
- New enum value 'WORK' added to category fields in AssociationSpecWithLabel, PublicAssociationDefinitionUserConfiguration, PublicAssociationDefinitionConfigurationUpdateResult, PublicAssociationDefinitionConfigurationUpdateRequest, PublicAssociationDefinitionConfigurationCreateRequest - existing exhaustive match expressions will break
- Resource function ordering changed (batch/purge and batch/update moved relative to labels endpoints) - while paths remain the same, this is a structural change

### Fixed
- Simplified auth config assignment using typed variable instead of type cast
- Removed redundant header map creation for API key injection
