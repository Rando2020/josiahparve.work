# josiahparve.work

Professional portfolio for Josiah Parve, a technical product operations and implementation leader focused on healthcare SaaS, governed delivery, analytics, automation, and cross-functional execution.

## Portfolio strategy

The site is designed as an evidence layer rather than a digital resume. It prioritizes:

- Measured impact above generic skills
- Three concise case studies
- Clear ownership, decisions, artifacts, and outcomes
- Public-safe examples with no employer, client, patient, PHI, PII, or proprietary data
- Fast, accessible static delivery with minimal JavaScript

## Local preview

```bash
python -m http.server 4173
```

Open `http://localhost:4173`.

## Deployment

The site is plain HTML, CSS, and JavaScript and can be published directly from the repository root with GitHub Pages.

1. Open repository Settings.
2. Select Pages.
3. Publish from the `main` branch and `/ (root)` folder.
4. Set the custom domain to `josiahparve.work`.
5. Verify the domain and enforce HTTPS after DNS resolves.

## Content governance

- Do not publish the private professional references document or reference contact details.
- Do not publish the current resume PDF because it contains a home address and phone number.
- Use a separate public resume with city/state, email, LinkedIn, and portfolio only.
- Keep all employer case studies generalized and supported by documented, aggregated outcomes.
- Never add client names, patient data, production screenshots, credentials, internal URLs, or proprietary workflows.

## Quality targets

- WCAG 2.2 AA
- Semantic HTML and keyboard navigation
- Respect `prefers-reduced-motion`
- Core Web Vitals targets: LCP at or below 2.5 seconds, INP at or below 200 ms, CLS at or below 0.1
- No third-party trackers by default
