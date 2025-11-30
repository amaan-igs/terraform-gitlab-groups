# GitLab Groups Configuration

This directory contains Terraform configuration for creating and managing GitLab groups using the `sudo-terraform-modules/groups/gitlab` module.

## Overview

The `main.tf` configuration creates a comprehensive organizational structure in GitLab with security-focused groups, specialized teams, and hierarchical subgroups.

## GitLab Group Structure

The following GitLab groups and subgroups are created:

```text
GitLab Instance
├── Engineering
│   └── DevOps Team
│       ├── Migrations Team
│       ├── Infrastructure Team
│       ├── Automation Team
│       ├── Compute Team
│       └── SAP BASIS Team
│           ├── SAP S4 HANA
│           ├── SAP B1
│           └── SAP NetWeaver
├── Security Team
├── Production Operations
├── Open Source Projects
└── Documentation
```

## Group Details

### Top-Level Groups

| Group Name | Path | Description | Features |
|------------|------|-------------|----------|
| **Engineering** | `engineering` | Main engineering organization | Internal visibility, developer project creation |
| **Security Team** | `security` | Information security and compliance | Maximum security settings, 2FA required, IP restrictions |
| **Production Operations** | `production` | Production systems and operations | 2FA required, controlled CI/CD access |
| **Open Source Projects** | `opensource` | Public open source projects | Public visibility, external collaboration enabled |
| **Documentation** | `docs` | Technical documentation and knowledge base | Wiki enabled, lightweight configuration |

### Engineering Subgroups

#### DevOps Team (`devops`)

Central DevOps operations with enhanced CI/CD access and specialized subteams:

- **Migrations Team** (`migrations`) - Database and application migration projects
- **Infrastructure Team** (`infrastructure`) - Cloud and on-premises infrastructure management
- **Automation Team** (`automation`) - DevOps automation and CI/CD pipeline development
- **Compute Team** (`compute`) - Server and container compute infrastructure
- **SAP BASIS Team** (`sap-basis`) - SAP system administration and BASIS management

#### SAP BASIS Subgroups

Specialized SAP teams under the BASIS team:

- **SAP S4 HANA** (`sap-s4hana`) - S/4HANA system administration and development
- **SAP B1** (`sap-b1`) - Business One system administration and customization
- **SAP NetWeaver** (`sap-netweaver`) - NetWeaver platform and ABAP development

## Security Configuration

### High-Security Groups

- **Security Team**: 2FA required, IP restrictions, comprehensive push rules
- **Production Operations**: 2FA required, controlled access, production-grade security
- **All SAP Groups**: 2FA enforced, custom runners only, enterprise security standards

### Access Controls

- **Project Creation**: Restricted to maintainer level or higher for sensitive groups
- **Subgroup Creation**: Limited to owners and maintainers
- **Shared Runners**: Configured based on team requirements and security needs

## Usage

1. **Configure Variables**: Update `terraform.tfvars` with your GitLab token and organization details
2. **Initialize**: Run `terraform init` to download the required modules
3. **Plan**: Execute `terraform plan` to review the changes
4. **Apply**: Run `terraform apply` to create the GitLab groups

## Prerequisites

- Terraform >= 1.3.0
- GitLab instance access with group creation permissions
- Valid GitLab personal access token with required scopes

## Module Source

This configuration uses the official Terraform Registry module:

- **Source**: `sudo-terraform-modules/groups/gitlab`
- **Version**: `0.2.0`

## Files

- `main.tf` - Main configuration with all group definitions
- `variables.tf` - Input variable definitions
- `terraform.tfvars.example` - Example variable values
- `simple.tf` - Simplified configuration for basic usage

## Outputs

The configuration provides comprehensive outputs including:

- Group IDs and URLs for each created group
- Hierarchical structure mapping
- Access settings and configuration details

For complete output reference, run `terraform output` after applying the configuration.
