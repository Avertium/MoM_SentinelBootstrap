# Microsoft Sentinel All-in-One

Avertium's Fork of Azure's Microsoft All-in-one V2 template is aimed at helping Avertium Engineers quickly create a full Microsoft Sentinel environment, speeding up deployment and configuration tasks with a quick and intuitive wizard, saving time and simplifying setup.

A link to the original repo and template is <a href="https://github.com/Azure/Azure-Sentinel/tree/master/Tools/Sentinel-All-In-One">here</a>.

## What does All-in-One do?

Microsoft Sentinel All-in-One automates the following tasks:

- Creates resource group
- Creates Log Analytics workspace
- Installs Microsoft Sentinel on top of the workspace
- Sets workspace retention, daily cap and commitment tiers if desired
- Enables UEBA with the relevant identity providers (AAD and/or AD)
- Enables health diagnostics for Analytics Rules, Data Connectors and Automation Rules
- Installs Content Hub solutions from a predefined list in three categories: 1st party, Essentials and Training
- Enables Data Connectors from this list:
    + Azure Active Directory (with the ability to select which data types will be ingested)
    + Azure Active Directory Identity Protection
    + Azure Activity (from current subscription)
    + Dynamics 365
    + Microsoft 365 Defender
    + Microsoft Defender for Cloud
    + Microsoft Insider Risk Management
    + Microsoft Power BI
    + Microsoft Project
    + Office 365
    + Threat Intelligence Platforms
    + ✨FusionEngine LogRhythm (Creates Custom Table and Data Collection Rule and Endpoint)
    + ✨FusionEngine SentinelOne (Creates Custom Table and Data Collection Rule and Endpoint)
- Enables analytics rules (Scheduled and NRT) included in the selected Content Hub solutions, with the ability to filter by severity
- Enables analytics rules (Scheduled and NRT) that use any of the selected Data connectors, with the ability to filter by severity
- ✨Connects to an Azure lighthouse

✨ Denotes customizations made in this fork of the All-in-One template

## Prerequisites

- Azure Subscription
- Azure user account with enough permissions to enable the desired connectors. See table at the end of this page for additional permissions. Write permissions to the workspace are **always** needed.
- Some data connectors require the relevant licence in order to be enabled. See table at the end of this page for details.

## Try it now!

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAvertium%2FMoM_SentinelBootstrap%2Fmaster%2Fazuredeploy.json/createUIDefinitionUri/https%3A%2F%2Fraw.githubusercontent.com%2FAvertium%2FMoM_SentinelBootstrap%2Fmaster%2FcreateUiDefinition.json" target="_blank">
    <img src="https://aka.ms/deploytoazurebutton""/>
</a>

## Supported connectors

The following table summarizes permissions, licenses and permissions needed and related cost to enable each Data Connector:

| Data Connector                                 | License         |  Permissions                    | Cost      |
| ---------------------------------------------- | --------------- |---------------------------------|-----------|
| Azure Active Directory (Tenant scope version only) | Any AAD license | Global Admin or Security Admin  | Billed    |
| Azure Active Directory Identity Protection  | AAD Premium 2   | Global Admin or Security Admin  | Free      |
| Azure Activity                                 | None            | Subscription Reader             | Free      |
| Dynamics 365                                   | D365 license    | Global Admin or Security Admin  | Billed    |
| Microsoft 365 Defender                         | M365D license   | Global Admin or Security Admin  | Free      |
| Microsoft Defender for Cloud                   | MDC license     | Security Reader                 | Free      |
| Microsoft Insider Risk Management              | IRM license     | Global Admin or Security Admin  | Free      |
| Microsoft PowerBi                              | PowerBi license | Global Admin or Security Admin  | Billed    |
| Microsoft Project                              | MS Project license | Global Admin or Security Admin | Billed  |
| Office 365                                     | None            | Global Admin or Security Admin  | Free      |
| Threat Intelligence Platforms                  | None            | Global Admin or Security Admin  | Billed    |
| FusionEngine LogRhythm                         | None            |                                 | Free      |
| FusionEngine SentinelOne                       | None            |                                 | Free      |
