# 🤔 Alignment Principles

This document describes the alignment philosophy and structural decisions behind the **Biblical section** of the *Parallelium* corpus.  
These principles guide how multilingual verses are paired, structured, and normalized across diverse traditions.

The alignment design emphasizes **historical faithfulness**, **computational usability**, and **structural clarity**, while remaining transparent about limitations and manual interventions.

---

## 🧭 Anchor Text

The **Latin Vulgate** serves as the primary alignment anchor due to its historical centrality and relatively stable verse structure.

- When a Vulgate version is unavailable for a specific verse or book, alignment is still performed using available language pairs from other traditions.
- In cases where a verse diverges (e.g., follows the Septuagint tradition), a modified reference is assigned (e.g., `"3:03"`) to distinguish it from the Vulgate-based verse (`"3:3"`). This approach preserves valuable content without requiring a Latin version.

**Example:**

```json
{
  "book": "nehemiae",
  "ref": "3:3",
  "data": {
    "la_vulgate": "portam autem Piscium aedificaverunt filii Asanaa ...",
    "gr_lxx": null,
    "en_wycliffe": "Forsothe the sones of Asamaa bildiden the yatis of fischis ...",
    "es_e6e8": "los fijos de assnaa fizieron la puerta delos peces ..."
  }
},
{
  "book": "nehemiae",
  "ref": "3:03",
  "data": {
    "la_vulgate": null,
    "gr_lxx": "καὶ τὴν πύλην τὴν ἰχθυηρὰν ᾠκοδόμησαν υἱοὶ Ασανα· ...",
    "en_coverdale": "But the Fyshporte dyd the children of Senaa buylde ...",
    "es_arragel": "& la puerta de los pesçes edeficaron los fiios de çanaa ..."
  }
}
```
---

## 🔗 Minimum Pairing Requirement

A verse is included **only if** it has at least **one aligned counterpart** in another language or tradition.

- Books or verses that appear in only one tradition are excluded (e.g., *IV Esdras* in the Vulgate, *1 Esdras* in the Septuagint, or *3–4 Maccabees* in the Greek canon).
- The dataset focuses strictly on **comparative alignment** between at least two witnesses.

---

## 🧱 Structural Exclusions

Books with **major structural divergence** are excluded when reliable verse mapping would require extensive manual effort.

- Example: the Septuagint version of *Esther* differs significantly from the Vulgate and other witnesses, and was therefore excluded for now.

---

## ✋ Manual Alignment Adjustments

To maintain alignment consistency across divergent textual traditions, some verses required **manual intervention**, such as:

- Splitting a verse across multiple references  
- Shifting a phrase to an adjacent verse to preserve structural correspondence  

These interventions are based **strictly on attested content** — never on reconstruction or editorial invention.

> All manual operations are documented separately to ensure transparency and reproducibility.
