# Locally

## Installation requirements

PyCoA requires `Python` version >= 3 and a version of [`Bokeh`](https://docs.bokeh.org/en/latest/) >= 2.4.0 is recommended.  
Please note that the tool currently works within `notebooks` of the [`jupyter`/`jupyterlab`](https://jupyter.org/) type, particularly for graphics output rendered by the host browser.

Many libraries are [required](../../requirements.txt), but explicit installation is only necessary when installing via an archive file or a git clone.

## Installing with `pip`

This is by far the easiest installation. It is applied either locally on the command line or within a notebook running on an external jupyter.

Requirements:
* [`pip`](https://pypi.org/project/pip/)
* [`git`](https://git-scm.com/downloads)

### On the command line

* To install the latest stable version, run the command

```bash
pip3 install --user git+https://github.com/coa-project/pycoa.git
```

which will install all the libraries required for `PyCoA` as well as `pycoa` itself for the user.

> If you want to install `pycoa` for all users of the machine, remove the `--user` option, i.e. :  
    ```
    pip3 install git+https://github.com/coa-project/pycoa.git
    ```

To retrieve a particular version, specify the _tag_ in the `pip install` command as follows to install the version tagged `v1.0`.

```bash
pip3 install --user git+https://github.com/coa-project/pycoa.git@v1.0
```

Finally, if you don't want to know the details of the installation, you can add the `--quiet` option to the `pip` command.

## Manual installation from sources

### Library requirements

In addition to the standard libraries, you will need to have the following on your system:

* [`python3`](https://www.python.org/downloads/)
* [`numpy`](https://numpy.org/)
* [`pip`](https://pypi.org/project/pip/)

and the packages in the [requirements.txt](../../requirements.txt) file, which can be accessed with a simple command 

```
pip3 install -r requirements.txt
```

> Note that a number of these libraries come automatically when the `pip` tool is installed.

### Installation with an archive file

They are available in [`zip`](https://github.com/coa-project/pycoa/zipball/main) or [`tarball`](https://github.com/coa-project/pycoa/tarball/main) format, or directly on the [github page of the `pycoa` project](https://github.com/coa-project/pycoa).

Download the archive and decompress it in the location of your choice for python packages on your system. If necessary, explicitly specify the installation path in your notebooks using `pycoa`:

```python
import sys
sys.path.insert(1, '/some/part/pycoa') # replace /some/part with the real installation path
```

### Cloning from GitHub

You can also recover the sources by cloning the project locally. 

```bash
git clone https://github.com/coa-project/pycoa.git
```

Here again, you will need to specify the installation path if necessary.

## Test for correct installation

To test that the library exists in the path use in python:

```python
import coa.front as cf
cf.getversion()
```