# Remaining work

What is left after the first version of NetGraph Analyzer (merged to `main`, CI green, 354 tests in the latest full local run).
Owners follow the module split in `README.md`. Keep this file and `PROJECT_CONTEXT.md` in sync.

## Deployment completed

- [x] Confirm chosen host: Streamlit Community Cloud; Python 3.12, entrypoint `app.py`.
- [x] Pin the locally tested runtime dependencies; separate pytest into `requirements-dev.txt`.
- [x] Update GitHub Actions and add exact deployment/public verification instructions in `DEPLOYMENT.md`.
- [x] Exclude generated output from Git and refresh docs for the current UI.
- [x] Release checks: 354 tests passed; `pip check` found no broken requirements; diff whitespace check passed.
- [x] User authorized publishing; baseline remote commit preserved as `v1.0.0`.
- [x] Published reviewed changes after Linux CI; `v1.0.0` and `v1.1.0` are available.
- [x] Created user-owned public repository `Tanish-Parikh/NetGraph-Analyzer` and pushed main and both tags.
- [x] Completed Cloud sign-in and deployed `main` / `app.py` on Python 3.12.
- [x] Verified public costs, algorithm traces, failure counts, office sample and downloads; recorded the live URL in README.

Live app: https://netgraph-mpstme.streamlit.app/ — free Streamlit Community Cloud deployment.
The Linux cloud build and live browser checks both passed. Presentation-device checks remain separate.

## Remaining tasks

| # | Task | Owner | Notes |
|---|---|---|---|
| 1 | Deploy to Streamlit Community Cloud | Arjun | Done: https://netgraph-mpstme.streamlit.app/ |
| 2 | Put the verified public app link in `README.md` | Arjun | Done; runtime dependencies pinned and deployment checks recorded. |
| 3 | Final presentation-device check | All | Local baseline browser checks passed on 20 Oct (desktop and phone-size emulation); recheck the illustrated MPSTME version on the actual presentation laptop and phone. See `PROJECT_CONTEXT.md` §7. |
| 4 | Report (PDF) | Saiyam compiles, all write | Sections: modelling, properties, theory (cut and cycle property proofs), Kruskal, Prim, vulnerability, results, system design, complexity. Worked example and figures can come from the app's PNG export. |
| 5 | Slides | All | Same sections as the report, plus a demo script. |
| 6 | 2-minute backup screen recording of the demo | Arjun | Backup in case hosting is down. |
| 7 | Rehearsal (10 minutes, live demo plus backup) | All | |
| 8 | Final submission: report PDF, GitHub link, app link | Saiyam | |
| 9 | Second-reader review of each module | Tanish ↔ Saiyam ↔ Arjun | Rotation is in `README.md`. |

## Optional improvements (not required by the PRD)

- Show the "add back the cheapest links that close cycles" idea from the proposal (e.g. CR–SB) as a suggestion in the Vulnerability tab.
- Add a simple screenshot or GIF of the app to the README.

## Known limitations

- MPSTME illustrations are a schematic case study. Equipment, cable routes and costs are illustrative,
  not a surveyed floor plan, actual inventory, or a claim about MPSTME's production network.
- CSV escaping and decimal precision were fixed during release review, with a regression test.
  Upload UI was removed at the user's request; parser remains for samples/tests.

- Dates in the source documents (presentation 15 Oct 2026, submission 16 Oct) were already past when the code was written; re-check the real deadlines.
- Adjacency matrix and drawings are skipped above 200 devices, as the PRD specifies.
- The Streamlit interface itself has no browser-level automated tests, only headless `AppTest` smoke tests.

## Done

The core application, CI workflow, tests and documentation are implemented. At the user's request,
the original 12-device campus sample and optional theory-notes feature (FR-16) have been removed.
MPSTME and office samples remain. CSV upload UI, Hub column and Reference checks UI were also removed by request. See `PROJECT_CONTEXT.md` §2 and §4 for adjusted PRD coverage.
