# Install

It is recommended to use a virtual environment for Python, such as [Anaconda](https://www.anaconda.com/products/individual).

## Step-by-step

First, we create a virtual environment.

```bash
conda create --name diffusion python=3
conda activate diffusion
```

The second command changes the prompt from `$` to `(diffusion)$`.
All further commands are assumed to be executed in this new environment.

Next, we install the dependencies.
We use the `conda` versions of the major packages as these usually work better.
In addition, the `conda` version of `numpy` comes with support for the Intel MKL, offering extra speed up on supported systems.

```bash
conda install numpy scipy matplotlib
```

Optionally, one can install `IPython` and/or `Jupyter` for interactive use.

```bash
conda install ipython jupyter
```

Now, we can install the code in this repository.

```bash
pip install git+https://github.com/janniklasrose/diffusion-models.git
```

Alternatively, from the local `clone`d repository, we can execute:

```bash
pip install --editable .
```

The `-e`/`--editable` flag tells `pip` to `install` the package path.
This leaves the source files editable.

## Reproducible environment

We provide the file [diffusion.yml](./diffusion.yml) to quickly create a tested `conda` environment.
Simply execute:

```bash
conda env create --file diffusion.yml --name diffusion
```

The file was created using

```bash
conda env export --name diffusion > diffusion.yml
```

and then edited to remove the `prefix` key and move `pip` requirements to the [requirements.txt](./requirements.txt) file.
