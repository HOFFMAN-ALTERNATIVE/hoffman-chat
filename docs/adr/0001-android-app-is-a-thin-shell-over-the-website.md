# 0001. Android app is a thin shell over the website

Status: accepted
Date: 2026-10-23

## Context
The product is a web chat. A native app is wanted for installability, but a second code base would double the maintenance.

## Options
1. Native app with its own UI: best platform feel, two code bases to keep in sync.
2. Progressive web app only: no store-style install on every device.
3. Capacitor shell that loads the site: one code base, install via APK.

## Decision
Option 3. The shell loads the site by URL and carries no logic.

## Consequences
Releases of the web app reach the phone without a new APK. The app needs a network and depends on the site being up. Revisit if offline use becomes a requirement.
