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
├─ index.html                         # GitHub Pages entry = τελευταίο roadmap (v4)
├─ docs/
│  ├─ roadmap/                         # το οπτικό HTML roadmap
│  │  ├─ Stavrakas_ERP_CRM_Roadmap.html      # canonical (latest)
│  │  └─ versions/                           # ιστορικό εκδόσεων
│  │     ├─ ..._Roadmap_v1_2026-06-13_1428.html
│  │     ├─ ..._Roadmap_v2_2026-06-13_1452.html
│  │     ├─ ..._Roadmap_v3_2026-06-13_1519.html
│  │     └─ ..._Roadmap_v4_2026-06-13_1554.html
│  └─ spec/                            # το κειμενικό spec
│     ├─ Stavrakas_ERP_CRM_Spec.md           # canonical (latest)
│     └─ versions/
│        └─ Stavrakas_ERP_CRM_Spec_v0.1_2026-06-13.md
├─ README.md
└─ CLAUDE.md
```

> Εκδόσεις: κάθε τύπος παραδοτέου (roadmap HTML / spec MD) έχει το δικό του canonical
> «latest» + `versions/` με date-stamped ιστορικό. Το `index.html` (root) είναι αντίγραφο
> του τελευταίου roadmap, απαραίτητο ως είσοδος του GitHub Pages.

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
