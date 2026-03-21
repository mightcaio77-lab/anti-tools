# Anti Tools

![Views](https://komarev.com/ghpvc/?username=Felix2CN&label=Views&color=blue&style=flat)

**Antigravity Account Management, Automation & Remote Control Extension**

Anti Tools is a VS Code extension developed for Antigravity AI IDE, providing multi-account switching, quota monitoring, scheduled wake-up, CDP automation, AI Chat, Telegram Bot remote control, Guardian daemon, and full **multi-language support** (English / Chinese).

- 🏪 **OpenVSX**: [open-vsx.org/extension/Felix2CN/anti-tools](https://open-vsx.org/extension/Felix2CN/anti-tools)
- 📦 **Manual**: Download latest `.vsix` from [Releases](https://github.com/Felix2G/anti-tools/releases) → `Extensions: Install from VSIX...`

---

## 🌟 Core Features

### 🔐 Intelligent Account & Schedule Management
- **Direct Switching in IDE**: Instant account switching via database injection with dual-insurance architecture (pre-exit injection + post-startup fallback).
- **Real-time Quota Monitoring**: Sidebar quota panel, low-quota warnings, status bar tooltips.
- **Schedule Visualization**: Automatic quota recovery timelines based on reset times and active windows.
- **Auto Wake-up**: Automated requests at predicted refresh points; fuzzy model matching.
- **Device Fingerprint Management**: Built-in Device Profile binding and randomization.

### 📱 Telegram Bot Remote Control
- **Agent Interaction**: Send messages to Agent, view replies, stop generation directly from Telegram.
- **Tool Activity Display**: Real-time tool operations (commands, file edits, code analysis) in Agent replies.
- **Model Management**: List, switch models with quota percentage and color indicators.
- **Remote Monitoring**: IDE startup notifications, screenshots, running status.
- **Session Export**: Auto-export last session `.md` on startup; `/export` for on-demand extraction.
- **Remote Boot**: Wake up IDE via Guardian `/boot` even when IDE is closed.
- **Scheduled Tasks**: Cron-based task management with multi-model concurrent wake-up.
- **Remote Terminal**: `/cmd` for shell commands, `/file_get` to retrieve files (requires unlock).

### 🤖 High-performance Auto-Accept (CDP)
- **Deep CDP Injection**: Penetrates Shadow DOM and Iframes for millisecond-level automated clicking.
- **Auto-Open Agent Chat**: Automatically opens Agent Chat if detected as closed.
- **Auto-Model Detection**: Real-time model reading and switching via CDP.
- **Security Guard**: Built-in dangerous command blacklist to prevent high-risk automation.
- **Token Usage Stats**: Status bar real-time `🧠 Token 👣 Files 💾 Storage`, refreshing every 10s.

### 💬 AI Chat Assistant
- **12 Preset Templates**: OpenAI, Claude, Gemini, Deepseek, Kimi, Ollama, etc.
- **Code Context**: One-click submission of current file/selection; copy/insert code blocks.
- **Multimodal Support**: Image upload via selection/paste/drag-and-drop (OpenAI Vision format).

### ☁️ Cloud Sync & Token Management
- **Cloud Folder Sync**: OneDrive / Google Drive / Dropbox local sync folder.
- **GitHub Gist Sync**: Private Gist with auto-create and update.
- **AES-256 Encryption**: All synced data encrypted; API keys stored via VS Code SecretStorage.

### 🛡️ Transparent Proxy (Windows)
- **Seamless Integration**: `version.dll` injection — only Antigravity core traffic is proxied.
- **Zero Dependencies**: Configure SOCKS5/HTTP directly in the extension.

### 🔐 Unified Security Password
- **IDE side**: Set via command palette; required for sensitive actions (API key copy, export).
- **Guardian side**: `/unlock`, `/lock`, `/setpwd` remote commands.

### 🛡️ Guardian Daemon
- **Native Autostart**: Windows Startup folder, silent background operation.
- **Heartbeat Monitoring**: Detects frozen IDE processes and takes over Bot control.
- **Proxy Inheritance**: Auto-detects system proxy (Registry / scutil).

### 🖥️ Multi-instance Management ✨ *2026-03-19*
- **Instance Isolation**: Each instance has its own account, workspace, and CDP port.
- **TG Remote Scheduling**: `/use` to switch active instance; `/instances` for global status.

---

## 🌐 Language / 语言

The extension interface and Telegram Bot support **English and Chinese**. Language is auto-detected from your IDE locale, or you can manually set it in the extension settings.

| Setting | Options | Default |
|:---|:---|:---|
| `anti-tools.language` | `auto` / `zh-cn` / `en` | `auto` |
| `anti-tools.telegram.botLanguage` | `auto` / `zh-cn` / `en` | `auto` |

- **IDE UI** — Follows your IDE display language automatically.
- **Bot replies** — Follows `botLanguage` setting; `auto` tracks the IDE language.
- **First-run prompt** — Non-Chinese IDE users receive a one-time prompt to switch to English.

---

## 📋 System Requirements

| Item | Requirements |
|:---|:---|
| **OS** | Windows 10/11 (Full), macOS (Partial) |
| **IDE** | Antigravity AI IDE (VS Code-based) |
| **Dependencies** | None ✅ (Self-contained) |

---

## 🔒 System Operations Disclosure

| Action | Path | Description |
|:---|:---|:---|
| **Config** | `~/.antigravity_tools/` | Account data, fingerprints, etc. |
| **Guardian** | `~/.antigravity_tools/guardian/` | Daemon deployment path |
| **Database** | `%APPDATA%/Antigravity/User/globalStorage/state.vscdb` | Login state injection for account switching |
| **CDP** | `argv.json` / Shortcut | Adds `--remote-debugging-port=9000` |

---

## 🤖 Telegram Bot Commands

### Basic
| Command | Description |
|:---|:---|
| `/start` | Show main menu |
| `/status` | IDE status, account, model, quota |
| `/help` | Full help |

### Agent
| Command | Description |
|:---|:---|
| `/send <msg>` | Send to Agent (supports `--model` param) |
| `/stop` | Stop current generation |
| `/latest` | Get latest reply (supports `export` param) |
| `/models` | Available model list with quotas |
| `/select <name>` | Switch model |

### Account & Quota
| Command | Description |
|:---|:---|
| `/quotas` | All account quota summary + switch buttons |
| `/switch <id>` | Remote account switch |
| `/screenshot` | Capture IDE screenshot |

### Scheduled Tasks
| Command | Description |
|:---|:---|
| `/schedule list` | View and manage Cron tasks |
| `/schedule add` | Add task |
| `/schedule import` | Bulk import tasks |
| `/schedule del` | Delete task |
| `/autoreset` | Toggle Guardian quota-reset auto-wakeup |

### Remote Control (Guardian)
| Command | Description |
|:---|:---|
| `/boot` | Remote start IDE |
| `/shutdown` | Remote close IDE |
| `/recent` | Open recent project |
| `/new_project` | Interactive new project |
| `/cmd <cmd>` | Shell command (requires unlock) |
| `/file_get <path>` | Retrieve file (requires unlock) |
| `/unlock` | 🔐 Unlock sensitive operations |
| `/lock` | 🔐 Manual lock |
| `/setpwd <pwd>` | 🔐 Remote set/change password |

---

## ⌨️ Keybindings

| Keys | Feature |
|:---|:---|
| `Ctrl+Alt+Shift+U` | Toggle Auto-Accept (ON/OFF) |

---

## 📄 Credits

- **Core inspiration**: [Antigravity-Manager](https://github.com/lbjlaq/Antigravity-Manager) by [lbjlaq](https://github.com/lbjlaq)
- **Proxy driver**: [antigravity-proxy](https://github.com/yuaotian/antigravity-proxy) by [yuaotian](https://github.com/yuaotian)
- **CDP inspiration**: [auto-accept-agent](https://github.com/Munkhin/auto-accept-agent) by [Munkhin](https://github.com/Munkhin)
- **UI reference**: [vscode-antigravity-cockpit](https://github.com/jlcodes99/vscode-antigravity-cockpit) by [jlcodes99](https://github.com/jlcodes99)

---

## 📜 License

MIT License. For educational and efficiency purposes only. Please comply with platform terms of use.

**Author**: [Felix2CN](https://github.com/Felix2G) | **Changelog**: [CHANGELOG.md](CHANGELOG.md)

---

## 中文说明

Anti Tools 是一个为 Antigravity AI IDE 开发的 VS Code 扩展，提供：  
多账号切换 · 配额监控 · 排程唤醒 · CDP 自动化 · AI Chat · Telegram Bot 远程控制 · Guardian 守护进程 · **中英文双语界面**

### 安装
- **🏪 Open VSX**: [open-vsx.org/extension/Felix2CN/anti-tools](https://open-vsx.org/extension/Felix2CN/anti-tools)
- **📦 手动安装**：从 [Releases](https://github.com/Felix2G/anti-tools/releases) 下载 `.vsix`，然后 `Ctrl+Shift+P` → `Extensions: Install from VSIX...`

### 语言设置
插件会自动跟随 IDE 语言，也可在设置中手动选择：
- `anti-tools.language`：界面语言（`auto` / `zh-cn` / `en`）
- `anti-tools.telegram.botLanguage`：Bot 回复语言（`auto` / `zh-cn` / `en`）

### Telegram Bot 配置
1. 在 `@BotFather` 创建 Bot，获取 Token。
2. 在插件设置中填写 `Telegram: Bot Token`。
3. 获取您的 Telegram User ID（可找 `@userinfobot`），填入 `Telegram: Allowed User Ids`。
4. 重启 IDE，Bot 将自动连接并发送启动通知。

### 主要配置项

| 设置项 | 默认值 | 说明 |
|:---|:---|:---|
| `quotaThreshold` | `10` | 配额低于此百分比时提示切换账号 |
| `autoCheckInterval` | `60` | 自动检查配额间隔（秒） |
| `monitoredModels` | `["gemini","claude","gpt"]` | 监控的模型关键字列表 |
| `quota.autoSchedule` | `fixed` | 排程模式：`none` / `fixed` / `smart` |
| `quota.useDuration` | `120` | 每个账号预估工作时长（分钟） |
| `wakeup.enabled` | `true` | 开启排程自动唤醒 |
| `wakeup.models` | `["claude"]` | 需要预热的模型列表 |
| `aiChat.enabled` | `false` | 启用 AI Chat 面板 |
| `sync.cloudFolder` | 空 | 云盘本地同步目录路径 |
| `sync.gistId` | 空 | GitHub Gist ID |

### 意见反馈
- **GitHub Issues**：[提交反馈](https://github.com/Felix2G/anti-tools/issues)

### 完整更新日志
请查看 [CHANGELOG.md](CHANGELOG.md)。
