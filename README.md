Project Overview
Goal: Build a secure, isolated enterprise network to practice Identity and Access Management (IAM) and Security Operations Center (SOC) analysis.

Tech Stack: VirtualBox, Windows Server 2022, Windows 10 Pro.

What I Accomplished: 
Configured an internal virtual network (intnet) with static IP addressing and DNS to allow domain communication while maintaining isolation.

Active Directory Setup: Promoted a Server 2022 instance to a Domain Controller for the talha.local forest.

IAM Implementation: Created Organizational Units (OUs) for departments like HR and applied Group Policy Objects (GPOs) to restrict system tools like the Command Prompt.

SOC Investigation: Analyzed Windows Security Logs (Event ID 4624) to verify successful user authentications and identify workstation source IPs.
