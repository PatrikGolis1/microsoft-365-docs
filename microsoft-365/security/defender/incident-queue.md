---
title: Prioritize incidents in Microsoft 365 Defender
description: Learn how to filter incidents from the incident queue in Microsoft 365 Defender
keywords: incident, queue, overview, devices, identities, users, mailbox, email, incidents, analyze, response, triage
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords: 
  - NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: 
  - M365-security-compliance
  - m365initiative-m365-defender
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid: 
  - MOE150
  - MET150
ms.technology: m365d
---

# Prioritize incidents in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Applies to:**
- Microsoft 365 Defender

Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident. Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products. This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.

The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes. It helps you sort through incidents to prioritize and create an informed cybersecurity response decision. This is also known as incident triage.

You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender portal</a>. Here's an example.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Example of the incident queue." lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::

The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.

By default, the incident queue in the Microsoft 365 Defender portal displays incidents seen in the last six months. The most recent incident is at the top of the list so you can see it first.

The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities. This helps you make an informed decision regarding the prioritization of incidents for analysis.

For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories. This allows you to quickly understand the scope of the incident.

For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*

> [!NOTE]
> Incidents that existed prior the rollout of automatic incident naming will not have their name changed.

The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat. Applying filters on the incident queue can help determine which incident requires immediate attention. 

## Available filters

From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents. Here is an example.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Example of the filters pane for the incident queue." lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

The default filter is to show all alerts and incidents with a **New** and **In progress** status.

This table lists the filter names that are available.

| Filter name | Description |
|:-------|:-----|
| Status | Select **New**, **In progress**, or **Resolved**. |
| Severity | The severity of an incident is indicative of the impact it can have on your assets. The higher the severity, the bigger the impact and typically requires the most immediate attention. Select **High**, **Medium**, **Low**, or **Informational**. |
| Incident assignment | Select Assigned to anyone, Assigned to me, or Unassigned. |
| Multiple service sources  | Specify whether the filter is for more than one service source. |
| Service sources  | Filter to only see incidents that contain alerts from: App Governance, Microsoft 365 Defender, Microsoft Defender for Office 365, Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Cloud Apps. |
| Tags | Select one or multiple tag names from the list. |
| Multiple categories  | Specify whether the filter is for more than one category. |
| Categories | Choose categories to focus on specific tactics, techniques, or attack components seen. |
| OS platform | Limit the incident queue view by operating system. |
| Classification | Filter incidents based on the set classifications of the related alerts. Select **True alert**, **False alerts**, or **Not set**. |
| Investigation state | Filter incidents by the status of automated investigation.  |
| Associated threat | Filter incidents by a named threat.  |
| Actors | Filter incidents by a named threat actor.  |
| Data sensitivity | Some attacks focus on targeting to exfiltrate sensitive or valuable data. By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents. <br><br>This filter is only available if Microsoft Information Protection is turned on.|
|||

## Save defined filters as URLs

Once you have configured a useful filter in the incidents queue, you can bookmark the URL of the browser tab or otherwise save it as a link on a Web page, a Word document, or a place of your choice. This will give you single-click access to key views of the incident queue, such as:

- New incidents
- High-severity incidents
- Unassigned incidents
- High-severity, unassigned incidents
- Incidents assigned to me
- Incidents assigned to me and for Microsoft Defender for Endpoint
- Incidents with a specific tag or tags
- Incidents with a specific threat category
- Incidents with a specific associated threat
- Incidents with a specific actor

Once you have compiled and stored your list of useful filter views as URLs, you can use it to quickly process and prioritize the incidents in your queue and [manage](manage-incidents.md) them for subsequent assignment and analysis.

## Next steps

After you've determined which incident requires the highest priority, select it and:

- [Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.
- Begin your [investigations](investigate-incidents.md).

## See also
- [Incidents overview](incidents-overview.md)
- [Manage incidents](manage-incidents.md)
- [Investigate incidents](investigate-incidents.md)
