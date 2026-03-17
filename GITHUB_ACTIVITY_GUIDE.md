# 🔄 Keeping Your GitHub Portfolio Active

A green contribution graph signals to recruiters that you're continuously learning and building. Here's how to stay active consistently.

---

## ✅ Quick Wins (Weekly Habits)

| Action | Frequency | Time Required |
|--------|-----------|--------------|
| Update a project README with new details | Weekly | 10 min |
| Add a new issue or resolved troubleshooting case to runbooks | Weekly | 15 min |
| Commit a new PowerShell or batch script | Bi-weekly | 20 min |
| Add a new certification badge or course progress note to README | Monthly | 5 min |
| Document a new IT incident and resolution in the `/projects` folder | Monthly | 30 min |

---

## 💡 Contribution Ideas

### 📂 Documentation Updates
- Add new real-world troubleshooting cases you solve at work (anonymized)
- Expand the network runbook with new scenarios
- Add a "lessons learned" section after each project

### 🛠️ Scripts & Tools to Build
- `onboarding.ps1` — PowerShell script to automate AD user creation
- `asset-audit.ps1` — Script to export a list of all AD computers to CSV
- `m365-license-report.ps1` — Script to list all M365 users and their licenses
- `ping-sweep.bat` — Simple batch script to ping a range of IPs on the LAN
- `disk-health-check.ps1` — Script to check disk space on all workstations

### 📓 Blog / Notes Folder (`/notes`)
Create a `/notes` folder and add short `.md` files about:
- Tips for resetting Windows 11 without data loss
- How to configure MFA in Microsoft 365
- Common Active Directory errors and fixes
- How to read Windows Event Viewer for troubleshooting

---

## 🤖 GitHub Actions Ideas

### Profile README Auto-Update
Use a GitHub Action to auto-update your profile README with:
- Last updated date
- Latest certification added
- Random IT tip of the day

```yaml
# .github/workflows/update-readme.yml
name: Update README
on:
  schedule:
    - cron: '0 0 * * 1'  # Every Monday
  workflow_dispatch:
jobs:
  update:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Update timestamp
        run: |
          echo "Last updated: $(date)" >> README.md
          git config user.email "action@github.com"
          git config user.name "GitHub Action"
          git commit -am "Auto-update timestamp" || echo "No changes"
          git push
```

---

## 🏷️ Recommended Badges to Add

Add these to your README for visual credibility:

```markdown
![Microsoft 365](https://img.shields.io/badge/Microsoft_365-Certified-D83B01?style=for-the-badge&logo=microsoft)
![Google IT](https://img.shields.io/badge/Google-IT_Support_Specialist-4285F4?style=for-the-badge&logo=google)
![Active Directory](https://img.shields.io/badge/Active_Directory-Expert-003366?style=for-the-badge&logo=microsoft)
![PowerShell](https://img.shields.io/badge/PowerShell-Scripting-5391FE?style=for-the-badge&logo=powershell)
```

---

## 📅 30-Day Kickstart Plan

| Week | Goal |
|------|------|
| Week 1 | Set up repository, push README and all project files |
| Week 2 | Write and commit 2 PowerShell scripts |
| Week 3 | Add a `/notes` folder with 3 IT tip articles |
| Week 4 | Add GitHub Actions workflow + update badge section |

---

> 📁 [Back to Portfolio](./README.md)
