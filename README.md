================================================================================
 Marstek Monitor — Installation & User Guide
================================================================================

 Platform:  macOS 14 (Sonoma) or later — Apple Silicon and Intel

================================================================================
 QUICK START — READ THIS FIRST
================================================================================

Marstek Monitor is not downloaded from the Mac App Store. Because of this,
macOS will block the app from opening until you tell it to trust the file.
This is a standard macOS security feature — not a problem with the app itself.

Follow these four steps and you will be up and running in under two minutes:

  Step 1 — Unzip the downloaded file.

  Step 2 — Drag MarstekMonitor.app to your Applications folder.

  Step 3 — Open Terminal.
           (Press CMD + Space, type Terminal, press Enter.)

  Step 4 — Copy and paste this command into Terminal, then press Enter:

               xattr -cr /Applications/MarstekMonitor.app

           You will not see any output. That is normal — it means it worked.

  Step 5 — Open MarstekMonitor from your Applications folder as usual.
           A battery icon will appear in your menu bar.

That is all. 

================================================================================
 BEFORE YOU START — ENABLE THE LOCAL API
================================================================================

Marstek Monitor communicates directly with your battery over your local
network using the Marstek API. This API must be enabled first.

  1. Open the Marstek app on your phone.
  2. Go to Settings.
  3. Enable the local API option.
  4. Leave the port at the default value of 30000.

You only need to do this once per battery.

================================================================================
 ADDING YOUR FIRST BATTERY
================================================================================

  1. Click the battery icon in the menu bar to open the dashboard.
  2. Click the + button in the top right corner.
  3. Click "Scan Network" to automatically search for Marstek devices
     on your network. This takes a few seconds.
  4. If a device is found, click it to select it. The name will be filled
     in automatically.
  5. Click Add.

If you prefer to add a device manually, enter the name and IP address
directly in the text fields instead of using the scan.

--------------------------------------------------------------------------------
 IMPORTANT — STATIC IP ADDRESSES
--------------------------------------------------------------------------------

 The app connects to your batteries using their IP address. If your router
 assigns IP addresses dynamically (which is the default for most routers),
 the address of your battery may change after a restart or power cut.
 If this happens, the app will show the battery as offline.

 We strongly recommend assigning a fixed (static) IP address to each battery
 in your router settings. The exact steps depend on your router brand, but
 the option is usually found under "DHCP reservations" or "Static leases."

 If the IP does change, you can update it in the app by clicking the pencil
 icon on the battery card.

================================================================================
 FEATURES — QUICK OVERVIEW
================================================================================

Marstek Monitor lives in your menu bar. The battery icon changes colour
to reflect the average state of charge across all your batteries:

  Red    — below 35%
  Orange — 35% to 60%
  Yellow — 60% to 85%
  Green  — 85% and above

Click the icon to open the dashboard. The dashboard has five tabs:

  Batteries     — Live SOC and power per device. Combined totals if you
                  have more than one battery.
  Grid Flow     — Real-time grid import and export. Phase detail optional.
  PV Solar      — Live solar output per string. Optional tab.
  Weather       — Solar forecast for today and tomorrow.
  Info          — Device details, firmware version, temperature.

================================================================================
 FEATURES — DETAILED
================================================================================

--------------------------------------------------------------------------------
 BATTERIES TAB
--------------------------------------------------------------------------------

This is the default tab. Each battery card shows:

  - Device name and IP address
  - Operating mode (e.g. Auto, AI)
  - State of charge as a percentage and a progress bar
  - Current status: Charging (green), Discharging (yellow) or Standby (white)
  - Current power in Watts
  - Online indicator: green dot = reachable, red dot = offline

If you have more than one battery, a totals bar appears at the bottom:

  - Combined average state of charge (%)
  - Combined power and direction (charging / discharging / standby)
  - Total installed capacity in Wh
  - Total remaining capacity in Wh

The data refreshes every 10 seconds automatically while this tab is open.

You can reorder your batteries by clicking the arrow button (top right)
and using the chevron buttons on each card.

--------------------------------------------------------------------------------
 GRID FLOW TAB
--------------------------------------------------------------------------------

Shows how much power is flowing between your home and the electricity grid.

  Positive value (orange)  — you are consuming power from the grid
  Negative value (green)   — you are exporting power to the grid
  Zero (white)             — the grid is balanced

You can toggle between Watts and kilowatts using the gauge button (top right).

If you have a three-phase connection and your device supports it, you can
enable phase detail in Settings to see Phase A, B and C separately.
On a single-phase connection, only Phase A will show a value.

Phase detail is only available when the operating mode is set to Auto or AI.

--------------------------------------------------------------------------------
 PV SOLAR TAB  (optional — can be hidden in Settings)
