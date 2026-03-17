# 🔐 Active Directory User Onboarding Workflow

## Overview
A standardized onboarding checklist and PowerShell-assisted workflow that streamlines the provisioning of new user accounts in Active Directory — reducing setup time and ensuring nothing is missed.

## Problem
New employee onboarding was inconsistent: different technicians followed different steps, accounts were sometimes provisioned with wrong permissions, and setups could take half a day.

## Solution
Created a reusable onboarding checklist and a set of PowerShell scripts to automate repetitive AD tasks, paired with a documented step-by-step runbook.

## Onboarding Checklist

### Pre-Arrival
- [ ] Create AD user account (name, UPN, OU placement)
- [ ] Assign security groups and role-based permissions
- [ ] Create Microsoft 365 mailbox and license assignment
- [ ] Configure email aliases and distribution group membership
- [ ] Set up OneDrive and SharePoint access
- [ ] Prepare workstation (OS image, software install)

### Day 1
- [ ] Hand over login credentials securely
- [ ] Test email, Teams, and VPN access
- [ ] Install required software and printers
- [ ] Configure MFA (Multi-Factor Authentication)
- [ ] Brief user on IT policies and helpdesk contact

### Post-Setup
- [ ] Log asset assignment in IT Asset Tracker
- [ ] Create helpdesk ticket and mark as resolved
- [ ] Schedule 1-week follow-up check-in

## Sample PowerShell Snippet

```powershell
# Create new AD user
New-ADUser `
  -Name "Sami Benaouana" `
  -GivenName "Sami" `
  -Surname "Benaouana" `
  -SamAccountName "s.benaouana" `
  -UserPrincipalName "s.benaouana@company.com" `
  -Path "OU=IT,DC=company,DC=com" `
  -AccountPassword (ConvertTo-SecureString "P@ssw0rd!" -AsPlainText -Force) `
  -Enabled $true
```

## Technologies Used
- Active Directory (Windows Server)
- PowerShell
- Microsoft 365 Admin Center
- Exchange Online

## Outcome
- Reduced new user setup time from ~4 hours to under **1.5 hours**
- Eliminated provisioning errors through checklist standardization
- Enabled junior technicians to handle onboarding independently

---

> 📁 [Back to Portfolio](../README.md)
