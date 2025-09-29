## 3D registration and analysis

## Installation

To create environment with conda
```bash
conda create -n 3d-analysis -c conda-forge python jupyter jupyter_contrib_nbextensions "imagecodecs>=2022.7.27" scikit-image scikit-learn einops squidpy scanpy tifffile ome-types pyyaml -y
conda activate 3d-analysis
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

### Registration of serial sections

**Notebook**: [serial_section_registration](https://github.com/ding-lab/ding-lab-spatial/blob/main/3d_analysis/serial_section_registration.ipynb)

**Description**

Covers registration procedure for serial section data.

### Annotation of 3D paths

**Notebook**: [3D path annotation](https://github.com/ding-lab/ding-lab-spatial/blob/main/3d_analysis/3D_path_annotation.ipynb)

**Description**

Covers how to annotate regions on registered 3D sections and analyze them.

Also shows how to get cells/transcripts that fall within a region, calculate mean expression across a region, and visualize paths.



