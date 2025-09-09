# FPICS-Iodination-Quant
Quantify site specific iodination using PSM level data

This Jupyter notebook quantifies iodination events on histidine (H) and tyrosine (Y) residues in peptide-spectrum match (PSM) data.

## Features
- Loads PSM data from a TSV file
- Filters and processes peptides with modifications
- Identifies and quantifies iodination on H/Y residues
- Calculates frequency and percentage of iodination per residue

## Requirements
- Python 3.x
- pandas

## Usage

1. **Prepare your PSM data**
   - Ensure you have a `psm.tsv` file with columns: `Peptide`, `Modified Peptide`, `Protein Start`, `Protein End`, `Assigned Modifications`, `Entry Name`.

2. **Set the file path**
   - Edit the `filepath` variable in the notebook to point to your `psm.tsv` file:
     ```python
     filepath = "/path/to/your/psm.tsv"
     ```

3. **Run all cells**
   - Execute each cell in order. The notebook will:
     - Load and clean the data
     - Extract and process modifications
     - Quantify iodination events
     - Output frequency and percentage tables

4. **Customize protein entry**
   - To analyze a specific protein, change the `entry_name` argument in:
     ```python
     iodo_quant(merge_psm, "MYG_HORSE")
     ```
     Replace `"MYG_HORSE"` with your protein of interest.

## Output
- Tables showing iodination frequency and percentage for H/Y residues in the selected protein.

## Example
```python
# Set file path
filepath = "/Users/nithesh/Documents/Iodo_script/20240227_FPI_apomyoglobin_NvD_plus-minusHis-correctDB/2024_02_25_KB_NoFAIMS_MV_004_A2/psm.tsv"

# Run quantification
iodo_quant_results = iodo_quant(merge_psm, "MYG_HORSE")
total_pep_appearances(iodo_quant_results, merge_psm, psm_clean)
