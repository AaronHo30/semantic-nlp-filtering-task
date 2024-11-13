# Semantic NLP Filtering for Deep Learning Papers in Virology/Epidemiology

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.15.14-blue)](https://www.python.org/downloads/release/python-31014/)
[![CI Status](https://github.com/AaronHo30/semantic-nlp-filtering-task/actions/workflows/ci.yml/badge.svg)](https://github.com/AaronHo30/semantic-nlp-filtering-task/actions)

## Table of Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Dataset](#dataset)
- [Approach](#approach)
  - [NLP Techniques](#nlp-techniques)
  - [Advantages Over Keyword-Based Filtering](#advantages-over-keyword-based-filtering)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
- [Development Setup](#development-setup)
  - [Setting Up Pre-Commit Hooks](#setting-up-pre-commit-hooks)
- [Continuous Integration](#continuous-integration)
  - [CI Configuration](#ci-configuration)
  - [Commit Message Guidelines](#commit-message-guidelines)
- [Results](#results)
- [License](#license)
- [Contact](#contact)

## Overview

This project offers a semantic NLP filtering framework for academic papers
focused on deep learning applications in virology and epidemiology. Using
advanced yet lightweight NLP techniques, it efficiently selects relevant
papers, categorizes findings, and extracts specific deep learning
methodologies.

## Objectives

- **Filtering**: Use semantic NLP to exclude papers unrelated to deep learning
  in virology or epidemiology.
- **Classification**: Organize relevant papers into four categories:
  `text mining`, `computer vision`, `both`, or `other`.
- **Method Extraction**: Detect and extract specific deep learning methods
  mentioned in relevant papers.

## Dataset

The dataset includes metadata and abstracts for 11,450 research papers from
PubMed, curated for deep learning applications in virology. Download it from
[this repository](https://github.com/jd-coderepos/virology-ai-papers/) and
place it under the `data/raw/` directory.

- **Fields**: Records include title, abstract, authors, and publication date,
  processed for filtering and categorization.

## Approach

### NLP Techniques

This project utilizes an optimized set of NLP techniques focused on semantic
accuracy and computational efficiency:

- **Topic Modeling**: Identifies primary topics for each paper.
- **Named Entity Recognition (NER)**: Detects key entities and methods
  mentioned.
- **Semantic Similarity**: Measures the semantic relevance of abstracts
  against predefined criteria.

### Advantages Over Keyword-Based Filtering

- **Contextual Understanding**: Captures contextual relevance, reducing false
  positives from ambiguous keywords.
- **Synonym Recognition**: Identifies relevant papers with varied terminology.
- **Precision**: Efficiently excludes irrelevant studies, streamlining manual
  review.

## Project Structure

```plaintext
├── data/
│   ├── external/                   # External data sources
│   ├── processed/                  # Processed data for analysis
│   └── raw/                        # Raw data for initial processing
│       └── virology-ai-papers/     # Dataset repository
│           ├── collection_with_abstracts.csv
│           └── README.md
├── notebooks/                      # Jupyter notebooks for exploratory analysis
├── reports/                        # Analysis reports and visualizations
│   └── figures/                    # Figures for reporting
├── src/                            # Source code
│   ├── classification.py           # Classification logic
│   ├── data_loading.py             # Data loading utilities
│   ├── filtering.py                # Filtering logic
│   ├── preprocessing.py            # Preprocessing functions
│   └── reporting.py                # Reporting utilities
├── tests/                          # Unit tests
│   ├── test_classification.py
│   ├── test_data_preprocessing.py
│   └── test_filtering.py
├── .cz.toml                        # Commitizen config for commit standards
├── .github/
│   ├── workflows/
│   │   └── ci.yml                  # CI configuration for GitHub Actions
├── .gitignore                      # Git ignore file
├── .pre-commit-config.yaml         # Pre-commit hooks configuration
├── .markdownlint.mdlrc             # Markdown linting configuration
├── LICENSE                         # License file
├── README.md                       # Project README file
└── requirements.txt                # Python dependencies
```

## Getting Started

### Prerequisites

- **Python 3.15.14**
- **Virtual Environment** (recommended):

  ```bash
  python3 -m venv venv
  source venv/bin/activate  # On Windows use `venv\Scripts\activate`
  ```

  Alternatively, you may use other environment managers like `conda`, `pyenv`,
  or `pyenv-virtualenv` to simplify project setup and dependency management.

- **Install Dependencies**:

  ```bash
  pip install -r requirements.txt
  ```

### Installation

Clone the repository:

```bash
git clone https://github.com/AaronHo30/semantic-nlp-filtering-task.git
cd semantic-nlp-filtering-task
```

Clone the dataset repository:

```bash
cd data/raw
git clone https://github.com/jd-coderepos/virology-ai-papers/
```

## Usage

1. **Verify Data**: Ensure the dataset is available in
   `data/raw/virology-ai-papers/`.
2. **Run Pipeline**: Execute the `main.py` script to start filtering and
   classification:

   ```bash
   python src/main.py
   ```

3. **View Results**: Processed data will appear in `data/processed/` for
   further review.

## Development Setup

To maintain code quality, configure pre-commit hooks with the provided
`.pre-commit-config.yaml`.

### Setting Up Pre-Commit Hooks

1. **Install pre-commit**:

   ```bash
   pip install pre-commit
   ```

2. **Initialize Hooks**:

   ```bash
   pre-commit install
   ```

3. **Run on All Files**:

   ```bash
   pre-commit run --all-files
   ```

The hooks include checks for code formatting, linting, and other quality
measures to ensure consistency.

### Pre-Commit Configuration

The `.pre-commit-config.yaml` includes hooks for:

- **Code Hygiene**: Whitespace, YAML validation, conflict detection.
- **Formatting**: Black, isort for standardized formatting.
- **Linting**: flake8 with plugins for code quality.
- **Type Checks**: mypy for annotations.
- **Security**: Bandit for vulnerability checks.
- **Spell Check**: codespell for common typos.

## Continuous Integration

This project uses GitHub Actions CI, configured in `.github/workflows/ci.yml`.
CI automates tests, code quality checks, and documentation verification to
maintain reliability.

### CI Configuration

The `.github/workflows/ci.yml` configures:

- **Linting**: Black, isort, flake8.
- **Type Checking**: mypy.
- **Security**: Bandit.
- **Testing**: pytest.
- **Documentation**: pydocstyle for docstring compliance.
- **Pre-Commit Hooks**: Executes all hooks.

### Commit Message Guidelines

This project follows the `Conventional Commits` standard. For commit message
consistency, a `.cz.toml` configuration is included to allow usage with
`commitizen` via the `cz commit` command if desired.

## Results

Results and dataset statistics are stored in `data/processed/` upon processing
completion.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for
more details.

## Contact

For inquiries, contact [a.hoffmann30@posteo.com](mailto:a.hoffmann30@posteo.com).
