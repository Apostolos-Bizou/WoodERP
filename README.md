# WoodERP — Σταύρακας Α.Ε. · ERP + CRM

**Codename:** WoodERP · **Πελάτης:** Σταύρακας Α.Ε. — Εμπόριο Ξυλείας, Λευκάδα
**Group lifecycle:** Φάση 1 — Mockup (Spec ✅ ολοκληρωμένο, mockup σε εξέλιξη)
**Status:** 🟡 Phase-1 mockup · fake data only · κανένα real backend/auth/PII
**Ημ/νία έναρξης:** 13 Ιουν 2026 · **v0.1**

## Τι είναι

Ενιαίο ERP + CRM που ψηφιοποιεί ένα εργοστάσιο/μάντρα ξυλείας που σήμερα δουλεύει
με χαρτί και «μνήμη στο μυαλό». Στόχος: να **ενισχύσει** τον υπάρχοντα τρόπο δουλειάς
και να επιστρέψει χρόνο στον CEO — όχι να αντικαταστήσει ένα σύστημα που ήδη αποδίδει.

Από τη συνέντευξη discovery (Κ. Σταύρακας · Κωνσταντίνα · Α. Καγκελάρης) βγήκαν 7 πόνοι:
ταμειακή ορατότητα (>30′/μέρα σε ~10 logins τραπεζών), μηδενική real-time εικόνα αποθήκης,
χάρτινη παραγγελιοληψία που «κάνει βόλτες», έλλειψη επιβεβαίωσης φόρτωσης, ανοργάνωτα
δρομολόγια/ETA, CRM-γνώση που ζει στο μυαλό ενός ανθρώπου, και custom κωδικοποίηση ξυλείας.

## 6 Modules (MVP)

1. **CRM & Πελάτης** — καρτέλα, ιστορικό, γρήγορη αναζήτηση
2. **Παραγγελιοληψία** — δελτίο on-the-spot σε tablet, κωδικοί + flex κωδικός για custom
3. **Εκτέλεση & Αποθήκη** — routing, picking, φόρτωση+φωτό, real-time stock
4. **Ταμειακή / Finance** — dashboard ροών, υποχρεώσεις, καρτέλα προς-πληρωμή
5. **Δρομολόγηση** — schedule ανά ζώνη/τονάζ/χωρητικότητα, αξιόπιστα ETA
6. **CEO Dashboard** — ενιαίο «terminal», KPIs

## Order state machine

`ΝΕΑ → ΔΡΟΜΟΛΟΓΗΜΕΝΗ → ΥΠΟ ΕΤΟΙΜΑΣΙΑ → ΦΟΡΤΩΘΗΚΕ → PENDING ΠΛΗΡΩΜΗΣ → ΠΛΗΡΩΘΗΚΕ (stock −) → ΚΛΕΙΣΤΗ`
(· ΑΚΥΡΩΘΗΚΕ μέχρι την πληρωμή). Το απόθεμα μειώνεται **μόνο** στη μετάβαση → ΠΛΗΡΩΘΗΚΕ.
Κάθε μετάβαση κρατά χρήστη + timestamp (audit trail).

## Δομή φακέλου

```
WoodERP/
├─ index.html        # Spec & Roadmap (το ίδιο με το docs, για GitHub Pages preview)
├─ docs/
│  └─ Stavrakas_ERP_CRM_Roadmap.html   # αρχικό spec/roadmap
├─ README.md
└─ CLAUDE.md
```

## Roadmap (Group lifecycle)

| Φάση | Παραδοτέο | Στόχος |
|---|---|---|
| 0 Discovery | Συνέντευξη & πόνοι | ✅ 100% |
| 1a Spec | User stories + data model | ✅ 100% |
| 1b Mockup | 5 οθόνες HTML (fake data) | 🟡 σε εξέλιξη |
| 2 Brand | Λογότυπο, παλέτα, typography | ⏳ |
| 3 Validation | Go/no-go από CEO | ⏳ |
| 4 Build | Vue 3 + Spring Boot + PostgreSQL (local) | ⏳ |
| 5 Production | Azure · real users | ⏳ |

## Επόμενα βήματα

5 οθόνες για το πρώτο mockup: CEO Dashboard · Δελτίο παραγγελίας (tablet) ·
Routing+Φόρτωση+φωτό · Λίστα Pending · Εικόνα Αποθήκης.

## Ανοιχτά ερωτήματα (πριν το engineering)

Λογιστικό σύστημα (integration;), τράπεζες (API aggregation;), policy κωδικοποίησης,
hardware/WiFi στους χώρους, offline λειτουργία, ρόλοι/δικαιώματα.

---
Next2Me Group · Phase 1 — Mockup
