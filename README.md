<div align="center">

# 🌐 Deploying a Static Website on AWS EC2 (Windows Server) using IIS

### Host your own HTML/CSS/JS website on a real cloud server — from a blank AWS account to a live public URL.

<br/>

![AWS](https://img.shields.io/badge/AWS-EC2-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![Windows Server](https://img.shields.io/badge/Windows-Server-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![IIS](https://img.shields.io/badge/IIS-Web%20Server-68217A?style=for-the-badge&logo=microsoft&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

![GitHub Repo stars](https://img.shields.io/github/stars/your-username/your-repo-name?style=for-the-badge&color=yellow)
![GitHub forks](https://img.shields.io/github/forks/your-username/your-repo-name?style=for-the-badge&color=blue)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![Made with Love](https://img.shields.io/badge/Made%20with-%E2%9D%A4-red?style=for-the-badge)

<br/>

**📚 Beginner-Friendly &nbsp;•&nbsp; 🏗️ Hands-On AWS Project &nbsp;•&nbsp; 🎓 Resume-Ready &nbsp;•&nbsp; ☁️ 100% Cloud Deployed**

[🚀 Live Demo](#-10-step-10--test-the-website) · [📖 Documentation](#-table-of-contents) · [🐛 Report Bug](../../issues) · [✨ Request Feature](../../issues)

</div>

<br/>

---

## 📋 Table of Contents

<details open>
<summary><b>Click to expand / collapse</b></summary>

| | | |
|---|---|---|
| [1. Introduction](#-1-introduction) | [11. Troubleshooting](#-11-step-11--troubleshooting-guide) | [21. Interview Questions](#-21-interview-questions-30) |
| [2. Project Objectives](#-2-project-objectives) | [12. Verification Checklist](#-12-step-12--project-verification-checklist) | [22. References](#-22-references) |
| [3. Architecture Overview](#-3-architecture-overview) | [13. Screenshots](#-13-screenshots-section) | [23. Contributing](#-23-contributing) |
| [4. Technologies Used](#-4-technologies-used) | [14. Commands Used](#-14-commands-used) | [24. License](#-24-license) |
| [5. Prerequisites](#-5-prerequisites) | [15. Networking Explained](#-15-networking-explanation) | [25. Author](#-25-author) |
| [6. Folder Structure](#-6-project-folder-structure) | [16. IIS Concepts](#-16-iis-concepts) | [26. Repository Topics](#-26-repository-topics) |
| [7. Step-by-Step Guide](#-7-step-by-step-practical-guide) | [17. AWS Concepts Learned](#-17-aws-concepts-learned) | [27. SEO Description](#-27-seo-description) |
| [8. Quick Start](#-quick-start-tldr) | [18. Best Practices](#-18-best-practices) | [28. Social Preview](#-28-github-social-preview-text) |
| [9. Deployment Steps](#-7-step-by-step-practical-guide) | [19. Future Improvements](#-19-future-improvements) | [29. Features](#-29-repository-features) |
| [10. Testing](#-10-step-10--test-the-website) | [20. Learning Outcomes](#-20-learning-outcomes) | [30. Final Notes](#-30-final-notes) |

</details>

---

## 🧭 1. Introduction

### 🔍 What is this project?

This repository documents a **complete, real-world cloud deployment project**: hosting a static website (HTML, CSS, and JavaScript) on a **Windows Server EC2 instance** in **AWS**, served by **Internet Information Services (IIS)** — Microsoft's native web server — and exposed to the public internet through a properly configured **Security Group**.

Unlike tutorials that only cover theory, this project walks through **every single click, command, and configuration screen** needed to go from *"I have an AWS account"* to *"my website is live at `http://<public-ip>`"*.

> 💡 **Tip:** This is one of the most common entry-level cloud/DevOps interview projects. Recruiters love seeing it because it touches AWS, networking, Windows Server administration, and basic web hosting all in one go.

### 🎯 Why was this project created?

Most beginners learn AWS through Linux-based EC2 tutorials, but **Windows Server + IIS** is just as important in real enterprise environments — many companies run legacy `.NET` applications, internal portals, and intranet sites entirely on IIS. This project fills that gap by documenting the **Windows side of cloud hosting** in full detail.

### 👥 Who should use this repository?

| Audience | Why this helps |
|---|---|
| 🎓 **Students** | A guided, practical AWS + Windows Server lab for coursework or self-study |
| 💼 **Job Seekers** | A portfolio-ready project to showcase on resumes, GitHub, and LinkedIn |
| ☁️ **Aspiring Cloud Engineers** | Real exposure to EC2, networking, and IIS administration |
| 🧑‍🏫 **Educators/Trainers** | A ready-made lab guide for classroom or workshop use |
| 🛠️ **Windows Admins moving to Cloud** | Bridges on-prem IIS knowledge with AWS cloud concepts |

### 🧠 Learning Outcomes at a Glance

By the end of this project, you will be able to:

- ✅ Launch and configure a Windows Server EC2 instance from scratch
- ✅ Connect to a remote Windows server using RDP
- ✅ Install and configure IIS as a production web server
- ✅ Deploy static website files to a live server
- ✅ Configure AWS Security Groups and Windows Firewall for web traffic
- ✅ Troubleshoot common HTTP errors (403, 404, 500)
- ✅ Understand core AWS networking concepts (VPC, Subnets, Public/Private IP)

---

## 🎯 2. Project Objectives

This project was designed around these core learning objectives:

- 🟧 **Learn AWS EC2** — instance creation, AMIs, instance types, key pairs, and lifecycle management
- 🟦 **Learn Windows Server** — administering a Windows Server OS entirely through Remote Desktop
- 🟪 **Learn IIS** — installing and configuring Microsoft's web server role
- 🌍 **Learn Static Website Deployment** — moving local project files onto a live server
- 🔐 **Learn AWS Networking & Security** — Security Groups, inbound/outbound rules, public IP addressing
- ☁️ **Learn Cloud Hosting Fundamentals** — the full lifecycle of taking an app from local machine → cloud → public internet

---

## 🏗️ 3. Architecture Overview

The diagram below illustrates the full request flow — from a user's browser all the way down to the static files served by IIS.

```text
                    ┌──────────────────────────┐
                    │      👤 User Browser      │
                    │  (Chrome / Edge / Firefox)│
                    └────────────┬─────────────┘
                                 │  HTTP Request (Port 80)
                                 ▼
                    ┌──────────────────────────┐
                    │        🌐 Internet         │
                    └────────────┬─────────────┘
                                 │
                                 ▼
                    ┌──────────────────────────┐
                    │  🛡️  AWS Security Group    │
                    │  (Inbound Rule: TCP 80)   │
                    └────────────┬─────────────┘
                                 │
                                 ▼
                    ┌──────────────────────────┐
                    │  💻 EC2 Windows Server     │
                    │   (Public IP Attached)    │
                    └────────────┬─────────────┘
                                 │
                                 ▼
                    ┌──────────────────────────┐
                    │  ⚙️  Internet Information  │
                    │     Services (IIS)        │
                    │   Default Web Site :80    │
                    └────────────┬─────────────┘
                                 │
                                 ▼
                    ┌──────────────────────────┐
                    │  📁 C:\inetpub\wwwroot     │
                    │  index.html · css · js    │
                    │       images/              │
                    └──────────────────────────┘
```

### 🔎 Component Breakdown

| Layer | Component | Role |
|---|---|---|
| 1️⃣ | **User Browser** | Sends an HTTP `GET` request to the server's public IP |
| 2️⃣ | **Internet** | Routes the request across the public network to AWS |
| 3️⃣ | **AWS Security Group** | Acts as a virtual firewall — only allows traffic on permitted ports (80, 3389) |
| 4️⃣ | **EC2 Windows Server** | The virtual machine running Windows Server OS in the AWS cloud |
| 5️⃣ | **IIS (Internet Information Services)** | The web server software that listens on port 80 and serves files |
| 6️⃣ | **`wwwroot` folder** | The physical location on disk where the static website files live |

> ⚠️ **Warning:** If *any* layer in this chain is misconfigured (Security Group, Windows Firewall, IIS service stopped, wrong folder), the website will **not** be accessible — this project's [Troubleshooting section](#-11-step-11--troubleshooting-guide) maps directly to this diagram.

---

## 🧰 4. Technologies Used

| Technology | Category | Purpose |
|---|---|---|
| 🟧 **AWS EC2** | Cloud Compute | Virtual server (instance) that hosts the entire environment |
| 🪟 **Windows Server (2019/2022)** | Operating System | OS running on the EC2 instance |
| 🟣 **IIS (Internet Information Services)** | Web Server | Serves the static website over HTTP |
| 🟠 **HTML5** | Frontend | Structure/content of the website |
| 🔵 **CSS3** | Frontend | Styling and layout of the website |
| 🟡 **JavaScript** | Frontend | Client-side interactivity |
| 🔌 **RDP (Remote Desktop Protocol)** | Remote Access | Used to remotely access and configure the Windows Server |
| 🛡️ **AWS Security Groups** | Networking/Security | Virtual firewall controlling inbound/outbound traffic |
| 🌍 **Public IP Address** | Networking | Makes the EC2 instance reachable from the internet |

---

## ✅ 5. Prerequisites

Before starting, make sure you have the following ready:

| Requirement | Details |
|---|---|
| ☁️ **AWS Account** | Sign up at [aws.amazon.com](https://aws.amazon.com/) — Free Tier eligible |
| 👤 **IAM User** | Recommended over using the root account, with `AmazonEC2FullAccess` policy |
| 💻 **A computer (Windows/Mac/Linux)** | Any OS with an RDP client works |
| 🔌 **Remote Desktop Client** | Built into Windows; macOS/Linux users need "Microsoft Remote Desktop" or Remmina |
| 🌐 **Stable Internet Connection** | Needed for RDP session and file uploads |
| 🧱 **Basic HTML/CSS Knowledge** | Helpful but not mandatory — sample files are provided |
| 🆓 **AWS Free Tier (optional)** | `t2.micro` / `t3.micro` Windows instances are Free Tier eligible for 12 months |

> 📝 **Note:** Windows Server AMIs consume Free Tier hours **faster** than Linux AMIs in some regions because of licensing overhead — keep an eye on your AWS Billing Dashboard.

---

## 📁 6. Project Folder Structure

```text
Project/
│
├── index.html          # Main landing page of the static website
│
├── css/
│   └── style.css        # All styling rules for the website
│
├── js/
│   └── script.js        # Client-side interactivity (optional)
│
├── images/               # All image/media assets used in the site
│
└── README.md            # You are here 📍
```

### 📦 Folder Explanation

| Folder/File | Purpose |
|---|---|
| `index.html` | The default document IIS looks for when the site loads — **must** be named exactly `index.html` (or configured as the default document) |
| `css/style.css` | Keeps styling separated from markup, following best practice |
| `js/script.js` | Holds any dynamic, client-side JavaScript logic |
| `images/` | Stores logos, icons, banners, and other visual assets |
| `README.md` | This documentation file |

---

## 🪜 7. Step-by-Step Practical Guide

> 💡 **Tip:** Each step below follows the same format — **Purpose → Explanation → Commands → Expected Output → Notes → Screenshot → Troubleshooting** — so you always know exactly where you are in the process.

### ⚡ Quick Start (TL;DR)

```text
1. Create AWS account → 2. Launch Windows EC2 → 3. Connect via RDP →
4. Install IIS → 5. Copy files to wwwroot → 6. Open port 80 →
7. Visit http://<public-ip> → 🎉 Done!
```

---

### 🟢 Step 1 — Create an AWS Account

**🎯 Purpose:** Get access to the AWS Management Console where the EC2 instance will be created.

**📖 Explanation:**
1. Go to [aws.amazon.com](https://aws.amazon.com/) and click **Create an AWS Account**.
2. Provide your email, password, and AWS account name.
3. Enter billing information (a card is required even for Free Tier).
4. Verify your identity via phone/SMS.
5. Choose the **Basic Support Plan** (Free).
6. Sign in to the **AWS Management Console**.

> ⚠️ **Warning:** Always set up **Billing Alerts** immediately after account creation to avoid unexpected charges.

**🖼️ Screenshot Placeholder:** `screenshots/01-aws-account-signup.png`

**🛠️ Troubleshooting:**
| Problem | Solution |
|---|---|
| Card verification fails | Use a valid international debit/credit card |
| Account stuck in "pending verification" | Wait up to 24 hours or contact AWS Support |

---

### 🟢 Step 2 — Launch a Windows Server EC2 Instance

**🎯 Purpose:** Create the virtual machine that will host the website.

**📖 Explanation — Configure each setting carefully:**

| Setting | Recommended Value | Why |
|---|---|---|
| **AMI (Amazon Machine Image)** | `Microsoft Windows Server 2022 Base` | Free-tier eligible, latest LTS-style release |
| **Instance Type** | `t2.micro` or `t3.micro` | Free Tier eligible, sufficient for a static site |
| **Key Pair** | Create new → download `.pem` file | Required to decrypt the Administrator password |
| **Network Settings (Security Group)** | Allow **RDP (3389)** and **HTTP (80)** | Needed for remote access and web traffic |
| **Storage** | Default 30 GB gp2/gp3 | Sufficient for Windows Server + IIS + static files |

**📋 Steps in Console:**
1. Navigate to **EC2 Dashboard → Launch Instance**.
2. Name your instance (e.g., `Static-Website-IIS-Server`).
3. Select the Windows Server 2022 AMI.
4. Choose instance type `t2.micro`.
5. Create/select a Key Pair and **download the `.pem` file** — you cannot re-download it later.
6. Under **Network Settings**, edit Security Group to allow:
   - `RDP` – Port `3389` – Source: *My IP* (recommended) or Anywhere (0.0.0.0/0)
   - `HTTP` – Port `80` – Source: Anywhere (0.0.0.0/0)
7. Keep storage at default settings.
8. Click **Launch Instance**.

**✅ Expected Output:** Instance state changes from `Pending` → `Running`, and a **Public IPv4 address** is assigned.

> 📝 **Note:** Wait 3–5 minutes after launch for **Status Checks** to pass (2/2 checks) before attempting to connect.

**🖼️ Screenshot Placeholder:** `screenshots/02-ec2-launch-config.png`

**🛠️ Troubleshooting:**
| Problem | Cause | Solution |
|---|---|---|
| Launch button greyed out | Missing key pair selection | Select or create a key pair |
| Instance stuck in "Pending" | Normal initial boot time | Wait 2–5 minutes |
| No Public IP assigned | Instance launched in a subnet without auto-assign public IP | Enable "Auto-assign Public IP" in subnet settings or attach an Elastic IP |

---

### 🟢 Step 3 — Connect to the Instance via RDP

**🎯 Purpose:** Remotely access the Windows Server desktop to perform configuration.

**📖 Explanation:**
1. In the EC2 Console, select your instance → click **Connect**.
2. Go to the **RDP Client** tab → click **Get Password**.
3. Upload the `.pem` key pair file you downloaded earlier.
4. Click **Decrypt Password** to reveal the Administrator password.
5. Click **Download Remote Desktop File** (`.rdp` file).
6. Open the downloaded `.rdp` file — your OS's Remote Desktop client will launch.
7. When prompted, enter username `Administrator` and the decrypted password.
8. Accept the certificate warning to proceed.

**💻 Commands (if using `mstsc` manually on Windows):**
```powershell
mstsc /v:<Public-IP-Address>
```

**✅ Expected Output:** The Windows Server desktop appears, showing **Server Manager** open by default.

**🖼️ Screenshot Placeholder:** `screenshots/03-rdp-connection.png`

**🛠️ Troubleshooting:**
| Problem | Cause | Solution |
|---|---|---|
| "Remote Desktop can't connect" | Security Group missing RDP rule | Add inbound rule for port 3389 |
| Wrong password error | Decrypted with wrong key pair | Re-download password, ensure correct `.pem` is used |
| Connection times out | Instance not fully booted | Wait a few more minutes and retry |
| Black screen after login | Display driver glitch | Disconnect and reconnect the RDP session |

---

### 🟢 Step 4 — Install IIS (Internet Information Services)

**🎯 Purpose:** Install the web server role that will serve the static website.

**📖 Explanation — Using Server Manager:**
1. Inside the RDP session, open **Server Manager** (opens automatically on login).
2. Click **Manage → Add Roles and Features**.
3. Click **Next** through *Before You Begin*, *Installation Type* (Role-based), and *Server Selection*.
4. On **Server Roles**, check ✅ **Web Server (IIS)**.
5. Click **Add Features** when prompted for dependent features.
6. Click **Next** through *Features* and *Role Services* (defaults are fine for static sites).
7. Click **Install** and wait for the process to complete.

**💻 Alternative — Install via PowerShell:**
```powershell
Install-WindowsFeature -Name Web-Server -IncludeManagementTools
```

**✅ Expected Output:** Installation progress bar reaches 100% with message *"Installation succeeded"*.

**🔍 Verify Installation:**
```powershell
Get-WindowsFeature -Name Web-Server
```
Expected result: `Install State : Installed`

**📖 Open IIS Manager:**
- Press `Win + R` → type `inetmgr` → Enter
- Or: **Server Manager → Tools → Internet Information Services (IIS) Manager**

**🖼️ Screenshot Placeholder:** `screenshots/04-iis-installation.png` , `screenshots/05-iis-manager.png`

**🛠️ Troubleshooting:**
| Problem | Cause | Solution |
|---|---|---|
| "Add Roles" greyed out | Insufficient permissions | Ensure logged in as Administrator |
| Installation fails | Pending Windows Updates/reboot | Restart the instance and retry |
| `inetmgr` command not found | IIS not yet installed | Complete the installation step first |

---

### 🟢 Step 5 — Locate the Web Root Folder

**🎯 Purpose:** Identify where IIS expects static website files to be placed.

**📖 Explanation:**

By default, IIS serves content from:

```text
C:\inetpub\wwwroot
```

This is the **physical path** mapped to the **"Default Web Site"** in IIS. Any file placed here becomes automatically accessible via HTTP, provided IIS is running and the firewall/Security Group allow port 80.

> 💡 **Tip:** You can confirm this mapping inside IIS Manager: select **Default Web Site** → in the **Actions** pane click **Basic Settings** → check the **Physical Path** field.

**✅ Expected Output:** Navigating to `C:\inetpub\wwwroot` in File Explorer shows the default `iisstart.htm` page and an `iisstart.png` image.

**🖼️ Screenshot Placeholder:** `screenshots/06-wwwroot-folder.png`

**🛠️ Troubleshooting:**
| Problem | Cause | Solution |
|---|---|---|
| Folder doesn't exist | IIS installation incomplete | Reinstall the Web-Server role |
| Access denied opening folder | Permission/UAC restriction | Run File Explorer as Administrator |

---

### 🟢 Step 6 — Deploy the Website Files

**🎯 Purpose:** Place your actual HTML/CSS/JS project inside the IIS web root so it becomes live.

**📖 Explanation — Two ways to transfer files into the EC2 instance:**

**Option A: Copy-Paste via RDP Clipboard**
1. On your **local machine**, copy your project folder (`Ctrl+C`).
2. Inside the **RDP session**, paste (`Ctrl+V`) into `C:\inetpub\wwwroot`.

**Option B: Upload via Browser (if no clipboard redirection)**
1. Inside the RDP session, open **Edge/Chrome**.
2. Upload your project to a temporary cloud link (Google Drive/GitHub) beforehand.
3. Download it directly inside the RDP session, then extract into `wwwroot`.

**📁 Final folder result inside `C:\inetpub\wwwroot`:**
```text
C:\inetpub\wwwroot\
│
├── index.html
├── css\style.css
├── js\script.js
└── images\
```

> ⚠️ **Warning:** Delete or rename the default `iisstart.htm` file — if both `iisstart.htm` and `index.html` exist, IIS may still load the default page depending on the Default Document priority order (see Step 7).

**🔍 Verify folder structure:**
```powershell
Get-ChildItem C:\inetpub\wwwroot -Recurse
```

**✅ Expected Output:** Command lists `index.html`, `css`, `js`, and `images` exactly as in your local project structure.

**🖼️ Screenshot Placeholder:** `screenshots/07-files-deployed.png`

**🛠️ Troubleshooting:**
| Problem | Cause | Solution |
|---|---|---|
| Clipboard paste not working | RDP local resources not enabled | Enable "Clipboard" under RDP file → Local Resources before connecting |
| Files missing after paste | Copy interrupted | Re-copy and verify file count matches |
| CSS/JS not loading on site | Incorrect relative paths in HTML | Ensure `<link>`/`<script>` tags use relative paths like `css/style.css` |

### 🟢 Step 7 — Configure the Default Document

**🎯 Purpose:** Ensure IIS automatically loads `index.html` when someone visits the root URL.

**📖 Explanation:**
1. Open **IIS Manager** → expand **Sites** → select **Default Web Site**.
2. Double-click **Default Document** (in the middle pane).
3. Check the list — `index.html` should be present. If not, click **Add** (right pane) and type `index.html`.
4. Use the **Move Up** action to place `index.html` at the **top** of the priority list (above `iisstart.htm` if it still exists).

**📖 Verify Bindings:**
1. Select **Default Web Site** → click **Bindings** (right pane).
2. Confirm a binding exists for **Type: http**, **Port: 80**, with no specific hostname restriction (so it responds to the public IP).

**✅ Expected Output:** When you reload the **Default Web Site** in IIS Manager, the **Content View** tab shows `index.html` as the active default page.

**🖼️ Screenshot Placeholder:** `screenshots/08-default-document.png`

**🛠️ Troubleshooting:**
| Problem | Cause | Solution |
|---|---|---|
| Old default page still loads | `iisstart.htm` ranked above `index.html` | Reorder list or delete `iisstart.htm` |
| "Default Document" feature missing | Static Content/Default Document role service not installed | Add Role Service via Server Manager |

---

### 🟢 Step 8 — Allow HTTP Traffic in AWS Security Group

**🎯 Purpose:** Open the network path at the AWS level so external traffic on port 80 can reach the instance.

**📖 Explanation:**
1. Go to **EC2 Console → Instances** → select your instance.
2. Click the **Security** tab → click on the linked **Security Group**.
3. Click **Edit Inbound Rules**.
4. Click **Add Rule**:

| Type | Protocol | Port Range | Source |
|---|---|---|---|
| HTTP | TCP | 80 | `0.0.0.0/0` (Anywhere) |
| RDP | TCP | 3389 | *My IP* (recommended) |

5. Click **Save Rules**.

> 🛡️ **Note on Outbound Rules:** By default, Security Groups allow **all outbound traffic** — this is fine for a static website and typically does not need modification.

**✅ Expected Output:** The inbound rules table shows an active rule allowing HTTP (80) from anywhere.

**🖼️ Screenshot Placeholder:** `screenshots/09-security-group-http.png`

**🛠️ Troubleshooting:**
| Problem | Cause | Solution |
|---|---|---|
| Website still unreachable after this step | Windows Firewall also blocking port 80 | Complete Step 9 |
| Rule won't save | Conflicting duplicate rule exists | Remove duplicate then re-add |

---

### 🟢 Step 9 — Configure Windows Defender Firewall

**🎯 Purpose:** Allow HTTP traffic *inside* the Windows OS itself — AWS Security Groups only control traffic at the network boundary, not inside the VM.

**📖 Explanation:**

When the **Web-Server (IIS)** role is installed, Windows **usually creates firewall rules automatically**, but it's important to verify them.

1. Open **Windows Defender Firewall with Advanced Security** (`wf.msc`).
2. Click **Inbound Rules**.
3. Look for rules named **"World Wide Web Services (HTTP Traffic-In)"** — ensure it's **Enabled** (green checkmark).
4. If missing, click **New Rule** → **Port** → TCP → Specific port `80` → **Allow the connection** → apply to all profiles → name it `Allow HTTP 80`.

**💻 Or via PowerShell:**
```powershell
New-NetFirewallRule -DisplayName "Allow HTTP 80" -Direction Inbound -Protocol TCP -LocalPort 80 -Action Allow
```

**✅ Expected Output:** Rule appears in the Inbound Rules list with status **Enabled**.

**🖼️ Screenshot Placeholder:** `screenshots/10-windows-firewall.png`

**🛠️ Troubleshooting:**
| Problem | Cause | Solution |
|---|---|---|
| Rule exists but still blocked | Rule scoped to wrong network profile | Enable rule for Public, Private, and Domain profiles |
| `wf.msc` won't open | Insufficient privileges | Run as Administrator |

---

### 🟢 Step 10 — Test the Website

**🎯 Purpose:** Confirm the entire chain (Security Group → Firewall → IIS → Files) is working end-to-end.

**📖 Explanation:**
1. Go to the **EC2 Console** and copy your instance's **Public IPv4 address**.
2. Open any browser (can be on your **local machine** — no need to stay inside RDP).
3. Navigate to:

```text
http://<Your-Public-IP-Address>
```

**✅ Expected Output:** Your custom static website (your `index.html`, styled with `style.css`, with `script.js` active) loads successfully in the browser. 🎉

**🖼️ Screenshot Placeholder:** `screenshots/11-website-live.png`

> 💡 **Tip:** Bookmark the public IP, but remember — **stopping and restarting** the EC2 instance changes the Public IP unless you attach an **Elastic IP**.

**🛠️ Troubleshooting:** See full guide in [Step 11](#-11-step-11--troubleshooting-guide) below.

---

### 🔴 Step 11 — Troubleshooting Guide

A categorized breakdown of every common issue and its fix:

| # | Issue | Likely Cause | Solution |
|---|---|---|---|
| 1 | **403 Forbidden** | Directory browsing disabled & no default document found | Set `index.html` as Default Document (Step 7) |
| 2 | **404 Not Found** | File missing or wrong path/filename | Verify exact file name and location in `wwwroot` |
| 3 | **500 Internal Server Error** | Misconfigured `web.config` or module error | Check `web.config` syntax; remove if not needed for static sites |
| 4 | **Website not loading at all** | Security Group or Firewall blocking port 80 | Re-check Steps 8 & 9 |
| 5 | **Security Group issue** | Inbound rule missing/misconfigured | Re-verify HTTP rule, port 80, source `0.0.0.0/0` |
| 6 | **Firewall issue** | Windows Firewall blocking inbound 80 | Re-check `wf.msc` rule status |
| 7 | **IIS not running** | World Wide Web Publishing Service stopped | Run `Start-Service W3SVC` in PowerShell |
| 8 | **Default document missing** | `index.html` not registered | Add via IIS Manager → Default Document |
| 9 | **Permission denied** | NTFS permissions on `wwwroot` restrict access | Grant `IIS_IUSRS` Read & Execute permission on the folder |
| 10 | **Static content disabled** | Static Content role service not installed | Add Role Service: Web Server → Common HTTP Features → Static Content |
| 11 | **Wrong folder used** | Files placed outside `wwwroot` or wrong site's physical path | Confirm path via IIS Manager → Basic Settings |
| 12 | **DNS / domain issue** | No domain configured (expected for IP-based testing) | Use Public IP directly, or configure Route 53 (see Future Improvements) |
| 13 | **Browser cache showing old page** | Cached old default IIS page | Hard refresh (`Ctrl+F5`) or open in Incognito mode |

> 📝 **Note:** 90% of "my website won't load" cases trace back to **either** the AWS Security Group **or** the Windows Firewall blocking port 80 — always check both first.

**💻 Useful Diagnostic Commands:**
```powershell
# Check if IIS service is running
Get-Service W3SVC

# Restart IIS completely
iisreset

# Check if port 80 is listening
netstat -an | findstr :80
```

---

### ✅ Step 12 — Project Verification Checklist

Use this checklist to confirm every component of the deployment is correctly in place:

- [ ] ☐ EC2 Windows Server instance is **Running** (2/2 status checks passed)
- [ ] ☐ Successfully connected via **RDP**
- [ ] ☐ **IIS** role installed and verified (`Get-WindowsFeature -Name Web-Server`)
- [ ] ☐ Website files uploaded to `C:\inetpub\wwwroot`
- [ ] ☐ `index.html` set as the **Default Document** (top priority)
- [ ] ☐ **HTTP (port 80)** allowed in AWS **Security Group**
- [ ] ☐ **HTTP (port 80)** allowed in **Windows Defender Firewall**
- [ ] ☐ `W3SVC` (World Wide Web Publishing Service) is running
- [ ] ☐ Website successfully loads at `http://<Public-IP>`
- [ ] ☐ CSS styling and JS functionality confirmed working on live site

---

## 📸 13. Screenshots Section

> Replace these placeholders with your own screenshots — store them in a `/screenshots` folder in the repo root.

| # | Screenshot | Description |
|---|---|---|
| 1 | `screenshots/01-aws-console.png` | AWS Management Console home |
| 2 | `screenshots/02-ec2-dashboard.png` | EC2 Dashboard showing running instance |
| 3 | `screenshots/03-rdp-connection.png` | Successful RDP connection screen |
| 4 | `screenshots/04-server-manager.png` | Server Manager with IIS role added |
| 5 | `screenshots/05-iis-manager.png` | IIS Manager interface |
| 6 | `screenshots/06-wwwroot-folder.png` | `C:\inetpub\wwwroot` contents |
| 7 | `screenshots/07-website-running.png` | Website loading successfully |
| 8 | `screenshots/08-browser-output.png` | Final browser output of the live site |
| 9 | `screenshots/09-security-group.png` | AWS Security Group inbound rules |
| 10 | `screenshots/10-windows-firewall.png` | Windows Defender Firewall rule for HTTP |

---

## 💻 14. Commands Used

| Command | Purpose |
|---|---|
| `mstsc /v:<IP>` | Launch Remote Desktop Connection to a specific IP |
| `ipconfig` | Display the instance's local IP configuration |
| `hostname` | Show the computer name of the server |
| `ping <IP/domain>` | Test network connectivity/latency to a target |
| `iisreset` | Restart all IIS services (Stop + Start) |
| `netstat -an \| findstr :80` | Check if port 80 is actively listening |
| `Get-WindowsFeature -Name Web-Server` | Verify whether the IIS role is installed |
| `Install-WindowsFeature -Name Web-Server -IncludeManagementTools` | Install IIS via PowerShell |
| `Get-Service W3SVC` | Check status of the World Wide Web Publishing Service |
| `Start-Service W3SVC` | Start the IIS web service if stopped |
| `New-NetFirewallRule ...` | Create a new Windows Firewall inbound rule |
| `Get-ChildItem -Recurse` | List all files/folders recursively (PowerShell equivalent of `ls -R`) |

> 💡 **Tip:** Most of these commands must be run from an **elevated PowerShell window** (Run as Administrator) inside the RDP session.

---

## 🌐 15. Networking Explanation

| Concept | Explanation |
|---|---|
| **Public IP** | A globally routable address assigned to the instance, allowing access from anywhere on the internet |
| **Private IP** | An internal address used for communication *within* the VPC; not reachable from the internet |
| **VPC (Virtual Private Cloud)** | An isolated virtual network within AWS where your EC2 instance lives |
| **Subnet** | A segmented range of IP addresses within a VPC, tied to a specific Availability Zone |
| **Internet Gateway** | A VPC component that allows resources with public IPs to communicate with the internet |
| **Security Group** | A stateful, instance-level virtual firewall controlling inbound/outbound traffic |
| **Windows Firewall** | An OS-level firewall inside the Windows Server itself — works *in addition to* the Security Group |
| **HTTP (Port 80)** | The standard protocol/port for unencrypted web traffic |
| **HTTPS (Port 443)** | The encrypted version of HTTP, using SSL/TLS certificates |
| **RDP (Port 3389)** | The protocol/port used for remote graphical access to Windows servers |

> ⚠️ **Warning:** Traffic must pass **both** the AWS Security Group **and** the Windows Firewall to reach IIS — blocking at either layer will break the site.

---

## ⚙️ 16. IIS Concepts

| Concept | Explanation |
|---|---|
| **Website** | A logical container in IIS that maps a hostname/port/IP binding to a physical folder |
| **Application Pool** | An isolated process boundary that runs one or more websites/apps — provides stability and security isolation |
| **Bindings** | Rules defining what protocol, IP, port, and hostname a site responds to |
| **Virtual Directory** | A folder exposed under a website's URL path that doesn't have to physically live inside the site's root folder |
| **Default Document** | The file (e.g., `index.html`) IIS automatically serves when no specific file is requested in the URL |
| **Authentication** | Controls *who* can access the site (Anonymous, Windows, Basic, etc.) — static sites typically use Anonymous |
| **Permissions (NTFS)** | File-system-level access control; the `IIS_IUSRS` group needs Read access to serve files |
| **Static Content** | The IIS module/role service responsible for serving plain files like `.html`, `.css`, `.js`, images |
| **Logging** | IIS can log every request (IP, time, status code) to log files for auditing/debugging |

---

## ☁️ 17. AWS Concepts Learned

| Concept | Explanation |
|---|---|
| **EC2 (Elastic Compute Cloud)** | AWS's core virtual server service |
| **Security Groups** | Virtual firewalls attached to instances |
| **Elastic IP** | A static public IP that persists across instance stop/start cycles |
| **Windows Server AMI** | A pre-configured machine image used to launch a Windows instance |
| **Instance Types** (`t2.micro`, `t3.micro`, etc.) | Define the vCPU/RAM/network resources allocated to the instance |
| **Billing & Cost Explorer** | Dashboards to monitor and control AWS spend |
| **Free Tier** | 750 hours/month of eligible instance types free for the first 12 months |
| **EBS Storage** | Elastic Block Store — the persistent virtual disk attached to EC2 instances |
| **Snapshots** | Point-in-time backups of EBS volumes, useful for disaster recovery |

---

## 🛡️ 18. Best Practices

- 🔒 **Never expose RDP (3389) to `0.0.0.0/0`** in production — restrict the source to your specific IP
- 📌 **Use an Elastic IP** if you need the public IP to remain constant across reboots
- 💾 **Take regular EBS Snapshots** as backups before major changes
- 👤 **Use IAM users with least-privilege policies** instead of logging in as the root AWS account
- 🔑 **Use strong, unique passwords** for the Windows Administrator account
- 🧱 **Keep Security Group rules minimal** — only open the ports you actually need
- 🎯 **Apply the Principle of Least Privilege** across IAM, Security Groups, and NTFS permissions alike
- 🔐 **Migrate to HTTPS** using a free certificate (Let's Encrypt or AWS Certificate Manager + CloudFront) for any real-world deployment
- 📊 **Enable CloudWatch monitoring** to track CPU, network, and status check metrics
- 🧹 **Terminate unused instances** to avoid ongoing Free Tier/billing surprises

---

## 🚀 19. Future Improvements

- 🌍 Attach a **custom domain name** (via Route 53 or any registrar)
- 🔐 Enable **HTTPS** with an **SSL/TLS certificate**
- ⚡ Integrate **Amazon CloudFront** as a CDN for global low-latency delivery
- 🛰️ Configure **Route 53** for DNS management and health checks
- 🔄 Build a **CI/CD pipeline** to auto-deploy on every Git push
- 🤖 Use **GitHub Actions** to automate file transfer to the EC2 instance
- 📦 Implement **Automatic Deployment Scripts** (PowerShell/AWS CLI based)
- ⚖️ Add an **Application Load Balancer** for high availability
- 📈 Configure **Auto Scaling Groups** to handle traffic spikes
- 🔭 Set up full **CloudWatch dashboards and alarms** for proactive monitoring

---

## 🎓 20. Learning Outcomes

After completing this project, you will have hands-on, demonstrable experience in:

- ✅ Provisioning and managing cloud virtual machines on AWS EC2
- ✅ Administering a Windows Server OS entirely via Remote Desktop
- ✅ Installing, configuring, and troubleshooting IIS as a production web server
- ✅ Understanding and applying AWS networking & security fundamentals
- ✅ Diagnosing real-world HTTP errors (403/404/500) methodically
- ✅ Working confidently with both the AWS Console and PowerShell
- ✅ Documenting a technical project to professional, recruiter-ready standards
- ✅ Building a genuine, demo-able cloud project for your portfolio/resume

---

## 🎤 21. Interview Questions (30+)

<details>
<summary><b>☁️ AWS EC2 & Cloud Computing (Q1–Q10)</b></summary>

<br/>

**Q1. What is Amazon EC2?**
A: EC2 (Elastic Compute Cloud) is an AWS service that provides resizable virtual servers ("instances") in the cloud, allowing users to run applications without owning physical hardware.

**Q2. What is an AMI?**
A: An Amazon Machine Image is a template containing the OS, configuration, and pre-installed software used to launch an EC2 instance.

**Q3. What's the difference between an Instance Type and an AMI?**
A: The AMI defines *what software/OS* runs on the instance; the Instance Type defines the *hardware resources* (vCPU, RAM, network performance) allocated to it.

**Q4. What is a Key Pair used for in EC2?**
A: A Key Pair (public/private key) is used to securely decrypt the auto-generated Administrator password for Windows instances, or to authenticate SSH for Linux instances.

**Q5. What is the AWS Free Tier?**
A: A program offering limited free usage (e.g., 750 hrs/month of `t2.micro`/`t3.micro` instances) for 12 months to new AWS accounts.

**Q6. What is an Elastic IP and why use one?**
A: A static public IP address that you can allocate to your AWS account and attach to an instance — it doesn't change even if the instance is stopped and restarted, unlike a standard public IP.

**Q7. What happens to the Public IP when you stop and start an EC2 instance?**
A: By default, the Public IP changes on every stop/start cycle unless an Elastic IP is attached.

**Q8. What is the difference between stopping and terminating an EC2 instance?**
A: Stopping shuts down the instance but preserves its EBS storage (can be restarted later); terminating permanently deletes the instance and, by default, its root volume.

**Q9. What is an EBS Snapshot?**
A: A point-in-time backup of an EBS volume, stored in S3, used for backup, recovery, or creating new volumes/AMIs.

**Q10. What is the shared responsibility model in AWS?**
A: AWS is responsible for the security *of* the cloud (hardware, infrastructure), while the customer is responsible for security *in* the cloud (OS patching, firewall rules, data, access management).

</details>

<details>
<summary><b>🪟 Windows Server (Q11–Q15)</b></summary>

<br/>

**Q11. What is Windows Server used for in cloud environments?**
A: It's an OS optimized for running enterprise applications, web servers (IIS), Active Directory, and other server-based workloads in cloud or on-prem data centers.

**Q12. What is Server Manager?**
A: A built-in Windows Server console used to manage roles, features, and configuration across one or multiple servers.

**Q13. What is RDP and how does it work?**
A: Remote Desktop Protocol is a Microsoft protocol (port 3389) that transmits the graphical desktop interface of a remote machine to a local client, enabling remote administration.

**Q14. How do you check which Windows features/roles are installed via PowerShell?**
A: Using `Get-WindowsFeature`, which lists all available and installed roles/features along with their install state.

**Q15. Why is it risky to expose RDP (port 3389) to the entire internet?**
A: It becomes a target for brute-force login attacks; best practice is to restrict the source IP range or use a VPN/bastion host instead.

</details>

<details>
<summary><b>⚙️ IIS (Q16–Q22)</b></summary>

<br/>

**Q16. What is IIS?**
A: Internet Information Services is Microsoft's web server software for hosting websites and web applications on Windows Server.

**Q17. What is an Application Pool in IIS?**
A: An isolated worker-process boundary that runs one or more websites, providing fault isolation so that a crash in one app pool doesn't affect others.

**Q18. What is a Default Document in IIS?**
A: The file IIS automatically serves (e.g., `index.html`) when a request doesn't specify an exact filename.

**Q19. What causes a 403 Forbidden error in IIS?**
A: Commonly caused by a missing Default Document combined with disabled directory browsing, or insufficient NTFS/IIS permissions on the requested resource.

**Q20. What causes a 500 Internal Server Error?**
A: Usually a misconfigured `web.config` file, a missing required module, or an application-level runtime error.

**Q21. What is `iisreset` used for?**
A: A command-line tool that stops and restarts all IIS-related services in one step — useful after configuration changes.

**Q22. What is the difference between a Website and a Virtual Directory in IIS?**
A: A Website is bound to its own IP/port/hostname and has its own application pool; a Virtual Directory is a sub-path under an existing website mapped to a different physical folder.

</details>

<details>
<summary><b>🌐 Networking & Security (Q23–Q30)</b></summary>

<br/>

**Q23. What is a Security Group?**
A: A virtual, stateful firewall in AWS that controls inbound and outbound traffic at the instance level, based on rules (protocol, port, source/destination).

**Q24. What does "stateful" mean in the context of a Security Group?**
A: If an inbound request is allowed, the corresponding outbound response is automatically allowed too, without needing a separate matching rule.

**Q25. What is the difference between a Security Group and a Network ACL?**
A: Security Groups operate at the instance level and are stateful; Network ACLs operate at the subnet level and are stateless, requiring explicit rules for both directions.

**Q26. What port does HTTP use by default? What about HTTPS?**
A: HTTP uses port 80; HTTPS (encrypted) uses port 443.

**Q27. What is a VPC?**
A: A Virtual Private Cloud is a logically isolated virtual network within AWS where you can launch resources like EC2 instances with full control over IP ranges, subnets, and routing.

**Q28. What is the purpose of an Internet Gateway?**
A: It's a horizontally scaled, redundant VPC component that enables communication between instances with public IPs and the internet.

**Q29. Why might a website still be unreachable even after opening port 80 in the Security Group?**
A: The OS-level firewall (Windows Defender Firewall) may still be blocking the port, or the web service (IIS/W3SVC) might not be running.

**Q30. What's the difference between a Public IP and a Private IP?**
A: A Public IP is internet-routable and reachable from anywhere; a Private IP is only routable within the VPC/internal network and is not directly reachable from the internet.

**Bonus Q31. Why use a static website project to learn cloud computing fundamentals?**
A: It's simple enough to focus entirely on infrastructure concepts (compute, networking, security, OS administration) without the added complexity of application code or databases — making it an ideal first hands-on cloud project.

</details>

---

## 📚 22. References

| Resource | Link |
|---|---|
| 📘 AWS EC2 Documentation | [docs.aws.amazon.com/ec2](https://docs.aws.amazon.com/ec2/) |
| 🪟 Windows Server Documentation | [learn.microsoft.com/windows-server](https://learn.microsoft.com/en-us/windows-server/) |
| ⚙️ IIS Documentation | [learn.microsoft.com/iis](https://learn.microsoft.com/en-us/iis/) |
| 🛡️ AWS Security Groups Guide | [docs.aws.amazon.com/vpc/security-groups](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html) |
| 🔌 Remote Desktop Protocol Docs | [learn.microsoft.com/remote-desktop-services](https://learn.microsoft.com/en-us/windows-server/remote/remote-desktop-services/) |
| 🆓 AWS Free Tier Details | [aws.amazon.com/free](https://aws.amazon.com/free/) |

---

## 🤝 23. Contributing

Contributions are what make the open-source community such an amazing place to learn and grow. Any contributions you make are **greatly appreciated**! 🙌

1. **Fork** the repository
2. **Create your Feature Branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit your Changes**
   ```bash
   git commit -m "Add: some AmazingFeature"
   ```
4. **Push to the Branch**
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Open a Pull Request** 🎉

> 💡 **Tip:** Please open an issue first for major changes, to discuss what you'd like to change. Don't forget to ⭐ **star this repo** if you found it useful!

---

## 📄 24. License

This project is licensed under the **MIT License**.

```text
MIT License

Copyright (c) 2026 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

See the [LICENSE](LICENSE) file for full details.

---

## 👤 25. Author

<div align="center">

### **[Your Name]**

☁️ Cloud & DevOps Enthusiast &nbsp;|&nbsp; 🐧 RHCSA Certified &nbsp;|&nbsp; 🌟 AWS Community Volunteer &nbsp;|&nbsp; 🔓 Open Source Contributor

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/your-username)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/your-profile)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:your.email@example.com)

</div>

| | |
|---|---|
| 🎓 **Role** | Cloud & DevOps Enthusiast |
| 🐧 **Certification** | Red Hat Certified System Administrator (RHCSA) |
| 🌍 **Community** | AWS Community Volunteer |
| 🔓 **Contribution** | Active Open Source Contributor |

---

## 🏷️ 26. Repository Topics

```text
aws  ec2  windows-server  iis  cloud  html  css  javascript
aws-project  cloud-computing  static-website  beginner-project
windows  aws-ec2  iis-server  devops  cloud-deployment  rdp
networking  security-groups
```

---

## 🔎 27. SEO Description

> A beginner-friendly, fully documented AWS project demonstrating how to deploy a static HTML/CSS/JS website on an EC2 Windows Server using IIS — covering EC2 setup, RDP, IIS configuration, AWS networking, security groups, and troubleshooting.

*(331 characters)*

---

## 🎨 28. GitHub Social Preview Text

> ☁️ **From Zero to Live Website** — Deploy a static site on AWS EC2 Windows Server with IIS. A complete, step-by-step cloud hosting project for students, job-seekers, and aspiring cloud engineers. 🚀

---

## ✨ 29. Repository Features

<table>
<tr>
<td width="50%" valign="top">

### 📖 Beginner Friendly
Every single step is explained — no prior AWS experience assumed.

</td>
<td width="50%" valign="top">

### 🏗️ Real Infrastructure
Uses an actual AWS EC2 instance, not a simulation or local environment.

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🛠️ Full Troubleshooting Guide
Covers 13+ common errors with causes and fixes.

</td>
<td width="50%" valign="top">

### 🎤 Interview-Ready
30+ interview Q&As covering AWS, Windows Server, IIS, and networking.

</td>
</tr>
<tr>
<td width="50%" valign="top">

### ✅ Verification Checklist
A clear checklist to confirm every layer of the deployment works.

</td>
<td width="50%" valign="top">

### 🚀 Future-Proof Roadmap
Clear next steps: HTTPS, CDN, CI/CD, Auto Scaling, and more.

</td>
</tr>
</table>

---

## 📝 30. Final Notes

This documentation is intended to function as a **complete cloud engineering lab guide** — suitable for self-study, classroom training, technical interviews, and portfolio presentation. Every configuration choice, command, and troubleshooting step reflects real, reproducible behavior on AWS and Windows Server/IIS.

> ⭐ **If this project helped you learn something new, consider starring the repository — it helps others discover it too!**

<div align="center">

### 🌟 Happy Cloud Hosting! 🌟

**Made with ☕, 🪟, and a lot of `Get-WindowsFeature` checks.**

</div>
