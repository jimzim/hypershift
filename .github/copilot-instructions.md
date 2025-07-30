# GitHub Copilot Instructions for HyperShift

## Project Overview
HyperShift is a middleware for hosting OpenShift control planes at scale that solves for cost and time to provision, as well as portability across clouds with strong separation of concerns between management and workloads. Clusters are fully compliant OpenShift Container Platform (OCP) clusters and are compatible with standard OCP and Kubernetes toolchains.

## Primary Technologies and Expertise Areas

### Go Development
- This is a Go-based project following standard Go conventions
- Use Go modules for dependency management
- Follow Go best practices for error handling, package structure, and testing
- Implement proper context handling for cancellation and timeouts
- Use structured logging with logr interface
- Apply Go idioms for concurrent programming when applicable

### OpenShift Integration
- Deep understanding of OpenShift Container Platform (OCP) architecture
- Knowledge of OpenShift operators, custom resources, and controllers
- Familiarity with OpenShift networking, storage, and security concepts
- Understanding of cluster lifecycle management in OpenShift environments
- Experience with OpenShift CI/CD pipelines and GitOps workflows

### AWS Cloud Platform
- Extensive AWS services integration including:
  - EC2 instances, VPCs, subnets, security groups
  - Route53 DNS management (private and public hosted zones)
  - IAM roles, policies, and instance profiles
  - S3 buckets for OIDC storage
  - EBS volumes and storage management
  - Load balancers (NLB) and VPC endpoints
  - KMS for encryption key management
- AWS shared VPC architecture and cross-account configurations
- Private cluster deployments with bastion hosts
- Multi-AZ deployments and high availability patterns

### ROSA (Red Hat OpenShift Service on AWS)
- ROSA managed policies and service integration
- ROSA cluster creation and management workflows
- ROSA-specific IAM role configurations and managed policies
- Integration patterns between ROSA and HyperShift
- ROSA shared VPC configurations and cross-account setups

## Code Style and Patterns

### Kubernetes Controllers
- Follow controller-runtime patterns for reconciliation loops
- Implement proper status reporting and condition management
- Use client-go and controller-runtime libraries effectively
- Apply Kubernetes API conventions and best practices

### AWS SDK Integration
- Use AWS SDK v1 with proper error handling and retries
- Implement exponential backoff for AWS API calls
- Handle AWS service limits and rate limiting gracefully
- Use proper AWS credential management and assume role patterns

### Error Handling
- Provide detailed, actionable error messages
- Use wrapped errors with context for better debugging
- Implement proper retry logic for transient failures
- Handle both temporary and permanent error conditions

## Architecture Patterns

### Infrastructure Management
- Understand hosted cluster vs management cluster separation
- Implement proper resource lifecycle management
- Handle cross-account AWS resource creation and management
- Support both public and private cluster configurations

### Security Considerations
- Follow principle of least privilege for IAM roles
- Implement proper RBAC configurations
- Handle sensitive data (credentials, certificates) securely
- Use encryption at rest and in transit where applicable

### Networking
- Understand VPC endpoint configurations for private clusters
- Implement proper DNS management for cluster access
- Handle load balancer configurations and ingress patterns
- Support both single and multi-AZ deployments

## Testing Patterns
- Write comprehensive unit tests with proper mocking
- Implement integration tests for AWS services
- Use testify framework for assertions and test structure
- Mock AWS services using interfaces for testability
- Include end-to-end test scenarios for cluster lifecycle

## Documentation Standards
- Provide clear API documentation for custom resources
- Include usage examples and troubleshooting guides
- Document AWS permission requirements and setup procedures
- Explain shared VPC configurations and cross-account setups

## Feature Development Guidelines
- Use feature gates for experimental functionality
- Follow TechPreviewNoUpgrade patterns for new features
- Implement proper validation for API fields and configurations
- Support both day-1 and day-2 operations for new features

## CI/CD and Release Management
- Understand the relationship with OpenShift release streams
- Support multi-architecture builds (x86_64, arm64)
- Implement proper versioning and tagging strategies
- Follow GitOps patterns for deployment management

## Troubleshooting Focus Areas
- AWS IAM permission issues and role assumption problems
- DNS resolution issues in private cluster configurations
- VPC endpoint connectivity and security group configurations
- Cross-account resource access and shared VPC setups
- ETCD backup and restore procedures
- Load balancer and ingress configuration problems

When helping with this codebase, prioritize solutions that are secure, scalable, and follow established patterns in the HyperShift project. Consider the multi-tenant nature of hosted clusters and the complexity of cross-account AWS configurations.
