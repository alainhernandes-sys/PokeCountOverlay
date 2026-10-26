# PokéCount Auto-Vision Overlay — Native Android APK Project

This project compiles into the native **`PokeCount-Overlay.apk`** Android app that works just like Poke Genie's overlay in your video:
1. Opens Android's **"Appear on top" (`SYSTEM_ALERT_WINDOW`)** permission once.
2. When you tap **START OVERLAY**, it opens Android's native **"Share your screen with PokéCount? -> Share one app -> Choose app to share (Pokémon GO)"** prompt (`MediaProjectionManager`).
3. Minimizes itself to the background (`moveTaskToBack(true)`) and draws the **draggable Orange Circle Bubble** (`TYPE_APPLICATION_OVERLAY`) directly on top of Pokémon GO.
4. Uses **Google ML Kit OCR** on the captured Pokémon GO screen to:
   - Automatically read the opponent Pokémon name in the top-right corner (`Feraligatr`, `Clodsire`, `Azumarill`, etc.).
   - Automatically count their PvPoke Fast Moves every GBL turn (`turns * 500ms`).
   - Show discreet Charged Move badges next to the orange bubble that light up when ready.
   - Automatically subtract the Charged Move's energy and Fast Move count when `"[Pokemon] used [Charged Move]!"` appears on screen (or when you tap a Charged Move badge).

---

## How to Get the `.apk` File (2 Easy Ways)

### Way 1: Free Cloud Build on GitHub (No Computer Needed — Do It From Your Phone)
1. Go to **[github.com/new](https://github.com/new)** in your browser (sign in or create a free account) and create a new repository named `pokecount-apk` (check **"Add a README file"**).
2. In your new repository, tap **Add file > Upload files**, and upload the unzipped contents of `PokeCountOverlay-Android` (make sure the `app` folder, `build.gradle.kts`, `settings.gradle.kts`, and `gradle.properties` are uploaded).
3. Tap the **Actions** tab at the top of your GitHub repository -> tap **New workflow** -> **set up a workflow yourself**, paste the contents of `GITHUB-ACTIONS-BUILD.yml`, and tap **Commit changes**.
4. Wait ~2 minutes for the green checkmark in the **Actions** tab, tap the finished run, and download **`PokeCount-Overlay-APK.zip`** — inside is your compiled **`app-debug.apk`**! Tap it on your Samsung phone to install.

### Way 2: Build on Any Windows / Mac / Linux Computer (Android Studio)
1. Download free **[Android Studio](https://developer.android.com/studio)** on any computer.
2. Click **Open** and select the unzipped `PokeCountOverlay-Android` folder.
3. Wait for Gradle sync to finish, then click **Build > Build Bundle(s) / APK(s) > Build APK(s)** in the top menu.
4. Click **locate** in the bottom-right notification to get `app-debug.apk`, send it to your Samsung phone (via USB, Google Drive, or email), and tap it to install!
