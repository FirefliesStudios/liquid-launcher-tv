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

Two features can cause the app to make a network request. Neither involves an account, and neither reports anything about you to us — we run no servers.

### Screensaver weather

There's no GPS, no location permission, and no IP lookup — your location is never detected. If you want weather on the screensaver, you manually type a city and pick it from a list. That single choice is the only location information the app ever has.

The city name you type is briefly sent to Open-Meteo to look up matching places. Once you pick one, it's saved on your TV, and the screensaver sends those coordinates to Open-Meteo about every 30 minutes to fetch current conditions — nothing else, and nowhere else.

If you don't set a weather location, the screensaver never makes any network requests at all. To clear one: Settings → Appearance → **Weather Location** → *Turn off weather*.

### Ambient Mode photos

If **Ambient Mode** is enabled, the screensaver loads photographs from Unsplash (`images.unsplash.com`). These are ordinary image downloads and carry no information about you beyond what any web request necessarily reveals. With Ambient Mode off, no photos are fetched.

Third-party services used:

| Service | What it receives | When | Privacy policy |
|---|---|---|---|
| Open-Meteo | the city name you type, then the coordinates you chose | only if you set a weather location | https://open-meteo.com/en/terms |
| Unsplash | nothing beyond the image request itself | only with Ambient Mode on | https://unsplash.com/privacy |

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
