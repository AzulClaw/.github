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
    <img alt="AzulClaw Marketplace screenshot" src="https://raw.githubusercontent.com/AzulClaw/AzulClaw-Core/main/img/screenshot_marketplace.png" />
  </a>
</p>

## Qu&eacute; es AzulClaw

AzulClaw es un asistente de IA de escritorio para equipos que trabajan en Azure y necesitan autonom&iacute;a sin perder control operativo.

Combina runtime local, memoria SQLite, l&iacute;mites de workspace, sandbox MCP y servicios Azure opcionales. La idea es simple: que los equipos puedan usar IA en su d&iacute;a a d&iacute;a sin convertir cada PC en un objetivo de ejecuci&oacute;n sin restricciones.

La aplicaci&oacute;n empaquetada funciona en Windows 10/11, no requiere permisos de administrador y trae incluido el backend Python y el servidor MCP.

## Producto en uso

<table>
  <tr>
    <td width="50%" valign="top">
      <img alt="AzulClaw chat screenshot" src="https://raw.githubusercontent.com/AzulClaw/AzulClaw-Core/main/img/screenshot01.png" />
      <br />
      <strong>Chat local</strong>
      <br />
      Conversaciones con contexto de sesi&oacute;n, estado del modelo y workspace local.
    </td>
    <td width="50%" valign="top">
      <img alt="AzulClaw files screenshot" src="https://raw.githubusercontent.com/AzulClaw/AzulClaw-Core/main/img/screenshot_files_01.png" />
      <br />
      <strong>Context y archivos</strong>
      <br />
      Trabajo con documentos y rutas validadas dentro del workspace configurado.
    </td>
  </tr>
  <tr>
    <td width="50%" valign="top">
      <img alt="AzulClaw heartbeats screenshot" src="https://raw.githubusercontent.com/AzulClaw/AzulClaw-Core/main/img/screenshot_heartbeat01.png" />
      <br />
      <strong>Heartbeats</strong>
      <br />
      Checks programados, recordatorios y rutinas de workspace ejecutadas de forma controlada.
    </td>
    <td width="50%" valign="top">
      <img alt="AzulClaw login screenshot" src="https://raw.githubusercontent.com/AzulClaw/AzulClaw-Core/main/img/screenshot_login.png" />
      <br />
      <strong>Azure sign-in</strong>
      <br />
      Inicio de sesi&oacute;n gestionado con Microsoft Entra ID sin exponer secretos en archivos locales ordinarios.
    </td>
  </tr>
</table>

## Proyectos principales

<table>
  <tr>
    <td width="50%" valign="top">
      <h3>AzulClaw Core</h3>
      <p>
        Aplicaci&oacute;n desktop con UI Tauri + React, backend Python,
        memoria local, scheduler, Bot Framework adapter, cliente MCP y sandbox de filesystem.
      </p>
      <p>
        <a href="https://github.com/AzulClaw/AzulClaw-Core"><strong>Repositorio</strong></a>
        |
        <a href="https://github.com/AzulClaw/AzulClaw-Core/tree/main/docs"><strong>Docs</strong></a>
        |
        <a href="https://github.com/AzulClaw/AzulClaw-Core/releases/latest"><strong>Releases</strong></a>
      </p>
    </td>
    <td width="50%" valign="top">
      <h3>AzulClaw Marketplace</h3>
      <p>
        Plano de control para publicar, certificar, aprobar, distribuir y revocar
        skills antes de que lleguen a usuarios o entornos de producci&oacute;n.
      </p>
      <p>
        <a href="https://github.com/AzulClaw/AzulClaw-Marketplace"><strong>Repositorio</strong></a>
        |
        <a href="https://github.com/AzulClaw/AzulClaw-Marketplace/tree/main/docs"><strong>Docs</strong></a>
        |
        <a href="https://github.com/AzulClaw/AzulClaw-Marketplace/tree/main/portal"><strong>Portal</strong></a>
      </p>
    </td>
  </tr>
</table>

## Por qu&eacute; existe

- **Runtime local.** Conversaciones, preferencias, embeddings e &iacute;ndices de b&uacute;squeda viven en SQLite en el dispositivo.
- **Aislamiento MCP.** Las operaciones de archivo pasan por un servidor MCP separado y validan rutas contra el workspace.
- **Identidad Azure-native.** Microsoft Entra ID es la ruta preferida para Azure OpenAI; Key Vault permite mantener secretos fuera de archivos locales.
- **Skills gobernadas.** Los empleados instalan capacidades aprobadas localmente; IT controla publicaci&oacute;n, versionado, aprobaci&oacute;n y revocaci&oacute;n.
- **Canales con relay Azure.** Telegram es el conector first-party actual; Bot Service, Functions y Service Bus permiten canales externos sin exponer el runtime local como webhook p&uacute;blico.

## Arquitectura

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

## Skills first-party

- Desktop Organizer: organiza carpetas a trav&eacute;s de una herramienta MCP local.
- Gemini: conecta AzulClaw con un agente remoto o endpoint compatible.
- Telegram: conecta AzulClaw a Telegram mediante el patr&oacute;n Azure Bot relay.

## Empezar

- Web de la aplicaci&oacute;n: <https://www.azulclaw.com>
- Descargar AzulClaw para Windows: <https://github.com/AzulClaw/AzulClaw-Core/releases/latest>
- Documentaci&oacute;n de Core: <https://github.com/AzulClaw/AzulClaw-Core/tree/main/docs>
- Marketplace y governance hub: <https://github.com/AzulClaw/AzulClaw-Marketplace>
- Modelo de skills: <https://github.com/AzulClaw/AzulClaw-Core/tree/main/skills>

---

<p align="center">
  <strong>AzulClaw brings AI autonomy to Azure teams without giving up local control.</strong>
</p>
