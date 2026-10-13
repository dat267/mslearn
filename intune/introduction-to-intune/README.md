# Introduction to Microsoft Intune

Source: Microsoft Learn module "Introduction to Microsoft Intune" (slug `intro-to-endpoint-manager`), MD-102 Endpoint Administrator material.

Module completed 2026-10-13.
Achievement: https://learn.microsoft.com/api/achievements/share/en-us/DatDo-7483/ZJYHW8V2?sharingId=15FA99AA28223E58

## Main takeaways

- Microsoft Intune is a single, integrated, cloud-based platform for managing, protecting, and monitoring all endpoints — both devices and apps — across Android, Android Enterprise, iOS/iPadOS, macOS, and Windows 10/11.
- Intune now combines Microsoft Intune, Microsoft Endpoint Configuration Manager, endpoint analytics, and Windows Autopilot under one console. If you already have Configuration Manager, you also have Intune; they are one management system.
- MDM protects the enrolled device; MAM protects data inside apps, which is what lets personal and unenrolled devices participate safely. Use both so only authorized people and devices reach corporate data.
- Cloud attach is a two-step path: **tenant attach** first (Configuration Manager connector registers the deployment with the Intune tenant, no co-management required), then **co-management** (Configuration Manager and Intune manage Windows 10/11 side by side, per-workload authority).
- Windows Autopilot turns new-device setup into "connect to network and sign in": Entra join, MDM autoenrollment, OOBE, group assignment, and reset/repurpose are all cloud-driven.
- Endpoint analytics supplies experience and performance insights with remediation recommendations, feeding the Microsoft Adoption Score.
- Intune leans on neighboring services for identity and protection: Microsoft Entra ID for identity and access, Microsoft Purview Information Protection, and Microsoft Defender.

## 1. Why endpoint management (Introduction)

The modern workplace changed the management problem: knowledge workers use multiple devices, shared and specialized devices are common (point of sale, ruggedized, interactive whiteboards, conference-room devices, holographic wearables), devices can be corporate- or user-owned, SaaS apps sit next to legacy apps, and IT is moving from manual, reactive work to automated, proactive work. Employees also use their own devices at work, school, and home, and expect seamless access to organizational resources.

Users can be employees, coworkers, or students. They may open personal files, browse unsecured sites, and install unsafe apps, yet they still need to reach corporate resources from iOS/iPadOS, Android, Windows, or macOS devices, whether company-owned or personal, across multiple device types and formats (app or browser).

The control pair is:

- **MDM (mobile device management)** — protects resources and data based on **enrolled** devices.
- **MAM (mobile application management)** — manages and protects data **within applications**.

Together they make sure only authorized people and devices get access to proprietary information, so users can safely work from a phone that meets the organization's security requirements.

A management infrastructure must: keep devices and apps compliant with security requirements, enforce policy from a single unified solution, support a diverse mobile environment, make corporate services available on every device, control how the workforce accesses and shares data, distribute digital policies to both corporate and personal devices, and give users a first-class support experience for products such as Office and Edge. Users benefit directly because certificates, Wi-Fi profiles, and VPN settings arrive automatically instead of being configured by hand.

Module learning objectives: the products, services, and capabilities that make up Microsoft Intune; how Intune and Microsoft Configuration Manager help protect endpoints; and what Intune can do for the organization.

## 2. What is Microsoft Intune?

A single, integrated platform to manage, protect, and monitor all endpoints, where **endpoints** means every app and device the organization uses: mobile devices, desktops and laptops, virtual machines, embedded devices, shared devices, retail point-of-sale devices, ruggedized devices, digital interactive whiteboards, conference-room devices, and holographic wearable computers.

Goals:

- Protect the data people access.
- Safeguard the devices and apps that reach organizational resources.
- Ensure proper credentials are used to access and share company data.
- Confirm security rules match organizational requirements.
- Confirm every member's devices are correctly configured and protected.
- Make corporate services available to users on all their devices.
- Give new members a good onboarding experience.
- Give users a first-class support experience.

Intune integrates Microsoft Intune, Configuration Manager, and Windows Autopilot, and one Intune console keeps cloud and on-premises devices, apps, and data secure. Configuration Manager and Intune are now one management system: if you already have Configuration Manager, you also have Intune.

## 3. Understand Microsoft Intune

Intune provides cloud-based mobile device management (MDM), cloud-based mobile application management (MAM), and cloud-based computer management. It controls features and settings on Android, Android Enterprise, iOS/iPadOS, macOS, and Windows 10/11 devices.

It integrates closely with Microsoft Entra ID (identity and access control), Microsoft Purview Information Protection, and Microsoft Defender advanced threat protection products. With Microsoft 365 it supports productivity on every device while protecting organizational information. For existing on-premises infrastructure such as Exchange or Active Directory, Intune connectors link to external services. Intune is part of Microsoft's security suite.

## 4. Understand Microsoft Endpoint Configuration Manager

Configuration Manager is a computer management solution for desktops, laptops, and servers on the network or on the internet. Attaching a Configuration Manager deployment to the Microsoft 365 cloud provides integration with Intune, Microsoft Entra ID, Microsoft Defender, and other cloud services.

