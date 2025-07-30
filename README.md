
<!-- GitHub banner -->
<p align="center">
  <img src="img/parallelium_banner_clean.png" alt="Parallelium – Aligned Scriptures Corpus banner" width="100%">
</p>

# 📖 Parallelium : an aligned scriptures dataset

> A multilingual corpus of aligned Biblical and Qur’anic texts — spanning medieval and modern languages — designed for computational and philological alignment tasks.  
> Serving as a benchmark dataset for multilingual alignment of historical religious texts.

## 📝 Description

*A multilingual dataset of aligned Biblical and Qur’anic texts, primarily in medieval languages, gathered from diverse external sources (see the 📂 Data Sources section). Selected modern editions are also included to enhance linguistic diversity and improve the robustness and generalizability of sentence alignment models.*

*The dataset is designed to support training and evaluation for historical, philological, and comparative linguistic applications.*


## 🎯 Project Scope

This dataset provides training data for multilingual alignment models. It includes over **48,000 aligned verses** and more than **4 million verse-level pairs**, covering **29 versions** in **9 languages**. The corpus spans both **medieval** and **modern** textual traditions.

It is intended as an **open and extensible training resource** for multilingual NLP — not a fixed benchmark. Future releases may include additional sources or metadata.

> 📌 Each aligned verse includes two or more versions. Pair counts reflect all _n choose 2_ language pairs per verse.

## 🌟 Goals and Audience

This dataset is designed to support the development and evaluation of **multilingual alignment models** tailored to historical texts — a domain often underserved by modern NLP resources.

Unlike standard parallel corpora, this dataset addresses challenges specific to historical-language contexts, including:

- Structural divergence across religious and textual traditions  
- Flexible or free word order in premodern languages  
- Non-standardized orthographies and inconsistent editorial practices  
- Gaps, mismatches, and overlaps in verse segmentation across versions  

By providing aligned data across a wide range of languages and periods, the corpus aims to:

- Enable **robust training** of alignment systems for historical and philological contexts  
- Support research on **translation shifts** and **textual transmission** across traditions  
- Serve as a **flexible foundation** for extended corpus-building, enrichment, or annotation  

### 🎯 Intended for:
- NLP researchers tackling low-resource or historical alignment  
- Digital humanists studying multilingual translation or textual variants  
- Scholars exploring transmission across religious and linguistic boundaries

## 📊 Dataset Overview

| Feature            | 📖 Biblia Corpus                                                                                   | 🕋 Qur’anic Corpus                                                                 |
|--------------------|---------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| **Text Types**     | Biblical texts (medieval and selected modern editions)                                            | Qur’anic translations in historical European languages and Arabic                 |
| **Languages**      | Latin, French, English, Castilian, Catalan, Italian, Portuguese, Greek                            | Arabic, Latin, English, French, Italian                                           |
| **Alignment Unit** | Verse-level (approximating sentence or clause)                                                    | Verse-level (based on surah:ayah structure)                                       |
| **Format**         | JSON                                                                                              | JSON                                                                              |
| **Use Case**       | Training multilingual alignment models *(not for textual criticism)*                              | Training multilingual alignment models *(not for religious or exegetical use)*    |
| **Aligned Verses** | 42,562                                                                                            | 6,236                                                                             |
| **Aligned Pairs**  | 3,927,811                                                                                          | 114,226                                                                           |



# 📂 Data Sources

The Biblical and Qur’anic texts were selected for their **structural compatibility** — namely, their verse-based (or surah:ayah in the case of the Qur’an) organization — and their widespread **cross-linguistic transmission**, which enables meaningful alignment across centuries and traditions.


### 🕰️ Medieval Bibles

| Language | Text                        | Source                                                                                                                                                                           | Format        |
|----------|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| en       | John Wycliffe Bible         | [GitHub](https://github.com/saibotsivad/john-wycliffes-bible/tree/master/raw-text)                                                                                              | `.txt`        |
| en       | Coverdale Bible             | [GitHub](https://github.com/Isidore-Guild/coverdale)                                                                                                                             | `.xml`        |
| en       | Great Bible                 | [EDGeS Corpus](https://spraakbanken.gu.se/en/resources/openedges)                                                                                                                | `.tsv`        |
| it       | Gospel of St. Matthew       | [Caterina Menichetti Edition](https://www.sismel.it/pubblicazioni/2059-il-vangelo-secondo-matteo-in-volgare-italiano-studio-ed-edizione-critica-delle-due-versioni-non-glossate)            | `.pdf`        |
| fr       | La Bible historiale         | [Project site](https://www.biblehistoriale.fr/index.php/xml-tei/)                                                                                                                | `.xml`        |
| fr       | Esther, Judith, Ruth        |Texts kindly provided by Claudio Lagomarsini                                                                                                                                                | Word\*        |
| fr       | Gospel of Matthew           |Transcription kindly provided by Seth Middleton                                                                                                                                                | `.txt`\*      |
| gr       | Septuagint (LXX)            | [Corpus Corporum](https://mlat.uzh.ch/browser?path=/17098/17099/17113/17110/17104)                                                                                               | `.xml`        |
| es       | Three Medieval Bibles       | [Proyecto Biblia Medieval](https://bibliamedieval.es/recursos/textos)                                                                                                            | `.txt`        |
| ca       | Three Medieval Bibles       | Texts kindly provided by Pere Casanellas [(Corpus Biblicum Catalanicum)](https://cbcat.abcat.cat/)                                                                                                       | `.xml`, Word\*|
| la       | Vulgata Sixto-Clementina    | [GitLab](https://gitlab.com/crosswire-bible-society/vulgate/-/blob/master/vulgate.osis.xml?ref_type=heads)                                                                      | `.xml`        |

> \* *These texts are not publicly shareable due to copyright restrictions.*

---

### 📅 Modern Editions

Nine Bibles in French, English, Portuguese, Greek, and Spanish from [this repository](https://github.com/thiagobodruk/bible), used to augment language diversity.

---

### 🕋 Qur’an

Multilingual alignment produced by the **[Coran 12-21](https://coran12-21.org/fr) project** — co-directed by **Mouhamadoul-Khaly Wélé and Tristan Vigliano** — covering 7 languages (Arabic, Latin, English, French, Italian, etc.), with texts kindly provided by Mouhamadoul-Khaly Wélé.
*Note: This resource is not publicly redistributable.*

---
## 📁 Data Format

The dataset is stored in structured JSON files:

- **Monolingual format**: dictionary of `{book → list of {ref, text}}`
- **Multilingual format**: list of aligned verses, each with `book`, `ref`, and a `data` map of translations

➡️ See [docs/data_structure.md](docs/data_structure.md) for full examples and schema.
