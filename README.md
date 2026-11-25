# ArbiterMate

The public side of [ArbiterMate](https://github.com/jshcrowthe/ArbiterMate): the companion app's releases, and the hourly auction house sales feed it reads.

## The app

Download the companion from the [latest release](https://github.com/jshcrowthe/ArbiterMate-public/releases/latest): `ArbiterMate-macos` for a Mac, `ArbiterMate.exe` for Windows. It installs the addon, keeps it current, and updates itself from these releases.

## The sales feed

Every hour, the `Poll` workflow reads each WoW Forever auction house from Blizzard's API, works out what sold from how listings change between snapshots, and publishes the result:

- [`feed.json`](https://github.com/jshcrowthe/ArbiterMate-public/releases/download/feed/feed.json): per auction house and item, units sold a day, average sale price, cheapest listing, units listed, price swing, and how much is bought to resell. Companions download this.
- `state.tar.gz` (same release): the poller's state, four weeks of sales per house (the last week by the hour, older weeks by the day), carried from run to run.

Blizzard's API names no sellers or buyers, so neither does this feed.

The poller and this workflow are built and deployed from ArbiterMate's `server/` folder; edit them there.
