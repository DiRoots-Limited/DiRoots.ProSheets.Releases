---
layout: default
title: "[Beta] Connect AI apps - MCP"
parent: ProSheets
nav_order: 5
nav_sections:
  - title: "Requirements"
    anchor: requirements
  - title: "Connect an AI app"
    anchor: connect-an-ai-app
  - title: "Your data"
    anchor: your-data
  - title: "For IT administrators"
    anchor: for-it-administrators
---

# [Beta] Connect AI apps - MCP
{: .no_toc }

Through MCP (Model Context Protocol), you can connect an AI app such as Claude or ChatGPT to ProSheets. In your own words, ask it to find, export, or schedule exports of sheets and views in the open Revit model. For example: "Export sheets A101 and A102 to PDF". Before running a plan, review the selected sheets and views, the destination, and any warnings about overwrites, uploads, or schedules. Keep approval prompts enabled in your AI app where available.

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Requirements

- Revit 2025 or later.
- Claude (the desktop app or Claude Code), the ChatGPT desktop app or Codex CLI, on the same PC. In the ChatGPT desktop app, use ProSheets in Work mode. ChatGPT in a browser cannot use ProSheets.
- Scheduled exports need a ProSheets Premium subscription.

## Connect an AI app

Before connecting, check [what project information your AI app can read](#your-data).

1. In Revit, go to File > Options and open the DiRoots tab. If the "Connect to AI apps" message appears the first time you open ProSheets, its Open Revit Options button takes you there.
2. Under Connect AI apps - MCP, turn on Claude or ChatGPT/Codex.
3. Click OK to keep the change. Cancel, or closing Options with the X, undoes it.
4. Start a new session in Claude Code or Codex CLI. If Claude Desktop is running, quit it fully, including from the notification area, and reopen it. A note under Claude reminds you. ProSheets makes the change once Claude Desktop is closed. If ProSheets is missing in the ChatGPT desktop app, reopen the app.
5. Open your model in Revit and ask the AI app what to export.

To disconnect an app, turn it off in the same place.

An app that ProSheets cannot find on your PC shows "Not installed". If the toggles are greyed out with "Turned off by your administrator.", contact your IT department.

## Your data

The connection between ProSheets and the AI app runs on your PC. Your connected AI app can read project information such as model names, sheet numbers, sheet names, and revisions before you approve an export. The app may send that information to its AI provider. Check your provider’s data policy and account settings, and follow your organization’s rules for sharing project information.

## For IT administrators

To turn the feature off, set the DWORD `AllowMcp` to `0` under `HKLM\SOFTWARE\Policies\DiRoots\ProSheets`, for example through Group Policy or Intune. ProSheets then refuses requests from AI apps and removes its entries from them at the next Revit start. Removing the value does not bring removed entries back: users turn the apps on again in Revit Options, and a Revit that was started while the value was set needs a restart.
