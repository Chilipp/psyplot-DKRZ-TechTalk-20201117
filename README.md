# Visualizing unstructured grids from scripts and GUI with psyplot

Presentation materials for the [TechTalk about psyplot][techtalk] by
Philipp S. Sommer at the [German Climate Computing Center (DKRZ)][DKRZ],
November 17th, 2020

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Chilipp/psyplot-DKRZ-TechTalk-20201117/main?filepath=psyplot-framework-presentation.ipynb)

## Abstract

psyplot (https://psyplot.github.io) is a data visualization framework that integrates rich computational and mathematical software packages (such as xarray and matplotlib) into a flexible framework for visualization. It differs from most of the visual analytic softwares such that it focuses on extensibility in order to flexibly tackle the different types of analysis questions that arise in pioneering research. The design of the high-level API of the framework enables a simple and standardized usage from the command-line, python scripts or jupyter notebooks. A modular plugin framework enables a flexible development of the framework that can potentially go into many different directions. The additional enhancement with a flexible GUI makes it the only visualization framework that can be handled from the convenient command-line, as well as via point-click handling. It also allows to build further desktop applications on top of the existing framework.

In this TechTalk, I will show the main functionalities of psyplot, with a special focus on the visualization of unstructured grids (such as ICON), and the usage of psyplot on the HPC facilities of the DKRZ (mistral, jupyterhub, remote desktop, etc.). My demonstration will cover in particular

- the psyplot framework
- how to use psyplot in python scripts (and jupyter notebooks)
- a guide to the psyplot GUI
- the new ncview-like interface build upon psyplot
- how to reuse plot configurations and generate respective templates


## About this presentation

### Static version

This presentation is a jupyter notebook presented with [RISE][rise]. You can
access the raw notebook at
[psyplot-framework-presentation.ipynb](psyplot-framework-presentation.ipynb).

### interactive version on mybinder.org

Alternatively, run it interactively on mybinder.org by clicking here:
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/Chilipp/psyplot-DKRZ-TechTalk-20201117/main?filepath=psyplot-framework-presentation.ipynb)

You will automatically start in presentation mode, but you can cancel this with
Alt-R to see the standard jupyter notebook layout.

### interactive version on mistral

You can also run this presentation notebook on mistral. To run it, please
proceed with the following commands from the terminal when connected to the DKRZ
supercomputing facilities via SSH:

```bash
git clone https://github.com/Chilipp/psyplot-DKRZ-TechTalk-20201117.git
module load python3
. `dirname $(which conda)`/../etc/profile.d/conda.sh
conda activate /work/gg0302/g260169/psyplot-examples/conda-env/

python -m ipykernel install --user --name psyplot-presi --display-name "IPython kernel for psyplot"
jupyter nbextension enable splitcell/splitcell
```

Then head over to https://jupyterhub.dkrz.de, login and click on _Preset_.
Click _start from preset profiles_ and enter your DKRZ project account.

Start it and, as soon as you see the notebook server (it will start in your `$HOME`) navigate to cloned repository and open the `psyplot-framework-presentation.ipynb`

### Local installation using repo2docker

In case you have docker installed on your local computer, you can simply use [repo2docker](https://repo2docker.readthedocs.io/en/latest/) to start this notebook.

Just type

```
repo2docker -P https://github.com/Chilipp/psyplot-DKRZ-TechTalk-20201117.git
```

and open the link that is shown to you at the end of the build process.

### Local installation manually

Clone the repository:

```bash
git clone https://github.com/Chilipp/psyplot-DKRZ-TechTalk-20201117
cd psyplot-DKRZ-TechTalk-20201117
```

Create a new conda environment via

```bash
conda env create -f binder/environment.yml
conda activate psyplot-presi
```

activate the splitcell jupyter extension

```bash
jupyter nbextension enable splitcell/splitcell
```

export some environment variables that are necessary for pyvista

```bash
export PYVISTA_OFF_SCREEN=true
export PYVISTA_USE_IPYVTK=true
export PYVISTA_PLOT_THEME=document
```


start the notebook server via

```bash
jupyter notebook
```

[techtalk]: https://www.dkrz.de/up/news-and-events/tech-talks/tech-talk-visualizing-unstructured-grids-from-scripts-and-gui-with-psyplot
[DKRZ]: https://www.dkrz.de/
