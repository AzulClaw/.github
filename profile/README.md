<p align="center">
  <a href="https://www.azulclaw.com">
    <img width="130" alt="AzulClaw mascot" src="https://raw.githubusercontent.com/AzulClaw/AzulClaw-Core/main/img/azulclaw.png" />
  </a>
</p>

<h1 align="center">AzulClaw</h1>

<p align="center">
  <strong>Enterprise desktop AI assistant for Azure teams.</strong>
  <br />
  Local-first. Governed. Ready to deploy.
</p>

<p align="center">
  <a href="https://www.azulclaw.com">
    <img alt="Website" src="https://img.shields.io/badge/Web-azulclaw.com-38BDF8?style=for-the-badge" />
  </a>
  <a href="https://github.com/AzulClaw/AzulClaw-Core/releases/latest">
    <img alt="Download AzulClaw for Windows" src="https://img.shields.io/badge/Download-Windows%20Installer-0078D4?style=for-the-badge&logo=windows&logoColor=white" />
  </a>
  <a href="https://github.com/AzulClaw/AzulClaw-Core">
    <img alt="AzulClaw Core" src="https://img.shields.io/badge/Core-Local%20Runtime-0F172A?style=for-the-badge" />
  </a>
  <a href="https://github.com/AzulClaw/AzulClaw-Marketplace">
    <img alt="AzulClaw Marketplace" src="https://img.shields.io/badge/Marketplace-Governance%20Hub-2563EB?style=for-the-badge" />
  </a>
</p>

---

<p align="center">
  <a href="https://github.com/AzulClaw/AzulClaw-Core">
    <img alt="AzulClaw Marketplace screenshot" src="https://github.com/AzulClaw/.github/blob/main/img/screenshot_marketplace.png" />
  </a>
</p>

## What is AzulClaw

AzulClaw is a desktop AI assistant for teams working on Azure that need autonomy without losing operational control.

It combines a local runtime, SQLite memory, workspace boundaries, an MCP sandbox, and optional Azure services. The idea is simple: teams can use AI in their day-to-day work without turning every PC into an unrestricted execution target.

The packaged application runs on Windows 10/11, does not require administrator permissions, and includes the Python backend and MCP server.

## Product in use

<table>
  <tr>
    <td width="50%" valign="top">
      <img alt="AzulClaw chat screenshot" src="https://raw.githubusercontent.com/AzulClaw/AzulClaw-Core/main/img/screenshot01.png" />
      <br />
      <strong>Local chat</strong>
      <br />
      Conversations with session context, model state, and local workspace.
    </td>
    <td width="50%" valign="top">
      <img alt="AzulClaw files screenshot" src="https://github.com/AzulClaw/.github/blob/main/img/screenshot_files_03.png" />
      <br />
      <strong>Context and files</strong>
      <br />
      Work with documents and validated paths inside the configured workspace.
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <img alt="AzulClaw heartbeats screenshot" src="https://github.com/AzulClaw/.github/blob/main/img/screenshot_heartbeat01.png?raw=true" />
      <br />
      <strong>Heartbeats</strong>
      <br />
      Scheduled checks, reminders, and workspace routines executed in a controlled way.
    </td>
    <td width="50%" valign="top">
      <img alt="AzulClaw login screenshot" src="https://github.com/AzulClaw/.github/blob/main/img/screenshot_login.png?raw=true" />
      <br />
      <strong>Azure sign-in</strong>
      <br />
      Sign-in managed through Microsoft Entra ID without exposing secrets in regular local files.
    </td>
  </tr>
</table>

## Main projects

<table>
  <tr>
    <td width="50%" valign="top">
      <h3>AzulClaw Core</h3>
      <p>
        Desktop application with a Tauri + React UI, Python backend,
        local memory, scheduler, Bot Framework adapter, MCP client, and filesystem sandbox.
      </p>
      <p>
        <a href="https://github.com/AzulClaw/AzulClaw-Core"><strong>Repository</strong></a>
        |
        <a href="https://github.com/AzulClaw/AzulClaw-Core/tree/main/docs"><strong>Docs</strong></a>
        |
        <a href="https://github.com/AzulClaw/AzulClaw-Core/releases/latest"><strong>Releases</strong></a>
      </p>
    </td>
    <td width="50%" valign="top">
      <h3>AzulClaw Marketplace</h3>
      <p>
        Control plane to publish, certify, approve, distribute, and revoke
        skills before they reach users or production environments.
      </p>
      <p>
        <a href="https://github.com/AzulClaw/AzulClaw-Marketplace"><strong>Repository</strong></a>
        |
        <a href="https://github.com/AzulClaw/AzulClaw-Marketplace/tree/main/docs"><strong>Docs</strong></a>
        |
        <a href="https://github.com/AzulClaw/AzulClaw-Marketplace/tree/main/portal"><strong>Portal</strong></a>
      </p>
    </td>
  </tr>
</table>

## Why it exists

- **Local runtime.** Conversations, preferences, embeddings, and search indexes live in SQLite on the device.
- **MCP isolation.** File operations go through a separate MCP server and validate paths against the workspace.
- **Azure-native identity.** Microsoft Entra ID is the preferred path for Azure OpenAI; Key Vault keeps secrets out of local files.
- **Governed skills.** Employees install approved capabilities locally; IT controls publishing, versioning, approval, and revocation.
- **Azure relay channels.** Telegram is the current first-party connector; Bot Service, Functions, and Service Bus enable external channels without exposing the local runtime as a public webhook.

## Architecture

```text
AzulClaw Desktop
  |
  +-- Tauri + React UI
  +-- Local orchestration runtime
  +-- SQLite memory and search
  +-- Heartbeats scheduler
  +-- MCP filesystem sandbox
  |
  +-- Optional Azure services
      +-- Azure OpenAI
      +-- Microsoft Entra ID
      +-- Azure Key Vault
      +-- Azure Bot Service
      +-- Azure Functions
      +-- Azure Service Bus
```

## First-party skills

- Desktop Organizer: organizes folders through a local MCP tool.
- Gemini: connects AzulClaw to a remote agent or compatible endpoint.
- Telegram: connects AzulClaw to Telegram through the Azure Bot relay pattern.

## Get started

- Application website: <https://www.azulclaw.com>
- Download AzulClaw for Windows: <https://github.com/AzulClaw/AzulClaw-Core/releases/latest>
- Core documentation: <https://github.com/AzulClaw/AzulClaw-Core/tree/main/docs>
- Marketplace and governance hub: <https://github.com/AzulClaw/AzulClaw-Marketplace>
- Skills model: <https://github.com/AzulClaw/AzulClaw-Core/tree/main/skills>

---

<p align="center">
  <strong>AzulClaw brings AI autonomy to Azure teams without giving up local control.</strong>
</p>
