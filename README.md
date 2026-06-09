# NGX Portfolio Analyser

A browser-based tool for Nigerian Exchange (NGX) investors to analyse their stock portfolio from a broker CSV export. No server, no sign-up — all data stays in your browser.

## Features

- **CSV import** — drag & drop or upload broker statements from Afrinvest, Coronation, Meristem, Stanbic, ARM, and other NGX brokers
- **Portfolio overview** — composition bar showing Equities / Fixed income / ETF breakdown with total value
- **Charts** — broker allocation, sector allocation, holdings by value, asset class breakdown, and top-10 concentration
- **Holdings table** — sortable and filterable by sector or broker, with per-position weight bars
- **P&L tracking** — add cost prices to any position to see unrealised gain/loss
- **Manual positions** — add, edit, or delete holdings directly without a CSV
- **Dark/light theme** — persisted across sessions
- **Offline-capable** — portfolio data saved to `localStorage`; nothing is sent to a server

## Getting Started

No installation or build step required.

1. Clone or download the repository
2. Open `index.html` in any modern browser
3. Upload your broker's CSV export

```bash
git clone https://github.com/Dayolabi/NGX_Portfolio_Analysis/
cd NGX_Analysis
open index.html   # macOS
# or just double-click index.html on Windows/Linux
```

## CSV Format

The app expects a CSV with at least these columns (standard NGX broker export format):

| Column | Description |
|---|---|
| `SYMBOLNAME` | Stock or instrument name |
| `HOUSENAME` | Broker name |
| `QUANTITY` | Number of units held |
| `CURRENTPRICE` | Current market price (₦) |

Sector and asset class are inferred automatically from the instrument name. You can override them at any time using the Edit button on any holding.

## Project Structure

```
NGX_Analysis/
└── index.html   # Entire app — HTML, CSS, and JS in one file
```

All dependencies are loaded from CDN:
- [Chart.js 4.4.1](https://www.chartjs.org/) — charting
- [PapaParse 5.4.1](https://www.papaparse.com/) — CSV parsing

## Privacy

Your portfolio data never leaves your device. The app runs entirely in the browser and writes only to `localStorage` under the key `ngx-portfolio-v1`.

## License

MIT
