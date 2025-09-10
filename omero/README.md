# Omero

## Uploading images

Images can be uploaded via the omero desktop application, or the command line.

The server address is `omero.ris.wustl.edu:4064` and the username and password is your wustl key.

#### Uploading via desktop

The [omero.insight desktop viewer](https://www.openmicroscopy.org/omero/downloads/) can be used to upload images via the desktop.

For instructions and how to upload, please see this [documentation](https://omero-guides.readthedocs.io/en/latest/upload/docs/import-desktop-client.html).

#### Uploading via the command line

First, we need to install the omero command line client. Here, we do so with Conda.

```bash
conda create -n omero -c conda-forge "python=3.12" jupyter omero-py -y
conda activate omero
```

For more info, see omero's [documentation](https://omero.readthedocs.io/en/stable/users/cli/import.html), but below is an example of uploading an image.

First, we login.
```bash
omero login
```

You should see a prompt like below, fill it out with the correct username and password (it should be your wustl key and password).
```bash
Server: [omero.ris.wustl.edu:4064]
Username: [estorrs]
Password:
```

Once logged in, we can import images. Make sure you replace `PROJECT_NAME` and `DATASET_NAME` with your project and dataset you are trying to upload to.
```bash
omero import /path/to/input/image -t Project:name:PROJECT_NAME/Dataset:name:DATASET_NAME
```
