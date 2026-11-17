# plan5-labs

SiLA 2 servers and connectors for laboratory instruments and robots, plus tools for using them.
[SiLA 2](https://sila-standard.com/) is an open standard for lab-device communication over gRPC;
every server below can be used from any SiLA 2 client.

> ⚠️ **Disclaimer**: These projects are under active development. They come with **no warranty**
> and the authors accept **no liability** for any results or damages. Use at your own risk, and
> verify safety before connecting to real hardware.

## SiLA 2 servers

Two implementation styles are used:

- **Connector** – built on the [UniteLabs CDK](https://gitlab.com/unitelabs/cdk/python-cdk).
- **Server** – built with the [`sila2`](https://gitlab.com/SiLA2/sila_python) Python package
  (code generated from SiLA feature definitions).

### Laboratory instruments

| Repository | Device | Device interface | Type |
|---|---|---|---|
| [atc-sila2-connector](https://github.com/plan5-labs/atc-sila2-connector) | Applied Biosystems Automated Thermal Cycler (ATC, A31487) | Vendor API through a Windows command executor | Connector |
| [xpeel-sila2-connector](https://github.com/plan5-labs/xpeel-sila2-connector) | Azenta Automated Plate Seal Remover (formerly Xpeel) | RS-232 serial | Connector |
| [tecan-infinite-connector](https://github.com/plan5-labs/tecan-infinite-connector) | Tecan Infinite 200 PRO plate reader (tested: F200 PRO) | USB via [PyLabRobot](https://github.com/PyLabRobot/pylabrobot) | Connector |
| [tapo-camera-sila2](https://github.com/plan5-labs/tapo-camera-sila2) | TP-Link Tapo network cameras (tested: C232) – snapshots, recording, pan/tilt | ONVIF + RTSP | Server |

### Robots and controllers

| Repository | Device | Device interface | Type |
|---|---|---|---|
| [FrankaResearch3-sila-connector](https://github.com/plan5-labs/FrankaResearch3-sila-connector) | Franka Research 3 arm and Franka Hand (with kinematic simulator) | [franky](https://github.com/TimSchneider42/franky) / Franka Control Interface | Connector |
| [bcap-sila2](https://github.com/plan5-labs/bcap-sila2) | DENSO robot controllers (e.g. RC9) – variables and tasks | ORiN b-CAP | Server |
| [kvcomplus-sila2](https://github.com/plan5-labs/kvcomplus-sila2) | KEYENCE KV series PLCs – device read/write | KV COM+ Library (Windows) | Server |
| [ardea-sila2](https://github.com/plan5-labs/ardea-sila2) | Ardea device (DENSO robot + KEYENCE PLC), combining bcap-sila2 and kvcomplus-sila2 | ORiN b-CAP + KV COM+ | Server |

## Tools

| Repository | Description |
|---|---|
| [sila2-mcp](https://github.com/plan5-labs/sila2-mcp) | MCP server that exposes SiLA 2 servers as tools, so an MCP client (e.g. Claude Code) can read properties and run commands directly |
