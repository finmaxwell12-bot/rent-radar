# Rent Radar

A working, browser-local Southampton student-housing prototype.

## Run locally — the same way as StudySpot

1. Extract this ZIP.
2. Open the RentRadar folder in VS Code or another editor.
3. Run this command inside RentRadar:

       python -m http.server 8000

4. Open http://localhost:8000 in your browser. Stop the server with Ctrl+C.

Alternatively use VS Code Live Server. No npm packages, API keys or build step
are required. Use the local server for PDF imports; opening index.html directly
can cause browser restrictions when loading the PDF reader module.

## Upload to a static host

Upload the contents of RentRadar so index.html is at the website root.
If selecting a project root, select the folder containing index.html.
There is no build step and no dist folder in this download.
A browser certificate warning is a separate domain/connection issue; changing
this folder layout cannot guarantee a fix for that warning.

## Included features

- Search, filters, saved homes, comparison and a housing budget planner.
- Fair-price badges based on median all-in costs in the sample dataset, with neighbourhood
  comparisons where at least two other homes are present and wider-sample fallback.
- Search alerts and in-app matches, including when a new local demo listing is added.
- PDF, DOCX, TXT and pasted contract input, processed locally; source-referenced clause
  extraction and a one-page A4 PDF export. Text stays in memory rather than local storage.
- Student profile verification request flow, and a clearly labelled fictional verified profile.
- Fictional tenancy-confirmed review examples and local review submissions pending checks.
- Landlord/agent workspace with local listing creation, sample student directory and enquiry drafts.
- University insights with neighbourhood filtering, sample medians and CSV export.

## Scope and limits

This is a prototype, not a connected rental marketplace. Student and tenancy verification
are demonstration workflows, not real identity checks. No email, SMS, push, background
monitoring, payment, live property feed, shared database or message delivery is connected.
Landlord listings, alerts, profiles, review requests and drafts remain on the same browser
where local storage is available. Partner workspaces are demo pages, not authenticated portals.

The contract tool is a deterministic extractive clause finder, not AI interpretation or
legal advice. It keeps original wording, shows source references, flags selected keywords
and labels unmatched topics. It may miss clauses, conditions or exceptions. Read the full
original document. PDF exports are deliberately limited to one page and may shorten passages;
the interactive source panel retains matching passages. Scanned PDFs need OCR first.
Limits: 5 MB, 60 PDF pages, 250,000 characters. DOCX references use paragraphs/clauses rather
than original Word page numbers. PDF references use extracted page and clause numbers.

Live deployment would require licensed data feeds, server-side authentication and permissions,
a verification provider, moderation, consent controls, a database and notification delivery.
The app does not ask for API keys or identity-document uploads.

## Files — StudySpot-style layout

- index.html: app shell and navigation
- style.css: responsive design
- app.js: all sample data, pages, contract extraction and interactions
- assets/: Rent Radar logo and illustrative photographs
- vendor/: document readers, PDF writer and their licence notices
- README.md: startup instructions and prototype limitations

The contract extractor, base app and additional workspaces are combined in
app.js. Existing source behaviour is retained; this is a packaging change.

## Third-party assets

The user supplied the logo. Example student-house photographs come from Portswood Student Houses:
https://portswoodstudenthouses.co.uk/about/shakespeare-avenue/
Photos show a separate example property. The fictional listings, prices and reviews do not
represent the photographed home. Copyright remains with the photographer/publisher; this
source export does not grant additional image rights.

Bundled open-source libraries:
- PDF.js / pdfjs-dist 5.4.296, Apache 2.0: https://github.com/mozilla/pdf.js
- Mammoth 1.10.0, BSD 2-Clause: https://github.com/mwilliamson/mammoth.js
- jsPDF 3.0.3, MIT: https://github.com/parallax/jsPDF
Preserve bundled licence notices when redistributing.
