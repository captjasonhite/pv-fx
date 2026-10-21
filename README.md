# pv-fx

Live USD/MXN and USD/CAD exchange rates as a tiny JavaScript file, refreshed every 15 minutes by GitHub Actions.

Free daily sources such as Frankfurter (ECB) and open.er-api.com publish the previous day's close. This repo fills the gap for [Cambio](https://cambio.jasonhite.com): `fetch_fx.py` pulls the current interbank rate from Yahoo Finance and writes `fx_live.js`:

```js
window.FX_LIVE = {"mxn": 18.64, "cad": 1.39, "t": 1792540800000};  // MXN per USD, CAD per USD, time in epoch ms
```

Pages load it from `raw.githubusercontent.com` and use it when it's fresher than 2 hours. If one fetch fails, the other pair's last value is kept; if both fail, the file is left unchanged.

## License

MIT. See [LICENSE](LICENSE).
