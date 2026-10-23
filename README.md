# Hoffman Chat

Private web chat for a small trusted group, with a thin Android shell. Skeleton.

## Status

Skeleton. This repository holds the layout, interfaces and decisions. The working implementation is not published.

## Why

A chat for a closed group that works the same in a browser and as an installed app, without a second code base.

## Architecture

The web client talks to a small HTTP API over HTTPS. The API owns users, messages and attachments behind an authorization layer that denies by default. The Android shell is a WebView wrapper pointing at the same site. Everything else is deployment detail kept out of this repository.

More in [docs/architecture.md](docs/architecture.md).

## Layout

- `client/` web UI
- `server/` HTTP API and message store (stub)
- `android-shell/` thin wrapper config example
- `docs/` architecture and ADRs

## Run

```sh
cp .env.example .env
python3 server/app.py   # serves /healthz only
```

## Design decisions

- [0001 Android app is a thin shell over the website](docs/adr/0001-android-app-is-a-thin-shell-over-the-website.md)

## Roadmap

- [ ] Authentication method ADR and implementation
- [ ] Persistent message store
- [ ] Real-time delivery
- [ ] Attachment handling with size and type limits
- [ ] Integration tests for authorization

## Security

See [SECURITY.md](SECURITY.md). CI runs a leak scan on every push.

## License

MIT, see [LICENSE](LICENSE).
