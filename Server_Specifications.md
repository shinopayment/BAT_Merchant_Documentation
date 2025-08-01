# Infrastructure Requirements Documentation for BAT

## Overview

This document outlines the infrastructure requirements for hosting the complete system applications including BackOffice, Windows Service and API applications, along with database and mobile device specifications.

## Server Infrastructure

### Production API and Windows Service Servers

**Quantity:** 2 units  
**Cost:** RM 1,500 each  
**Total Cost:** RM 3,000

#### Specifications
- **Azure VM:** Azure Windows Server Virtual Machine (Standard F4s v2 subscription)
- **Operating System:** Windows Server 2022 Datacenter Azure Edition
- **RAM:** 8GB
- **Processor:** Intel Xeon Platinum 4 vCPUs
- **Disk Space:** Minimum 100GB
- **Special Features:** Higher processing speed optimization

#### Purpose
These servers will host all system applications including:
- API services
- Windows Service

### Production BackOffice Server

**Quantity:** 1 unit  
**Cost:** RM 800

#### Specifications
- **Operating System:** Azure Windows Server Virtual Machine (Standard B4als v2 subscription)
- **Operating System:** Windows Server 2022 Datacenter Azure Edition
- **RAM:** 8GB
- **Processor:** AMD EPYC 7763v 4 vCPUs
- **Disk Space:** Minimum 100GB

#### Purpose
These servers will host all system applications including:
- BackOffice
- Cron Job

### Runtime Requirements

**Required Framework:** ASP.NET Core Runtime 8.0

All servers must have ASP.NET Core Runtime 8.0 installed to support the application stack.

## Database Infrastructure

### Database Configuration

**Quantity:** 2 units  
**Cost:** RM 250 each  
**Total Cost:** RM 500

#### Primary Database (Production)
- **Platform:** Azure Database
- **Tier:** Standard Tier (minimum)
- **DTUs:** Minimum 20
- **Storage:** Minimum 10GB (scalable)

#### Replica Database (Backup)
- **Platform:** Azure Database
- **Tier:** Standard Tier (minimum)
- **DTUs:** Minimum 20
- **Storage:** Minimum 10GB (scalable)
- **Purpose:** Backup and disaster recovery

#### Scalability Notes
- Database storage can be scaled up as needed.
- **DTU (Database Transaction Unit)** refers to a blended measure of CPU, memory, reads, and writes for Azure SQL Databases. DTU allocation can be increased to improve database performance as application demands grow.
- Backup database provides redundancy and failover capabilities.

## Mobile Device Requirements

### Agent Mobile Devices

#### Operating System Requirements
- **Platform:** Android OS
- **Version:** 8.0 and above

#### Hardware Specifications
- **RAM:** 4GB minimum
- **Storage:** Minimum 200MB free storage space for application installation

#### Required Permissions
The mobile application requires the following system permissions:
- **SMS:** For message handling and notifications
- **Notification:** For push notifications and alerts
- **Storage:** For local data caching and file management
- **Background Service:** For continuous operation and real-time updates
- **Internet Connection:** WiFi or Mobile Data connectivity required

#### Network Requirements
- Stable internet connection (WiFi or Mobile Data)

## Cost Summary

| Component | Quantity | Unit Cost | Total Cost |
|-----------|----------|-----------|------------|
| Production Servers (F4s v2) | 2 | RM 1,500 | RM 3,000 |
| Backup Server (B4als v2) | 1 | RM 800 | RM 800 |
| Production Database | 1 | RM 250 | RM 250 |
| Replica Database | 1 | RM 250 | RM 250 |
| **Total Monthly Cost** | | | **RM 4,300** |

*Note: Mobile device costs not included as these are agent-provided devices*

## Architecture Notes

### High Availability
- Multiple production servers provide load balancing and redundancy
- Database replica ensures data backup and recovery capabilities
- Mobile agents can operate with periodic synchronization even with the mobile application is running in background

### Scalability Considerations
- Server specifications can be upgraded as needed
- Database storage and DTUs are scalable
- Additional servers can be added in the future as demand grows

### Security Requirements
- All servers should be configured with appropriate security groups
- Database access should be restricted to application servers only

## Deployment Checklist

### Server Setup
- [ ] Provision Azure Windows Server VMs
- [ ] Install ASP.NET Core Runtime 8.0
- [ ] Configure network security groups
- [ ] Setup With IIS
- [ ] Install and configure applications

### Database Setup
- [ ] Provision Azure Database instances
- [ ] Configure database replication
- [ ] Set up backup schedules
- [ ] Configure connection strings to the application

### Mobile Deployment
- [ ] Verify Android device compatibility
- [ ] Install mobile application
- [ ] Configure permissions
- [ ] Test connectivity to servers
- [ ] Validate all required features

## Maintenance and Monitoring

### Regular Tasks
- Monitor server performance and resource utilization
- Review database performance metrics
- Ensure mobile devices maintain connectivity

### Performance Optimization
- Regularly review DTU usage and scale as needed
- Monitor disk space usage across all servers
- Optimize application performance based on usage patterns
- Review and adjust server specifications as workload changes