# pdf2data

[![PyPI version](https://badge.fury.io/py/pdf2data-tools.svg)](https://pypi.org/project/pdf2data-tools/)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Transforms PDF files into machine-readable JSON files. Extracts tables, figures, text blocks, metadata, and references from scientific papers and documents.

> **Note:** The repository is under active development for an article publication. Some errors are expected. Please report any issues on the [issues page](https://github.com/Pocoyo7798/pdf2data/issues).

## Installation

### From PyPI (recommended)

```bash
pip install pdf2data-tools
```

### With optional dependencies

```bash
# For the full PDF2Data pipeline (layout detection, OCR, etc.)
pip install pdf2data-tools[pdf2data_pipeline]
```

### From source (development)

```bash
conda create --name pdf2data python=3.10
conda activate pdf2data
git clone git@github.com:Pocoyo7798/pdf2data.git
cd pdf2data
pip install -e .
```

## Usage

### As a library

```python
from pdf2data.pdf2data_pipeline import PDF2Data

pipeline = PDF2Data(
    layout_model="DocLayout-YOLO-DocStructBench",
    input_folder="path/to/pdfs",
    output_folder="path/to/results",
)
```

### Command line

```bash
# Extract tables and figures
pdf2data_block path_to_folder path_to_results

# Extract text
pdf2data_text path_to_folder path_to_results

# Extract metadata
pdf2data_metadata path_to_folder path_to_results

# Extract references
pdf2data_references path_to_folder path_to_results
```

## License

Apache Software License 2.0
