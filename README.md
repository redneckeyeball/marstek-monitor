================================================================================
 Marstek Monitor — Installation & User Guide
================================================================================

 Platform:  macOS 14 (Sonoma) or later — Apple Silicon and Intel

================================================================================
 QUICK START — READ THIS FIRST
================================================================================

Marstek Monitor is not downloaded from the Mac App Store. Because of this,
macOS may block the app from opening. This is a standard macOS security
feature — not a problem with the app itself.

Follow these steps and you will be up and running in under two minutes:

  Step 1 — Drag MarstekMonitor.app to your Applications folder.

  Step 2 — Double-click the "RunMarstekMonitor.webloc" icon in this window.
           You will be able to download and install a shortcut that automatically  
           removes the macOS security restriction for this app.
           Give it script rights if it asks for it.

  Step 3 — Open MarstekMonitor from your Applications folder.
           A battery icon will appear in your menu bar.

That is all.

--------------------------------------------------------------------------------
 QUICK FIX — If the app still won't open
--------------------------------------------------------------------------------

  1. Open Terminal.
     (Press CMD + Space, type Terminal, press Enter.)
  2. Copy and paste this command and press Enter:

         xattr -cr /Applications/MarstekMonitor.app

  3. You will not see any output. That is normal — it means it worked.
  4. Open MarstekMonitor from your Applications folder as usual.

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
  Grid Flow     — Real-time energy flow, meter readings, and import/export
                  chart. Phase detail optional.
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

The data refreshes automatically while this tab is open.

You can reorder your batteries by clicking the arrow button (top right)
and using the chevron buttons on each card.

--------------------------------------------------------------------------------
 GRID FLOW TAB
--------------------------------------------------------------------------------

The Grid Flow tab gives you a complete picture of how energy moves between
your home, your battery, and the electricity grid.

  ENERGY FLOW DIAGRAM
  -------------------
  An animated real-time diagram shows the live power flows between your
  solar panels, battery, home, and the grid. Arrows animate in the direction
  energy is actually moving, so you can see at a glance whether you are
  importing, exporting, or self-consuming.

  GRID POWER
  ----------
  The current grid power is displayed prominently:

    Positive value (orange)  — you are consuming power from the grid
    Negative value (green)   — you are exporting power to the grid
    Zero (white)             — the grid is balanced

  You can toggle between Watts and kilowatts using the gauge button (top right).

  If you have a three-phase connection and your device supports it, you can
  enable phase detail in Settings to see Phase A, B and C separately.
  On a single-phase connection, only Phase A will show a value.

  Phase detail is only available when the operating mode is set to Auto or AI.

  ENERGY METERS
  -------------
  Below the flow diagram, three meter panels track your cumulative energy
  consumption over time:

    Today     — energy consumed from and exported to the grid today
    This week — totals for the current week
    This month — totals for the current month

  Each meter shows:
    - Grid import (kWh consumed from the grid)
    - Grid export (kWh sent back to the grid)
    - Standby power (estimated idle consumption of your home when no
      large appliances are running, calculated automatically)

  The standby power figure helps you understand your base load — the minimum
  energy your home consumes even when everything is switched off.

  IMPORT / EXPORT CHART
  ---------------------
  A time-series chart at the bottom of the tab shows your grid import,
  grid export and battery power over time. The three values are plotted
  in different colours so you can quickly see how they relate throughout
  the day.

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
  - Operating mode
  - Battery temperature (°C)
  - Remaining capacity and rated capacity in Wh, with a progress bar
  - IP address and MAC
  - WiFi SSID

Click the refresh button (top right) to force a reload of all info data.

================================================================================
 ALARMS
================================================================================

Marstek Monitor can alert you when something needs your attention. Alarms
are shown as an on-screen notification and can optionally also send a push
notification to your phone via the free ntfy app (see below).

--------------------------------------------------------------------------------
 AVAILABLE ALARMS
--------------------------------------------------------------------------------

  Battery offline
  ---------------
  Triggered when a battery stops responding to the app.
  This usually means the IP address has changed or the device has lost power.
  Or possibly that the API is no longer enabled.

  CT disconnected
  ---------------
  Triggered when the current transformer (CT clamp) that measures your
  grid connection is no longer detected by the battery.
  Without the CT, the battery cannot control grid import and export correctly.

  State of charge too low
  -----------------------
  Triggered when the battery level drops below the threshold of 10%.
  Useful if you want to be warned before the battery is fully depleted.

  Operating mode changed
  ----------------------
  Triggered when the operating mode of a battery changes unexpectedly
  (for example, if it switches from Auto to Standby without you changing it).

--------------------------------------------------------------------------------
 CONFIGURING ALARMS
--------------------------------------------------------------------------------

  1. Open Settings by clicking the gear icon in the bottom bar.
  2. Go to the Alarms section.
  3. Enable or disable each alarm individually.

--------------------------------------------------------------------------------
 PHONE NOTIFICATIONS VIA NTFY
--------------------------------------------------------------------------------

In addition to on-screen alerts, Marstek Monitor can send push notifications
directly to your phone using ntfy — a free, open-source notification service
that requires no account.

  HOW TO SET IT UP

  Step 1 — Install the ntfy app on your phone.
           Available for iOS and Android. Direct link available from the app.

  Step 2 — Copy the topic code.
           A topic is simply a unique name for your notification channel.
         
  Step 3 — Subscribe to your topic in the ntfy app.
           Open ntfy → tap + → enter your topic code → Subscribe.

  Once configured, any alarm that fires will also send a push notification
  to all devices subscribed to your topic.

  The ntfy service is free for personal use. Notifications are sent via
  ntfy.sh servers. No account or login is required.

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

  Alarms
  ------
  Configure which alarms are active and set the low SOC threshold.
  Optionally enter an ntfy topic to receive phone notifications.
  See the Alarms section above for full details.

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

Energy meters show no data or reset unexpectedly:
  - The meters are calculated from your battery's internal counters.
  - A battery restart or firmware update may reset the counters.
  - Daily and weekly totals reset automatically at midnight and on Monday.

ntfy notifications are not arriving:
  - Check that the topic name in Marstek Monitor matches exactly what you
    subscribed to in the ntfy app (it is case-sensitive).
  - Make sure your phone has an internet connection and notifications
    are allowed for the ntfy app in your phone's settings.
  - Use the test button to check your configration

App does not open or closes immediately:
  - Make sure you have run the xattr command from the Quick Start section.

Solar forecast shows no data:
  - Open the Weather tab and click Settings to verify that your location
    and panel details are configured.

Which Marstek batteries are supported?
  - Venus A / C
  - Venus D / E
  
  For the Venus E, I have been told that the API on v1 and v2 does not work.

================================================================================
 PRIVACY
================================================================================

Marstek Monitor runs entirely on your local network.
It does not collect, store or transmit any personal data.

The only external connections are:
  - forecast.solar — for the solar forecast, using the GPS coordinates
    you provided. No account or personal data is required.
  - ntfy.sh — if you enable phone notifications, alarm messages are sent
    via the ntfy service using your chosen topic name. No account or
    personal data is required.

No login or internet connection is required to use the core features.

================================================================================
 SUPPORT
================================================================================

Questions, feedback or bug reports? Contact the developer:

  sdebruyn@telenet.be

================================================================================
 © 2026 Steven Debruyn — Marstek Monitor is donationware.
 Free to use. If you enjoy it, consider supporting the developer.
================================================================================
