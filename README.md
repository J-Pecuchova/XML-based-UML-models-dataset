# Diagrammatic dataset on AI-generated formative feedback for XML-based UML models (Data in Brief)

**DOI:** 10.5281/zenodo.19037343

This repository provides the following files and folders:

- **`student_data25.csv`** — anonymized student-level dataset with demographic indicators, quiz/exam performance, and course outcomes.
- **`feedback_data25.csv`** — dataset containing teacher-generated and AI-generated formative feedback linked to UML modeling assignments.
- **`xml_models/`** — original UML model exports from Enterprise Architect in XML format, used as the primary input for AI-based evaluation.
- **`images/`** — PNG renderings of the UML models, included for visual reference and transparency.


### Folder structure

```text
.
├── student_data25.csv
├── feedback_data25.csv
├── xml_models/
│   ├── E0A1/
│   ├── E0A2/
│   ├── E0A3/
│   ├── E0A4/
│   ├── S0U1/
│   ├── S0U2/
│   ├── S0U3/
│   └── S0U4/
└── images/
    ├── E0A1/
    ├── E0A2/
    ├── E0A3/
    ├── E0A4/
    ├── S0U1/
    ├── S0U2/
    ├── S0U3/
    └── S0U4/
```

Files in `xml_models/` and `images/` follow the pattern:

`<StudentID>_<diagram_type>.<extension>`

Examples:

- `290125_class.xml`
- `290125_class.png`

where:

- `StudentID` = anonymized student identifier
- `diagram_type` = UML diagram type such as `class`, `activity`, `usecase`, etc.
- `extension` = `xml` for Enterprise Architect export, `png` for rendered image

Subfolder names indicate assignment/exam group:

- `S0U1`–`S0U4` = semester UML assignments
- `E0A1`–`E0A4` = exam UML assignments

## File format notes

Both CSV files are:

- comma-separated (`sep=','`)
- UTF-8 encoded
- suitable for loading with standard spreadsheet tools or `pandas`

## Loading with Python (pandas)

```python
import pandas as pd

student_df = pd.read_csv("student_data25.csv", sep=",", encoding="utf-8")
feedback_df = pd.read_csv("feedback_data25.csv", sep=",", encoding="utf-8")
```

Due to repository size constraints only a small representative subset of images may be included directly in the repository for preview and reference purposes. 

> [!IMPORTANT]
> The complete PNG image archive is distributed separately as `images.zip` in Release `v1.0.0`.
