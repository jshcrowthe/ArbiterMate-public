# ArbiterMate data

The hourly auction house sales feed for [ArbiterMate](https://github.com/jshcrowthe/ArbiterMate)'s companion app.

Every hour, the `Poll` workflow reads each WoW Forever auction house from Blizzard's API, works out what sold from how listings change between snapshots, and publishes the result:

- [`feed.json`](https://github.com/jshcrowthe/ArbiterMate-data/releases/download/feed/feed.json): per auction house and item, units sold a day, average sale price, cheapest listing, units listed, price swing, and how much is bought to resell. Companions download this.
- `state.tar.gz` (same release): the poller's state, a week of sales per house, carried from run to run.

Blizzard's API names no sellers or buyers, so neither does this feed.

The poller and this workflow are built and deployed from ArbiterMate's `server/` folder; edit them there.
