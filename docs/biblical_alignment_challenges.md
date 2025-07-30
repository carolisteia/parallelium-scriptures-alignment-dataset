# 🧩 Structural and Editorial Challenges in Aligning Biblical Texts
This document outlines the major challenges, limitations, and editorial decisions involved in constructing the **Biblical alignment section** of the *Parallelium* dataset.

Aligning Biblical texts at scale involves confronting the complex transmission history that spans religious traditions, languages, and manuscript cultures. This requires addressing significant structural and philological variation. These challenges include differences in book organization, verse numbering, canonical content, and translation lineage.

The alignment strategies described here aim to support **computational training and evaluation**, rather than scholarly critical editions or theological study. As such, certain compromises and simplifications were made to enable consistency, transparency, and reusability.

The following sections provide examples of structural divergence across traditions, justification for exclusion or realignment of specific books or verses, and a clear statement of the dataset's intended use and limitations.


## 🔍 Challenges

### 🤩 Source Heterogeneity

- While modern Bibles are widely available online, medieval versions are rare and often exist only in print or in inaccessible formats.

- Encoding inconsistencies and varying editorial conventions across sources require substantial normalization and preprocessing.

---

### ⚖️ Traditions and Variant Structures

- The texts in this dataset originate from multiple religious and textual traditions, requiring careful textual literacy to align responsibly.

- Canonical order and verse mapping vary significantly between traditions. Books may differ not only in name, but also in structure—being combined, split, reordered, expanded, or labeled differently across canons. These structural divergences directly influence alignment choices.

---

### 🧱 Representative Examples of Structural Differences

#### 📚 Combined vs. Separate Books

- In the Latin Vulgate, *Ezra* and *Nehemiah* appear as *1 Esdras* and *2 Esdras*.
- In the Septuagint, *1 Esdras* (*Esdras A*) is a distinct book that overlaps partially with *Ezra* and includes unique material (e.g., the “Three Bodyguards” episode).
- *2 Esdras* (*Esdras B*) in the Septuagint aligns more closely with the Hebrew and Latin narrative but uses a different naming convention.

#### ➕ Additions and Rearrangements

- The book of *Daniel* includes supplementary material such as *Susanna*, *Bel and the Dragon*, the *Prayer of Azariah*, and the *Song of the Three Young Men*.
- In the Septuagint, the *Prayer* and the *Song* are embedded in Daniel 3; in the Vulgate, they are often marked as separate insertions with distinct headings.

#### 🔢 Divergent Chapter and Verse Numbering

- Some traditions split or combine verses differently. For example, the *Epistle of Jeremiah* is presented as *Baruch 6* in the Vulgate.
- The *Psalms* are notoriously variable in numbering across Hebrew, Greek, and Latin versions, complicating verse-level mapping.

#### 🧾 Supplemental or Non-Canonical Additions

- *Psalmus 151* appears in the Septuagint and some Vulgate manuscripts, but it lacks a standardized placement and is often excluded from canonical Psalters.

Even when books are nominally shared, deep structural differences often prevent straightforward alignment. In such cases, editorial intervention—such as verse-splitting, segment reordering, or exclusion—may be required to ensure integrity and consistency.

---

## 🛠️ Use and Limitations

⚠️ This dataset is intended **exclusively for training and evaluation purposes** in computational and philological contexts.

It does **not preserve canonical verse numbering**, nor does it claim textual completeness or editorial neutrality. As such, it is **not suitable** for:

- Scholarly editions or critical apparatus  
- Canonical or liturgical citation  
- Fine-grained textual-critical analysis


➡️ Return to [Dataset Overview](dataset-overview.md)
