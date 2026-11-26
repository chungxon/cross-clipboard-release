# Cross Clipboard beta: tester guide

Thanks for testing. Cross Clipboard sends what you copy to your other devices, end-to-end encrypted. This beta is Android, through Google Play, iPhone and iPad, through TestFlight, and Windows and macOS, as a zip from [the latest release](https://github.com/chungxon/cross-clipboard-release/releases/latest).

![A copy on a Mac shows up on an Android phone, then the phone sends one back](https://github.com/chungxon/cross-clipboard-release/raw/main/media/demo.gif)

Contact: `lesonlhld@gmail.com`. Bugs and ideas: [open an issue](https://github.com/chungxon/cross-clipboard-release/issues/new/choose).

## Join on Android

1. Join the Google Group [test-it-together](https://groups.google.com/g/test-it-together) with the Google account your phone uses for Play
2. Open the [opt-in link](https://play.google.com/apps/testing/dev.chungxon.crossclipboard), on the phone or in a browser signed in to that account, and tap "Become a tester"
3. Install Cross Clipboard from the Play link on that page. It may take a few minutes to show up after you join
4. Please stay in the test for at least 14 days: Google lets the app go public only after 12 testers stayed that long

To leave, open the opt-in link again and tap "Leave the program", then uninstall.

## Join on iPhone or iPad

iOS 15 or later.

1. Open [the TestFlight link](https://testflight.apple.com/join/mKMy2upy) on the iPhone or iPad
2. Install TestFlight from the App Store if it asks, then tap "Accept" and "Install"
3. TestFlight builds stop working after 90 days: install the newer build when TestFlight offers it

To leave, open TestFlight, Cross Clipboard, "Stop Testing", then delete the app.

## Install on macOS

macOS 12 or later.

1. Download `Cross-Clipboard-<version>-macos-universal.zip` from [the latest release](https://github.com/chungxon/cross-clipboard-release/releases/latest), for Apple silicon and Intel Macs. Unzip it and move `Cross Clipboard.app` to Applications
2. Open it. macOS says it cannot verify the app: click Done. Then either:
   - In Terminal, run `xattr -dr com.apple.quarantine "/Applications/Cross Clipboard.app"` and open the app again
   - Or System Settings, Privacy & Security, scroll down, Open Anyway, and enter your Mac password. On macOS 14 or earlier, a right-click on the app, Open, also works

   Do this again for each new zip
3. Closing the window, or `Cmd+Q`, keeps the app running in the menu bar. Quit it from the menu bar icon's menu

To remove it, quit the app and move it to the Trash.

## Install on Windows

Windows 10 or 11, 64-bit.

1. Download `Cross-Clipboard-<version>-windows-x64.zip` from [the latest release](https://github.com/chungxon/cross-clipboard-release/releases/latest). Right-click it, Extract All, to a folder where it can stay, for example in Documents. Open at Login starts the app from there
2. Open `cross_clipboard.exe` in the extracted folder. The app is not signed, so Windows SmartScreen warns about it: click "More info", then "Run anyway"
3. Closing the window keeps the app running in the system tray (the up arrow next to the clock). Quit it from the tray icon's menu

To remove it, quit the app, delete the folder, and delete `%APPDATA%\dev.chungxon\Cross Clipboard`, where it keeps its history and key.

## First run

1. Create an account with your email and a password (at least 8 characters), or Continue with Google or Apple, or Email Me a Code. Apple can hide your email: the app still sends the code to the relay address Apple gives it
2. With email and password, open the link in the confirmation email, then sign in
3. Set a PIN of at least 6 characters. The PIN makes the key that encrypts your copies. The server never has it, so **a lost PIN cannot be recovered**: Forgot PIN resets it and the synced history is lost
4. On your other devices, sign in with the same account and PIN. Or choose Sign In with a Device on the new device (a computer shows a QR) and scan it from a phone already signed in (Settings, Link a Device). Turn on Send Encryption Key there, or the new device asks for the PIN
5. On Android and iOS, allow notifications when asked, to get copies from other devices while the app is closed
6. Home shows First Steps: add a device, try a copy, then Quick Access on a phone or a picker shortcut on a computer

## What to try

- Copy a text or an image on one device, check it shows on the other
- Settings, Quick Access: Share Without Opening, Pinned Notification, Floating Bubble, Clipboard Keyboard
- The home screen widgets and the Send Clipboard Quick Settings tile
- Search, pins, details, deleting items, and Settings, Connected Devices
- Windows: set a Clipboard Picker Shortcut in Settings, Desktop (there is none by default). It opens your history over any app; pick an item and it is pasted there. A left click on the tray icon opens it too, an Alt-click opens the app window
- Windows: Open at Login and Show in Taskbar in Settings, Desktop
- iOS: Share a text or image to Cross Clipboard from another app, the Clipboard Keyboard and the widgets
- macOS: the Clipboard Picker Shortcut as on Windows. To paste into the app you were in, allow Accessibility when Settings asks (Paste into Other Apps); without it the item is only copied

## Known issues

- Android lets an app read the clipboard only while it is open. A copy made in another app is sent when you open Cross Clipboard, or right away through Share, the text menu, the tile, the Floating Bubble or the keyboard
- The Pinned Notification and the widgets get new copies while the app is closed only with Clipboard Notifications on (Settings, Notifications), and only texts. Images and long texts arrive when the app opens
- A notification for a copy shows its first 100 characters, a password too. To keep them off the lock screen, choose "Hide sensitive content" in the phone's lock screen notification settings
- Copies from password managers are sent like any other copy. One marked private stays private on your other devices, so most clipboard histories there skip it (Samsung Keyboard does not). A device on an older build skips it
- A short or simple PIN is easier to guess for someone who gets the encrypted data from the server. Use a long one
- Please do not tap ads just to support the app: AdMob counts such taps as invalid and can turn the ads off

Windows:

- No notifications: copies from other devices show in the history and the picker, without a notification
- The picker cannot paste into an app run as administrator: the item is only copied, paste it with `Ctrl+V`
- A pick from a tray click is only copied, as the click takes the focus away from your app. Use the shortcut to paste
- After the picker closes, a text field in Cross Clipboard loses its cursor: click it again
- An image with transparency loses it
- With Open at Login, the window may flash for a moment when Windows starts

iOS:

- iOS asks "Allow Paste" each time the app reads a copy made in another app, so copies are sent by hand by default. To stop the prompt, Settings, Sync, Paste Without Asking opens the app's page in iOS Settings: set Paste from Other Apps to Allow
- The Shortcuts actions ask you to unlock the iPhone first
- Share and the keyboard send right away only within about an hour of the app's last run. After that they say "Sends when you open Cross Clipboard": open the app once
- An account made with Continue with Apple: Delete Account confirms with Apple again. If you delete it another way, also remove the app in your Apple ID settings, under Sign in with Apple

macOS:

- Notifications only while the app runs (it stays in the menu bar). Copies sent while it is quit show in the history when it opens
- It does not update itself: download the new zip from Releases

The full list for each build is in the release notes on Play, TestFlight and GitHub.

## Privacy

- Your copies and images are encrypted on the device with your PIN's key. The server stores them encrypted and cannot read them, and deletes them after 7 days
- The server sees your email, your account and device ids, device names, and when and how big each copy is
- Crash reports (Android, iOS): when the app crashes, a report with the error's type, where in the code it happened, the phone model and the system version goes to Firebase Crashlytics. It never holds your copies. Reports are deleted after 90 days
- Usage counts and timings (Android, iOS): which features are used (a sign-in method, a copy sent and whether it was text or an image, a second device, the first copy received, a setting changed) and how long some steps take go to Firebase, never what you copied. Turn it off in Settings, About, Share Usage Data
- Ads (Android, iOS): the app shows Google AdMob ads, a banner on Home and a few in the history list. On iOS it asks first whether apps may track you; without it the ads are not personalized. AdMob gets the advertising ID, the IP address and the ads you see and tap, never your copies or your email. In the EEA and the UK the app asks first; change it in Settings, About, Ad Privacy
- Windows and macOS send no crash reports, no usage counts and show no ads
- Privacy policy: `https://crossclipboard.chungxon.dev/privacy`
- Delete your account and its data: Settings, Account & Security, Delete Account, or `https://crossclipboard.chungxon.dev/delete-account`

## Feedback

Copies not arriving? Settings, Sync, Check Sync shows what stops sync on this device, with a button to fix it.

[Open an issue](https://github.com/chungxon/cross-clipboard-release/issues/new/choose) (a GitHub account is needed), or email `lesonlhld@gmail.com`. In the app, Settings, About, Contact Support opens it with the version, the device and the sync settings filled in, never what you copied. Issues are public. Please say:

- what you did, what you expected, what happened
- the device model and its system version (Android, iOS, macOS), or the Windows version (run `winver`)
- the app version (Settings, About)
- a screenshot or screen recording if you can

Never post or send your PIN, passwords or private copies.

## Updates

Play and TestFlight update the app like any other. To get a fix sooner, open the app's page in Play and tap Update. The release notes say when an update matters, for example when an older version stops syncing.

To get an email for each new build, Watch [the release repo](https://github.com/chungxon/cross-clipboard-release) on GitHub: Custom, Releases.

On macOS, quit the app and replace it in Applications with the one from the new zip. On Windows nothing updates by itself: download the new zip from Releases, quit the app from the tray, replace the folder's files with the new ones, and open it again. The history and the key stay, as they are kept in `%APPDATA%`. On both, the app looks for a new build when it opens and once a day: Settings, About then shows Update Available with the version. That row, or Check for Updates, opens Releases.
