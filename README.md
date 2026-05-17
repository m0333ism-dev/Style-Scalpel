# Style-Scalpel
Style Scalpel is a Windows-based forensic stylometric AI-text detector. It uses interpretable linguistic and stylometric features to estimate whether a text is more likely to be human-written or AI-generated.

## Download

The latest Windows executable is available from the Releases page:

**Latest version:** v1.3
<img width="768" height="568" alt="image" src="https://github.com/user-attachments/assets/9447f51e-ff85-4492-a2be-58e7f5c6ecbc" />

Download:

[Download Style Scalpel v1.3](https://github.com/m0333ism-dev/Style-Scalpel/releases/tag/v1.3)

## Important note

Older versions v1.1 and v1.2 are deprecated. Use v1.3 only.

## What it does

- Analyses pasted text or uploaded documents
- Uses interpretable stylometric features
- Produces AI/Human likelihood output
- Designed for academic and forensic-style text analysis

## System requirements

- Windows 10 or Windows 11
- No Python installation required for the `.exe` version

## Academic note

This tool is connected to my research on forensic stylometric detection of AI-generated text. The OSF archive is used for research storage and version documentation.

## Benchmark comparison: IDMGSP scientific-paper benchmark

Style Scalpel was evaluated against the IDMGSP benchmark for distinguishing human-written and machine-generated scientific papers. The table below reports accuracy (%) using the same reporting style as the IDMGSP benchmark paper. These results should be interpreted as benchmark evidence for formal scientific-paper text, not as universal proof of AI authorship detection.

| Model | Train dataset | TEST | OOD-GPT3 | OOD-REAL | TECG | TEST-CC |
|---|---:|---:|---:|---:|---:|---:|
| LR-1gram (tf-idf) | TRAIN | 95.3 | 4.0 | 94.6 | 96.1 | 7.8 |
| LR-1gram (tf-idf) | TRAIN + GPT3 | 94.6 | 86.5 | 86.2 | 97.8 | 13.7 |
| LR-1gram (tf-idf) | TRAIN-CG | 86.6 | 0.8 | 97.8 | 32.6 | 1.2 |
| RF-1gram (tf-idf) | TRAIN | 94.8 | 24.7 | 87.3 | 100.0 | 8.1 |
| RF-1gram (tf-idf) | TRAIN + GPT3 | 91.7 | 95.0 | 69.3 | 100.0 | 15.1 |
| RF-1gram (tf-idf) | TRAIN-CG | 97.6 | 7.0 | 95.0 | 57.0 | 1.7 |
| Galactica | TRAIN | 98.4 | 25.9 | 95.5 | 84.0 | 6.8 |
| Galactica | TRAIN + GPT3 | 98.5 | 71.2 | 95.1 | 84.0 | 12.0 |
| Galactica | TRAIN-CG | 96.4 | 12.4 | 97.6 | 61.3 | 2.4 |
| RoBERTa | TRAIN | 72.3 | 55.5 | 50.0 | 100.0 | 63.5 |
| RoBERTa | TRAIN + GPT3 | 65.7 | 100.0 | 29.1 | 100.0 | 75.0 |
| RoBERTa | TRAIN-CG | 86.0 | 2.0 | 92.5 | 76.5 | 9.2 |
| GPT-3 | TRAIN-SUB | 100.0 | 25.9 | 99.0 | 100.0 | N/A |
| DetectGPT | — | 61.5 | 0.0 | 99.9 | 68.7 | N/A |
| ChatGPT-IO | — | 69.0 | 49.0 | 89.0 | 0.0 | 3.0 |
| LLMFE | TRAIN + GPT3 | 80.0 | 62.0 | 70.0 | 90.0 | 33.0 |
| **Style Scalpel / stylometric model** | **TRAIN** | **98.75** | **7.5** | **98.5** | **99.90** | **2.80** |
| **Style Scalpel / stylometric model** | **TRAIN-CG** | **97.49** | **10.9** | **98.33** | **90.30** | **0.65** |
| **Style Scalpel / stylometric model** | **TRAIN + GPT3** | **98.46** | **99.3** | **94.4** | **100.0** | **3.23** |

**Interpretation.** The stylometric model is highly competitive on the main IDMGSP TEST split, reaching 98.75% under TRAIN, 98.46% under TRAIN + GPT3, and 97.49% under TRAIN-CG. Its performance is also strong on OOD-REAL and TECG. However, the model performs poorly on TEST-CC, which appears to contain substantial encoding or extraction artifacts. This limitation is reported openly because the tool is intended as a transparent analytical aid, not as automatic proof of AI use.

**Benchmark source:** Abdalla, M. H. I., Malberg, S., Dementieva, D., Mosca, E., & Groh, G. (2023). *A benchmark dataset to distinguish human-written and machine-generated scientific papers*. Information, 14(10), 522. https://doi.org/10.3390/info14100522

## Disclaimer

This detector should be used as an analytical aid, not as the only evidence for accusing a writer of using AI.
## License

This project is licensed under the Apache License 2.0.

The detector is provided for research and educational use. It should be treated as an analytical aid, not as standalone proof that a text is AI-generated or human-written.

## OSF Archive

The research archive and additional project materials are available on OSF:

https://osf.io/2d39j/overview?view_only=62cf45079b42459f9f54dbc90bdb5209

## Warning

Windows may show a SmartScreen warning because the executable is not code-signed. This warning means Windows does not recognize the publisher. It does not automatically mean the file is unsafe.

Cite the software:
Style Scalpel v1.3. DOI: https://doi.org/10.17605/OSF.IO/2D39J

Copyright [2026] [Muhammad Ismail]
