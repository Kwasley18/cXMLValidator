# Coupa cXML & Global E-Invoicing Validator (Work in progress)

A browser-based tool for procurement and AP integration teams. It does two things:

1. Validates Coupa cXML invoices before transmission, catching the structural issues that cause 400/403/406 rejections.
2. Analyzes regional e-invoicing formats from eight countries, translating local field names into English and checking against each country's schema.

**Early draft / work in progress.** The cXML side is functional but rule coverage is still growing. The regional compliance side covers 8 countries with more planned.

**[Live demo](https://Kwasley18.github.io/cXMLValidator/)**

## Coupa cXML validator

Paste a cXML invoice and get a grouped report covering XML structure (well-formedness, DOCTYPE, DTD, encoding), payload metadata (`payloadID`, ISO 8601 timestamps), header and authentication blocks, invoice header fields, and the common triggers behind 400/403/406 errors. Each finding is color-coded with a short explanation of why it matters.

## Regional compliance validator

Auto-detects the format, validates required fields per the country's spec, and shows local field names alongside English translations. Currently supports:

- Poland (KSeF FA(3))
- Mexico (CFDI 4.0)
- Romania (CIUS-RO)
- Serbia (SEF UBL 2.1)
- Germany (X-Rechnung)
- Norway (EHF)
- Denmark (OIOUBL)
- Generic PEPPOL UBL

Includes math reconciliation on totals and bundled sample payloads.

## Planned

Deeper Coupa line-item rules, support for order responses and ship notices, more countries (France, Italy, Spain, India), cross-format conversion.

## Tech

Single-file HTML, vanilla JavaScript, no dependencies, no build step. Runs entirely in the browser — no payload data leaves the user's machine.
