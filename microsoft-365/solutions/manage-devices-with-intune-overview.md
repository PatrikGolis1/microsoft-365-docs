---
title: "Manage devices with Intune"
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: dougeby
audience: ITPro
ms.topic: article
description: Enroll your endpoint devices in Microsoft Intune as part of your Zero Trust security architecture, protecting against ransomware while building in protection for remote workers. 
ms.prod: microsoft-365-enterprise
ms.localizationpriority: high
ms.collection:
- enroll devices into Intune
- manage device endpoints
- zero trust deployment stack
- device management with zero trust
ms.custom: 
keywords: 
---

# Manage devices with Intune Overview

A core component of enterprise-level security includes managing and protecting devices. Whether you’re building a Zero Trust security architecture, hardening your environment against ransomware, or building in protections to support remote workers, managing devices is part of the strategy. 
While Microsoft 365 includes several tools and methodologies for managing and protecting devices, this guidance walks through Microsoft’s recommendations using Microsoft Intune. This is the right guidance for you if you:

- Plan to enroll devices into Intune through Azure AD Join (including Hybrid Azure AD Join).
- Plan to manually enroll devices into Intune.
- Allow BYOD devices with plans to implement protection for apps and data and/or enroll these devices into management.

On the other hand, if your environment includes plans for co-management including Microsoft Endpoint Configuration Manager, see [Co-management documentation](/mem/configmgr/comanage/) to develop the best path for your organization. If your environment includes plans for Windows 365 Cloud PC, see [Windows 365 Enterprise documentation](/windows-365/enterprise/) to develop the best path for your organization. 

## Why manage endpoints?
The modern enterprise has an incredible diversity of endpoints accessing their data. This setup creates a massive attack surface, and as a result, endpoints can easily become the weakest link in your Zero Trust security strategy. 

Mostly driven by necessity as the world shifted to a remote or hybrid work model, users are working from anywhere, from any device, more than anytime in history. Attackers are quickly adjusting their tactics to take advantage of this change. Many organizations face constrained resources as they navigate these new business challenges. Virtually overnight, companies have accelerated digital transformation. Simply stated, the way people work has changed — we no longer expect to access the myriad of corporate resources only from the office and on company-owned devices.

Gaining visibility into the endpoints accessing your corporate resources is the first step in your Zero Trust device strategy. Typically, companies are proactive in protecting PCs from vulnerabilities and attack while mobile devices often go unmonitored and without protections. To ensure you’re not exposing your data to risk, we need to monitor every endpoint for risks and employ granular access controls to deliver the appropriate level of access based on organizational policy. For example, if a personal device is jailbroken, you can block access to ensure that enterprise applications are not exposed to known vulnerabilities.

This series of articles walks through a recommended process for managing devices that access your resources. If you follow the recommended steps, your organization will achieve very sophisticated protection for your devices and the resources they access.


## Implementing the layers of protection on and for devices

Protecting the data and apps on devices and the devices themselves is a multi-layer process. There are some protections you can gain on unmanaged devices. After enrolling devices into management, you can implement more sophisticated controls. When threat protection is deployed across your endpoints, you gain even more insights and the ability to automatically remediate some attacks. Finally, if your organization has put the work into identifying sensitive data, applying classification and labels, and configuring data loss prevention policies, you can obtain even more granular protection for data on your endpoints.

The following diagram illustrates building blocks to achieve a Zero Trust security posture for Microsoft 365 and other SaaS apps that you introduce to this environment. The elements related to devices are numbered 1 through 7. These are the layers of protection device administers will coordinate with other administrators to accomplish. 