--------------------------------------------------------------------------------

Shows the live power output of your solar panels, broken down per string:

  P1, P2, P3, P4 — individual string power in Watts
  Green dot       — string is active
  Grey dot        — string is inactive or not connected

The total output across all strings is shown in the top right.
If you have multiple batteries with solar support, a grand total is shown
at the bottom.

This tab is hidden by default. You can enable it in Settings.
If your device does not support solar monitoring, the tab will show
an informational message instead of data.

--------------------------------------------------------------------------------
 WEATHER & SOLAR FORECAST TAB
--------------------------------------------------------------------------------

Shows a solar energy forecast for today and tomorrow, based on your location
and the specifications of your PV installation.

The forecast includes:
  - Expected energy yield in kWh (today and tomorrow)
  - Expected peak output in Watts and the time it occurs
  - Sunrise and sunset times
  - An hourly chart of expected power output throughout the day

To use this tab, you must configure your location and panel details first.
Click the Settings button (top right of the Weather tab) to open the
Solar Forecast Settings window.

  Location
  --------
  Enter your address, city, or postal code and click the magnifying glass.
  The app will look up the coordinates automatically.

  Tilt angle (degrees)
  --------------------
  The angle at which your panels are mounted.
    0  = completely flat (e.g. flat roof)
    90 = completely vertical (e.g. wall-mounted)
  A typical roof installation is between 30 and 40 degrees.

  Panel direction (azimuth)
  -------------------------
  The compass direction your panels face.
  South (180°) is optimal for locations in the northern hemisphere.
  Choose the option that best matches your installation.

  Peak power (kWp)
  ----------------
  The total installed capacity of your solar panels in kilowatt-peak.
  This is the maximum power your system can produce under ideal conditions.
  You can find this value on your inverter documentation or installer report.
  Example: a system with 10 panels of 400 Wp each = 4.0 kWp.

The forecast updates automatically once every 20 minutes at most, to stay
within the limits of the free forecast.solar API tier (12 calls per hour).
When you save new settings, a fresh forecast is fetched immediately.

--------------------------------------------------------------------------------
 INFO TAB
--------------------------------------------------------------------------------

Shows technical details about each battery:

  - Device model name
  - Firmware version
  - Operating mode and CT state
  - Battery temperature (°C)
  - Remaining capacity and rated capacity in Wh, with a progress bar
  - IP address

Click the refresh button (top right) to force a reload of all info data.

================================================================================
 SETTINGS
================================================================================

Open Settings by clicking the gear icon in the bottom bar of the dashboard.

  Launch at login
  ---------------
  Start Marstek Monitor automatically when you log in to your Mac.
  The app runs quietly in the menu bar — it will never open a window
  or interrupt you at startup.

  Show totals
  -----------
  Show the combined battery level and power bar at the bottom of the
  Batteries tab when you have more than one battery connected.

  Show phase details in Grid Flow
  --------------------------------
  Show individual Phase A, B and C power values in the Grid Flow tab.
  Only useful for three-phase connections.

  Show PV Solar tab
  -----------------
  Enable or disable the PV Solar tab in the dashboard.
  Disable this if your Marstek device does not support solar monitoring.

  Show Weather tab
  ----------------
  Enable or disable the Weather & Solar Forecast tab in the dashboard.

  Automatically check for updates
  --------------------------------
  Check for a new version of Marstek Monitor each time you open the dashboard.
  If an update is available, a notification window will appear.
  You can also check manually by clicking "Check for updates."

================================================================================
 TROUBLESHOOTING
================================================================================

App does not find my battery during network scan:
  - Make sure the local API is enabled in the Marstek phone app.
  - Make sure your Mac and battery are on the same network.
  - Make sure macOS has granted the app local network access:
    System Settings → Privacy & Security → Local Network
    → enable Marstek Monitor.
  - You can also open this screen directly from the Troubleshooting section
    in the app's Settings.

Battery shows a red dot (offline):
  - The IP address of the battery is no longer reachable.
  - Check your router to see if the address has changed.
  - Click the pencil icon on the battery card to update the IP address.
  - See the note on static IP addresses above.

App does not open or closes immediately:
  - Make sure you have run the xattr command from the Quick Start section.

Solar forecast shows no data:
  - Open the Weather tab and click Settings to verify that your location
    and panel details are configured.

Which Marstek batteries are supported ?
- Venus A / C
- Venus D / E    

================================================================================
 SUPPORT
================================================================================

Questions, feedback or bug reports? Contact the developer:

  sdebruyn@telenet.be

================================================================================
 © 2026 Steven Debruyn — Marstek Monitor is donationware.
 Free to use. If you enjoy it, consider supporting the developer. Get PREMIUM
================================================================================
