# Security policy

## Supported versions

Only the **latest release** receives security fixes. The app can update itself from *Settings > Updates*.

## Reporting a vulnerability

Please **do not open a public issue** for a security problem.

Use GitHub's private reporting instead: open the **Security** tab of this repository and choose **Report a vulnerability**
(*Privately report a security vulnerability*). Include the app version (Settings > Updates), your Windows version and the steps
to reproduce. You will get an answer as soon as possible; please allow a few days.

If the Security tab does not show that option, open a normal issue that says only "I would like to report a security problem"
and **no technical details**, and the maintainer will contact you.

## What is and is not in this repository

- This repository holds **official installers and the signed version list** (`latest.json` and `latest.json.sig`) only.
  There is no source code, no secrets and no user data here.
- Only the maintainer's account can publish releases. Other people can read and download, but cannot change anything.

## How the app protects itself and you

- **Signed updates.** `latest.json` is signed with an Ed25519 key that is kept off this repository. The app embeds the public key,
  checks the signature, then checks the installer's size and SHA-256 and re-checks them right before running it. A forged or
  modified release is rejected.
- **Trusted locations only.** The installer lives in a folder only administrators can write to; external tools such as
  `winget` are run only from trusted locations.
- **Reversible changes.** Everything the app changes is logged and can be undone; the history is integrity-protected.
- **No telemetry.** The app does not send data about your PC. Network use is limited to what you ask for and a read-only update
  check. See [PRIVACY.md](PRIVACY.md).

## Verifying a download

Compare the SHA-256 of the installer with the `sha256` value in the release's `latest.json`:

```powershell
Get-FileHash .\SkontzControlSystem-Setup-<version>.exe -Algorithm SHA256
```

## Scope

In scope: the installer, the in-app updater, privilege escalation or code execution through the app, and tampering with the
history or the update channel. Out of scope: issues that need an already compromised administrator account, and social
engineering.
