# KG2L Universal R50 Connector

**Free, experimental Windows connector for Garmin Approach R50 with Muni Golf and PurePlay Golf.**

> **v1.0 RC1: community test build.** This is an unofficial, unsigned application. It has passed an initial real-world test on one Windows simulator PC, not extensive testing across different systems.

## Download

**Download from [Releases](../../releases)** when the v1.0-rc1 release appears.

Under **Assets**, choose **KG2L-R50-Universal-v1.0-RC1.zip**. Do **not** choose GitHub's automatically generated "Source code (zip)" archive. That is not the application.

**Release status: The binary release upload is pending.** The public README is available now, but the downloadable ZIP must still be attached to a release.

The release ZIP contains **R50_Universal_Connector.exe**, **R50_Universal_Engine.exe**, **README.txt**, and **SHA256.txt**.

## System requirements

- **64-bit Windows 10 or Windows 11 PC**, with sufficient hardware for the simulator.
- **Garmin Approach R50.** R10 and other launch monitors are not supported.
- **An existing, legitimately installed GSPro installation containing GSPconnect.exe.** This component is required but is NOT included in our download. Relevant GSPro licensing requirements still apply.
- **Muni Golf or PurePlay Golf installed on the same Windows PC**, with OpenConnect enabled.
- A network connection between the PC and Garmin R50.

**Not supported:** iPad/iPhone, Android, macOS, or Linux.

The connector uses GSPconnect but **the GSPro game must be closed while using Muni or PurePlay**. Users do not need Python or PyInstaller.

## Step-by-step installation

1. **Download** KG2L-R50-Universal-v1.0-RC1.zip from the Release Assets. **Extract** all files to a folder, such as C:\R50-Universal\. Do not run an EXE from the compressed ZIP.
2. Keep **R50_Universal_Connector.exe** and **R50_Universal_Engine.exe** in the **same folder**. Launch only **R50_Universal_Connector.exe**.
3. **Close GSPro** and all other connector apps. Our bridge requires local TCP port **9050**.
4. Connect your R50 and Windows PC to the same compatible network, or use the R50 Wi-Fi hotspot. On the R50 choose **Connect > GSPro**.
5. Launch **Muni Golf** or **PurePlay Golf** on that Windows PC, load a range or course, and select **OpenConnect / Open Connect API** as the launch monitor.
   - **Muni:** Set its OpenConnect listening port to **921**. This universal connector's Muni mode uses TCP **921**.
   - **PurePlay:** Choose **OpenConnect (JSON)**, not the separate binary PurePlay Connect option. The connector's PurePlay port initially shows **921**, but the correct value must **match the port set in PurePlay**.
6. Open **R50_Universal_Connector.exe**. It may start automatically with saved settings. Click **Stop connector** to change mode or port; choose **muni** or **pureplay**, then click **Start connector**.
7. The launcher looks for your installed **GSPconnect.exe**, and lets you click **Browse** if needed. A common location is C:\GSProV1\Core\GSPC\GSPconnect.exe; your installation may differ.
8. Confirm the R50 shows **READY**. Hit a test shot and then a putt. Confirm they actually register in your chosen simulator.
9. **Stop the connector before reopening the GSPro game.**

## Troubleshooting and feedback

- No connection: verify GSPconnect.exe exists, the R50 is on the correct network and in GSPro connection mode, and the simulator has OpenConnect enabled on the matching port.
- Port **9050** in use: close GSPro and other connectors.
- Putting issues: look for PUTT, PUTT NOT SENT, PUTT FORWARD, or PUTT WARNING in the launcher Activity log.
- Full launcher log: **%LOCALAPPDATA%\R50_Muni_Pilot\logs\launcher.log**

When reporting bugs in Discord, include simulator name, R50 status, what happened, and a relevant log excerpt. **Remove personal information from logs before posting.**

## Testing and security

Initial testing included **two successful holes in PurePlay (including putting)**, a successful **Muni** test, and **three GSPro holes after stopping the connector**. Other Windows computers and extended sessions have not yet been extensively tested.

This is an **unsigned** community utility, so Windows may show reputation warnings. Verify the download source and SHA-256 checksums, and do not disable security protections just to run untrusted software.

## Disclaimer

Free, experimental, unofficial software provided **as-is without warranty**. Not affiliated with, endorsed by, or supported by Garmin, GSPro, Muni Golf, or PurePlay Golf. No proprietary third-party binaries are included; users must comply with their software licenses.
