# 🧱 Data Structure

This document describes the data format used throughout the **Parallelium** dataset, including both monolingual and multilingual alignment files.  
All data is stored in structured **JSON** to ensure maximum portability and ease of integration in computational pipelines.

The structure is designed to:

- Be easy to parse with standard JSON tools (e.g., `json` module in Python, `pandas`, `jq`, etc.)
- Preserve verse-level alignment across versions
- Handle missing or partial data gracefully

---

### 📘 Monolingual JSON

Each monolingual file is a **JSON dictionary**, where each key is a biblical book name (in lowercase Latinized form), and each value is a list of verse objects.  
Each object contains:

- `ref`: a string verse reference in `chapter:verse` format (e.g., `"1:1"`)
- `text`: the full verse text, unsegmented

Example:

```json
{
  "malachias": [
    {
      "ref": "1:1",
      "text": "Carga dela palabra del sennor a israel en mano de malechias:"
    }
  ]
}
```

### 🌍 Multilingual JSON

Multilingual aligned files are stored as a **list of dictionaries**.  
Each dictionary represents a single aligned verse and contains the following fields:

- `book`: the book name (`"genesis"`, `"isaiae"`, etc.)
- `ref`: the verse reference in `"chapter:verse"` format (e.g., `"1:2"`)
- `data`: a nested dictionary mapping **version IDs** to their corresponding translation strings,  
  or `null` if no version is available for that verse.

Example:

```json
[
  {
    "book": "genesis",
    "ref": "1:2",
    "data": {
      "la_vulgate": "terra autem erat inanis...",
      "gr_lxx": "ἡ δὲ γῆ ἦν ἀόρατος...",
      "en_coverdale": "...",
      "fr_historiale": "...",
      "it_beta": null
    }
  }
]
```

### 📘 Structure Summary

| Format               | Structure                            | Scope               | Use Case                     |
|----------------------|---------------------------------------|----------------------|------------------------------|
| **Monolingual JSON** | `{ book: [ {ref, text} ] }`          | One language         | Intermediate/raw input       |
| **Multilingual JSON**| `[ {book, ref, data} ]`              | Aligned versions     | Final aligned corpus         |

**Field Definitions:**

- `book`: Book name (in lowercase)  
- `ref`: Canonical verse reference in `chapter:verse` format  
- `data`: Dictionary mapping version IDs to verse text (or `null` if missing)


