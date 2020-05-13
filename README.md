# Using `scanpy` and `besca` to analyse single-cell sequencing data

Jitao David Zhang, 07.05.2020

## Background

In this tutorial, we explore how to use the software `scanpy` and `besca` to
analyse single-cell sequencing data.

`scanpy` is a python library that provides
data structure and functions to analyse single-cell sequencing data. It is
developed by the Fabian Theis lab. Its source code is available on GitHub
[theislab/scanpy](https://github.com/theislab/scanpy), and the documentation is
available at [readthedocs](https://scanpy.readthedocs.io/).

`besca` stands for *BEDA's single-cell sequencing analysis*. It is built on the
top of scanpy and offers additional useful data structures and python functions.

In this tutorial,  we go through the basic analysis single-cell data with both
scanpy and besca.

## Install scanpy and besca

Due to a precompiled binary file, `besca` only runs on linux 64bit systems.

```bash
pip install scanpy[louvain]
pip install git+https://github.com/bedapubc/besca.git
```

After installation of besca, set the executable flag to the binary file.

```bash
pip show besca | grep Location | cut -f 2 -d ":" | \
  awk -v OFS="" '{print "chmod u+x" $0 "/besca/export/reformat"}' | bash
```

If you encounter problems with the installation of besca, try using conda, or
cloning the GitHub repository from GitHub
[bedapubc/besca](https://github.com/bedapubc/besca) and
install it locally. If it still does not work, please report an issue.
