# Active Directory Lab: Domain Setup and Security Policies

## Objective
This project involved architecting a functional Windows Domain environment to practice centralized administration, Identity & Access Management (IAM), and security auditing. The goal was to understand how enterprise networks manage user permissions, enforce security policies, and generate authentication logs for security investigations.

## Environment & Technologies
* **Hypervisor:** Oracle VirtualBox
* **Servers:** Windows Server 2022 (Domain Controller)
* **Endpoints:** Windows 10 Pro (Client Workstation)
* **Core Concepts:** Active Directory Domain Services (AD DS), Group Policy Objects (GPO), IAM, Windows Event Viewer.

## Step 1: Establishing the Domain & Organizational Structure
I deployed a Windows Server 2022 virtual machine, promoted it to a Domain Controller, and established the `talha.local` domain. 

After successfully joining the Windows 10 client workstation to the domain, I built out an organizational structure. I created a dedicated Human Resources (HR) Organizational Unit (OU) to logically separate these users and efficiently manage their specific departmental permissions and assets.

## Step 2: Attack Surface Reduction via Group Policy
To practice enforcing enterprise security standards, I implemented a Group Policy Object (GPO) targeting the HR OU. 

* **The Policy:** I configured a strict policy to deny HR users access to the Command Prompt. 
* **The Verification:** I logged into the Windows 10 client as an HR user and executed the `gpupdate /force` command to pull the latest domain policies. I then attempted to launch the Command Prompt, confirming the system successfully blocked access, effectively reducing the endpoint's attack surface.

<img width="1019" height="771" alt="cmd-blocked-policy" src="https://github.com/user-attachments/assets/1ea7b913-8cd5-4f06-8e43-d47bee15b158" />

*Verification of the GPO actively denying an HR user access to the Command Prompt.*

## Step 3: Authentication Auditing & Log Investigation
A critical component of centralized identity management is tracking who logs in and from where. 

Using the Windows Event Viewer on the Domain Controller, I audited the network's login activity. I specifically filtered for **Event ID 4624 (An account was successfully logged on)** to track user sessions, verify authentication protocols, and identify the source IP addresses of the connected clients.

<img width="1026" height="871" alt="event-viewer-logs" src="https://github.com/user-attachments/assets/d22d6cd0-9679-48cc-94d4-6d5bd7da4140" />

*Windows Event Viewer logs identifying a successful Event ID 4624 authentication, highlighting the user session and source network data.*

## What I Learned
Building this domain environment provided a deep understanding of how corporate networks are secured and monitored. I gained practical experience in:
* Architecting Active Directory domains and managing Organizational Units.
* Deploying and verifying Group Policy Objects (GPOs) to enforce security baselines.
* Navigating Windows Event Viewer to conduct authentication audits and hunt for critical security Event IDs.
