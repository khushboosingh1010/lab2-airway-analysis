# Lab 2: Gene Expression in Human Airway Cells

Author: Khushboo Singh

## Research question

Which gene records have the largest absolute log2 fold changes in average expression between dexamethasone-treated and untreated human airway smooth-muscle cells?

## Data source

Both implementations download the processed FPKM matrix directly from NCBI GEO study GSE52778. An internet connection is required.

Data URL:
https://www.ncbi.nlm.nih.gov/geo/download/?acc=GSE52778&format=file&file=GSE52778_All_Sample_FPKM_Matrix.txt.gz

## Analysis

Calculate average expression across four treated and four untreated samples. Calculate log2 fold changes using a pseudocount of 0.1, retain records with an average of at least 1 FPKM in either group, and plot the ten largest absolute log2 fold changes.

This is a descriptive comparison, not a statistical significance test.

## Rerun Python

Requirements: Python 3.12, Jupyter Notebook, pandas, numpy, and matplotlib.

Install these packages in your Python environment using:
`python -m pip install notebook nbconvert pandas numpy matplotlib`

Start Jupyter using:
`python -m jupyter notebook`

Open `python/lab2_airway_python_final.ipynb` in Jupyter.
Select the environment containing the required packages, restart the kernel, run all cells, and save the notebook.

To export the saved notebook, open a separate Terminal window in the `python` folder and run:
`python -m jupyter nbconvert --to html lab2_airway_python_final.ipynb`

Use the same Python environment as the notebook. This creates `lab2_airway_python_final.html`.

## Rerun R

Requirements: R, RStudio, knitr, rmarkdown, and Pandoc. RStudio includes Pandoc.

Install the R packages in the R Console using:
`install.packages(c("knitr", "rmarkdown"))`

Open `r/lab2_airway_r_final.Rmd` in RStudio and click Knit to generate the HTML report. Knitting executes the analysis in a separate R session.

## Rerun mixed-language extra credit

Requirements: RStudio, knitr, rmarkdown, reticulate, and a Python environment with pandas installed. An internet connection is required.

Install the R packages in the R Console:
`install.packages(c("knitr", "rmarkdown", "reticulate"))`

Install pandas in your chosen Python environment using Terminal:
`python -m pip install pandas`

Before knitting, select that Python environment in the R Console:
`Sys.setenv(RETICULATE_PYTHON = "/full/path/to/your/python")`

Replace the example path with the actual Python executable on your computer.

Open Open `extra-credit/mixed_language_extra_credit.Rmd` in RStudio and click Knit. This runs Python and R from top to bottom and creates `mixed_language_extra_credit.html`. Python calculates group means, passes the table to R through reticulate, and R calculates fold changes and creates the plot.

## Expected results

The loaded matrix has 23,273 rows and 41 columns. Both implementations should identify the same top ten records. FTL has the largest positive log2 fold change, and SNORD54 has the largest negative log2 fold change.

## AI assistance

See `AI_USAGE.md` for details of ChatGPT assistance and how the outputs were checked.
