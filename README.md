# Getting Started with NHANES in R
This one-hour workshop introduces participants to the structure of NHANES data and demonstrates a beginner-friendly R workflow for importing local files, joining participant-level tables, creating first visualizations, and saving outputs.

NHANES, the National Health and Nutrition Examination Survey, is a CDC/NCHS program that combines interviews, physical examinations, laboratory measures, and dietary information. In this workshop, we will explore how NHANES files are organized by cycle and file family, why codebooks and documentation should be stored with the data, and how to use relative paths to import local XPT files from a prepared project folder.

Using selected NHANES files, participants will inspect variables, perform basic data cleaning, join tables, and create simple figures using the tidyverse ecosystem, with emphasis on `dplyr` and `ggplot2`. Although the examples use NHANES data, the workflow and R skills introduced here are broadly applicable to many public health, nutrition, and research datasets.

## Workshop Materials
This repository contains three main sets of materials.

| Material | Location in this repository | Purpose |
|---|---|---|
| Hands-on project folder | `NHANES_workshop/` | Folder to use during the live R demo. It contains the simplified R Markdown file, local NHANES data files, documentation, and output folders. |
| Written tutorial | `nhanes_workshop_tutorial.html` | Main written tutorial. It includes fuller explanations, reference tables, package links, interpretation notes, and code output. Open it in any web browser after downloading the file. |
| Lecture slides | `NHANES_workshop_slides.pdf` | Slides used for the conceptual overview of NHANES file structure, cycles, documentation, and survey design reminders. |

The `NHANES_workshop/` folder is structured as a small reproducible R project:

```text
NHANES_workshop/
  code/             # simplified R Markdown code-along file
  data/
    raw/            # original NHANES XPT files
    processed/      # joined or cleaned output data
  docs/
    documentation/  # NHANES documentation and codebooks
  outputs/
    figures/        # figures created during the demo
    tables/         # optional table outputs
```

## Before the Workshop
Please complete the setup steps below before the session.

### 1. Install R

Download and install R from CRAN:

<https://cran.r-project.org/>

### 2. Install RStudio Desktop

Download and install RStudio Desktop from Posit:

<https://docs.posit.co/ide/user/#rstudio-ide-oss-downloads>

### 3. Download This Repository

On the GitHub repository page, click **Code** and then **Download ZIP**. Unzip the downloaded file and keep the folder in a location you can find easily, such as your Desktop.

### 4. Open or Create a Code-Along File

Open RStudio, then open the provided simplified R Markdown file:

```text
NHANES_workshop/code/nhanes_workshop_demo.Rmd
```

You may also choose to type along in a new R Markdown file. If you do this, save the new file inside the `NHANES_workshop/code/` folder. Keeping the R Markdown file in `code/` allows the relative paths used in the workshop, such as `../data/raw`, to work with the prepared folder structure.

### 5. Install Required R Packages

The live demo uses two R packages:

- `tidyverse`: data wrangling and visualization, including `dplyr`, `readr`, and `ggplot2`.
- `haven`: importing NHANES SAS transport files (`.XPT`).

If you have not installed these packages before, run the following commands in the RStudio Console. You only need to install packages once on your computer.

```r
install.packages("tidyverse")
install.packages("haven")
```

During the workshop, the R Markdown file will load the packages with `library(tidyverse)` and `library(haven)`.

You are now ready for the workshop.

## How to Use the Materials
During the workshop, use `NHANES_workshop/code/nhanes_workshop_demo.Rmd` to follow along with the live demo, or create your own R Markdown file inside `NHANES_workshop/code/` and type along from the beginning. The provided file contains the essential code for importing NHANES files, checking variables, joining tables, recoding variables, creating plots, and saving outputs.

Participants are encouraged to download the full `NHANES_workshop/` folder, even if they plan to create their own R Markdown file. The folder already contains the raw NHANES files in `data/raw`, CDC documentation in `docs/documentation`, and output folders for processed data and figures. This structure supports reproducible R workflows because the code can use relative paths instead of computer-specific absolute paths.

Use `nhanes_workshop_tutorial.html` when you want the fuller written explanation, and use `NHANES_workshop_slides.pdf` for the lecture sections.

## Workshop Goals
By the end of the session, participants should be able to:

1. Describe how NHANES public-use files are organized by cycle and file family.
2. Explain why CDC documentation and codebooks are part of the dataset.
3. Use relative paths to import local NHANES `.XPT` files.
4. Join participant-level files using the shared identifier `SEQN`.
5. Inspect variables and check missing values in a joined dataset.
6. Create basic `ggplot2` visualizations from joined NHANES data.
7. Save figures and processed data outputs.
8. Recognize when NHANES survey design variables matter for later analysis.

## Notes About Analysis
This workshop teaches data organization, import, joining, and first visualization workflows. It does not teach full survey-weighted NHANES analysis.

NHANES uses a complex survey design. For descriptive population estimates, analyses usually require the correct sample weights, strata, and primary sampling units. The workshop briefly identifies these concepts so participants know what to look for in later analyses.

## Helpful Resources
- About NHANES: <https://www.cdc.gov/nchs/nhanes/about/index.html>
- NHANES datasets and documentation: <https://wwwn.cdc.gov/nchs/nhanes/default.aspx>
- NHANES tutorials: <https://wwwn.cdc.gov/nchs/nhanes/tutorials/default.aspx>
- Tidyverse: <https://www.tidyverse.org/>
- R for Data Science, 2e: <https://r4ds.hadley.nz/>
- dplyr: <https://dplyr.tidyverse.org/>
- ggplot2: <https://ggplot2.tidyverse.org/>
- haven: <https://haven.tidyverse.org/>
