# The California HIVer Project — website

Two-page static site for the California HIVer Project, a statewide ED-based
HIV testing data collaboration (CalEDHIV). Part of the HIVer Research Program,
Bennett Lab, Department of Emergency Medicine, Stanford University School of
Medicine. Supported by NIH/NIAID K08AI181642.

## Structure

- `index.html` — home page: mission, enrollment meter, county grid, steps.
- `need.html` — "The need": ED visit trend (HCAI 2005-2025) and 2024 payer mix.
  Chart data comes from `CalEDHIV/data/processed/chhs_statewide_ed_trend.csv`
  (built by `scripts/08_data_chhs_statewide_ed_trend.py`).

## Hosting

GitHub Pages, deploy-from-branch (main, root). Every push updates the live
site. Pages carry a noindex tag during the quiet-launch phase; remove it at
full launch.

## Editing rules

- The meter, county grid, and legend show real enrollment only. Update them
  together when a site joins.
- No Stanford marks in the banners. The Stanford Medicine logo appears only
  under "Collaborating institutions."
- Partner logos go up only with each institution's written permission.
