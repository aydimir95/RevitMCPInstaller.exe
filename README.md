# RevitMCPInstaller.exe

**RevitMCPInstaller.exe** is a lightweight Windows application designed to simplify the process of installing the [Revit MCP Plugin](https://github.com/revit-mcp/revit-mcp-plugin). It automatically places the required DLLs and `.addin` manifest into the correct Revit 2024 folders, enabling you to quickly connect Revit to the [Revit MCP](https://github.com/revit-mcp/revit-mcp) server and leverage AI-driven workflows without manual file placements or compiling code.

---

## Table of Contents

1. [Features](#features)  
2. [Requirements](#requirements)  
3. [Installation](#installation)  
4. [Usage](#usage)  
5. [Troubleshooting](#troubleshooting)  
6. [License](#license)  
7. [Credits](#credits)

---

## Features

- **Automated File Placement**  
  Detects your Revit 2024 installation folder (or allows manual selection) and places the `.addin` and DLL files in the correct location.

- **Beginner-Friendly Setup**  
  No need for Visual Studio or coding expertise; simply run the installer and start using Revit MCP.

- **Error Handling & Logging**  
  Notifies you with on-screen messages if any issues occur (missing directories, file copy errors, etc.).

---

## Requirements

- **Windows 10 or later** (tested on Windows 10 and 11)  
- **Revit 2024**  
- Permissions to read/write to Revit’s install directories (Run as Admin recommended)

---

## Installation

1. **Download the Installer**  
   Grab the latest release of **RevitMCPInstaller.exe** from the [Releases section](#) (replace this link with your actual Releases page).

2. **Run as Administrator**  
   Right-click on **RevitMCPInstaller.exe** and select **Run as administrator** to ensure you have the necessary file-system permissions.

3. **Follow On-Screen Prompts**  
   - The installer attempts to auto-detect your Revit 2024 directory.  
   - If it fails or you have multiple Revit versions, you can specify the correct path manually.

4. **Finish Installation**  
   After the process completes, you should see a success message. Your `.addin` and DLL files will be placed in `%ProgramData%\Autodesk\Revit\Addins\2024\` (by default).

---

## Usage

1. **Verify Installation**  
   Open Revit 2024. Under the **Add-Ins** tab, look for **Revit MCP Plugin**. If it’s there, the installer worked.

2. **Enable MCP Service**  
   Click **Start MCP Service Listening** (or equivalent) inside the plugin’s interface. Make sure your [Revit MCP server](https://github.com/revit-mcp/revit-mcp) is also running (via `npm run build` and the correct config in Claude).

3. **Open Claude**  
   Launch the Claude Desktop client, ensuring the `claude_desktop_config.json` points to your local `index.js` (built from `revit-mcp`).

4. **Test a Command**  
   Type an instruction like:  
   > Create a 10-foot wall in Revit  
   Revit should respond by generating a wall if everything is configured correctly.

---

## Troubleshooting

- **Missing Add-In Button**  
  - Verify Revit 2024 is installed.  
  - Check `%ProgramData%\Autodesk\Revit\Addins\2024\` for the `.addin` file.  
  - Rerun the installer as Administrator.

- **Claude Doesn’t Recognize Revit MCP**  
  - Double-check the `index.js` path in `claude_desktop_config.json`.  
  - Fully close Claude via Task Manager before reopening.  
  - Ensure Node.js 18+ is installed for Revit MCP.

- **Permission Errors**  
  - Right-click **RevitMCPInstaller.exe** → **Run as Administrator**.  
  - Temporarily disable antivirus if it blocks file-copy operations.

---

## License

Distributed under the [MIT License](LICENSE). You’re free to modify and distribute this tool as long as the license file remains intact.

---

## Credits

- [Revit MCP Plugin](https://github.com/revit-mcp/revit-mcp-plugin) for the core Revit-side functionality.  
- [Revit MCP](https://github.com/revit-mcp/revit-mcp) for the AI-driven BIM workflow.  
- Special thanks to the Revit MCP community for their ongoing support and feedback.

---

**Happy Designing with Revit + Claude MCP!**  
If you have issues or suggestions, please open an [Issue](#) or a [Pull Request](#).  
