Using scanpy and besca to analyse single-cell sequencing data
===
Jitao David Zhang, 07.05.2020

# Background

We explore how to use `scanpy` and `besca` to analyse single-cell sequencing data.

# Install scanpy and besca

Due to a precompiled binary file, `besca` only runs on linux 64bit systems.

```bash
pip install scanpy[louvain]
pip install git+https://github.com/bedapubc/besca.git
```

After installation of besca, set the executable flag to the binary file.

```bash
pip show besca | grep Location | cut -f 2 -d ":" | awk -v OFS="" '{print "chmod u+x" $0 "/besca/export/reformat"}' | bash
```

If you encounter problems with the installation of besca, try using conda, or cloning the git repository [https://github.com/bedapubc/besca](https://github.com/bedapubc/besca) and install it locally. If neither method helps, please report an issue.
