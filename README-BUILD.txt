╔══════════════════════════════════════════════════════════════╗
                 SARA'S  LUCK  —  PHONE APP (Android)
╚══════════════════════════════════════════════════════════════╝

This is a Capacitor project (same toolchain as your LunaLog app). Build it
once into an .apk, install it on your phone, and it runs forever — it
self-updates Powerball on every launch and remembers via the phone's storage.

TRY IT FIRST (no build needed)
  Open  www/index.html  in a browser to see exactly what the app looks like.
  On the phone, the "Refresh now" button and auto-refresh pull the latest
  Powerball draw over the internet.

BUILD THE APK  (you already have Node + Android Studio from LunaLog)
  1. Open a terminal in this folder ("Saras Luck Mobile").
  2. npm install
  3. npx cap add android
  4. npx @capacitor/assets generate --android        (turns resources/icon.png
        into the pink-dice launcher icon; skip if you don't have the tool)
  5. npx cap sync
  6. Either:
       npx cap open android      → in Android Studio: Build ▸ Build APK(s)
     or from the terminal:
       cd android
       gradlew assembleDebug
     The APK lands at:
       android/app/build/outputs/apk/debug/app-debug.apk
  7. Copy that .apk to your phone (email/USB/Drive), tap it, allow
     "install from unknown apps," and install. Pink dice, home screen, done.

HOW IT STAYS CURRENT BY ITSELF
  On every launch (and via "Refresh now") the app fetches the Texas Lottery's
  public Powerball file, recomputes the frequencies, the most-drawn line, and
  the Edge pick, and saves them on the phone. No server, no account, no cost.
  Works offline too — it just shows the last saved numbers.
  (Lotto America ships with the app's current numbers; those refresh whenever
  you rebuild. Powerball is the one that self-updates live.)

WHAT'S INSIDE
  www/index.html   the whole app (self-contained)
  www/manifest.json, icon-192/512.png   icons + install metadata
  resources/icon.png   1024px master icon for the launcher
  capacitor.config.json, package.json   Capacitor project files

A NOTE, ONCE
  The Edge pick leans into the faint signals the past data can't fully rule
  out. It is not a disclaimer to say this plainly: it does not change your
  odds (still 1 in 292M / 1 in 26M). It's the most defensible guess in a game
  with no guessable answer. Play one line you like, keep it, budget it, enjoy.
