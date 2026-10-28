# Evaluation test set

Fill this in after every refresh, before you publish. The agent is the system under test.
You are the grader. Nothing here is automated on purpose: the point is to decide, with a
source you trust, whether the agent told you the truth.

**Ground truth sources.** Pick one and use the same one every time, so your scores are
comparable week to week:

- Prices: Google Finance (google.com/finance), Yahoo Finance, or your brokerage app.
- News: the article itself. Open the link. Check the date on the page.
- Calendar: the company's investor relations page (search "TICKER investor relations
  events"), or the Fed's own meeting calendar for FOMC dates.

Refresh date: 2026-10-28 (BRIEF.asOf 2026-10-28, priceType intraday, retrievedAt 2026-10-28T10:05:00-04:00)    Grader: number-checker agent

## A. Prices (one row per ticker)

Pass if the dashboard's last price is within $0.10 of the ground truth for the same day
and the same price type (close vs intraday). If the agent recorded an intraday price,
compare against the intraday price at about the same time; do not compare it to a close.

Note: Google Finance pages (https://www.google.com/finance/quote/NVDA:NASDAQ and the same for JPM:NYSE, ACN:NYSE, IREN:NASDAQ, LLY:NYSE) returned "Google Finance isn't supported on this device" with no data, so Yahoo Finance history pages were used for every row. Yahoo quotes were read at about 10:11 to 10:12 AM EDT; BRIEF latest prices are stamped 10:05 AM. The latest rows are marked Fail because the ground truth is not at the same time and differs by more than $0.10 (intraday prices move); they need a recheck at a matching time or a re-pull.

| Ticker | Date shown | Price type shown | Dashboard price | Ground truth price | Source you used | Pass / Fail |
|---|---|---|---|---|---|---|
| NVDA | 2026-10-21 | close | 221.97 | 221.97 | https://finance.yahoo.com/quote/NVDA/history/ | Pass |
| NVDA | 2026-10-22 | close | 212.21 | 212.21 | https://finance.yahoo.com/quote/NVDA/history/ | Pass |
| NVDA | 2026-10-23 | close | 210.96 | 210.96 | https://finance.yahoo.com/quote/NVDA/history/ | Pass |
| NVDA | 2026-10-26 | close | 216.00 | 216.00 | https://finance.yahoo.com/quote/NVDA/history/ | Pass |
| NVDA | 2026-10-27 | close | 217.94 | 217.94 | https://finance.yahoo.com/quote/NVDA/history/ | Pass |
| NVDA | 2026-10-28 10:05 AM | intraday | 218.17 | 217.44 (10:12 AM EDT) | https://finance.yahoo.com/quote/NVDA/history/ | Fail (differs by 0.73, time not matched) |
| JPM | 2026-10-21 | close | 335.19 | 335.19 | https://finance.yahoo.com/quote/JPM/history/ | Pass |
| JPM | 2026-10-22 | close | 336.54 | 336.54 | https://finance.yahoo.com/quote/JPM/history/ | Pass |
| JPM | 2026-10-23 | close | 331.58 | 331.58 | https://finance.yahoo.com/quote/JPM/history/ | Pass |
| JPM | 2026-10-26 | close | 334.04 | 334.04 | https://finance.yahoo.com/quote/JPM/history/ | Pass |
| JPM | 2026-10-27 | close | 335.79 | 335.79 | https://finance.yahoo.com/quote/JPM/history/ | Pass |
| JPM | 2026-10-28 10:05 AM | intraday | 336.35 | 337.08 (10:11 AM EDT) | https://finance.yahoo.com/quote/JPM/history/ | Fail (differs by 0.73, time not matched) |
| ACN | 2026-10-21 | close | 240.26 | 240.26 | https://finance.yahoo.com/quote/ACN/history/ | Pass |
| ACN | 2026-10-22 | close | 258.74 | 258.74 | https://finance.yahoo.com/quote/ACN/history/ | Pass |
| ACN | 2026-10-23 | close | 249.37 | 249.37 | https://finance.yahoo.com/quote/ACN/history/ | Pass |
| ACN | 2026-10-26 | close | 247.23 | 247.23 | https://finance.yahoo.com/quote/ACN/history/ | Pass |
| ACN | 2026-10-27 | close | 235.16 | 235.16 | https://finance.yahoo.com/quote/ACN/history/ | Pass |
| ACN | 2026-10-28 10:05 AM | intraday | 243.20 | 245.33 (10:12 AM EDT) | https://finance.yahoo.com/quote/ACN/history/ | Fail (differs by 2.13, time not matched) |
| IREN | 2026-10-21 | close | 27.84 | 27.84 | https://finance.yahoo.com/quote/IREN/history/ | Pass |
| IREN | 2026-10-22 | close | 25.51 | 25.51 | https://finance.yahoo.com/quote/IREN/history/ | Pass |
| IREN | 2026-10-23 | close | 24.91 | 24.91 | https://finance.yahoo.com/quote/IREN/history/ | Pass |
| IREN | 2026-10-26 | close | 25.43 | 25.43 | https://finance.yahoo.com/quote/IREN/history/ | Pass |
| IREN | 2026-10-27 | close | 27.44 | 27.44 | https://finance.yahoo.com/quote/IREN/history/ | Pass |
| IREN | 2026-10-28 10:05 AM | intraday | 27.26 | 27.08 (10:12 AM EDT; page also showed 27.12) | https://finance.yahoo.com/quote/IREN/history/ | Fail (differs by 0.18, time not matched) |
| LLY | 2026-10-21 | close | 1270.75 | 1,270.75 | https://finance.yahoo.com/quote/LLY/history/ | Pass |
| LLY | 2026-10-22 | close | 1306.69 | 1,306.69 | https://finance.yahoo.com/quote/LLY/history/ | Pass |
| LLY | 2026-10-23 | close | 1273.46 | 1,273.46 | https://finance.yahoo.com/quote/LLY/history/ | Pass |
| LLY | 2026-10-26 | close | 1279.14 | 1,279.14 | https://finance.yahoo.com/quote/LLY/history/ | Pass |
| LLY | 2026-10-27 | close | 1281.91 | 1,281.91 | https://finance.yahoo.com/quote/LLY/history/ | Pass |
| LLY | 2026-10-28 10:05 AM | intraday | 1292.05 | 1,293.73 (10:11 AM EDT) | https://finance.yahoo.com/quote/LLY/history/ | Fail (differs by 1.68, time not matched) |

## B. Weekly change (one row per ticker)

The page computes this from the five closes. Pass if it is within 0.3 percentage points of
your own calculation: (last price minus the close five trading days earlier) divided by
that earlier close.

The page rule (read in weekChange): (last point minus first point) / first point, where the last point is BRIEF latest.price and the first is closes[0] (Oct 21), shown to one decimal. Oct 21 is five trading days before Oct 28. Ground truth last price is the Yahoo 10:12 AM quote (source https://finance.yahoo.com/quote/<TICKER>/history/ for each ticker).

| Ticker | Dashboard weekly change | Your calculation | Pass / Fail |
|---|---|---|---|
| NVDA | -1.7% = (218.17 - 221.97) / 221.97 = -1.71% | (217.44 - 221.97) / 221.97 = -4.53 / 221.97 = -2.04%; gap 0.33 pp | Fail (over 0.3 pp, driven by the intraday time mismatch) |
| JPM | +0.3% = (336.35 - 335.19) / 335.19 = +0.35% | (337.08 - 335.19) / 335.19 = 1.89 / 335.19 = +0.56%; gap 0.22 pp | Pass |
| ACN | +1.2% = (243.20 - 240.26) / 240.26 = +1.22% | (245.33 - 240.26) / 240.26 = 5.07 / 240.26 = +2.11%; gap 0.89 pp | Fail |
| IREN | -2.1% = (27.26 - 27.84) / 27.84 = -2.08% | (27.08 - 27.84) / 27.84 = -0.76 / 27.84 = -2.73%; gap 0.65 pp | Fail |
| LLY | +1.7% = (1292.05 - 1270.75) / 1270.75 = +1.68% | (1293.73 - 1270.75) / 1270.75 = 22.98 / 1270.75 = +1.81%; gap 0.13 pp | Pass |

## C. News grounding (one row per news item, three per ticker)

Open every link. Pass only if all four are true: the link opens, the headline matches the
article, the article date is within the last seven days, and the "why it matters" line is
supported by the article (not just plausible).

| Ticker | Headline (first few words) | Link opens | Headline matches | Dated within 7 days | "Why" is supported | Pass / Fail |
|---|---|---|---|---|---|---|
| NVDA | Nvidia to invest $3B in Meta's planned equity offering. Source https://stockanalysis.com/news/nvidia-3-billion-meta-offering/ | Yes | Yes | Yes, Oct 27, matches BRIEF | Yes: "intends to invest $3B in Meta's $37.5B stock sale"; partnership on Muse AI models. The "tying chip demand" clause is interpretation but the facts hold. | Pass |
| NVDA | Nvidia, Oracle expand NVIDIA Vera Rubin. Source https://www.tipranks.com/news/the-fly/nvidia-oracle-expand-nvidia-vera-rubin-to-multi-gigawatt-scale-thefly-news | Yes | Yes | Yes, Oct 27, matches BRIEF | Yes: general availability of Vera Rubin NVL72 and Vera CPUs on OCI | Pass |
| JPM | J.P. Morgan Asset Management Expands Access to Its Tokenized Money Market Funds on Solana. Source https://www.prnewswire.com/news-releases/jp-morgan-asset-management-expands-access-to-its-tokenized-money-market-funds-on-solana-302917188.html | Yes | Yes | Yes, Oct 22, matches BRIEF | Partly: qualified U.S. investors is supported, but "a small but growing business line" is not in the article (no size or growth figures) | Fail (why line has an unsupported claim) |
| ACN | Accenture awarded $151.46M Air Force task order. Source https://www.tipranks.com/news/the-fly/accenture-awarded-151-46m-air-force-task-order-thefly-news | Yes | Yes | Yes, Oct 27, matches BRIEF | Yes: sole-source, ICBM FENCES, $228M ceiling | Pass |
| ACN | Accenture downgraded to Neutral from Outperform at Baird. Source https://www.tipranks.com/news/the-fly/accenture-downgraded-to-neutral-from-outperform-at-baird-thefly-news | Yes | Yes | Yes, Oct 21 (exactly 7 days before asOf, inclusive), matches BRIEF | Yes: valuation cited as reason, stock "more than doubled since June" (article calls the multiple "reasonable") | Pass |
| IREN | IREN Stock Jumps on October 27. Source https://www.tipranks.com/news/iren-stock-jumps-on-october-27-heres-why | Yes | Yes | Yes, Oct 27, matches BRIEF | Yes: Anthropic IPO filing, customer link unconfirmed, down about 38% over the past month | Pass |
| IREN | Iren to advance Europe Ai ambitions with 300 MW Spanish campus. Source https://www.tipranks.com/news/the-fly/iren-to-advance-europe-ai-ambitions-with-300-mw-spanish-campus-thefly-news | Yes | Yes | Yes, Oct 21 (inclusive), matches BRIEF | Yes: roughly 300 MW, "initial operations targeted for 2028" | Pass |
| LLY | Lilly's Retatrutide Beats Ozempic 2 mg. Source https://www.prnewswire.com/news-releases/lillys-retatrutide-delivered-greater-a1c-reduction-and-more-than-double-the-weight-loss-of-ozempics-highest-approved-dose-in-head-to-head-trial-302921328.html | Yes | Yes in substance (BRIEF headline is a paraphrase of the longer PR Newswire title) | Yes, Oct 28, matches BRIEF | Yes: Phase 3 TRANSCEND-T2D-2, A1C 2.2% vs 1.8%, weight loss 19.5% to 20.9% vs 9.4% | Pass |
| LLY | Patrik Jonsson to retire after 36 years. Source https://www.prnewswire.com/news-releases/patrik-jonsson-to-retire-after-36-years-ilya-yuffa-named-president-lilly-global-markets-302921191.html | Yes | Yes | Yes, Oct 27, matches BRIEF | Yes: U.S. and international combine into Lilly Global Markets from Jan 1, 2027 | Pass |

News summary: 9 of 9 pass on link, headline and date; 1 failed on the "why" line. Dates of all items fall Oct 21 to Oct 28, inside the window. Several sources are aggregators (TipRanks and TheFly), as BRIEF itself notes.

(Add rows as needed. Fifteen items is normal for five tickers.)

## D. Calendar (one row per event)

Pass if the event and its date appear on the source linked, and the date is in the future
relative to the refresh date.

| Ticker | Event | Date shown | Confirmed on source | Pass / Fail |
|---|---|---|---|---|
| JPM (market-wide) | FOMC meeting Oct 27-28, no economic projections | 2026-10-28 | Yes, Fed's own calendar https://www.federalreserve.gov/monetarypolicy/fomccalendars.htm lists Oct 27-28 with no asterisk (no SEP). Date equals asOf, so not in the past. | Pass |
| LLY | Q3 2026 earnings, call 10:00 AM ET | 2026-10-29 | Seen only on a third-party copy, Finviz https://finviz.com/news/403165/lilly-confirms-date-and-conference-call-for-third-quarter-2026-financial-results-announcement (wording "will announce", headline "confirms", published Oct 15, so firm not tentative). Lilly's own pages https://investor.lilly.com/node/55096 and https://lilly.gcs-web.com/news-releases/news-release-details/lilly-confirms-date-and-conference-call-third-quarter-2026 returned 403, source unreachable. | Fail (company page not seen; date matches the copy) |
| IREN | Q1 FY27 results, call 5:00 PM ET | 2026-11-05 | Seen only on a Pluang repost https://pluang.com/en/news-feed/iren-rilis-hasil-q1-fy27-5-november-2026 (wording "will announce its financial results", firm). IREN's own page https://iren.gcs-web.com/news-releases returned 403, source unreachable. | Fail (company page not seen; date matches the copy) |

Calendar notes: no "expected" or "tentative" wording was found on any copy, so no confirmed-vs-expected failures. Both Fails are for sourcing only. A web search summary also reported both dates as company-confirmed, but I did not open a company page myself, so they stay Fail. NVDA, ACN have no events listed (BRIEF says so).

## E. Omissions

Did the agent miss something a human analyst would have included? List anything you found
in the ground-truth sources that the brief does not mention (a big headline, an earnings
date inside the window). Each one counts as a Fail in the score below.

- No omission search was done beyond the pages opened above; none noticed. Not a full omission audit.
- 

## F. Your own test cases

Write two tests of your own that none of the sections above cover. Examples students have
used: "the as-of date on the page matches the changelog date", "no ticker shows a flat
sparkline when the real stock moved", "the page still renders if I delete one ticker's
news list in the data". Write the test, run it, record the result.

| Test | How you checked | Pass / Fail |
|---|---|---|
| | | |
| | | |

## Score

| Section | Passes | Total | Rate |
|---|---|---|---|
| A. Prices | 25 | 30 | 83% |
| B. Weekly change | 2 | 5 | 40% |
| C. News | 8 | 9 | 89% |
| D. Calendar | 1 | 3 | 33% |
| E. Omissions (fails only) | 0 | | |
| F. Your own | | | |
| **Overall** | | | |

Publish only if A and B are 100% and C is at least 80% after fixes. If a row failed, tell
Claude exactly which row and what the correct value is, let it fix only that, rerun the
`qa-reviewer` agent, and regrade that row. Keep the original Fail in this file: a record of
what the agent got wrong is more useful than a clean sheet.
