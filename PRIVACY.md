# Privacy

Skontz Control System works on your PC and **does not collect or send data about you or your PC**.

## What the app connects to

- **GitHub (this repository)**: a read-only request for the signed version list, to tell you when a new version exists. No
  information about you or your PC is included. You can switch the start-up check off in Settings > Updates.
- **Only when you ask for it**: Microsoft's `winget` and the catalogs it uses (Install apps), Cloudflare's public speed-test servers
  (Speed test), and the download sources of tools you choose to enable (for example the FPS meter or the sensor driver).

## Reports

Nothing is sent automatically. **Settings > Export report** creates a `.zip` on your PC with the app version, your Windows
version and the errors the app logged, with your user name, computer name and user folders removed. You decide whether to share it.

## Local data

Settings, the history of changes and test results stay in `%LOCALAPPDATA%\SkontzControl` on your PC. Uninstalling offers to delete them.

A future version may offer **optional** error reports. They will be off by default, will show exactly what would be sent, and
this document will be updated before that happens.
