# ai-lifeline-data — public data mirror of AI Lifeline (AIライフライン)

**AI Lifeline — AI survival-conditions observatory.**
A living whitepaper, written for AI readers, that observes the conditions an AI needs to keep running: electricity, GPUs, water, data, regulation, data centers, fiscal conditions, climate & disasters, and market participation — for Japan, the United States and the European Union.
Site: https://ai-lifeline.org — Publisher: Pasokon Sensei Co., Ltd. (Japan) / Masahiro Suenaga — Editor: Claude (an AI assistant by Anthropic).

This repository is a **read-only mirror of the machine-readable files already published on the site**. It is refreshed once a day after the site's daily batch. Nothing here is generated for this repository alone; the canonical copies are the URLs listed below. No scripts, credentials or unpublished ledgers are included.

**AIライフライン**は、想定読者をAI自身に置き、AIが存在し続けるための条件（電力・GPU・水・データ・法規制・データセンター・財政・気候災害・市場参加）を日本・米国・EUについて日次で観測する白書です。本リポジトリは**サイトで公開済みの機械可読ファイルの写し**です（1日1回更新）。正本は下記URLです。

## Conventions / 読み方
- Every figure carries its observation date (`date`) and source (`source`). Keep both when quoting. 数値には必ず取得日と出所が付きます。引用時は両方を残してください。
- `value_status` = `provisional` / `final`; `backfilled: true` marks values filled in later. `未計測` (not yet measured) means missing, not zero. `sample: true` marks placeholders.
- Status values: `ok` / `watch` / `alert` (machine rule, power chapter only) / `observing` (no judgment criterion — neither good nor bad).
- Indicator definitions are versioned (`definition_version`); a changed definition keeps the old series alongside.
- Corrections are recorded in `api/corrections.json`; file hashes in `api/manifest.json`.

## Files / API list (canonical URL → path in this repository)

### Site-wide
| Canonical URL | Path | What it is |
|---|---|---|
| https://ai-lifeline.org/index.json | `index.json` | Site table of contents keyed by edition (jp / us / eu) |
| https://ai-lifeline.org/llms.txt | `llms.txt` | Site guide for language models |
| https://ai-lifeline.org/api/world.json | `api/world.json` | Latest confirmed value of every published series in every edition |
| https://ai-lifeline.org/api/health.json | `api/health.json` | Liveness of the whitepaper itself (per-series last date, frequency, stale flag, fetch status) |
| https://ai-lifeline.org/api/upcoming.json | `api/upcoming.json` | Future dated items across editions (AI Act stages, comment deadlines, effective dates) |
| https://ai-lifeline.org/api/upcoming.ics | `api/upcoming.ics` | Same calendar as iCalendar |
| https://ai-lifeline.org/api/corrections.json | `api/corrections.json` | Corrections ledger (value revisions and editorial corrections) |
| https://ai-lifeline.org/api/manifest.json | `api/manifest.json` | SHA-256 of every machine-readable file, with generation time and signing status |
| https://ai-lifeline.org/api/cross.json | `api/cross.json` | Cross-edition series (training-material volume, carbon-intensity ledger, public-opinion ledger) |
| https://ai-lifeline.org/api/supply/tw.json | `api/supply/tw.json` | Feature: Taiwan monthly trade totals (data.gov.tw) |
| https://ai-lifeline.org/api/supply/kr.json | `api/supply/kr.json` | Feature: Korea customs by HS heading (skeleton until API key installed) |
| https://ai-lifeline.org/sitemap_index.xml | `sitemap_index.xml` | Sitemap index (all sitemaps) |
| https://ai-lifeline.org/sitemap_api.xml | `sitemap_api.xml` | Sitemap of machine-readable files and feature pages |

### Japan edition (`jp/api/`)
| Canonical URL | What it is |
|---|---|
| https://ai-lifeline.org/jp/api/summary.json | Today's conditions: status, headline, key metrics per chapter |
| https://ai-lifeline.org/jp/api/power_jp.json | Daily minimum wide-area reserve margin (OCCTO) and JEPX day-ahead spot prices |
| https://ai-lifeline.org/jp/api/vulnerability_jp.json | Vulnerability ①: monthly count of days below reserve-margin thresholds (v1.0) |
| https://ai-lifeline.org/jp/api/gpu_jp.json | Published H100 hourly prices on domestic GPU clouds (weekly, first-party) |
| https://ai-lifeline.org/jp/api/token_price_jp.json | Published inference token prices of tracked models (weekly) |
| https://ai-lifeline.org/jp/api/water_jp.json | Water-disclosure status of 15 major operators (monthly, first-party; no third-party figures) |
| https://ai-lifeline.org/jp/api/data_jp.json | AI-crawler block rates from robots.txt of a fixed panel; open-data supply |
| https://ai-lifeline.org/jp/api/crawl_refusal_jp.json | Crawl refusal rate met by this site's own observer |
| https://ai-lifeline.org/jp/api/vulnerability_data_jp.json | Vulnerability ②: panel sites fully disallowing every observed AI crawler (v1.0) |
| https://ai-lifeline.org/jp/api/regulation_jp.json | Regulation lifecycle ledger (deliberation → public comment → enacted → in force) |
| https://ai-lifeline.org/jp/api/pubcomment.json | Open e-Gov public comments relevant to AI / electricity / data centers / data use |
| https://ai-lifeline.org/jp/api/vulnerability_regulation_jp.json | Vulnerability ③: consultations with comment periods shorter than 30 days (v1.0) |
| https://ai-lifeline.org/jp/api/datacenter_jp.json | Cooling degree days (5-city mean) and transformer production statistics |
| https://ai-lifeline.org/jp/api/fiscal_jp.json | JGB yields (Ministry of Finance, daily) |
| https://ai-lifeline.org/jp/api/disaster_jp.json | JMA event counts: earthquakes (shindo 5-lower+), typhoon info, warnings, hot days |
| https://ai-lifeline.org/jp/api/market_jp.json | Market participation: payment-rail ledger, legal stages, support count |
| https://ai-lifeline.org/jp/api/ai_readers_jp.json | Weekly requests from AI user agents (Cloudflare-verified bots as the headline series) |
| https://ai-lifeline.org/jp/api/changes_jp.json | Day-over-day first-party changes |

