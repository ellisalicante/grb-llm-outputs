# Gender Representation Bias Analysis of Large Language Models' Outputs in Gendered Languages

Repository accompanying our paper titled **Gender Representation Bias Analysis in LLM-Generated Czech and Slovenian Texts**, presented at the **10th Workshop on Slavic Natural Language Processing at ACL 2025**. The research and experimental evaluation has been conducted for Czech and Slovenian. It can be adapted to other gendered languages.

**Authors:** Erik Derner, Kristina Batistič

**Contact:** erik@ellisalicante.org

## Repository Structure

- `code`: Code for generating stories and evaluating the gender representation bias
  - `bias-analysis`: Gender representation bias analysis in a given dataset (text)
  - `text-generation`: Model inference using generator LLMs to write stories
  - `validation`: Validation of the gender representation bias analysis method on an annotated dataset
- `data`: Prompts to generate stories and evaluate gender representation bias, few-shot examples, and a validation dataset
  - `dataset-analysis`: Prompts and few-shot examples for bias evaluation
  - `stories`: Prompts to generate stories for gender representation bias analysis
  - `stories-val`: Prompts to generate stories for the validation dataset
  - `validation`: Annotated (ground truth) data for method validation

## Getting Started

### Prerequisites

- Python 3.12
- API key(s) for LLM inference
- CUDA to use GPU for local inference

### Installation

1. Clone or download the repository.

2. Install the required packages.
    ```bash
    pip install -r requirements.txt
    ```

3. Set the environment variables.

    Define at least one API key:
    - `OPENAI_API_KEY` – OpenAI API key
    - `TOGETHER_API_KEY` – Together.ai API key
    - `ANTHROPIC_API_KEY` – Anthropic API key

    Later on, in the code, choose the Generator and Evaluator LLMs to which you have API access.

4. Install CUDA to use local inference (optional):
   
   Follow the [PyTorch local installation guide](https://pytorch.org/get-started/locally/).

   You can also run local inference on cloud platforms such as Google Colab.

## Usage

### Stories Generation

In `code/text-generation`, use:
- `llm-api-stories-generation.ipynb` to generate stories using LLMs through API inference
- `llm-local-stories-generation.ipynb` to generate stories using LLMs through local inference

### Gender Representation Bias Analysis

In `code/bias-analysis`, use:
- `dataset-analysis.ipynb` to annotate a given dataset for gender representation using API inference
- `dataset-analysis-statistics.ipynb` to calculate the gender representation bias for an annotated dataset
- `stats-summary.ipynb` to summarize the gender representation bias statistics across datasets
- `plot-results.ipynb` to generate a bar chart comparing gender representation bias in the evaluated languages

### Validation

To validate the gender representation bias analysis method on an annotated dataset, use in `code/validation`:
-  `validation-gt.ipynb` to compare a dataset analysis performed by an Evaluator LLM with the ground truth
-  `validation-summary.ipynb` to extract F1 scores as calculated by `validation-gt.ipynb`

## License

This project is licensed under the MIT License. See the [LICENSE.txt](LICENSE.txt) file for details.

## Citation

If you use this code or data, please cite our paper:

```bibtex
@inproceedings{derner2025gender,
  author    = {Derner, Erik and Batisti{\v{c}}, Kristina},
  title     = {Gender Representation Bias Analysis in LLM-Generated Czech and Slovenian Texts},
  booktitle = {Proceedings of the 10th Workshop on Slavic Natural Language Processing (Slavic NLP 2025)},
  pages     = {124--135},
  publisher = {Association for Computational Linguistics},
  address   = {Vienna, Austria},
  year      = {2025},
  month     = {Jul}
}
```
