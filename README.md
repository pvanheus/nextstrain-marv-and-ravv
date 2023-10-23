## Nextstrain build for Marburg and Ravn viruses

This repository provides a [Nextstrain](https://nextstrain.org) build of the Marburg and Ravn virus data from Genbank,
supplemented with data from [virological.org](https://virological.org) for strains from Ghana and Equatorial Guinea.
The output can be seen on the [SANBI](https://www.sanbi.ac.za) Nextstrain [MARVRAVV page](https://nextstrain.sanbi.ac.za/marvravv).

This build is based on the config in the [Zika tutorial repository](https://github.com/nextstrain/zika-tutorial).

### How to build

Install Nextrain CLI using [these instructions]. For Singularity based setup, use `nextstrain setup --set-default singularity`.

Check out this repository. If you have your own data, add sequences to `data/sequences.fasta` and metadata to `data/metadata.tsv`. Follow the fields specified in the first line of the metadata file.

Run `nextstrain build .` in the top level directory of the repository. The outputs got into the `results/` folder and the files needed by the [Auspice](https://docs.nextstrain.org/projects/auspice/en/stable/) display application are the in `auspice/` folder. You can either view using a local copy of Auspice (e.g. run `nextstrain view auspice/`) or drag the `marvravv.json` file to [https://auspice.us/](https://auspice.us/).

