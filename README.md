# Rechnelia Legal Documents

This repository contains the legal documents for Rechnelia, a software product operated by **Mahdi Ghorban Pour - Digitexia**.

## Current Documents

| Document | Markdown | PDF | Changelog |
| --- | --- | --- | --- |
| Terms of Service | [Version 1.0.0](terms-of-service/Rechnelia-Terms-of-Service.md) | [Download](terms-of-service/Rechnelia-Terms-of-Service.pdf) | [History](terms-of-service/CHANGELOG.md) |
| Privacy Policy | [Version 1.0.0](privacy-policy/Rechnelia-Privacy-Policy.md) | [Download](privacy-policy/Rechnelia-Privacy-Policy.pdf) | [History](privacy-policy/CHANGELOG.md) |
| Data Processing Agreement | [Version 1.0.0](dpa/Rechnelia-DPA.md) | [Download](dpa/Rechnelia-DPA.pdf) | [History](dpa/CHANGELOG.md) |

Each directory contains a canonical Markdown file, its generated PDF, a changelog, and immutable versioned release snapshots under `archive/`.

## Build PDFs

```powershell
npm ci
./scripts/build-pdfs.ps1
```

Build one document with `./scripts/build-pdfs.ps1 -Document privacy-policy` (or `terms-of-service` / `dpa`). The build reads YAML metadata, creates a versioned Markdown snapshot if absent, and generates matching canonical and archived PDFs. Existing archive files are never overwritten.

Microsoft Edge is used by default. Set `PDF_BROWSER` to another Chromium-compatible executable if needed.

## Release Policy

1. Update and review the canonical Markdown.
2. Increment its version and update its dates.
3. Update the corresponding changelog.
4. Run the PDF build.
5. Verify canonical and archived pairs are byte-identical.
6. Never modify an existing archive release; issue a new version for corrections.

These documents are templates based on the application's implemented behavior. They should receive qualified legal review before production publication or acceptance.
