# CellVoyager Replication Reproduction Guide

This folder is used to reproduce the CellVoyager COVID-19 PBMC case-study trajectory using a DeepSeekv4 model.

## Deepseek API Key
Go to platform.deepseek.com
Sign up / log in
Go to API Keys in the left sidebar
Click Create new API key. 
Top up a few dollar


## Repository Setup

Clone the original repository:

```bash
git clone https://github.com/zou-group/CellVoyager.git
cd CellVoyager
```

Create the conda environment:

```bash
conda env create -f environment.yml
conda activate CellVoyager
```

## Dataset Download
Download the COVID-19 PBMC dataset:

```bash
curl -o example/covid19.h5ad \
"https://hosted-matrices-prod.s3-us-west-2.amazonaws.com/Single_cell_atlas_of_peripheral_immune_response_to_SARS_CoV_2_infection-25/Single_cell_atlas_of_peripheral_immune_response_to_SARS_CoV_2_infection.h5ad"
```

## API Key Setup

The legacy execution mode expects the environment variable `OPENAI_API_KEY`.

Export the DeepSeek API key as:

```bash
export OPENAI_API_KEY="YOUR_DEEPSEEK_KEY"
```

## Running CellVoyager

Run the trajectory with:

```bash
python run_cellvoyager.py \
  --h5ad-path example/covid19.h5ad \
  --paper-path example/covid19_summary.txt \
  --analysis-name output \
  --execution-mode legacy \
  --model-name deepseek/deepseek-v4-flash \
  --num-analyses 1 \
  --max-iterations 4
```

## Output Notebook

The notebook output is saved under:

```text
outputs/output_<timestamp>/output_analysis_1.ipynb
```

## Notes

- Initial failures were primarily due to LiteLLM provider routing and API-key environment variable expectations.
- LiteLLM required a provider-prefixed model name (`deepseek/...`) rather than `deepseek-v4-flash` alone.
- Total runtime for the successful trajectory was approximately 30 minutes.
- Total DeepSeek cost was below $0.05 USD.