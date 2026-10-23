# Architecture

The web client talks to a small HTTP API over HTTPS. The API owns users, messages and attachments behind an authorization layer that denies by default. The Android shell is a WebView wrapper pointing at the same site. Everything else is deployment detail kept out of this repository.

## Out of scope for this skeleton

Implementation details, real configuration, deployment specifics and product content.
