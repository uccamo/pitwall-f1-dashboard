# 🏎️ Pitwall – F1 Race Dashboard

**A fast, mobile-first Formula 1 analytics dashboard that turns live race data into results, pace comparisons, tyre strategy and weather insights — in a single HTML file with zero dependencies.**

![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)
![No Dependencies](https://img.shields.io/badge/dependencies-none-success)
![Data: OpenF1](https://img.shields.io/badge/data-OpenF1%20API-FF5A5F)

🔗 **Live demo:** https://uccamo.github.io/pitwall-f1-dashboard/

---

## 📌 Overview

Pitwall lets any F1 fan or analyst explore real Formula 1 sessions from **2023 to the current season**. Pick a season, a race weekend and a session (Practice, Qualifying, Sprint or Race), and the dashboard pulls real telemetry-derived data from the public [OpenF1 API](https://openf1.org) and visualises it instantly.

It was built to practise working with a real-world REST API, handling rate limits and imperfect data, and presenting complex information clearly on a phone screen — all without frameworks or build tools.

---

## ✨ Features

| Tab | What it shows |
|-----|---------------|
| **Results** | Podium in team colours, full classification, race time / gap to leader, pit-stop count, and DNF / DNS / DSQ flags |
| **Pace** | Lap-by-lap driver vs driver comparison chart, fastest and average lap for each, and who was quicker (outlier laps such as pit and safety-car laps filtered out) |
| **Tyres** | Stint-by-stint tyre strategy for every driver, colour-coded by compound (Soft, Medium, Hard, Intermediate, Wet) |
| **Weather** | Track and air temperature over the session, max track temp, average air temp, humidity, and rainfall |

**Also includes**
- Season, race weekend and session pickers that load automatically
- Graceful loading, empty and error states with a one-tap retry
- Responsive, mobile-first dark UI with sticky tabs and safe-area support for notched phones
- Accessibility touches: ARIA labels, visible keyboard focus, and reduced-motion support

---

## 🛠️ Tech Stack

- **HTML5, CSS3 and vanilla JavaScript (ES6+)** — no frameworks, no libraries, no build step
- **Hand-built SVG charting engine** for line charts (axes, gridlines, scaling, gaps)
- **OpenF1 REST API** for live Formula 1 data
- **Google Fonts** (Bricolage Grotesque)

---

## 🧠 Engineering Highlights

- **Rate-limit aware API client** — requests are throttled (~380 ms apart) to respect the OpenF1 free tier, with automatic retry and exponential backoff on HTTP 429.
- **In-memory caching** — every API response is cached, so switching tabs or drivers is instant and never re-fetches.
- **Race-condition safe loading** — a request token discards stale responses when the user changes season or session mid-load.
- **Resilient to missing data** — if official results aren't published for a session, the app falls back to the last recorded track positions.
- **Smart data cleaning** — pace charts use a median-based filter to drop pit, out-lap and safety-car outliers so comparisons are fair.
- **Readable team colours** — text colour on each team badge is picked automatically from the colour's luminance for contrast.
- **Security-minded rendering** — all API text is HTML-escaped before it reaches the page.

---

## 🚀 Getting Started

No installation needed.

```bash
git clone https://github.com/uccamo/pitwall-f1-dashboard.git
cd pitwall-f1-dashboard
```

Then open `index.html` in any modern browser. An internet connection is required to fetch data from OpenF1.

Or just use the hosted version on GitHub Pages: https://uccamo.github.io/pitwall-f1-dashboard/

---

## 📂 Project Structure

```
pitwall-f1-dashboard/
├── index.html   # Entire app: markup, styles and logic
└── README.md
```

---

## 🔮 Future Improvements

- Driver and constructor championship standings
- Sector-time and mini-sector comparisons
- Live timing during race weekends
- Installable PWA with offline caching
- Export charts as images for sharing

---

## 🙏 Acknowledgements

- Data provided by [OpenF1](https://openf1.org), a free and open-source Formula 1 API.
- This is an unofficial fan project and is not affiliated with or endorsed by Formula 1, the FIA or any team.

---

## 👤 Author

**Digambar More** — student developer exploring AI and web development.
GitHub: [@uccamo](https://github.com/uccamo)
