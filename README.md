# Dubai IT Support Jobs — Tracker (internal, dedup memory only)

Not meant for browsing. This repo exists so a daily scheduled cloud agent has persistent memory across runs, since each cloud-agent session starts fresh with no history otherwise.

- `jobs.json` — canonical list of every job posting link ever reported to Telegram, one object per posting: `{link, company, zone, title, date_found}`. The daily agent reads this first, skips any `careers_url`-derived posting whose exact link is already in here, and only Telegrams + appends genuinely new postings.
- `zones/*.json` — the target-company list per Dubai zone/weekday, each entry: `{company, description, careers_url, zone_evidence}`. Built via real web research (verified companies + working careers URLs), not guessed. One file per weekday zone:
  - `monday_downtown_difc_businessbay.json`
  - `tuesday_deira_burdubai_creek.json`
  - `wednesday_szr_tradecentre.json`
  - `thursday_mediacity_internetcity_tecom.json`
  - `friday_jlt_dmcc.json`
  - `saturday_alquoz_dip_jafza.json`
  - `sunday_jumeirah_marina_jbr.json`

Human-facing output is a Telegram message, not this repo. See the AyoubOS vault note `03 Projects/Job Search - IT Support Dubai.md` for the full plan and schedule.
test push access
