# SupTikker

Single-file local testnet3 p2fk.io price ticker and publisher.

- Open `index.html` directly in a browser.
- Default search keyword is `#BTC`.
- Includes coin presets (`#BTC`, `#LTC`, `#DOG`, `#XTZ`, `#ETH`), 24h multi-user chart overlays, profile/handle resolution, and IPFS avatar loading.
- Includes Sup!? testnet3 WIF wallet unlock + auto posting loop with configurable interval (default 60 minutes, supports `0` for immediate loop when funded).
- Caps p2fk.io API calls at 50 per 10 seconds. Separately, each open app page shares a Mempool queue across balances, UTXOs, fee estimates and broadcasts: it sends up to 10 attempts in a burst, then waits 10 seconds before the next burst. HTTP 429 pauses the queue for at least 10 seconds (longer if an exposed `Retry-After` header specifies it).
- Uses the 47 regional hosts from the supplied [Mempool monitoring dashboard](https://monitoring.mempool.space/) snapshot, ordered roughly by distance from the central US. The dashboard probes mainnet, but the app uses `/testnet/api` on those hosts to keep wallet operations on Testnet3. If an endpoint times out after 10 seconds or is unavailable, the app tries the next node and uses that node for new requests.
