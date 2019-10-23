# Azure for PostgreSQL

## PaaS offering

- Single Server: 
  - Select vcpus, storage, memory
  - Selecting the right cpu has an impact in cost and performance
- Hyperscale (Citus) server: 
  - Sharding and query parallelization 

## Connectivity:
- Azure for PostgreSQL - PaaS
  - Option to connect Azure Service
  - Open a specic IP
  - Service endpoint via VNet integration
- IaaS
  - Deploy, manage, patch VMs
  - Install PostgreSQL
  - VMs deployed to a subnet on a VNET
    - No outside communication possible

## Replication:

- Option 1
  -	Write to one region
  - Replicate to other regions and read from other regions
  -	If write region goes down, reading from a secondary region is supported until the write region comes back-up
-	Option 2
  - Have two write regions
  - Have application write to both regions and manually coordiate replication logic

## Backup/Restore:

- Back is automatic
  - Full backup weekly/differential twice a day/transactional log 5 minutes
- Restore
  - From the portal choose the date and time
- RTO/RPO
  - Depending on the tier but 12 hours for RTO, less than one hour for RPO
  - Recommendations:
    - 99.99% one region
    -	Have at least one read replica
    - Select geo-redundant storage

## Security:

- Encryption at rest is the Azure default
- Encryption in motion is the default, but can be turned off
- Role level security avaiable by managing the system with a credentialed user
- Ability to create users and grant them privileged with the admin account
-	Currently there's no Azure AD Authentication

