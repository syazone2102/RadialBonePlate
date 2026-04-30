# RadialPlate CDSS — Android Build Guide

## Prerequisites

Install these tools first (in order):

### 1. Node.js
Download from: https://nodejs.org/en/download  
Choose **LTS version** → Windows Installer (.msi) → Install with defaults.

### 2. Android Studio
Download from: https://developer.android.com/studio  
Install with defaults. On first launch, let it download the Android SDK.

### 3. Java (included with Android Studio)
Android Studio installs JDK automatically. No separate install needed.

---

## Build Steps

Open **PowerShell** in the project folder (right-click → "Open in Terminal"), then run these commands **one by one**:

### Step 1 — Install Capacitor
```powershell
npm install
```

### Step 2 — Scaffold Android Project
```powershell
npx cap add android
```

### Step 3 — Copy Web Files into Android Project
```powershell
npx cap sync android
```

### Step 4 — Open in Android Studio
```powershell
npx cap open android
```

---

## Build APK in Android Studio

1. Wait for Gradle to sync (bottom bar shows progress)
2. Menu → **Build** → **Build Bundle(s) / APK(s)** → **Build APK(s)**
3. Click **locate** when it finishes — your APK is in `android/app/build/outputs/apk/debug/app-debug.apk`

---

## Install on Android Phone

**Option A — USB:**
1. Enable Developer Mode on phone: Settings → About Phone → tap "Build Number" 7 times
2. Enable USB Debugging: Settings → Developer Options → USB Debugging
3. Connect phone via USB → Android Studio → Run ▶ → Select your device

**Option B — File Transfer:**
1. Copy `app-debug.apk` to your phone
2. Open it → Allow "Install Unknown Apps" → Install

---

## Notes
- The app bundles all HTML + FEA data files (~25 MB APK)
- 3D model viewer works fully on Android Chrome WebView
- AR mode works on ARCore-supported Android devices
