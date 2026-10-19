Identity Decision Lab
A personal product marketing work demonstration for John Miranda. It simulates the business trade-offs of identity-risk decision policies, then produces an editable buyer brief. It is independent and unaffiliated with any employer or vendor.
Open
Extract the folder and double-click index.html. No installation, account, backend, or API key required. Or run `python3 -m http.server 8878 --bind 127.0.0.1` and open http://localhost:8878.
Demonstration
Set a scenario and explicit economics/review assumptions.
Compare two approve/review/decline threshold policies on the same 1,000 synthetic applications.
Inspect legitimate approvals, fraudulent approvals, direct declines, abandonment, review workload, and modeled contribution.
Switch between fraud, growth, and finance buyer perspectives.
Edit and export the buyer brief; export the synthetic cohort to inspect routing.
An effective interview demonstration: compare a more permissive policy with a stricter one, explain the cost of false positives and missed fraud, change loss assumptions, and show how the interpretation changes. Discuss the evidence required before making a vendor or customer claim.
What it demonstrates
Buyer education, technical-to-commercial translation, scenario analysis, trade-offs, sales discovery, and evidence-based positioning. These are adjacent to John's enterprise AI marketing, launch, and sales enablement experience. This is new personal work, not a past employer project or proof of historical ownership or revenue.
Socure's public Sigma Identity Fraud overview describes fraud prevention, legitimate-customer approvals, and manual review efficiency: https://www.socure.com/products/sigma-identity-fraud (reviewed October 18, 2026). The simulation explores that category tension; it does not reproduce any Socure model, data, score, product, or benchmark. No claims are made about Socure performance.
Method
Fixed pseudorandom seed 42617. Exactly 50 fraud/950 good applications in the standard scenario, or 150 fraud/850 good under attack. Good scores are 100U^1.8; fraud scores are 100(1-U^1.8). Scores overlap and are not calibrated probabilities. Labels are generated before scores; this is a toy simulation, not learned prediction. Synthetic IDs identify records only.
Approve when score < low. Decline when score >= high. Review otherwise. Review catches the chosen share of reviewed fraud; uncaught fraud is approved. The chosen share of reviewed good applicants abandons; remaining reviewed good applicants are approved. Fractional values are expected outcomes.
Net contribution = approved good * contribution - approved fraud * loss - reviewed count * review cost. This omits vendor fees, review delay/capacity, customer lifetime effects, compliance constraints, label delay, drift, and fairness analysis. All review cases incur cost, including abandonment. No production recommendation or universal best policy is implied. Do not enter real identity information.
Files and testing
index.html: workflow. style.css: responsive office UI. app.js: deterministic simulation and exports. tests/model.test.cjs: conservation and hand-calculated outcome checks.
Run `node tests/model.test.cjs` and `node --check app.js`.
All processing is in memory in the browser. No analytics, storage, model API, or outbound requests. Leaving/reloading loses edits unless downloaded. Changes to assumptions require rebuilding; opening the story step regenerates its draft. Download edits before revisiting it.
Repository
No remote or push is configured. John can review the project, initialize Git if using the ZIP, make his own first commit, and publish it himself. For static hosting, upload index.html, style.css, and app.js; no build command required.
