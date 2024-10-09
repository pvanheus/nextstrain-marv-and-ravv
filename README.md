## Nextstrain build for Marburg and Ravn viruses

This repository provides a [Nextstrain](https://nextstrain.org) build of the Marburg and Ravn virus data from Genbank,
supplemented with data from [virological.org](https://virological.org) for strains from Ghana and Equatorial Guinea.
The output can be seen on the [SANBI](https://www.sanbi.ac.za) Nextstrain [MARVRAVV page](https://nextstrain.sanbi.ac.za/marvravv).

This build is based on the config in the [Zika tutorial repository](https://github.com/nextstrain/zika-tutorial).

### How to build

Install Nextrain CLI using [these instructions](https://docs.nextstrain.org/projects/cli/en/stable/installation/). The standalone installer options or installation via bioconda are preferred methods.

The actual steps of the alignment and tree building are done using a Snakemake workflow. The Nexstrain CLI offers commands for setting up the software needed to run this workflow, either using Docker or Singularity/Apptainer containers or via conda. The container based setup is preferred. The default is to use Docker, which can be setup with `nextstrain setup docker`, but for Singularity based setup, use `nextstrain setup --set-default singularity`.

Next, check out this repository (`git clone git@github.com:pvanheus/nextstrain-marv-and-ravv.git`) and cd to the repository directory (`cd nextstrain-marv-and-ravv`). 

If you have your own data, add sequences to `data/sequences.fasta` and metadata to `data/metadata.tsv`. Follow the fields specified in the first line of the metadata file.

Run `nextstrain build .` in the top level directory of the repository. The outputs got into the `results/` folder and the files needed by the [Auspice](https://docs.nextstrain.org/projects/auspice/en/stable/) display application are the in `auspice/` folder. You can either view using a local copy of Auspice (e.g. run `nextstrain view auspice/`) or drag the `marvravv.json` file to [https://auspice.us/](https://auspice.us/).

### Excluded strains

The following strains are excluded from analysis by the automated pipeline:


EU500827.1
DQ447652
DQ447659
DQ447656
DQ447654
DQ447660
DQ447655
DQ447658
DQ447657
DQ447653
MG725616
DQ447650
DQ447651

The are retained in the datasets for further analysis.
