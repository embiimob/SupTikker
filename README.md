# SupTikker

Single-file local testnet3 p2fk.io price ticker and publisher.

- Open `index.html` directly in a browser.
- Default search keyword is `#BTC`.
- Includes coin presets (`#BTC`, `#LTC`, `#DOG`, `#XTZ`, `#ETH`), 24h multi-user chart overlays, profile/handle resolution, and IPFS avatar loading.
- Includes Sup!? testnet3 WIF wallet unlock + auto posting loop with configurable interval (default 60 minutes, supports `0` for immediate loop when funded).
- Uses a client-side rate limiter capped at 50 API calls per 10 seconds.
