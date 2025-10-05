# What is this script for?
This script is designed to run [GPAW](https://gpaw.readthedocs.io/) on [Lambda's](https://cloud.lambda.ai/instances) new ARM-based server with an NVIDIA GH200.


## Installation
To run it, simply pull the git to a directory on the server and run the following commands.

```bash
cd Lambda-ARM_NVIDIA-GH200-2DMatSynthPredictions`
chmod a+x install.sh
sudo ./install.sh
```

This will install and compile [LibvdWXC](https://gitlab.com/libvdwxc/libvdwxc), [ELPA](https://elpa.mpcdf.mpg.de/), and [MAGMA](https://icl.utk.edu/magma/)

In the `install.sh` script, you can specify which versions of `MAGMA` and `ELPA` you want via the variables `ELPA_VER` and `MAGMA_VER`. Though, it should be noted that the `ELPA` version is currently set to the newest version that consistenly works with `GPAW` (version 2023.11.001).

In addition to this, the `install.sh` script installs [FFTW3](), [OpenBLAS](), [OpenMPI](), [SCALAPACK]() (with MPI support), and [LibXC]()

Finally, the script builds a custom `~/.gpaw/siteconfig.py` file to install `GPAW` with the correct linkers.

## Use
To use the current script included, simply run these following commands:
```bash
cd ~/code
source ~/.bashrc
python3 main.py
```