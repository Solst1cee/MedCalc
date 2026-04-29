# MedCalc MVP

Mobile-first static PWA for quick bedside calculators with session memory.

## Run Locally

```powershell
python -m http.server 4173 --bind 127.0.0.1
```

Open:

```text
http://127.0.0.1:4173/
```

## Current Calculators

- Creatinine Clearance: Cockcroft-Gault with age, sex, weight, and serum creatinine.
- IV / Inotrope Infusion: two-way dose rate and infusion rate editor with draft drug presets, concentration presets, unit conversion, and warnings.
- Renal Drug Dose: demo renal dosing bands using saved CrCl.
- Reference: shows the draft infusion drug data used by the calculator.

Calculators update automatically once the required fields are filled. There is no calculate button in the current workflow.

The infusion drug data is intentionally structured as a draft scaffold. Verify and replace values with local protocol/reference data before clinical use.

## Layout

- Mobile: starts on the tool list, then opens each calculator as a sub-page with a back button.
- Desktop: keeps a scrollable tool panel on the left and a larger calculator panel on the right.

## Session Memory

Inputs and reusable outputs are stored in `sessionStorage`, so they last only for the current browser session. No patient identifiers are requested or stored.

Examples of reused values:

- weight
- serum creatinine
- calculated CrCl
- recently used infusion concentration

## Clinical Safety

This MVP is for workflow testing. Drug dose bands are placeholders and must be replaced with verified local protocols or references before clinical use.
