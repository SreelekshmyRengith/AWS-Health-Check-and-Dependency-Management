# AWS Health Check and Dependency Management

This repository demonstrates the implementation of health checks and dependency management to enhance the reliability of a distributed system hosted on AWS. It showcases strategies to ensure fault tolerance, graceful degradation, and effective traffic routing using AWS services.

## Project Overview

This project involves deploying a distributed application on AWS, configuring health checks, managing dependencies, and ensuring high availability and reliability.

### Key Features
- **Health Checks**: Configure and monitor instance health using `/healthcheck` endpoints.
- **Dependency Management**: Simulate and handle service failures gracefully using AWS Systems Manager and IAM roles.
- **Load Balancer Routing**: Implement traffic routing through Elastic Load Balancer (ELB) based on instance health.
- **Graceful Degradation**: Serve static fallback pages during outages to ensure a smooth user experience.
- **Auto Scaling Integration**: Automatically spin up healthy instances when failures occur.
- **CloudWatch Monitoring**: Capture and analyze metrics to identify and resolve system bottlenecks.

## Architecture
- **VPC**: Custom Virtual Private Cloud with subnets across multiple availability zones for high availability.
- **Auto Scaling Group (ASG)**: Ensures system reliability by dynamically managing instances.
- **Elastic Load Balancer (ELB)**: Directs traffic to healthy instances based on deep health checks.
- **CloudFormation Templates**: Automates the deployment of infrastructure and application configurations.

## Deployment Steps
1. **Infrastructure Setup**:
   - Deploy the VPC and related resources using CloudFormation.
   - Launch instances across multiple availability zones.

2. **Application Deployment**:
   - Deploy the web application through CloudFormation templates.
   - Configure ELB to route traffic based on `/healthcheck` endpoint.

3. **Simulating Failures**:
   - Modify IAM roles and disable services to simulate failures.
   - Observe behavior under failure conditions, such as 502 Bad Gateway errors.

4. **Monitoring and Recovery**:
   - Use CloudWatch metrics to monitor system health and recover instances.
   - Analyze and resolve bottlenecks based on captured metrics.

5. **Graceful Degradation**:
   - Configure static fallback pages to provide a user-friendly experience during failures.

## Usage
- Access the web application via the provided URL.
- Use the `/healthcheck` endpoint to verify instance health.
- Simulate service failures and observe system behavior.

## Observations and Learnings
- **Elastic Load Balancer Behavior**: Identifies and routes traffic to healthy instances only.
- **Fail-Open Strategy**: Ensures user experience is maintained with static fallback pages during outages.
- **Proactive Monitoring**: CloudWatch metrics enable quick identification and resolution of failures.
