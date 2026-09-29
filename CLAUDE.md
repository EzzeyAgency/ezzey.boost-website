# BOOST static site

Plain static HTML deployed by Vercel from `main`. Each page is a self-contained `.html` file at the repo root with its own inline CSS; there is no shared include or build step.

## Rule: "Featured In" section (required on every marketing page)

Every page that shows the "Featured In" section must use the linked version below, exactly as `index.html` has it. This applies to every page created from now on (2026-09-29 onward), not just existing ones.

- Each outlet name is a link to the article, opening in a new tab (`target="_blank" rel="noopener"`).
- All six outlets are included, in this order: Forbes, Entrepreneur, MarketingProfs, MarTech.zone, CEOWORLD magazine, Total Retail.
- When creating a new page (usually by copying an existing page), keep this block and its CSS intact.
- When an outlet or URL changes, update it on every page that has the section in the same commit, so all pages stay identical.
- `terms.html` is intentionally excluded (legal page, no Featured In section).

Check all pages match:

```sh
for f in *.html; do echo "$f $(grep -A10 '<div class="featured">' "$f" | md5sum)"; done
```

### Markup

```html
      <div class="featured">
        <p class="label">FEATURED IN</p>
        <div class="logos">
          <a class="logo-forbes" href="https://www.forbes.com/sites/rhettpower/2022/08/14/4-website-errors-your-company-cant-afford-to-make/" target="_blank" rel="noopener">Forbes</a>
          <a class="logo-ent" href="https://www.entrepreneur.com/growing-a-business/how-to-build-the-infrastructure-needed-to-scale-your-company/438387" target="_blank" rel="noopener">Entrepreneur</a>
          <a class="logo-mp" href="https://www.marketingprofs.com/articles/2022/48354/digital-marketing-campaign-budgets" target="_blank" rel="noopener"><span class="tri">&#9654;</span>MarketingProfs</a>
          <a class="logo-mt" href="https://martech.zone/author/rbodey/" target="_blank" rel="noopener">MarTech.zone</a>
          <a class="logo-ceo" href="https://ceoworld.biz/2022/06/24/4-growth-hacking-moves-to-replace-your-traditional-marketing-tactics/" target="_blank" rel="noopener">CEOWORLD magazine</a>
          <a class="logo-tr" href="https://www.mytotalretail.com/article/build-grow-and-scale-your-way-to-e-commerce-experience-success/" target="_blank" rel="noopener">Total Retail</a>
        </div>
      </div>
```

### CSS (in the page's `<style>`)

```css
.featured{text-align:center;}
.featured .label{
  color:#8A9098;font-weight:600;font-size:12px;
  letter-spacing:3px;margin-bottom:26px;
}
.featured .logos{
  display:flex;justify-content:center;align-items:baseline;
  gap:52px;flex-wrap:wrap;color:#7C838B;
}
.logo-forbes{font-family:Georgia,'Times New Roman',serif;font-weight:700;font-size:26px;letter-spacing:0.5px;}
.logo-ent{font-family:Georgia,'Times New Roman',serif;font-weight:700;font-style:italic;font-size:26px;}
.logo-mp{font-weight:700;font-size:16px;}
.logo-mp .tri{color:#7C838B;font-size:12px;margin-right:4px;}
.logo-mt{font-weight:700;font-size:17px;}
.logo-ceo{font-weight:700;font-size:15px;}
.logo-tr{font-weight:700;font-size:17px;}
.featured .logos a{color:inherit;text-decoration:none;transition:color .2s;}
.featured .logos a:hover,.featured .logos a:hover .tri{color:var(--heading);}
```

Mobile (inside the existing small-screen media query): `.featured .logos{gap:28px;}`
