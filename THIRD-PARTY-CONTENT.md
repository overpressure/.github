# Games, apps and other people's files

**TL;DR.** overpressure publishes only its own code and open source. It doesn't help to get around a license,
DRM, an entitlement or an account, and it doesn't pass on anyone else's files. Requests that need one of these
are closed as *not planned*, and links to such material are removed. Everything else is open to discussion in
the issues. This page describes how the project works. It isn't legal advice.

## What the project publishes

- Its own code and open source projects, each with its source. Where a license asks for the complete source,
  the release carries it.
- Never firmware, vendor libraries, games, apps, store content, system images or backups: not in a repository,
  a release, an issue, a pull request or the chat.
- A headset's own files reach its system from the owner's own headset at the install, and stay on that
  headset. The PICO 4's
  [distribution.md](https://github.com/overpressure/phoenix/blob/main/docs/distribution.md) lists each file and
  where it comes from.
- An owner's backups and built images hold vendor files. They are the owner's own copies and stay private.

## What the project doesn't do

- Break, remove, emulate or skip a license check, DRM, an entitlement check, a store's or an account's
  service, or a signature.
- Take apps or games out of their store with their licenses, or run another store's purchases without that
  store.
- Help with cracks, keys, unlocked paid content or copies of games and apps.
- Copy code from a project whose license doesn't allow it. To make hardware work, the project studies how the
  stock system drives it and writes its own code.

## The owner's own choice

The headset belongs to its owner. If an owner decides to do any of the above anyway, with other tools or on their
own, that is their decision and their responsibility alone. overpressure has no part in it, doesn't support
it, and isn't responsible for what follows from it. Issues about it are closed.

## Purchases

An app or game runs where its publisher ships it, under that store's terms. When a publisher ships it on Steam
(for Linux, for Windows through Proton, or as an Android build through Lepton), it runs here as on the Steam
Frame. Purchases from a headset's own store stay with that store and its account. The installer's *Restore to
stock* brings the stock system back, with access to them.

## Contributions

A contribution goes out under the license of what it changes (each repository's THIRD-PARTY.md). It has to be
the contributor's own work, or come from a project whose license allows it, with that license kept.

## How a request is handled

- **Needs one of the things above:** the issue is closed as *not planned*. A comment says which part, and what
  is possible instead, for example a publisher's Steam release.
- **Links to cracks, vendor files or other people's content:** removed from issues, pull requests and the chat.
  The issue is locked when the talk keeps going there.
- **Unsure:** ask in the [Development room](https://matrix.to/#/#overpressure-dev:matrix.org) before opening an
  issue.
