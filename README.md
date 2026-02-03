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

---
