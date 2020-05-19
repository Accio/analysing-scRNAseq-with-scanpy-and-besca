# Tutorials of using `scanpy` and `besca` to analyse single-cell sequencing data

[Jitao David Zhang](mailto:jitao_david.zhang@roche.com), 07.05.2020

## Background

This repository helps you start using two Python packages,  `scanpy` and
`besca`, to analyse single-cell sequencing data.

`scanpy` is a Python library that provides
data structure and functions to analyse single-cell sequencing data. It is
developed by the Fabian Theis lab. Its source code is available on GitHub
[theislab/scanpy](https://github.com/theislab/scanpy), and the documentation is
available at [readthedocs](https://scanpy.readthedocs.io/).

`besca` stands for *BEDA's single-cell sequencing analysis*. It is built on the
top of scanpy and offers additional useful data structures and python functions.
It is developed by the Bioinformatics and Exploratory Data Analysis (BEDA) team
at Roche Pharma Research and Early Development. The source code is available on
GitHub [BEDApub/besca](https://github.com/BEDApub/besca).

We go through the basic analysis single-cell data with both `scanpy` and `besca`.

* [scanpy-tutorial-3kPBMC.ipynb](./scanpy-tutorial-3kPBMC.ipynb) shows how to
    analyse a PBMC dataset with scanpy, following the tutorial of scanpy. You
    probably want to start with this to learn the basics of scanpy.
* [besca-workflow.ipynb](./besca-workflow.ipynb) is a guided tour of the
  standard workflow of besca. It complements the standard scanpy workflow by
  additional QC plots, integrated batch correction, and file exports that adhere
  to the FAIR (findable, accessible, interoperable, and reusable) principle.

## Install scanpy and besca

### Requisite

Due to a pre-compiled binary file, `besca` only runs on 64-bit Linux systems.

### Installation

```bash
pip install scanpy[louvain]
pip install git+https://github.com/bedapubc/besca.git
```

After installation of besca, set the executable flag to the binary file.

```bash
pip show besca | grep Location | cut -f 2 -d ":" | \
  awk -v OFS="" '{print "chmod u+x" $0 "/besca/export/reformat"}' | bash
```

If you encounter problems with the installation of besca, try using `Anaconda`.
Alternatively, you may consider cloning the GitHub repository from GitHub
[bedapubc/besca](https://github.com/bedapubc/besca) and installing it locally.

If it still does not work, please [report an
issue](https://github.com/BEDApub/besca/issues).
