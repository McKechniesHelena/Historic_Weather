# 🌦️ Historic Weather Averages

A single-page web app that shows the **typical weather for any U.S. ZIP code**, averaged
over roughly the last 10 years — broken down **by week**, with a click-to-expand
**day-by-day** view.

## Features

- Enter a U.S. ZIP code and see 10-year climate averages.
- **Summary cards:** annual avg high, avg low, avg humidity, total precipitation.
- **Charts:** average high/low temperature by week, weekly precipitation + humidity, and the
  **chance of a wet week** (% of years in which that week saw more than ½ inch of precipitation).
- **Weekly table:** avg high, avg low, typical weekly precip, avg humidity for all 53 weeks.
- **Click any week** to expand a day-by-day breakdown.
- **Unit toggle:** °F / inches ↔ °C / mm (re-renders live).

## How the averaging works

Each calendar day (e.g. "Jan 1") is averaged across all ~10 years of records, then days are
grouped into 7-day weeks. "Week 1" is the typical Jan 1–7, "Week 2" is Jan 8–14, and so on.

## Data sources

- **[Open-Meteo](https://open-meteo.com/)** historical reanalysis (ERA5) — daily temperature,
  precipitation, and relative humidity. Free, no API key. This is gridded reanalysis data
  (not a single station) and lags a few days, so the date range is capped ~1 week back.
- **[Zippopotam.us](https://www.zippopotam.us/)** — ZIP code → latitude/longitude. U.S. only.

## Running it

It's a static file with no build step — just open `index.html` in any modern browser.

To serve it locally (e.g. to avoid file:// quirks):

```sh
python -m http.server 8123
# then visit http://localhost:8123
```

## Notes / ideas

- U.S. ZIP codes only (could be extended to other countries).
- Possible additions: record high/low per week, "chance of rain" (% of days with measurable
  precip), snowfall, or a shareable URL that remembers the ZIP.
