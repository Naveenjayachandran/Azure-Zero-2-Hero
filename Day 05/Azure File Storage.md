# Azure File Storage - Overview for DevOps Engineers

## What is Azure File Storage?

Azure File Storage is a fully managed, cloud-based file share service provided by Microsoft Azure. It allows files to be shared across applications and virtual machines (VMs) using the Server Message Block (SMB) protocol. This makes it ideal for applications that need shared access to configuration files, logs, or data.

### Key Features:
- **Fully Managed**: No infrastructure management required.
- **Cross-Platform Access**: Windows, Linux, macOS support.
- **Access Protocols**: SMB 3.0, REST API.
- **Security**: Encryption at rest and in transit, AD integration.
- **Scalability**: Up to 100 TiB per share.
- **Snapshot Support**: For backups and versioning.
- **Hybrid Capability**: Azure File Sync for syncing with on-prem.

---

## When to Use Azure File Storage

Use Azure File Storage when:
- You need a shared file system accessible by multiple VMs or containers.
- Applications require centralized configuration or data files.
- You want persistent shared storage for apps or services.
- You’re migrating legacy apps that rely on traditional file shares.
- Hybrid cloud scenarios demand syncing between on-prem and Azure.

### Common Use Cases:
- Shared application settings (`config.yaml`, `.env`)
- Deployment script repositories
- Log file aggregation
- Shared storage for container volumes
- Hosting static assets across services

---

## DevOps Engineer Use Case Example

### Scenario:
A DevOps engineer manages a deployment pipeline where multiple instances of an application need to access a shared configuration file (`config.yaml`) during deployment.

### Step-by-Step:

#### 1. Create Storage Account and File Share
```bash
az storage account create \
  --name mystorageacct \
  --resource-group myResourceGroup \
  --location uksouth \
  --sku Standard_LRS

az storage share create \
  --name sharedconfigs \
  --account-name mystorageacct
