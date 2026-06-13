# CLAUDE.md — WoodERP

Συμβάσεις για το project WoodERP (Σταύρακας Α.Ε. ERP+CRM). Διάβασέ το πριν δουλέψεις εδώ.

## Ταυτότητα
- **Codename:** WoodERP · **Πελάτης:** Σταύρακας Α.Ε. (εμπόριο ξυλείας, Λευκάδα)
- **Group lifecycle phase:** Φάση 1 — Mockup (Spec ✅, mockup σε εξέλιξη)
- **GitHub:** `Apostolos-Bizou/WoodERP` (public) · GitHub Pages preview από `index.html`
- **Local archive:** `C:\Users\akage\Documents\Projects\WoodERP`

## Δομή αρχείων & εκδόσεις
- `index.html` (root) = GitHub Pages entry, αντίγραφο του τελευταίου roadmap.
- `docs/roadmap/` → canonical `Stavrakas_ERP_CRM_Roadmap.html` + `versions/` (date-stamped ιστορικό).
- `docs/spec/` → canonical `Stavrakas_ERP_CRM_Spec.md` + `versions/` (date-stamped ιστορικό).
- **Κανόνας έκδοσης:** νέα έκδοση → ενημέρωσε canonical (+ root index.html για roadmap) ΚΑΙ πρόσθεσε date-stamped αντίγραφο στο αντίστοιχο `versions/`. Ποτέ μην σβήνεις παλιές εκδόσεις.

## Κανόνες φάσης (group-lifecycle)
- Είμαστε σε **Φάση 1**: single-file HTML mockups, **fake data μόνο**.
- ❌ ΟΧΙ real backend, ❌ ΟΧΙ real auth, ❌ ΟΧΙ PII, ❌ ΟΧΙ custom domain, ❌ ΟΧΙ real users.
- Group Standard stack (Vue 3 + Spring Boot + PostgreSQL) μπαίνει από **Φάση 4** — όχι τώρα.
- Πριν περάσουμε φάση: ρητό go/no-go από τον CEO (Φάση 3 gate).

## Πρώτο mockup — scope (5 οθόνες)
CEO Dashboard · Δελτίο παραγγελίας (tablet) · Routing+Φόρτωση+φωτό · Λίστα Pending · Εικόνα Αποθήκης.
Εκτός 1ου mockup: Δρομολόγηση (Epic E), finance βάθος (D3-D4), production queue (C8), σχέδια (B5 placeholder).

## Domain σημειώσεις
- Κωδικοποίηση: Μελαμίνες = αυστηροί κωδικοί · ξυλεία = custom/ελεύθερη περιγραφή. ΟΧΙ υπερ-κωδικοποίηση.
- Απόθεμα μειώνεται **μόνο** στη μετάβαση → ΠΛΗΡΩΘΗΚΕ. Ακύρωση επιτρέπεται μέχρι την πληρωμή.
- Κάθε μετάβαση κατάστασης: χρήστης + timestamp (audit trail).

## Cross-references (Group skills)
`group-lifecycle` · `project-router` · `project-filing` · `group-stack-conventions` (Φάση 4+) · `change-management` (μετά το production).
