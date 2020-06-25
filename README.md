# Introduction to Cheminformatics

This repository contains some notebooks that will teach you how to get started
with cheminformatics and machine learning in a notebook environment.

To start viewing the notebooks without having to install anything locally,
a Binder link will be included.

To get started locally, I recommend using the `environment.yml` included here
to create a `conda` environment, which will ensure all the packages are
installed and linked correctly. Most noteably, `mol2vec` is not included on
PyPI as of June 25 2020, and `environment.yml` automates installation through
the Github repository for `mol2vec`.

## Notes for `mol2vec` training

For this notebook series, we will use the ZINC15 database to pull SMILES.
Inside the `data` folder is a wget script which will pull data down from the
ZINC15 servers.

Feel free to fork and/or contribute!

## Notes for Google colab

These notebooks will also function on Google Colab, which has better computing
resources than Binder. The kicker, however, is that `conda` environments are
not well supported. To make sure everything is installed properly, you will
need to add the following code into the top of any notebook:

```python
# This installs RDKit on this Google Colab instance.
# Recipe from here: https://iwatobipen.wordpress.com/2018/11/01/run-rdkit-and-deep-learning-on-google-colab-rdkit/
!pip install git+https://github.com/samoturk/mol2vec
!wget -c https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh
!chmod +x Miniconda3-latest-Linux-x86_64.sh
!time bash ./Miniconda3-latest-Linux-x86_64.sh -b -f -p /usr/local
!time conda install -q -y -c conda-forge rdkit

# honestly not too desirable, but this points to the rdkit installation
import sys
sys.path.append('/usr/local/lib/python3.7/site-packages/')
```

This will ensure `mol2vec` is installed, along with RDKit (which needs `conda`).