Use Configuration Manager to deploy apps, software updates, and operating systems; configure sites and clients; and run and monitor management tasks. It supports Windows and macOS. Managed devices can run in virtual environments (Hyper-V on Windows servers, or Azure VMs), and the Configuration Manager client can be installed on an Azure-based server VM.

## 5. Cloud attach: tenant attach and co-management

Cloud attach lets you use both Intune and Configuration Manager from within Intune. There are two steps, and they can be taken incrementally toward full cloud attachment: tenant attach delivers immediate value, and co-management adds extra value.

**Tenant attach** registers the Configuration Manager deployment with the Intune tenant, letting Intune recognize and act on Configuration Manager devices and infrastructure from the cloud. A Configuration Manager connector carries the data flow to Intune; it needs an Intune tenant connection but does **not** require co-management to be enabled.

**Co-management** concurrently manages Windows 10/11 devices with both Configuration Manager and Intune. It combines existing on-premises Configuration Manager and Active Directory investment with the cloud (Intune, Microsoft Entra ID, and Microsoft 365). You choose whether Configuration Manager or Intune is the management authority per workload, so some tasks stay on-premises while others run in the cloud.

Two paths to co-management:

- Existing Windows 10/11 Configuration Manager clients: set up hybrid Microsoft Entra ID and enroll the devices into Intune.
- New cloud-based Windows 10/11 devices: join Microsoft Entra ID and auto-enroll in Intune, then install the Configuration Manager client.

Enrolling existing Configuration Manager clients in co-management immediately gains: Conditional Access with device compliance; Intune-based remote actions such as restart, remote control, and factory reset; centralized device health visibility; Microsoft Entra ID linking users, devices, and apps; and modern provisioning with Windows Autopilot.

## 6. Endpoint analytics

Endpoint analytics give insight into how well the organization works and the quality of experience delivered to users. It identifies configuration or hardware issues that slow devices down, provides recommended actions to fix them, and supports proactive changes that avoid disrupting users or generating help desk tickets. It is part of the Microsoft Adoption Score, which supplies productivity data, insights, and recommendations for user experience and the organization's overall technology experience.

## 7. Windows Autopilot

Windows Autopilot simplifies enrollment by supplying the enrollment details before the user receives a new computer. The Autopilot process runs the first time the computer powers on, and the only user interaction is connecting to a network and verifying credentials; everything else is automated.

Using cloud-based services, Autopilot can: automatically join devices to Microsoft Entra ID; autoenroll devices into MDM services such as Intune; restrict rights on the device; autoassign devices to configuration groups; present customized out-of-box-experience (OOBE) content; and reset, repurpose, and recover devices. The result is less IT time deploying, managing, and retiring devices, less infrastructure to maintain, and maximum ease of use for end users.

## 8. Knowledge check — answers and reasoning

1. Unique feature of co-management in a hybrid environment → **seamless integration of cloud and on-premises management tasks.** Co-management is not mobile-only, and it does not remove on-premises tools; it blends them.
2. How tenant attach differs from co-management → **tenant attach registers devices with Intune without enabling co-management features.** Tenant attach does not require Microsoft Entra enrollment, and co-management is not exclusive to Android and iOS.
3. Keeping app data secure on corporate and personal devices → **apply MAM policies to restrict data sharing within the app.** Unrestricted access and requiring MDM enrollment on all devices both miss the point of protecting data inside apps.
4. Balancing user experience with security → **Conditional Access.** Endpoint Analytics is insight and recommendations; Windows Autopilot is provisioning.
5. Protecting organizational apps on personal devices → **apply MAM policies that control data access within apps.** Blocking personal devices or forcing conversion to corporate ownership is not the mechanism.
6. Why choose co-management over pure Intune → **to leverage existing on-premises investments while gaining cloud benefits.** It is not about avoiding cloud services or managing non-Microsoft devices exclusively.
7. Reducing data-loss risk on work-and-home mobile devices while letting employees use them freely → **implement MAM policies to manage data access and sharing inside applications.** Requiring MDM for any app access or blocking out-of-hours usage does not fit the goal.
8. Reducing deployment time and infrastructure for new devices → **Windows Autopilot.** Endpoint Analytics is insight; co-management is dual management.
9. Component responsible for identity and access control → **Microsoft Entra ID.** Endpoint Analytics and Windows Autopilot do not provide identity.

## 9. Self-check

- I can define an endpoint and name at least four device categories Intune manages.
- I can separate MDM from MAM and explain why BYOD needs MAM.
- I can state what Intune now combines (Intune, Configuration Manager, endpoint analytics, Windows Autopilot) and the "if you have Configuration Manager you have Intune" point.
- I can order cloud attach correctly and say what tenant attach gives you versus what co-management adds, including it is Windows 10/11 and per-workload authority.
- I can describe what Autopilot automates and name the only two user steps.
- I can say where endpoint analytics sits (Adoption Score) and what it produces.
- I can name the three identity/protection integrations: Entra ID, Purview Information Protection, Defender.
