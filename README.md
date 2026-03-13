# ⚡ KATZ APK MAKER PRO v3

> **Turn any project into a signed Android APK — entirely in your browser. No Android Studio. No SDK. No command line.**

[![Try Free](https://img.shields.io/badge/⚡_TRY_FOR_FREE-katzai.github.io-c6ff00?style=for-the-badge&labelColor=0d0f17)](https://katzai.github.io/KATZ-APK-MAKER-/)
[![License](https://img.shields.io/badge/License-Free-green?style=for-the-badge&labelColor=0d0f17)](https://katzai.github.io/KATZ-APK-MAKER-/)
[![Platform](https://img.shields.io/badge/Platform-Browser-blue?style=for-the-badge&labelColor=0d0f17)](https://katzai.github.io/KATZ-APK-MAKER-/)

---

## 🚀 What Is KATZ APK Maker?

KATZ APK Maker Pro is a **fully browser-based Android APK builder**. It takes your source code — whether it's a simple HTML/JS web app, a Python script, a Flutter project, a React app, or a C/C++ program — and compiles it into a proper, signed `.apk` file using **GitHub Actions as the free cloud build engine**.

There is no backend server. There is no KATZ account to create. It works entirely from a single HTML file running in your browser, communicating directly with the GitHub API.

### ✨ In 5–10 minutes, you go from:
- Your source files (or a URL) →
- A configured Android project →
- A GitHub repository with a build workflow →
- A compiled, signed `.apk` ready to install on any Android device

---

## 🎯 Key Features

| Feature | Details |
|---|---|
| **8 Project Types** | HTML/JS, URL, Python, React, Flutter, C/C++, Java/Kotlin, Unity WebGL |
| **Real-time Pipeline** | Terminal-style live log with per-phase progress tracking |
| **Auto-signed APKs** | Keystore generated & password stored as encrypted GitHub secret |
| **Granular Permissions** | Toggle Camera, Microphone, Storage, Geolocation, Internet per-app |
| **Custom Appearance** | Upload icon, set theme/background/splash colors, status bar style |
| **Display Modes** | Standalone, Fullscreen, or Minimal UI |
| **Screen Orientation** | Any (auto-rotate), Portrait only, Landscape only |
| **SDK Targeting** | Min API 21–28, Target API 33–34 (Android 14) |
| **Zero Installation** | Runs in any modern browser, nothing to install locally |
| **Free Build Minutes** | GitHub gives 2,000 Actions minutes/month (≈250–400 APK builds) |

---

## 📋 Prerequisites

Before using KATZ APK Maker, you need:

1. **A free GitHub account** — [github.com/signup](https://github.com)
2. **A GitHub Personal Access Token** with `repo` scope (see setup below)

That's it. No Android Studio, no Java JDK, no Gradle — all of that runs in GitHub's cloud.

---

## 🔑 GitHub Token Setup

1. Log into [github.com](https://github.com)
2. Click your profile picture → **Settings**
3. Scroll down → **Developer settings** (bottom-left)
4. **Personal access tokens** → **Tokens (classic)**
5. Click **Generate new token (classic)**
6. Give it a name (e.g., `katz-apk-maker`)
7. Set expiration: **90 days** or **No expiration**
8. Check the **`repo`** scope checkbox
9. Click **Generate token** — copy it immediately (starts with `ghp_`)

> ⚠️ You only see the token once. If you lose it, generate a new one.

---

## 🛠️ How To Use

### Step 1 — App Details (📱)
Click the **Step 01** card and fill in:
- **App Name** — Display name shown on the home screen (e.g., `My App`)
- **Package ID** — Reverse-domain format: `com.yourname.appname` (lowercase, dots only)
- **Version Name** — Human-readable version: `1.0.0`
- **Version Code** — Integer version, increment each release: `1`
- **Display Mode** — `Standalone` (recommended), `Fullscreen`, or `Minimal UI`
- **Orientation** — `Any`, `Portrait`, or `Landscape`
- **Min SDK** — Minimum Android version (API 21 = Android 5.0 = 98% device coverage)
- **Target SDK** — Always use latest (API 34 / Android 14)

### Step 2 — Appearance (🎨)
Click the **Step 02** card:
- **Theme Color** — Tints the status bar / toolbar (hex or color picker)
- **Background Color** — Shown during splash/load before your app renders
- **App Icon** — Upload a 512×512 PNG (JPG/SVG/WebP also accepted). Auto-converted to all required densities. If skipped, a letter icon is generated from your app name + theme color.
- **Splash Background** — Color shown on the Android splash screen
- **Status Bar Style** — Light (white icons) or Dark (black icons)

### Step 3 — Project Files (📁)
Click the **Step 03** card:
1. **Choose your language/framework** from the grid
2. **Upload your source files** via drag-and-drop or file picker
3. For URL mode: just paste the website address — no files needed

### Step 4 — GitHub Config (🔑)
Click the **Step 04** card:
- **GitHub Token** — Paste your `ghp_...` token
- **GitHub Username** — Your exact GitHub username
- **Repository Name** — New or existing repo name (e.g., `my-apk-build`)
- **Branch** — Default is `main`

### Step 5 — Build ⚡
Click the **BUILD MY APK** button. The pipeline runs automatically:

```
Phase 1: Generate Android project files in-browser         ~3–5 sec
Phase 2: Create GitHub repo + push files + set secrets     ~10–30 sec
Phase 3: GitHub Actions compiles your APK in the cloud     ~4–14 min
Phase 4: KATZ downloads & extracts the APK to your browser ~5–15 sec
```

### Step 6 — Install
1. Extract the downloaded `.zip` file to find your `.apk`
2. Transfer to your Android phone (USB, Drive, Bluetooth, etc.)
3. On your phone: **Settings → Apps → Special app access → Install unknown apps** → Allow your file manager
4. Tap the `.apk` → Install → Done 🎉

---

## 🌐 Supported Project Types

### HTML / CSS / JavaScript
Upload any web project — SPAs, games, tools, dashboards. Wrapped in a full-screen WebView Activity.
- Supports: localStorage, Canvas, WebGL, fetch API, Service Workers
- Build time: **~4–6 min**

### Website / Live URL
Enter any `https://` URL. KATZ creates an APK that opens the site in a full-screen WebView.
- No files needed
- Perfect for: web tools, portfolios, online apps
- Build time: **~4–5 min**

### Python
Upload Python `.py` files. Uses the **Chaquopy 14.0** plugin to run native Python inside Android.
- Python 3.8 runtime
- Supports most pure-Python pip packages (NumPy, etc.)
- Build time: **~8–12 min**

### React / React Native
- **React Web**: Upload your `npm run build` output — wrapped in WebView
- **React Native**: Upload source + `package.json` for native RN compilation
- Build time: **~6–10 min**

### Flutter
Upload your Flutter project source. The Actions workflow installs Flutter SDK (latest stable) and runs `flutter build apk --release`.
- Dart null safety supported
- Build time: **~10–14 min**

### C / C++
Upload C/C++ source files. KATZ auto-generates `CMakeLists.txt` and NDK Gradle config.
- Android NDK r25 · CMake 3.22
- ABI targets: `arm64-v8a`, `armeabi-v7a`
- Build time: **~8–12 min**

### Java / Kotlin
Upload Java or Kotlin source files with standard Android structure.
- JDK 17 · Kotlin 1.9+ · Jetpack Compose ready
- Build time: **~5–8 min**

### Unity (WebGL Export)
Export your Unity project as a WebGL build, then upload the output files. Wrapped in a WebGL-capable WebView APK.
- Requires: Unity WebGL export
- Fullscreen mode recommended
- Build time: **~5–7 min**

---

## 🔒 Permissions

Toggle any of these in the **Step 05 — Permissions** card:

| Permission | Description |
|---|---|
| **Internet** | Always enabled — required for WebView apps |
| **Camera** | `android.permission.CAMERA` |
| **Microphone** | `android.permission.RECORD_AUDIO` |
| **Storage Read** | `READ_EXTERNAL_STORAGE` |
| **Storage Write** | `WRITE_EXTERNAL_STORAGE` |
| **Geolocation** | `ACCESS_FINE_LOCATION` + WebView geolocation bridge |

---

## ⚙️ Build Pipeline — Technical Details

### Phase 1: Project Generation (In-Browser)
KATZ generates all required Android project files entirely in JavaScript before touching GitHub:
- `AndroidManifest.xml` — with all permissions, activity config, display mode
- `app/build.gradle` — Gradle config with correct `minSdk`, `targetSdk`, dependencies
- `settings.gradle` — project structure
- `.github/workflows/build-apk.yml` — the GitHub Actions workflow
- `MainActivity.java` (or language-specific entry point)
- `res/layout/activity_main.xml`
- `res/values/strings.xml`, `colors.xml`, `themes.xml`
- `res/mipmap-*/ic_launcher.png` — all icon density variants
- Language-specific configs (CMakeLists.txt for C/C++, Chaquopy config for Python, etc.)

### Phase 2: GitHub Push
1. Authenticates with GitHub API using your token
2. Creates the repo if it doesn't exist (or uses existing)
3. Encrypts your keystore password using GitHub's libsodium-based secrets API
4. Sets `KEYSTORE_PASSWORD` and `KEY_PASSWORD` as encrypted repository secrets
5. Pushes all files via GitHub Contents API with per-file progress tracking

### Phase 3: GitHub Actions Build
The generated workflow runs on `ubuntu-latest` and:
1. Checks out the repository
2. Sets up JDK 17 (Temurin)
3. Installs Gradle 8.2
4. Configures Android SDK (API 34)
5. Runs `./gradlew assembleRelease`
6. Signs the APK using the keystore with the stored secret password
7. Uploads the APK as a workflow artifact

KATZ polls the Actions API every **10 seconds**, displays elapsed time + ETA, and waits up to **8 minutes** for completion.

### Phase 4: APK Download
1. Fetches artifact download URL from GitHub API
2. Downloads the artifact ZIP (browser fetch)
3. Extracts the `.apk` using **JSZip** (in-browser)
4. Triggers a `<a download>` browser download
5. Provides manual download link as fallback

---

## 📊 GitHub Actions Free Tier

| Metric | Value |
|---|---|
| Free minutes/month | **2,000 minutes** |
| Minutes per HTML/JS build | ~4–6 min |
| Minutes per Python/C++ build | ~8–12 min |
| Minutes per Flutter build | ~10–14 min |
| **Estimated builds/month (free)** | **~150–500 builds** |

> GitHub Actions minutes reset monthly on your account billing cycle.

---

## ❗ Troubleshooting

### `Invalid token — HTTP 401`
Your token is expired, incorrectly copied, or missing the `repo` scope.
→ Go to GitHub → Settings → Developer Settings → Regenerate token with `repo` scope.

### `All pushes failed — check token scope`
Your token doesn't have `repo` write permission.
→ Create a new token and make sure the **`repo`** checkbox is checked.

### `Build failed / conclusion: failure`
Your source files or package ID have an issue.
→ Check `github.com/YOUR_USER/YOUR_REPO/actions` for detailed Gradle logs.
→ Common causes: invalid package ID format, malformed source files, missing `main.py` entry.

### `Timed out waiting for build`
The build took longer than 8 minutes (common for Flutter/Python on cold runners).
→ Go to your GitHub repo's Actions tab, wait for the build to finish, then download the artifact manually from the workflow run's Artifacts section.

### `Package ID invalid`
Format must be `com.yourname.app` — lowercase letters, numbers, and dots only. At least 2 segments separated by a dot. No underscores at the start of segments.

### `Auto-download failed (browser security restriction)`
Some browsers block artifact downloads from the GitHub API directly.
→ Use the manual download link provided in the result panel, or download directly from `github.com/YOUR_USER/YOUR_REPO/actions`.

---

## 💡 Tips & Best Practices

- **Icon**: Use a 512×512 transparent PNG for the best result. Non-square images are center-cropped.
- **Package ID**: Choose it carefully — changing it later counts as a different app on Android.
- **Version Code**: Always increment by 1 (or more) for each new build if you want OTA-style updates.
- **Keystore continuity**: The generated keystore password is saved as a GitHub secret. Reuse the same repo to maintain signature continuity across app updates.
- **Repo reuse**: Running KATZ again with the same repo name updates all files and triggers a fresh build — great for iteration.
- **Python packages**: List pip packages in your `requirements.txt`. Chaquopy installs them at build time.
- **Flutter**: Run `flutter pub get` locally first to ensure `pubspec.lock` is committed.

---

## 🏗️ Architecture

```
KATZ APK MAKER PRO
│
├── Frontend (Single HTML file, runs in browser)
│   ├── Step Cards UI (6 modals)
│   ├── Project file generator (pure JS)
│   ├── GitHub API client (REST)
│   ├── Secrets encryption (libsodium via CDN)
│   ├── Build pipeline orchestrator
│   ├── Actions API poller
│   └── APK extractor (JSZip)
│
├── GitHub (your account — free)
│   ├── Repository (auto-created)
│   ├── Encrypted secrets (keystore passwords)
│   └── GitHub Actions runner (Ubuntu)
│       ├── JDK 17 (Temurin)
│       ├── Gradle 8.2
│       ├── Android SDK (API 34)
│       ├── Toolchains (Flutter / NDK / Chaquopy)
│       └── APK artifact upload
│
└── You
    └── Download signed .apk → install on Android
```

---

## 🔗 Links

- **🚀 Try KATZ APK Maker For Free**: [katzai.github.io/KATZ-APK-MAKER-/](https://katzai.github.io/KATZ-APK-MAKER-/)
- **📖 GitHub Token Docs**: [docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
- **⚙️ GitHub Actions Free Tier**: [github.com/features/actions](https://github.com/features/actions)

---

## ⚡ Try It Now

**[→ TRY KATZ APK MAKER FOR FREE](https://katzai.github.io/KATZ-APK-MAKER-/)**

No signup. No install. No cost. Just build.

---

*KATZ APK Maker Pro v3 · Browser-based Android APK Builder · Powered by GitHub Actions*
