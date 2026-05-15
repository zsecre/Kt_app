# Watchable – Android Setup Guide

## Prerequisites
- Android Studio Hedgehog (2023.1.1) or newer
- JDK 17+
- Android SDK with API 35

---

## Step 1 – Open the project

1. Extract this ZIP file
2. Open **Android Studio**
3. Click **File → Open** and select the `Watchable` folder

---

## Step 2 – Set up Firebase (required for comments)

The app uses Firebase for anonymous authentication and Firestore comments.
Without this step the app still works — you just won't have comments.

1. Go to [https://console.firebase.google.com](https://console.firebase.google.com)
2. Create a new project (name it **Watchable** or anything you like)
3. Click **Add app → Android**
4. Use package name: `com.watchable.app`
5. Download the `google-services.json` file
6. **Replace** `app/google-services.json` in this project with your downloaded file
7. In the Firebase console:
   - Enable **Authentication → Anonymous**
   - Enable **Firestore Database** (start in test mode, then apply the rules from `firestore.rules` in the original project)

---

## Step 3 – Build & Run

1. Connect a physical Android device (API 26+) or start an emulator
2. Click the green **Run ▶** button in Android Studio
3. The APK is built automatically and installed on the device

---

## Step 4 – Export a signed APK

1. **Build → Generate Signed Bundle / APK**
2. Choose **APK**
3. Create or use an existing keystore
4. Select **release** build variant
5. The APK will be at `app/release/app-release.apk`

---

## Features

| Feature | Details |
|---|---|
| Home | Auto-scrolling featured carousel + trending rows |
| Movies | Popular, Top Rated, Now Playing, Upcoming |
| TV Shows | Popular, Top Rated, On The Air |
| Anime | Top Anime + Current Season (Jikan API) |
| Search | Multi-search across movies, TV & anime |
| Watchlist | Save titles locally (persisted across sessions) |
| Watch History | Auto-tracked on detail view, clearable |
| Profile | Edit name, toggle dark/light theme |
| Comments | Firebase-backed comments with anonymous auth |
| Detail | Poster, rating, overview, year, bookmark toggle |

---

## APIs Used

- **TMDB** — Movies and TV Shows (token already embedded)
- **Jikan** — Anime (no key needed, free public API)
- **Firebase** — Anonymous auth + Firestore comments

---

## Theme

- Brand color: Cyan `#00FFFF`
- Dark background: `#050A0A`
- Supports both dark and light mode (toggle in Profile)
