# josiahparve.work

Professional portfolio for Josiah Parve, a technical product operations and implementation leader focused on healthcare SaaS, governed delivery, analytics, automation, and cross-functional execution.

## Portfolio strategy

The site is designed as an evidence layer rather than a digital resume. It prioritizes:

- Measured impact above generic skills
- Three case studies anchored in business problems, decisions, artifacts, and outcomes
- A flagship Governed Delivery proof experience
- Clear ownership and honest AI-assisted engineering language
- Public-safe examples with no employer, client, patient, PHI, PII, or proprietary data
- Fast, accessible static delivery with minimal JavaScript

## Site structure

```text
.
├── index.html
├── styles.css
├── script.js
├── case-studies/
│   ├── governed-delivery.html
│   ├── governed-delivery.css
│   ├── healthcare-implementation.html
│   └── digital-governance.html
└── public/downloads/intelligent-services-demo/
    ├── synthetic-intake.md
    ├── readiness-scorecard.md
    ├── risk-register.csv
    ├── raci-matrix.csv
    ├── jira-import.csv
    ├── evidence-checklist.md
    ├── uat-plan.csv
    ├── go-no-go-summary.md
    └── post-launch-review.md
```

## Flagship case-study structure

`case-studies/governed-delivery.html` contains:

1. Executive Summary
2. The Operational Problem
3. Users and Stakeholders
4. Product Workflow
5. Product Walkthrough
6. Architecture
7. Governance Model
8. Decisions and Tradeoffs
9. Implementation Artifacts
10. Testing and Validation
11. Known Limitations
12. Enterprise Roadmap
13. My Role and Contribution
14. Live Demo and GitHub CTA
15. Related Case Studies

## Screenshot capture checklist

The walkthrough currently contains explicit public-safe placeholders. Replace each placeholder only with a screenshot captured from synthetic demo data.

- [ ] Messy synthetic intake loaded in the free-trial interface
- [ ] Readiness score showing 82 out of 100 and three mandatory blockers
- [ ] Detected platform stack showing Snowflake, dbt, MFT, Power BI, and REST API
- [ ] Launch blocker details with severity, owner, evidence, and required resolution
- [ ] Generated epic, story, and task hierarchy
- [ ] Jira or ADO dry-run export preview
- [ ] Evidence packet grouped by control domain and approval owner
- [ ] Final launch-readiness summary with resolved blockers and named human decision owners

Before publishing a screenshot:

- Confirm all names, organizations, identifiers, URLs, and data are synthetic.
- Crop out local paths, tokens, environment values, browser profiles, and notifications.
- Confirm no employer, customer, patient, PHI, PII, credential, or proprietary information is visible.
- Add useful alternative text when replacing the visual placeholder.
- Compress the image and record dimensions to avoid layout shift.

## Local preview

```bash
python -m http.server 4173
```

Open `http://localhost:4173`.

## Local validation

Run the static validation helper below from the repository root:

```bash
python - <<'PY'
from html.parser import HTMLParser
from pathlib import Path
from urllib.parse import urlparse

root = Path('.')
errors = []

class LinkParser(HTMLParser):
    def __init__(self):
        super().__init__()
        self.links = []
    def handle_starttag(self, tag, attrs):
        values = dict(attrs)
        if tag in {'a', 'link', 'script', 'img'}:
            target = values.get('href') or values.get('src')
            if target:
                self.links.append(target)

for html_file in root.rglob('*.html'):
    parser = LinkParser()
    parser.feed(html_file.read_text(encoding='utf-8'))
    for target in parser.links:
        parsed = urlparse(target)
        if parsed.scheme or target.startswith(('mailto:', '#')):
            continue
        relative = target.split('#', 1)[0].split('?', 1)[0]
        if not relative:
            continue
        resolved = (html_file.parent / relative).resolve()
        if not resolved.exists():
            errors.append(f'{html_file}: missing {target}')

for public_file in list(root.rglob('*.html')) + list((root / 'public').rglob('*')):
    if public_file.is_file() and '—' in public_file.read_text(encoding='utf-8', errors='ignore'):
        errors.append(f'{public_file}: contains an em dash')

if errors:
    raise SystemExit('\n'.join(errors))
print('Static link, download, and public-copy checks passed.')
PY
```

Manual checks:

- Keyboard through every navigation item, call to action, table, and download link.
- Confirm visible focus treatment and logical heading order.
- Test at 320 px, 375 px, 768 px, 1024 px, and 1440 px widths.
- Confirm workflow, artifact cards, tables, and screenshot slots stack without horizontal page overflow.
- Enable reduced-motion preferences and confirm no required information depends on animation.
- Open every proof artifact directly and confirm readable MIME behavior or download behavior.
- Validate structured data and metadata after deployment.

## Deployment

The site is plain HTML, CSS, and JavaScript and can be published directly from the repository root with GitHub Pages.

1. Open repository Settings.
2. Select Pages.
3. Publish from the `main` branch and `/ (root)` folder.
4. Set the custom domain to `josiahparve.work`.
5. Verify the domain and enforce HTTPS after DNS resolves.

## Privacy safeguards

- Do not publish the private professional references document or reference contact details.
- Do not publish the current resume PDF because it contains a home address and phone number.
- Use a separate public resume with city/state, email, LinkedIn, and portfolio only.
- Keep employer case studies generalized and supported by documented, aggregated outcomes.
- Use synthetic organizations, users, identifiers, data, requirements, and screenshots in public proof artifacts.
- Never add client names, patient data, production screenshots, credentials, internal URLs, tokens, local environment values, or proprietary workflows.
- Do not imply legal advice, regulatory certification, production readiness, or autonomous authority for high-risk decisions.

## Quality targets

- WCAG 2.2 AA
- Semantic HTML and keyboard navigation
- Respect `prefers-reduced-motion`
- Core Web Vitals targets: LCP at or below 2.5 seconds, INP at or below 200 ms, CLS at or below 0.1
- No third-party trackers by default
- No unnecessary runtime dependencies
- No em dashes in public copy

## Definition of done

The flagship proof phase is complete when:

- [x] All required case-study sections are present.
- [x] Deterministic logic, AI assistance, human authority, and output boundaries are visibly differentiated.
- [x] The current maturity and known limitations are stated without overstating production readiness.
- [x] Nine synthetic downloadable implementation artifacts are available.
- [x] Homepage, flagship page, footer, and related case studies provide internal links.
- [x] Case-study structured metadata and canonical information are present.
- [x] Public copy contains no em dashes.
- [x] Static local links and download paths pass validation.
- [ ] Eight public-safe screenshots replace the labeled placeholders.
- [ ] A deployed public demo is available, or the page continues to state that local run instructions are the current access path.
- [ ] Manual keyboard, mobile, reduced-motion, and deployed structured-data testing is completed and documented in the pull request.
