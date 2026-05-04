# 📥 Daily File Downloader — Home Assistant Blueprint

[![Open your Home Assistant instance and show the blueprint import dialog with this blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?url=https://github.com/mark1foley/schedule_file_download/schedule_download.yaml)

A simple but powerful Home Assistant blueprint that automatically downloads a file from a URL every day at a time you choose — using the core [Downloader integration](https://www.home-assistant.io/integrations/downloader/).

---

## ✨ Features

- ⏰ **Scheduled daily trigger** — runs at whatever time you specify
- 🔗 **Configurable URL** — download any publicly accessible file
- 📁 **Subdirectory support** — organise downloads into subfolders
- 🏷️ **Custom filename** — save the file with a name of your choosing
- ♻️ **Overwrite mode** — always replaces the existing file, keeping things fresh

---

## 📋 Prerequisites

The **Downloader** integration must be installed and configured before using this blueprint.

[![Add Downloader Integration](https://my.home-assistant.io/badges/config_flow_start.svg)](https://my.home-assistant.io/redirect/config_flow_start?domain=downloader)

During setup you'll be prompted to choose a download directory. This will be the root folder for all downloads (e.g. `/config/downloads`). The directory must exist and be writable by the Home Assistant process.

> **Note:** If the Downloader integration is not configured, the automation will fail at runtime. Check **Settings → Automations → your automation → Traces** for error details.

---

## 🚀 Installation

### Option 1 — One-click import (recommended)

Click the button below to import the blueprint directly into your Home Assistant instance:

[![Import Blueprint](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?url=https://github.com/mark1foley/schedule_file_download/schedule_download.yaml)

### Option 2 — Manual installation

1. Download [`daily_downloader.yaml`](./daily_downloader.yaml)
2. Copy it to your HA config directory:
   ```
   config/blueprints/automation/YOUR_FOLDER/daily_downloader.yaml
   ```
3. In Home Assistant, go to **Settings → Automations & Scenes → Blueprints**
4. Click **Reload Blueprints**
5. Find **Daily File Downloader** and click **Create Automation**

---

## ⚙️ Configuration

When creating an automation from this blueprint, you'll be prompted for the following:

| Input | Required | Description |
|---|---|---|
| **Time to run** | ✅ | The time each day the download will be triggered |
| **Download URL** | ✅ | The full URL of the file to download |
| **Subdirectory** | ➖ | Subfolder within the download directory (leave blank for root) |
| **Filename** | ✅ | The filename to save the downloaded file as |

---

## 💡 Example Use Cases

- Download a daily weather data file or CSV export
- Fetch an updated blocklist or allowlist for network tools
- Pull a fresh configuration file from a remote source
- Archive a daily report or log from a web service

---

## 🔍 Troubleshooting

**The automation runs but no file appears**
- Check that the Downloader integration is correctly configured with a valid, writable directory
- Verify the URL is publicly accessible (try opening it in a browser)
- Review the automation trace: **Settings → Automations → your automation → Traces**

**The automation doesn't trigger**
- Confirm the time is set correctly and the automation is enabled
- Check that Home Assistant's timezone is configured correctly under **Settings → System → General**

**Download fails with a service error**
- The Downloader integration may not be set up — click the badge above to configure it
- Ensure the subdirectory exists within your configured download directory

---

## 📄 License

This blueprint is released under the [MIT License](./LICENSE).

---

## 🙏 Acknowledgements

Built using the Home Assistant [Downloader integration](https://www.home-assistant.io/integrations/downloader/).
