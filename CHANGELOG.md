# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.2.0] - 2025-11-30

### Added

- **Comprehensive Documentation Improvements**:
  - Added Contributing Guide (`.github/contributing.md`) with module-specific guidelines
  - Enhanced README with clear usage examples and organizational structure visualization
  - Added tree structure documentation for complex group hierarchies

- **Advanced Example Configurations**:
  - Complete organizational structure with Engineering → DevOps → specialized teams
  - SAP BASIS team structure with S4HANA, B1, and NetWeaver subgroups
  - Security team with maximum security settings and strict access controls
  - Production operations group with enhanced security and controlled access
  - Open source projects group with public visibility and collaboration features
  - Documentation team with appropriate settings for knowledge management

- **Security and Compliance Features**:
  - Integrated Checkov security scanning with custom configuration (`.checkov.yaml`)
  - Updated GitHub Actions workflow with security scanning pipeline
  - Added semantic versioning compliance while maintaining registry compatibility
  - Enhanced security settings for SAP and production environments

- **CI/CD Pipeline Enhancements**:
  - Two-stage GitHub Actions pipeline (validation → security scan)
  - Terraform format checking and validation
  - Checkov security scanning with custom rules
  - Pre-commit hook configuration examples

### Changed

- **Module Source References**: Updated all examples to use Terraform Registry format (`sudo-terraform-modules/groups/gitlab`)
- **Version Management**: Aligned all version references to v0.2.0 across documentation and examples
- **Documentation Structure**: Reorganized documentation with better navigation and clear sections
- **Security Configuration**: Optimized Checkov rules to work with Terraform Registry modules

### Fixed

- **Registry Compatibility**: Resolved Checkov CKV_TF_1 warnings while maintaining best practices for registry modules
- **Documentation Links**: Fixed all module source references to use proper registry format
- **Markdown Formatting**: Corrected linting issues across all documentation files

### Documentation

- **Usage Examples**: All examples now demonstrate real-world organizational structures
- **Contributing Process**: Clear guidelines for module contributors and maintainers

### Technical Details

- **Registry Format**: compatibility with Terraform Registry publication standards
- **Security Scanning**: Integrated Checkov with module-specific rule configuration  
- **Module Structure**: Enhanced with comprehensive examples and production-ready configurations

## [0.1.0] - 2025-11-29

### Added

- Initial release of GitLab Groups Terraform module
- Complete GitLab group resource configuration with all available attributes
- Comprehensive input variable definitions with validation
- Advanced security features support:
  - Two-factor authentication enforcement
  - IP restriction ranges for access control
  - Push rules with commit validation
  - Default branch protection settings
- Access control and permission management:
  - Project and subgroup creation level controls
  - Membership and sharing restrictions
  - Forking prevention controls
- CI/CD integration features:
  - Shared runners configuration
  - Minutes limits management
  - Auto DevOps support
- Communication and notification controls:
  - Email domain restrictions
  - Notification settings
  - Wiki access level configuration
- Organizational structure support:
  - Nested groups (parent-child relationships)
  - Visibility level management
  - Avatar configuration
- Comprehensive output values:
  - Basic group information
  - Structured outputs for easy integration
  - Convenience outputs for common use cases
- Input validation for all variables:
  - Path validation with regex patterns
  - Access level validation
  - Numeric constraint validation
  - Email domain validation
- Complete documentation:
  - Usage examples (basic, advanced, enterprise)
  - Input/output reference tables
  - Security considerations
  - Contributing guidelines
- Example configurations:
  - Simple setup for basic usage
  - Complete setup with advanced features
  - Automated setup script
  - Variable examples with documentation
- Terraform version constraints:
  - Terraform >= 1.3.0
  - GitLab provider ~> 18.0

### Technical Details

- **Provider Support**: GitLab provider v18.0+ for full feature compatibility
- **Terraform Compatibility**: Requires Terraform 1.3.0 or higher
- **Module Structure**: Follows Terraform module best practices
- **Validation**: Comprehensive input validation to prevent configuration errors
- **Documentation**: Complete API reference and usage examples

[0.1.0]: https://github.com/SUDO-Terraform-Modules/gitlab-groups/releases/tag/v0.1.0