![Microsoft 365 Zero Trust deployment stack](../media/devices/m365-zero-trust-deployment-stack-devices.png#lightbox)

In this illustration: 


|&nbsp;|Step |Description  |Licensing requirements  |
|---------|---------|---------|---------|
|1     | Configure starting-point Zero Trust identity and device access policies       | Work with your identity administrator to [Implement Level 2 App Protection Policies (APP) data protection](manage-devices-with-intune-app-protection.md). These policies do not require that you manage devices. You configure the APP policies in Intune. Your identity admin configures a Conditional Access policy to require approved apps.          |E3, E5, F1, F3, F5    |
|2     | Enroll devices into management       | This task requires more planning and time to implement. While you have a choice of tools and methods to accomplish this, [Step 3—Enroll devices into management](manage-devices-with-intune-enroll.md) guides you through the process using Intune with Autopilot and automated enrollment.      | E3, E5, F1, F3, F5        |
|3     | Configure compliance policies        |  You want to be sure devices that are accessing your apps and data meet minimum requirements, for example they’re password or pin-protected and the operating system is up to date. Compliance policies are the way to define the requirements that devices must meet. [Step 3. Set up compliance policies](manage-devices-with-intune-compliance-policies.md) helps you configure these policies.        |   E3, E5, F3, F5      |
|4     | Configure Enterprise (recommended) Zero Trust identity and device access policies        |Now that your devices are enrolled, you can work with your identity admin to [tune Conditional Access policies to require healthy and compliant devices](manage-devices-with-intune-require-compliance.md).          | E3, E5, F3, F5        |
|5     |Deploy configuration profiles      | As opposed to device compliance policies that simply mark a device as compliant or not based on criteria you configure, configuration profiles actually change the configuration of settings on a device. You can use configuration policies to harden devices against cyberthreats. See [Step 5. Deploy configuration profiles](manage-devices-with-intune-configuration-profiles.md).        | E3, E5, F3, F5        |
|6     |Monitor device risk and compliance to security baselines         | In this step, you connect Intune to Microsoft Defender for Endpoint. With this integration, you can then monitor device risk as a condition for access. Devices that are found to be in a risky state will be blocked. You can also monitor compliance to security baselines. See [Step 6. Monitor device risk and compliance to security baselines](manage-devices-with-intune-monitor-risk.md).       | E5, F5        |
|7     |Implement data loss prevention (DLP) with information protection capabilities   | If your organization has put the work into identifying sensitive data and labeling documents, you can work with your information protection admin to [protect sensitive information and documents on your devices](manage-devices-with-intune-dlp-mip.md).         | E5, F5 compliance add on        |
| | | | |

## Coordinating endpoint management with Zero Trust identity and device access policies

This guidance is tightly coordinated with the recommended [Zero Trust identity and device access policies](../security/office-365-security/microsoft-365-policies-configurations.md). You will be working with your identity team to carry through protection that you configure with Intune into Conditional Access policies in Azure AD. 

Here’s an illustration of the recommended policy set with step callouts for the work you will do in Intune/MEM and the related Conditional Access policies you will help coordinate in Azure AD. 

[![Zero Trust identity and device access policies](../media/devices/identity-device-overview-steps.png#lightbox)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/devices/identity-device-overview-steps.png)


In this illustration:
- In Step 1, [Implement Level 2 App Protection Policies (APP)](manage-devices-with-intune-app-protection.md) you configure the recommended level of data protection with APP policies. Then you work with your identity team to configure the related Conditional Access rule to require use of this protection.
- In Steps 2, 3 and 4, you enroll devices into management with Intune/MEM, define device compliance policies, and then coordinate with your identity team to configure the related Conditional Access rule to only allow access to compliant devices. 

<!---
## Managing change with users
--->

## Learning for administrators
The following resources help administrators learn concepts about using MEM and Intune.

[Simplify device management with Microsoft Endpoint Manager](/learn/modules/simplify-device-management-with-microsoft-endpoint-manager/)
Description: Learn about modern management and the Microsoft Endpoint Manager and how the business management tools in Microsoft 365 can simplify management of all your devices.

[Set up Microsoft Intune](/learn/modules/set-up-microsoft-intune/)
Description: Microsoft Intune, which is a part of Microsoft Endpoint Manager, helps you protect the devices, apps, and data that the people at your organization use to be productive. After completing this module, you will have set up Microsoft Intune. Set up includes reviewing the supported configurations, signing up for Intune, adding users and groups, assigning licenses to users, granting admin permissions, and setting the MDM authority.
