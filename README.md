# making_code_example_r

This is a reproducible code example that uses R and Bioconductor. It requires R 4.5 to reproduce the code.

## Reproducing my notebook

1. Try opening this project up in Positron or RStudio:
    a. Positron: **File >> New Folder From Git** and add the repository URL: https://github.com/fhdsl/mcr_example_r) to the field
    b. RStudio: **File >> New Project >> Version Control >> Git** and add the repository URL: https://github.com/fhdsl/mcr_example_r
2. `renv` should install automatically
3. Run `renv::restore()` and wait for packages to install - depending on your system, this may take a while.
4. Try opening `01-preprocessing.qmd` and try running the code.

## How did I make this?

1. Create a project in Positron using **File >> New Folder from Template**
2. Run `renv::init()` to start the `renv` environment (isolating packages)
3. Install packages, using `install.packages()` and `BiocManager::install()`
4. Make sure my notebook `01-preprocessing.qmd` runs with the installed packages
5. Use `renv::snapshot()` to save the lockfile.
6. Commit the following files to the Git Repository
    - `data/`
    - `.gitignore`
    - .Rprofile
    - .renv.lock
    - renv/activate.R
    - renv/settings.json
    - 01-preprocessing.qmd
7. Push project to GitHub

## (Optional) Making the Project Binder ready

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/fhdsl/mcr_example_r/HEAD?urlpath=rstudio)

If you want to make your project ready to run on Binder:

1. Run `quarto create project` and use `Default` to add quarto files
2. Run `quarto use binder` to create the necessary files
3. Commit the following files:
     `apt.txt`, `postBuild`, `runtime.txt`, `install.R`
4. Go to https://mybinder.org and put in the URL: https://github.com/fhdsl/mcr_example_r and under File to Open, select "URL" and put in `rstudio`
5. Hit the launch button and debug the build process. It will take a while, because it is building from source.
6. Copy the badge button URL and paste into your `README.md`