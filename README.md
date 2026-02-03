# Increase CPU for a Virtual Machine using OLVM

This document describes the standard procedure to increase CPU resources for a Virtual Machine using **Oracle Linux Virtualization Manager (OLVM)**.

The steps follow best practices to avoid application or data issues during the VM shutdown process.

---

## ⚠️ Pre-Shutdown Checks (VERY IMPORTANT)

Before shutting down the VM, **confirm the following**:

### 1. Application & Database Validation
- Ensure **all application services** are stopped gracefully
- Ensure **database services** (Oracle, MySQL, PostgreSQL, etc.) are properly shut down
- Confirm no active user sessions or running batch jobs
- Verify there are no ongoing backups, cron jobs, or maintenance tasks

> ⚠️ Never force shutdown a VM with running DB or application services.

---

### 2. Stakeholder Confirmation
- Confirm maintenance window approval
- Inform application / DB teams about the planned shutdown
- Get explicit confirmation to proceed

----------
## 🔽 VM Shutdown Procedure
### 1. Gracefully shut down the VM from inside the OS:
```
 shutdown -h now
```
### 2. Confirm the VM is fully powered off in OLVM
## 🔧 CPU Increase Steps in OLVM
### Login to OLVM
### Navigate to:
```
Compute → Virtual Machines
```
### 3. Select the required VM
### 4. Click Edit
### 5. Open the System tab
### 6. Update the CPU value as required
### 7. Click OK to save changes

## 🔼 VM Power-On
### 1. Power on the VM using the Run icon in OLVM
### 2. Wait for the VM to boot completely

## ✅ Post-Change Verification
### After the VM is up, verify the CPU change from inside the OS:
```
lscpu
```
**Confirm:**
***Updated CPU count is reflected***
***No system errors during boot***

## Post-Startup Checks ##
### Start application services ###
### Start database services ###
### Verify application accessibility ###
### Monitor system logs for errors: ###
```
journalctl -xe
```

## 📝 Notes
### CPU changes require VM shutdown in OLVM
### Always prefer graceful OS shutdown
### Perform changes during approved maintenance windows
### Validate application performance after the CPU increase
