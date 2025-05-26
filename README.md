# AlgaeLncPred

**AlgaeLncPred** is a specialized machine learning model designed for predicting long non-coding RNAs (lncRNAs) in algae species. This tool provides accurate identification of lncRNAs from transcriptomic data, specifically optimized for algal genomes.

## Features

- **Species-specific optimization**: Tailored for algae species with specialized training datasets
- **High accuracy prediction**: Uses advanced machine learning algorithms with multiple feature sets
- **Easy-to-use interface**: Simple command-line tool requiring only FASTA input
- **Comprehensive output**: Provides detailed feature analysis and prediction probabilities
- **Open source**: Completely free and available for academic and research use

## Installation

```bash
git clone https://github.com/username/AlgaeLncPred.git
cd AlgaeLncPred
```

## Prerequisites

- Python 2.7
- R (for logistic regression model)
- Required Python packages (see `requirements.txt`)

## Usage

### Basic Command

```bash
python AlgaeLncPred.py -x Algae_Hexamer.tsv -d Algae.logit.RData -g input.fasta -o output.txt
```

### Parameters

| Parameter | Description | Required |
|-----------|-------------|----------|
| `-x` | Pre-trained hexamer frequency data file | Yes |
| `-d` | Logistic regression model file (.RData) | Yes |
| `-g` | Input FASTA file containing transcript sequences | Yes |
| `-o` | Output file name for prediction results | Yes |

### Example

```bash
python AlgaeLncPred.py \
    -x Algae_Hexamer.tsv \
    -d Algae.logit.RData \
    -g Chlamydomonas_reinhardtii.test.fasta \
    -o Chlamydomonas_reinhardtii.output
```

## Output Format

The output file contains the following columns:

| Column | Description |
|--------|-------------|
| 1 | Transcript ID |
| 2 | Open Reading Frame (ORF) length |
| 3 | Fickett score |
| 4 | Hexamer score |
| 5 | Prediction probability |

### Interpretation

- **Probability < 0.46**: Transcript likely to be lncRNA
- **Probability ≥ 0.46**: Transcript likely to be mRNA

## Model Performance

AlgaeLncPred has been trained and validated on comprehensive algae transcriptomic datasets, achieving high accuracy in distinguishing lncRNAs from protein-coding transcripts.

## Input Requirements

- **File format**: FASTA format
- **Sequence type**: RNA transcript sequences
- **Species**: Optimized for algae species (tested on *Chlamydomonas reinhardtii*)

## Example Output

```
TranscriptID    ORF_Length    Fickett_Score    Hexamer_Score    Prediction_Probability
transcript_001  45            0.23             -1.45            0.12
transcript_002  1250          0.87             2.34             0.89
transcript_003  78            0.34             -0.87            0.28
```

## File Structure

```
AlgaeLncPred/
├── AlgaeLncPred.py          # Main prediction script
├── Algae_Hexamer.tsv        # Pre-trained hexamer frequency data
├── Algae.logit.RData        # Logistic regression model
├── example/
│   ├── Chlamydomonas_reinhardtii.test.fasta    # Example input
│   └── Chlamydomonas_reinhardtii.output        # Example output
├── requirements.txt         # Python dependencies
└── README.md               # This file
```

## Citation

If you use AlgaeLncPred in your research, please cite:

```
[Your paper citation will go here]
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contributing

We welcome contributions! Please feel free to submit issues, feature requests, or pull requests.

## Contact

For questions or support, please contact:
- Email: [your-email@institution.edu]
- Issues: [GitHub Issues](https://github.com/username/AlgaeLncPred/issues)

## Acknowledgments

- Thanks to the algae research community for providing valuable datasets
- Special acknowledgment to contributors and beta testers

---

**Note**: This tool is designed for research purposes. For clinical or commercial applications, please contact the authors for appropriate licensing.
