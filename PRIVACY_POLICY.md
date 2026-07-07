# Privacy Policy for MarstekMonitor

**Last updated: July 7, 2026**

This Privacy Policy describes how MarstekMonitor ("the app", "we", "our") handles information when you use the app. MarstekMonitor is developed by Steven Debruyn ("the developer") as an independent, single-developer project.

We wrote this policy in plain language on purpose. If anything is unclear, contact us — see [Contact](#contact) below.

---

## Summary (TL;DR)

- MarstekMonitor does **not** create user accounts, does **not** use analytics or advertising SDKs, does **not** track you across apps or websites, and does **not** sell or share your data with third parties for advertising purposes.
- All of your device settings (battery IP addresses, dashboard preferences, etc.) are stored **locally on your Mac only**, using Apple's standard `UserDefaults` storage. We never receive a copy of this data.
- The app talks directly, over your local network, to the Marstek battery devices you configure. This traffic never leaves your home network.
- A small number of specific features send limited, non-identifying data to third-party services in order to work (see the [table below](#data-shared-with-third-party-services)). Each of these is described in detail, including what is sent and why.
- MarstekMonitor is a paid app. Your purchase is processed entirely by Apple through the App Store; we never receive or store your payment details.

---

## Data We Collect and Store Locally (on your device only)

The following information is stored **only on your own Mac**, in the app's local application storage (`UserDefaults`) and/or your local file system. It is never transmitted to the developer, and the developer has no server that receives it:

- Configuration of the Marstek battery devices you add (name, local IP address, port)
- Your dashboard, notification, and display preferences (e.g. selected tab, alarm thresholds, web dashboard port)
- The geographic coordinates you enter for solar production forecasting (latitude/longitude, panel orientation and capacity), if you use that feature
- Your optional [ntfy.sh](https://ntfy.sh) topic name, if you set one up for alerts
- Simple usage counters used only to occasionally show an in-app "support the developer" reminder (e.g. number of days used, whether you've already contributed) — this data never leaves your device and is not visible to the developer in any form
- Whether you've dismissed or skipped a particular version notice

None of this data is linked to your identity, none of it is used for tracking, and none of it is collected by the developer.

## Local Network Access

MarstekMonitor communicates directly with Marstek battery devices on your home network using a local protocol (UDP), and can optionally run a small local web server so you can view your battery dashboard from another device on the same network (e.g. a phone or tablet at home). Both of these:

- Operate entirely within your local network
- Never send your battery data to the developer or to any external server
- Require macOS's Local Network permission, which the app will ask you to grant

## Data Shared with Third-Party Services

To provide certain features, MarstekMonitor sends a limited amount of data directly from your device to the following third-party services. The developer does not operate any of these services, does not receive a copy of what is sent, and has no access to their servers or logs.

| Service | What is sent | Why | Linked to you? |
|---|---|---|---|
| [Open-Meteo](https://open-meteo.com) | The geographic coordinates you configure | To display a local weather forecast | No — Open-Meteo does not require or receive an account identifier from this app |
| [Forecast.Solar](https://forecast.solar) | The geographic coordinates, panel orientation, and system size you configure | To estimate your solar production forecast | No |
| [ntfy.sh](https://ntfy.sh) | The alert message and the topic name you chose | Only if you enable this optional feature, to deliver push-style alerts to your phone or other devices | No, unless you chose an identifiable topic name yourself — see the note below |
| [GitHub](https://github.com) (raw.githubusercontent.com) | Nothing beyond a standard, anonymous web request | To fetch the app's user manual content for display in-app | No |
| Apple (App Store) | Your purchase transaction | To process your one-time payment for the app | Handled entirely by Apple, under Apple's own privacy policy |

**A note on ntfy.sh:** ntfy.sh topics are public by design — anyone who knows or guesses your topic name can subscribe to it. Choose a random, non-identifying topic name, and avoid including personal information in it. This is a property of the ntfy.sh service itself, not something MarstekMonitor controls.

Because these services are operated by third parties, your use of them is also subject to their own privacy policies. We encourage you to review the privacy policies of any service listed above if you have concerns about how they individually handle data.

## Data We Do Not Collect

To be explicit, MarstekMonitor does **not**:

- Require or support account creation or sign-in
- Include any analytics, crash-reporting, or advertising SDKs
- Track you across other companies' apps or websites
- Collect or transmit precise device location (GPS) — the coordinates used for weather/solar forecasting are manually typed in by you, not read from device location services
- Sell or rent your data to anyone, for any purpose
- Access your contacts, photos, camera, or microphone

## Children's Privacy

MarstekMonitor is a utility for monitoring home battery systems and is not directed at children. We do not knowingly collect personal information from children.

## Data Retention and Deletion

Since almost all data described in this policy is stored locally on your Mac and never reaches the developer, you are in full control of it at all times. You can delete all locally stored app data by removing the app and its associated preferences, or by using macOS's standard app-data management tools. There is no developer-side account or database to request deletion from, because none exists.

## Your Rights (EU/EEA and elsewhere)

The developer is based in Belgium (EU). Because MarstekMonitor does not collect personal data on any server operated by the developer, most data protection rights under the GDPR (such as access, correction, or erasure requests) are automatically satisfied by the fact that the data never leaves your device. For any question about a specific feature's data handling, contact us using the details below and we will clarify or, where applicable, assist.

## Security

Because MarstekMonitor does not operate any backend servers or databases containing your personal data, there is no central store of your information that could be affected by a data breach on our end. Communication with third-party services listed above uses standard HTTPS encryption where applicable.

## Changes to This Policy

If this policy changes, we will update the "Last updated" date at the top of this document and, for material changes, note this in the app's release notes. We recommend checking this page occasionally if you have privacy concerns.

## Contact

If you have any questions about this Privacy Policy or how MarstekMonitor handles data, contact the developer:

**Steven Debruyn**
Email: MarstekMonitor@telenet.be

---

*This document is also published at: [https://github.com/redneckeyeball/marstek-monitor/blob/main/PRIVACY_POLICY.md]*
