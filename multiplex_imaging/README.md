## Multiplex Imaging Pipeline

## Installation

Requires:
- Python
- [multiplex-imaging-pipeline](https://github.com/estorrs/multiplex-imaging-pipeline)

To create environment with conda and jupyter
```bash
conda create -n multiplex-imaging -c conda-forge "python==3.9" jupyter jupyter_contrib_nbextensions -y
conda activate multiplex-imaging
pip install deepcell harmonypy git+https://github.com/estorrs/multiplex-imaging-pipeline.git
```

## Launching notebooks on the lab cluster

Below are some example commands to run jupyter from the lab cluster with this notebook. For more information on running jupyter in the lab cluster, see the [Jupyter Notebooks]() section in the lab wiki.

Wherever you see `NODE` below that is the name of whatever node you are running the notebook on (i.e. sequoia, tortugas, etc.).

1. On lab cluster `NODE`
```bash
cd multiplex-imaging
jupyter notebook --port 12121 --no-browser --ip="0.0.0.0" # port could be any number, using 12121 here
```

2. On your local machine. Remember to replace NODE with the correct name, USERNAME with your username, and also the port number if you are using a different port.
```bash
ssh -L 12121:NODE:12121 -N USERNAME@katmai.wusm.wustl.edu
```

Then copy the url from step 1 and paste it in your browser, it should look something like `http://127.0.0.1:12121/?token=4ca086c94f7f56a8a0aa5463ebece24c01081e15c9bb4f1f`

## Notebooks

### Image conversion, segmentation, and cell typing

**Notebook**: [multiplex_imaging_analysis](https://github.com/ding-lab/ding-lab-spatial/blob/main/multiplex_imaging/multiplex_imaging_analysis.ipynb)

**Description**

- Covers the following procedures:
  + Conversion of Phenocycler qptiff to OME-TIF format
  + Cell segmentation of OME-TIF
  + Cell feature generation
  + Isolation of sections. (Useful for slides with many sections).
  + Basic cell typing workflow.
   

### Basic image manipulation

**Notebook**: [basic_image_manipulation](https://github.com/ding-lab/ding-lab-spatial/blob/main/multiplex_imaging/basic_image_manipulation.ipynb)

**Description**

Covers basic image manipulations, including:
- Reading of OME-TIF metadata
- Image viewing

For more information on manipulation of arrays in python, see [numpy](https://numpy.org/).





