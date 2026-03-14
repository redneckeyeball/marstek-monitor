# marstek-monitor
Marstek Monitoring app for MacOS

================================================================================
 Marstek Monitor — Installation Guide
================================================================================

Marstek Monitor is a macOS menubar app that monitors your Marstek Venus
battery devices in real time. Data refreshes every 5 seconds.
No admin rights required.

REQUIREMENTS
------------
- macOS 14 (Sonoma) or later
- Marstek Venus battery device connected to your local network

================================================================================
 BEFORE YOU START
================================================================================

In the Marstek app on your phone, first enable the local API in the settings.
You can keep it at the default port 30000, no need to change it.

================================================================================
 INSTALLATION
================================================================================

1. Unzip the downloaded file.
2. Drag MarstekMonitor.app to your Applications folder.
3. Open Terminal (Spotlight: CMD + Space, type Terminal, press Enter).
4. Run the following command:

       xattr -cr /Applications/MarstekMonitor.app

   (This is required because macOS blocks apps that are not downloaded from
   the App Store. This command tells macOS to trust the app.)

5. You can now open the app normally from your Applications folder.

================================================================================
 FIRST USE
================================================================================

Click the battery icon in the menubar to open the dashboard.
Click the + button to add your Marstek Venus device.

You can use the Scan Network button to automatically discover devices
on your network. If a device is found, click it to select it — the name
will be filled in automatically.

If you prefer to add a device manually, enter the name and IP address directly.

================================================================================
 DASHBOARD
================================================================================

Each battery card shows:
- Device name and IP address
- State of charge (%)
- Current status: Charging (green), Discharging (yellow) or Standby (white)
- Current power in Watts
- Connection indicator: green = online, red = offline

If you have more than one battery, a totals bar is shown at the bottom
with the combined SOC, power and total capacity.

================================================================================
 IMPORTANT — STATIC IP ADDRESSES
================================================================================

The app connects to your batteries using their IP addresses.
If you have not assigned a static IP address to your batteries in your router,
we strongly recommend that you do so.

Without a static IP, the address may change after a restart. If this happens,
the app will no longer be able to find the battery (shown as offline).
You can fix this by editing the device in the app and entering the new IP,
but assigning a fixed IP in your router prevents this issue entirely.

================================================================================
 TROUBLESHOOTING
================================================================================

App does not find my battery during scan:
  - Make sure the local API is enabled in the Marstek phone app.
  - Check that your Mac and battery are on the same WiFi network.
  - Make sure macOS has granted the app local network access.
    Go to System Settings → Privacy & Security → Local Network
    and make sure Marstek Monitor is enabled.

Battery shows a red dot (offline):
  - The IP address is no longer reachable. Check if the IP has changed
    in your router and update it in the app using the pencil icon.

App does not open or closes immediately:
  - Make sure you have run the xattr command in step 4 of the installation.

================================================================================
 SUPPORT
================================================================================

Questions or feedback? Contact the developer:
sdebruyn@telenet.be

================================================================================
 © 2026 Steven Debruyn
================================================================================