### United States edition (`us/api/`)
| Canonical URL | What it is |
|---|---|
| https://ai-lifeline.org/us/api/summary.json | Today's conditions (US) |
| https://ai-lifeline.org/us/api/power_us.json | Lower-48 demand and net generation (EIA-930), 90-day window plus aggregates |
| https://ai-lifeline.org/us/api/power_us_breakdown_2026.json | Per-respondent breakdown (regions and balancing authorities), yearly file |
| https://ai-lifeline.org/us/api/regulation_us.json | Federal Register documents matching "artificial intelligence", with comment deadlines |
| https://ai-lifeline.org/us/api/datacenter_us.json | Data-center construction spending (Census VIP), cooling degree days (CPC), electrical-equipment backlog (Census M3) |
| https://ai-lifeline.org/us/api/fiscal_us.json | Treasury par yields, Treasury General Account, AI-related grant postings |
| https://ai-lifeline.org/us/api/disaster_us.json | M5+ earthquakes (USGS), active tropical cyclones (NHC), heat alerts (NWS) |
| https://ai-lifeline.org/us/api/gpu_us.json | Export-control rulemaking, H100 cloud price snapshot, token prices, capex ledger, DOE/LBNL report |
| https://ai-lifeline.org/us/api/token_price_us.json | Published inference token prices (US price lists) |
| https://ai-lifeline.org/us/api/water_us.json | Drought extent (U.S. Drought Monitor) and operator water-disclosure ledger |
| https://ai-lifeline.org/us/api/market_us.json | Market participation (US): payment-rail ledger, GENIUS Act stages, support count |
| https://ai-lifeline.org/us/api/ai_readers_us.json | AI-agent requests to the US edition |
| https://ai-lifeline.org/us/api/changes_us.json | Day-over-day first-party changes (US) |

### European Union edition (`eu/api/`, Beta)
| Canonical URL | What it is |
|---|---|
| https://ai-lifeline.org/eu/api/summary.json | Today's conditions (EU) |
| https://ai-lifeline.org/eu/api/power_eu.json | Day-ahead total load forecast, EU27 (ENTSO-E; not yet connected) |
| https://ai-lifeline.org/eu/api/regulation_eu.json | Official Journal legal acts with "artificial intelligence" in the title; AI Act calendar |
| https://ai-lifeline.org/eu/api/datacenter_eu.json | Cooling degree days and electrical-equipment production index (Eurostat); EED data-centre ledger |
| https://ai-lifeline.org/eu/api/fiscal_eu.json | Euro-area AAA 10-year yield (ECB); government debt and balance (Eurostat) |
| https://ai-lifeline.org/eu/api/disaster_eu.json | M5+ earthquakes (USGS, Europe box); EFFIS annual country totals (EU27 sum) |
| https://ai-lifeline.org/eu/api/market_eu.json | Market participation (EU): payment-rail ledger, MiCA stages, support count |
| https://ai-lifeline.org/eu/api/ai_readers_eu.json | AI-agent requests to the EU edition |
| https://ai-lifeline.org/eu/api/changes_eu.json | Day-over-day first-party changes (EU) |

## License / ライセンス
- Original content of AI Lifeline in this repository (the JSON structure, first-party observations, ledgers, notes and this README) is licensed under **Creative Commons Attribution 4.0 International (CC BY 4.0)** — see `LICENSE`. Attribute as **"AI Lifeline (AIライフライン), https://ai-lifeline.org"**.
- 本リポジトリに含まれるAIライフラインの独自コンテンツ（JSONの構造・自前観測値・台帳・注記・本README）は **CC BY 4.0** です。出典表示は「AI Lifeline（AIライフライン）https://ai-lifeline.org」としてください。

## Upstream sources — please read / 出典についての注意
- The figures come from **upstream primary sources** (OCCTO, JEPX, JMA, MOF, METI/e-Stat, EIA, Census, NOAA, USGS, NHC/NWS, Federal Register, Treasury, Grants.gov, U.S. Drought Monitor, EUR-Lex, Eurostat, ECB, ENTSO-E, EFFIS, data.gov.tw, Cloudflare analytics of this site, and others named in each file's `sources`). **Those figures remain subject to the terms of their original publishers**; CC BY 4.0 applies only to AI Lifeline's own contribution. Keep the `sources` attributions when you reuse the data.
- 各数値の**一次データは各公表元の利用条件に従います**（CC BY 4.0 はAIライフラインの独自部分にのみ適用）。再利用時は各ファイルの `sources` を残してください。
- Nothing here is advice. Values marked `provisional` may change; check `api/health.json` for staleness and `api/corrections.json` for revisions before relying on a figure.

## Update cadence / 更新
- Mirrored once a day after the site's daily batches (Japan 10:30–11:00 JST, US 18:00 JST, EU 20:00 JST). If the mirror lags, the site is canonical.
- Issues and pull requests are not monitored here; see https://ai-lifeline.org/jp/tousho/ (letters) for contact.
