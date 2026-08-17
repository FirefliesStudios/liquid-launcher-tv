# Privacy Policy — Liquid Launcher TV

**Last updated:** 16 August 2026

Liquid Launcher TV ("the app") is a home-screen launcher for Android TV, Google TV and Fire TV, published by Fireflies Studios.

**The app has no accounts, no analytics, no advertising, and no tracking of any kind. We operate no servers and we do not receive, store, or have access to any of your data.**

---

## What stays on your device

All of the following is stored locally on your TV and never transmitted anywhere:

- Your settings — theme, clock format, wallpaper choice, screensaver and weather preferences
- Your app arrangement, hidden apps, and per-app custom icons
- Your premium purchase status, held in the device's hardware-backed encrypted storage
- The list of apps installed on your TV, read from the system so the launcher can display them
- "Continue Watching" entries, read from the system TV provider that your streaming apps write to

None of this is uploaded, backed up to us, or shared with anyone.

---

## What leaves your device

There is exactly one feature that makes network requests: the **screensaver weather widget**.

When the screensaver is showing and **Weather** is enabled, the app:

1. Requests `https://ipwho.is/`, which reads your public IP address and returns an approximate location (city-level latitude and longitude). We never see this request; it goes directly from your TV to that service.
2. Sends those approximate coordinates to `https://api.open-meteo.com/` to retrieve current conditions.

The coordinates are used only to display the temperature and condition on the screensaver. They are held in memory, never written to storage, and never sent anywhere else. This is an approximate, IP-derived location — the app does not request or use Android's location permission, and has no access to GPS.

**You can turn this off.** Settings → Appearance → Screensaver → **Weather**. With Weather off, the screensaver makes no network requests at all.

Separately, if **Ambient Mode** is enabled, the screensaver loads photographs from Unsplash (`images.unsplash.com`). These are ordinary image downloads and carry no information about you beyond what any web request necessarily reveals.

Third-party services used:

| Service | Purpose | Privacy policy |
|---|---|---|
| ipwho.is | approximate location from IP | https://ipwho.is/privacy-policy |
| Open-Meteo | weather conditions | https://open-meteo.com/en/terms |
| Unsplash | ambient screensaver photos | https://unsplash.com/privacy |

---

## Accessibility service

The app includes an optional accessibility service used for a single purpose: letting the **Home** button open Liquid Launcher on devices where the built-in launcher would otherwise take priority.

It is deliberately scoped as narrowly as the platform allows:

- **It cannot read screen content.** The service declares `canRetrieveWindowContent="false"`, so the system never provides it with the text or contents of any window.
- It receives only `typeWindowStateChanged` events, and only from four packages: the Google TV / Android TV launchers and Liquid Launcher itself.
- It filters key events solely to detect Home and Back presses.

It collects nothing, stores nothing, and transmits nothing. The service is off unless you enable it, and you can disable it at any time in your TV's Accessibility settings.

---

## Purchases

Premium is a one-time in-app purchase processed entirely by **Google Play Billing**. We never see or receive your payment details. Your purchase is validated on-device and recorded as a single flag in encrypted local storage.

Refunds are handled by Google Play: https://support.google.com/googleplay/answer/2479637

---

## Permissions

| Permission | Why |
|---|---|
| `INTERNET` | screensaver weather and ambient photos only |
| `READ_TV_LISTINGS`, `READ_EPG_DATA`, `WRITE_EPG_DATA`, `READ_CHANNELS` | read and manage Continue Watching entries in the system TV provider |
| `READ_MEDIA_IMAGES`, `READ_MEDIA_VIDEO`, `READ_EXTERNAL_STORAGE` (Android 12 and below) | let you pick your own wallpaper from your device |
| `RECEIVE_BOOT_COMPLETED` | optional "Start on Boot" |

The app does **not** request `QUERY_ALL_PACKAGES`. To show your apps it uses a scoped `<queries>` declaration, so it can see only apps that publish a launcher or TV-input entry point — not your full installed-app list.

Media you select as a wallpaper stays on your device and is never uploaded.

---

## Children

The app is a general-purpose utility and is not directed at children. It collects no personal information from anyone, regardless of age.

---

## Changes

If this policy changes, the updated version will be published here with a new "last updated" date.

---

## Contact

Questions about privacy: use the support email listed on the [Google Play listing](#), or [open an issue](../../issues) in this repository.
