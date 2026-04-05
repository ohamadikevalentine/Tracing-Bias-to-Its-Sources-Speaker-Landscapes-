# Tracing Bias to Its Sources: Platform-Level Bias Analysis Code

This repository contains the Python code used for the platform-level analysis in the paper **“Tracing Bias to Its Sources: A Word Embedding Audit of Racism in South African News Outlets.”** The code measures how strongly South African news platforms are associated with Black- and White-linked stereotype vocabularies in an ensemble of pretrained speaker-landscape embeddings.

This repository includes the analysis code only. It does **not** include code for training the speaker-landscape embeddings. For the original speaker-landscape method and training code, see Schuld et al. (2024): https://github.com/mariaschuld/speaker-landscapes

## What the code does

The notebook performs the following analyses:

- loads an ensemble of 10 pretrained platform-level Word2Vec embeddings (embeddings included in the repo)
- measures stereotype associations with a race dimension
- filters stereotypes based on directional consistency
- validates stereotype associations against human ratings
- compares the platform-level stereotype scores with scores from the earlier aggregate analysis
- computes platform-level similarity to Black and White stereotype centroids
- produces scatterplots and ranked outputs for platform associations

## Repository contents

- `Tracing-Bias-to-Its-Sources-Speaker-Landscapes-.ipynb`  
  Main analysis notebook used for the paper.

## Data and model inputs

The notebook expects access to external files stored locally or on Google Drive, including:

- pretrained platform-level embedding files for 10 runs (included in repo)
- human ratings data
- comparison data from the earlier aggregate study (Ohamadike et al., 2025).

## Main analysis steps

### 1. Load pretrained embeddings
The notebook loads an ensemble of 10 pretrained `KeyedVectors` models representing platform-level embeddings.

### 2. Measure stereotype projection
Using predefined Black and White stereotype lists, the code estimates how stereotypes align with the race dimension across the ensemble.

### 3. Validate against human ratings
The resulting stereotype scores are correlated with human ratings to assess whether the embedding-based associations correspond to South African judgements.

### 4. Compare with prior aggregate analysis
The stereotype associations from the platform-level analysis are compared with those reported in the earlier aggregate study.

### 5. Compute platform association scores
Each platform vector is compared to Black and White stereotype centroids using cosine similarity.

### 6. Generate outputs
The notebook exports figures and spreadsheets used in the paper.

## Outputs

The notebook generates outputs such as:

- stereotype cosine similarity tables
- correlation plots with human ratings
- cross-analysis comparison plots
- platform scatterplots
- ranked platform scores saved to spreadsheet files

## Requirements

The notebook uses Python packages including:

- `pandas`
- `numpy`
- `matplotlib`
- `scipy`
- `gensim`
- `nltk`
- `adjustText`

Some setup in the notebook assumes a Google Colab environment and Google Drive mounting.

## Notes

- This repository contains analysis code only.
- Embedding training is not included (see Schuld et al., 2024).
- File paths in the notebook may need to be edited to match your local environment.
- The code was developed for the analyses reported in the paper and may require small adjustments for reuse on new data.

## Citation

If you use this code, please cite the associated paper:

Ohamadike, N., Durrheim, K., & Primus, M. *Tracing Bias to Its Sources: A Word Embedding Audit of Racism in South African News Outlets.*

For the speaker-landscape method, please also cite:

Schuld, M. et al. (2024). *Speaker landscapes*. GitHub repository: https://github.com/mariaschuld/speaker-landscapes
