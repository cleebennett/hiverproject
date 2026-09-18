# The California HIVer Project — website

Single-page static site for the California HIVer Project, a statewide ED-based
HIV testing data collaboration (CalEDHIV). Part of the HIVer Research Program,
Bennett Lab, Department of Emergency Medicine, Stanford University School of
Medicine. Supported by NIH/NIAID K08AI181642.

## Structure

- `index.html` — the whole site. All CSS is inline. The Stanford Medicine logo
  is embedded as a data URI (used with permission; see
  `CalEDHIV/website/logos/permissions.csv` in the project archive).

## Deploy

Hosted on Cloudflare Pages, connected to this repository. Every push to `main`
redeploys automatically. During the preview phase the site sits behind a
Cloudflare Access policy (email allowlist).

## Editing rules

- The meter, county grid, and legend show real enrollment only, and must be
  updated together (see "How to add a participating site" below).
- No Stanford marks in the banners. The Stanford Medicine logo appears only
  under "Collaborating institutions."
- Partner logos go up only with each institution's written permission.

## How to add a participating site

Each participating ED changes five things in `index.html`. Keep them consistent.

1. **The meter count.** Find `<span class="n num">0</span>` in the hero and
   raise the number by one for each ED that has contributed data.
2. **The county count.** In the same line, the second number is the count of
   DISTINCT counties with at least one contributing ED.
3. **The bar.** In the `<style>` block, `.fill{ ... width:0%; ... }` — set
   width to (EDs / 310) as a percent, e.g. 5 EDs = 1.6%.
4. **The county square.** Every square carries its county name:
   `<div class="cty" title="Fresno"></div>`. For a county with a contributing
   ED, change its class to `cty on`. For a county only in conversation,
   change it to `cty part`. Search the county name to find the square.
5. **The legend.** Update the three numbers: Contributing (n counties),
   In conversation (n counties), Not yet (58 minus the other two).

Then commit and push. The live site updates in about a minute.

Sites are counted anonymously on the page. Naming an ED publicly, or adding
its logo under "Collaborating institutions," requires that institution's
written permission first.
