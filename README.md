# BzH-Punish

### Advanced Punishment & Moderation System for Minecraft Servers

**Take control of moderation with BzH-Punish!**

BzH-Punish is a Minecraft server moderation plugin designed to help staff teams manage punishments, review player histories, organize punishment templates, and maintain a consistent moderation workflow.

Featuring configurable storage options, moderation commands, and a Java API, BzH-Punish brings essential punishment tools together in one plugin.

---

## 📑 Table of Contents

- [Features](#-features)
- [Requirements](#-requirements)
- [Installation](#-installation)
- [Configuration](#️-configuration)
- [Commands](#-commands)
- [Permissions](#-permissions)
- [Storage Setup](#️-storage-setup)
- [Multi-Server Setup](#-multi-server-setup)
- [Developer Information](#-developer-information)
- [Support and Bug Reports](#-support-and-bug-reports)
- [Credits](#-credits)

---

## ✨ Features

### ⚖️ Punishment Management

- Ban and temporary ban management.
- Mute and temporary mute management.
- Player warnings and warning removal.
- Kick players with a specified reason.
- IP bans and IP mutes.
- Unban, unmute, IP unban, and IP unmute tools.
- Punishment removal utilities.

### 📋 Punishment Templates

- Create reusable punishment templates.
- List available templates.
- View template details.
- Apply templates to players.
- Delete and reload templates.
- Manage template-related permissions.

### 📚 Punishment History

- View player punishment histories.
- Navigate history using pages.
- Configure default and maximum history page sizes.
- Clear player histories with appropriate permissions.

### ❄️ Player Freeze Tools

- Freeze players during investigations.
- Support duration-based or permanent freezes where configured.
- Unfreeze players when an investigation is complete.

### 🗄️ Flexible Data Storage

- SQLite storage for straightforward single-server setups.
- MySQL storage as an alternative backend.
- Optional synchronization for supported punishment states across servers using a shared MySQL database.

### 🛡️ Security and Staff Tools

- Security monitoring and staff notifications.
- Configurable security logging and monitoring thresholds.
- IP whitelist management through security commands.
- Configurable punishment broadcasts.
- Configuration reload commands.

### 🔌 Developer API

- Java API for punishment-related integrations.
- Custom punishment and unpunishment events.
- Extensibility for developers integrating moderation features into other plugins.

---

## 📦 Requirements

- Java 17 or a compatible newer Java runtime.
- A Minecraft server version compatible with the plugin's API requirements.
- Built against Paper API 1.20.6.

> **Compatibility Notice:** The current project targets Paper API 1.20.6. Compatibility with other Minecraft versions and server implementations should be verified before use.

---

## 🚀 Installation

1. Download the latest BzH-Punish JAR from the project's [Releases](../../releases) page.
2. Stop your Minecraft server.
3. Place the JAR file inside your server's `plugins` directory.
4. Start the server.
5. Open `plugins/BzH-Punish/config.yml`.
6. Review the configuration and select your preferred storage backend.
7. Configure staff permissions using your permissions management plugin.
8. Test the commands and verify the console output.

Always back up your server and test new releases before deploying them on a production server.

---

## ⚙️ Configuration

BzH-Punish provides configurable settings for its moderation and storage systems.

Depending on the selected features, settings include:

- Storage backend selection: SQLite or MySQL.
- Punishment broadcast settings.
- Ban-related player handling.
- Warning notifications.
- Command cooldowns.
- History pagination limits.
- Date and time formatting.
- Automatic cleanup settings.
- Security monitoring and staff notifications.
- Optional multi-server synchronization.

Review the generated configuration files for the exact available options and default values. Back up your configuration before making changes.

---

## 🧭 Commands

The main command is `/bpunish`.

| Command | Description |
|---|---|
| `/bpunish` | Display available commands |
| `/bpunish ban <player> <time> <reason>` | Ban a player |
| `/bpunish mute <player> <time> <reason>` | Mute a player |
| `/bpunish warn <player> <reason>` | Warn a player |
| `/bpunish kick <player> <reason>` | Kick a player |
| `/bpunish ipban <player> <time> <reason>` | Apply an IP ban |
| `/bpunish ipmute <player> <time> <reason>` | Apply an IP mute |
| `/bpunish unban <player>` | Remove a ban |
| `/bpunish unmute <player>` | Remove a mute |
| `/bpunish unwarn <player> [amount]` | Remove warnings |
| `/bpunish ipunban <ip\|player>` | Remove an IP ban |
| `/bpunish ipunmute <ip>` | Remove an IP mute |
| `/bpunish history <player> [page]` | View punishment history |
| `/bpunish clearhistory <player>` | Clear punishment history |
| `/bpunish unpunish <player> <template>` | Remove a supported punishment |
| `/bpunish freeze <player> [duration\|perm] [reason]` | Freeze a player |
| `/bpunish unfreeze <player>` | Unfreeze a player |
| `/bpunish reload` | Reload configuration |
| `/bpunish security` | Access security tools |
| `/bpunish template` | Access template tools |

Standalone aliases may also be available, including `/ban`, `/mute`, `/warn`, `/kick`, `/history`, `/unban`, `/unmute`, `/freeze`, and `/unfreeze`.

> **Important:** Consult in-game help and tab completion for the exact syntax supported by your installed version.

---

## 🔐 Permissions

The plugin uses the `bzhpunish.*` permission namespace.

| Permission | Purpose |
|---|---|
| `bzhpunish.*` | Main permission wildcard |
| `bzhpunish.ban` | Ban players |
| `bzhpunish.mute` | Mute players |
| `bzhpunish.warn` | Warn players |
| `bzhpunish.kick` | Kick players |
| `bzhpunish.ipban` | Apply IP bans |
| `bzhpunish.ipmute` | Apply IP mutes |
| `bzhpunish.unban` | Remove bans |
| `bzhpunish.unmute` | Remove mutes |
| `bzhpunish.unwarn` | Remove warnings |
| `bzhpunish.ipunban` | Remove IP bans |
| `bzhpunish.ipunmute` | Remove IP mutes |
| `bzhpunish.unpunish` | Remove supported punishments |
| `bzhpunish.history` | View player histories |
| `bzhpunish.clearhistory` | Clear player histories |
| `bzhpunish.reload` | Reload configuration |
| `bzhpunish.freeze` | Freeze players |
| `bzhpunish.unfreeze` | Unfreeze players |
| `bzhpunish.template.create` | Create templates |
| `bzhpunish.template.delete` | Delete templates |
| `bzhpunish.template.list` | List templates |
| `bzhpunish.template.info` | View template details |
| `bzhpunish.template.reload` | Reload templates |
| `bzhpunish.security` | Access security commands |
| `bzhpunish.security.notify` | Receive security notifications |
| `bzhpunish.notify` | Receive punishment broadcasts |
| `bzhpunish.admin` | Administrative access |
| `bzhpunish.template.*` | Template permission wildcard |
| `bzhpunish.unpunish.template.*` | Template-based unpunish wildcard |

Review `plugin.yml` and the command implementation to verify every permission, wildcard, and default before assigning staff roles.

---

## 🗄️ Storage Setup

### SQLite

SQLite is intended for a straightforward single-server setup.

Use the generated configuration as the source of truth for the available options and default database filename.

### MySQL

To use MySQL:

1. Create a database and a dedicated database user.
2. Configure the connection details in the generated configuration.
3. Ensure the database server is reachable from the Minecraft server.
4. Restart the server and verify successful database initialization.
5. Test persistence by restarting the server and checking punishment records.

Never publish database passwords or other private credentials.

---

## 🌐 Multi-Server Setup

BzH-Punish includes an optional synchronization setting intended for supported multi-server deployments using a shared MySQL database.

Before enabling it:

1. Configure each backend to use the intended shared database.
2. Verify connectivity and database permissions.
3. Review the synchronization settings.
4. Test punishment creation and removal across all participating servers.
5. Monitor the console for database and synchronization errors.

Do not assume every plugin state or action is synchronized unless it has been verified.

---

## 🧑‍💻 Developer Information

BzH-Punish includes Java API components and punishment-related custom events.

The project contains the following API/event classes:

- `BzHPunishAPI`
- `PlayerPunishEvent`
- `PlayerUnpunishEvent`

Consult the source code for exact method signatures, event properties, and integration instructions.

---

## 🐛 Support and Bug Reports

When reporting a bug, include:

- Minecraft server software and version.
- Java version.
- BzH-Punish version.
- Relevant console errors or stack traces.
- Steps to reproduce the issue.
- Relevant configuration with passwords and other secrets removed.

Please provide clear reproduction steps to help identify and resolve problems efficiently.

---

## ❤️ Credits

Developed by **BzH-Community**.

Thank you for checking out BzH-Punish! Feedback, bug reports, and suggestions are welcome.
