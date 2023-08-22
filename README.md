# Stochastic Weather Generator v2.0

## Code repository of the weather regime-based stochastic weather generator: WR-SWG (or WGEN) ##

The WGEN was first developed by [Prof. Scott Steinschneider](https://github.com/SteinschneiderLab) (Cornell University) (see *Steinschneider et al., 2019*). 
Since then, it has been upgraded, applied to different locations, and used for varying purposes by [the Steinschneider Research Group]( https://blogs.cornell.edu/steinschneider/) and their collaborators.

The WGEN is designed to be a flexible tool that can facilitate computationally fast, internally consistent scenario generation to support climate vulnerability assessments of water systems in a way that is more easily connected to advances in climate science. 
It is well suited for risk-based simulation studies of system-of-systems that span large regions and multiple sectors (e.g., food, energy, and water).
The tool is useful in expediting the adoption of bottom-up vulnerability assessments across water, food, and energy sectors, by providing a regional set of scenarios that can be tailored for individual locations and analyses.

WGEN-v2.0 scripts were developed in the R Foundation for Statistical Computing Platform Desktop System Type x64-based PC with Intel(R) Core(TM) i7-9700 CPU 3.00 GHz 8 Cores 8 Logical Processors 64.0 GB RAM (64-bit) R version 4.2.0 (RStudio 2022-04-22 ucrt).

A permanent and archived version of this repository is available on Zenodo [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7311768.svg)](https://doi.org/10.5281/zenodo.7311768) (all versions DOI).

### How to cite

If you use the WGEN scripts (as a whole, or partially, and/or as a template for your research work), 
or its results/methods, please cite the references below.

1. Steinschneider, S., Ray, P., Rahat, S. H., & Kucharski, J. (2019). A weather‐regime‐based stochastic weather generator for climate vulnerability assessments of water systems in the western United States. *[Water Resources Research](https://doi.org/10.1029/2018WR024446)*, 55(8), 6923-6945.

```bibtex
@article{steinschneider2019weather,
  title={A weather-regime-based stochastic weather generator for climate vulnerability assessments of water systems in the western United States},
  author={Steinschneider, Scott and Ray, Patrick and Rahat, Saiful Haque and Kucharski, John},
  journal={Water Resources Research},
  volume={55},
  number={8},
  pages={6923--6945},
  year={2019},
  publisher={Wiley Online Library}
}
```

2. Najibi, N., Mukhopadhyay, S., & Steinschneider, S. (2021). Identifying weather regimes for regional‐scale stochastic weather generators. *[International Journal of Climatology](https://doi.org/10.1002/joc.6969)*, 41(4), 2456-2479.
```bibtex
@article{najibi2021identifying,
  title={Identifying weather regimes for regional-scale stochastic weather generators},
  author={Najibi, Nasser and Mukhopadhyay, Sudarshana and Steinschneider, Scott},
  journal={International Journal of Climatology},
  volume={41},
  number={4},
  pages={2456--2479},
  year={2021},
  publisher={Wiley Online Library}
}
```

## For the Public

Summaries of this package in a plain language will be available soon. If you'd like a high-level overview of its components, please visit us again at a later time. 


## For Researchers

We are committed to making our work findable, accessible, interoperable and reusable ([FAIR principles](https://www.nature.com/articles/sdata201618)) by the scientific community and the society at large.
The programming language/platform (i.e., [R](https://www.r-project.org/)) and data used here are publicly available via the public preservation repositories without any charges.
All code is posted on this repository.

The following sections outline the steps you can take to run the WGEN.

#### Repository organization

- `README.md` is what you are looking at now.
- `R_sessionInfo.txt` contains list of packages in `R` (_attached base packages, attached packages, and loaded via a namespace_) with their release version. 
- `LICENSE` describes the terms of the GNU GENERAL PUBLIC LICENSE under which our code is licensed. This is a "free, copyleft license for software and other kinds of works, that guarantees end users the four freedoms to run, study, share, and modify the software".
- `docs/` contains the articles (PDF format) published in peer-reviewed journals.
- `Programs/` contains the scripts required to run the WGEN, from identifying the weather regimes (`Programs/config.WRs.param.NHMM.R` or `Programs/config.WRs.non_param.R`), to simulating the weather information (`Programs/config.simulations.R`), providing the output files, and plotting the diagnostics (`Programs/functions.for.figures/`).
- `Data/` contains a link to a permanent repository to download sample data/format to run the WGEN. The raw inputs are stored in `Data/processed.data.files/` for the large-scale atmospheric circulations and observational weather records. The final output files are located in `Data/simulated.data.files/WGEN.out`
- `Figures/` contains a list of diagnostics and statistics to examine the performance of WGEN outputs. _If you want to use these figures, you are responsible for complying with the policies of the journals our papers have been published, or going to be published, but we mainly ask that you cite our papers when you do so._


#### To browse the codes

> If you want to browse our code, this section is for you

You will find R scripts/functions in `Programs/`.
You can open them and they will render in GitHub.
This will show you how we developed different modules of the WGEN, and produced the output files in `Data/`, along with some additional commentary.

If you want to dig deeper, but not to run our codes, then you may want to look at the R functions in `Programs/functions/` and/or the three modules as `Programs/config.__.R`.

#### To run WGEN

> If you want to reproduce or modify our results, this section is for you

Please note: **running this will require 0.5-1 GB of disk space, depending on the length of the input/output data**.
*All commands here assume standard Windows terminal; UNIX may be subtly different*.

First, you will need to install `R` and `Rstudio`.

Next, you will need to `git clone` the repository to your machine, or download `Programs`.


In order to run, you will need to do two things to access the required data:

1. Download the files from `Data/` and store them in a folder titled `Data` next to the `Programs` and `Figures` in your directory. *Note that you need to provide a similar input data (format, structure) for your particular case*. A permanent `Data` repository is available on Zenodo [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7311768.svg)](https://doi.org/10.5281/zenodo.7311768).

1. Start with `config.WRs.non_param.R` or `config.WRs.param.NHMM.R` to identify/simulate the weather regimes.

**Now you can run `config.simulations.R`!**

We again remind you that running will need a considerable disk space as it depends on the spatiotemporal dimensions of the input files and the length of outputs, e.g., *how many years of weather data to generate?*

#### To plot different weather diagnostics

> If you want to plot different statistics, this section is for you

Finally, you can run the diagnostic function `Programs/functions.for.figures/plot.statistics.full.diagnostics.long.R` to assess the performance of the WGEN through a set of selected statistics for precipitation (e.g., floods, droughts, monthly/yearly distributions, inter-annual variability, long-term dry/wet spells).
A similar diagnostics can be produced for other variables (e.g., temperature, wind, etc.).

### Issues and Comments

- If you have issues related to the software/packages, please raise an issue in the Issues tab.
- If you have comments, please contact the correspondence of this repository [Nasser Najibi](https://nassernajibi.com) directly.

### License
This project is licensed under the MIT License - see the [LICENSE.md](https://github.com/nassernajibi/WGEN-v2.0/blob/83e90d81cd08d2aa18e998d7ad42c8c437308f9a/LICENSE) file for details.

**Disclaimer:**
You are running the scripts/functions which means you will not blame the author(s)/developer(s) if they break your stuff.
The scripts/functions are provided AS IS without warranty of any kind. Author(s) disclaim all implied warranties, including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. 
In no event shall the author(s) be held liable for any damages whatsoever (including, without limitation, any sorts of damages or loss) arising out of the use of or inability to use the scripts or documentation.
Author(s) retain the right to alter this disclaimer at any time.
The contents contained in this repository or within the articles are not the opinions of the funding agencies, affiliated university, or the U.S. Government but reflect the authors' opinions.

![Screenshot](https://brand.cornell.edu/assets/images/examples/trademarks/brand_registered.svg)
