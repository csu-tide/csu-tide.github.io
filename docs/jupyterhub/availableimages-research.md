---
layout: default
title: Available Container Images
parent: JupyterHub
nav_order: 5
has_children: false
description: ""
permalink: /jupyterhub/images
---

# Available Container Images

JupyerHub makes use of a container image to execute your code/commands. 
You must use a container image that contains the software you wish to use. 
We use provide official [Jupyter Docker Stacks](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html#core-stacks){:target="_blank"} notebook images. 
However, additional images can be created for specific needs.

All images include GPU Nvidia and CUDA support, and will provide access to GPU resources if selected during container launch.

{: .note }
Some container images have been discontinued, see [discontinued container images](#discontinued-container-images) for alternatives.

## General Container Images

The following general purpose containers are available for use.

| Name                               | Image               | Software             | JupyterHub Instance             |
|:-----------------------------------|:--------------------|:---------------------|:--------------------------------|
| Jupyter Stack Minimal Notebook     | [minimal-notebook](https://github.com/jupyter/docker-stacks/tree/main/images/minimal-notebook){:target="_blank"} | Ubuntu 22.04.4<br/>JupyterLab 4.2.4<br/>Python 3.11.9<br/>Git 2.34.1<br/>vi<br/>nano<br/>wget<br/>unzip<br/>tzdata | CSU TIDE, SDSU |
| Jupyter Stack R Notebook           | [r-notebook](https://github.com/jupyter/docker-stacks/tree/main/images/r-notebook){:target="_blank"} | (Everything in jupyter/minimal-notebook)<br/>The R interpreter and base environment<br/>IRKernel to support R code in Jupyter notebooks<br/>tidyverse packages from [conda-forge](https://conda-forge.org/feedstock-outputs/index.html){:target="_blank"}<br/>[caret](https://topepo.github.io/caret/index.html){:target="_blank"}, [crayon](https://cran.r-project.org/web/packages/crayon/index.html){:target="_blank"}, [devtools](https://cran.r-project.org/web/packages/devtools/index.html){:target="_blank"}, [forecast](https://cran.r-project.org/web/packages/forecast/index.html){:target="_blank"}, [hexbin](https://cran.r-project.org/web/packages/hexbin/index.html){:target="_blank"}, [htmltools](https://cran.r-project.org/web/packages/htmltools/index.html){:target="_blank"}, [htmlwidgets](https://www.htmlwidgets.org/){:target="_blank"}, [nycflights13](https://cran.r-project.org/web/packages/nycflights13/index.html){:target="_blank"}, [randomforest](https://cran.r-project.org/web/packages/randomForest/index.html){:target="_blank"}, [rcurl](https://cran.r-project.org/web/packages/RCurl/index.html){:target="_blank"}, [rmarkdown](https://rmarkdown.rstudio.com/){:target="_blank"}, [rodbc](https://cran.r-project.org/web/packages/RODBC/index.html){:target="_blank"}, [rsqlite](https://cran.r-project.org/web/packages/RSQLite/index.html){:target="_blank"}, [shiny](https://shiny.rstudio.com/){:target="_blank"}, [tidymodels](https://www.tidymodels.org/){:target="_blank"}, [unixodbc](http://www.unixodbc.org/){:target="_blank"} packages from [conda-forge](https://conda-forge.org/feedstock-outputs/index.html){:target="_blank"} | CSU TIDE, SDSU |
| Jupyter Stack SciPy Notebook       | [scipy-notebook](https://github.com/jupyter/docker-stacks/tree/main/images/scipy-notebook){:target="_blank"} | (Everything in jupyter/minimal-notebook)<br/>[altair](https://altair-viz.github.io/){:target="_blank"}, [beautifulsoup4](https://www.crummy.com/software/BeautifulSoup/){:target="_blank"}, [bokeh](https://docs.bokeh.org/en/latest/){:target="_blank"}, [bottleneck](https://bottleneck.readthedocs.io/en/latest/){:target="_blank"}, [cloudpickle](https://github.com/cloudpipe/cloudpickle){:target="_blank"}, [conda-forge::blas=*=openblas](https://www.openblas.net/){:target="_blank"}, [cython](https://cython.org/){:target="_blank"}, [dask](https://www.dask.org/){:target="_blank"}, [dill](https://pypi.org/project/dill/){:target="_blank"}, [h5py](https://www.h5py.org/){:target="_blank"}, [matplotlib-base](https://matplotlib.org/){:target="_blank"}, [numba](https://numba.pydata.org/){:target="_blank"}, [numexpr](https://github.com/pydata/numexpr){:target="_blank"}, [openpyxl](https://openpyxl.readthedocs.io/en/stable/){:target="_blank"}, [pandas](https://pandas.pydata.org/){:target="_blank"}, [patsy](https://patsy.readthedocs.io/en/latest/){:target="_blank"}, [protobuf](https://developers.google.com/protocol-buffers/docs/pythontutorial){:target="_blank"}, [pytables](https://www.pytables.org/){:target="_blank"}, [scikit-image](https://scikit-image.org/){:target="_blank"}, [scikit-learn](https://scikit-learn.org/stable/){:target="_blank"}, [scipy](https://scipy.org/){:target="_blank"}, [seaborn](https://seaborn.pydata.org/){:target="_blank"}, [sqlalchemy](https://www.sqlalchemy.org/){:target="_blank"}{:target="_blank"}, [statsmodel](https://www.statsmodels.org/stable/index.html){:target="_blank"}, [sympy](https://www.sympy.org/en/index.html){:target="_blank"}, [widgetsnbextension](https://ipywidgets.readthedocs.io/en/latest/user_install.html#installing-in-classic-jupyter-notebook){:target="_blank"}, [xlrd](https://www.python-excel.org/){:target="_blank"} packages<br/>ipympl and ipywidgets for interactive visualizations and plots in Python notebooks<br/>[Facets](https://github.com/PAIR-code/facets){:target="_blank"} for visualizing machine learning datasets | CSU TIDE, SDSU |
| Jupyter Stack Tensorflow Notebook  | [tensorflow-notebook](https://github.com/jupyter/docker-stacks/tree/main/images/tensorflow-notebook){:target="_blank"} | (Everything in jupyter/scipy-notebook and its ancestor images)<br/>[tensorflow](https://www.tensorflow.org/){:target="_blank"} machine learning library<br/>Jupyter Server Proxy to support TensorBoard | CSU TIDE, SDSU |
| Jupyter Stack PyTorch Notebook     | [pytorch-notebook](https://github.com/jupyter/docker-stacks/tree/main/images/pytorch-notebook){:target="_blank"} | (Everything in jupyter/scipy-notebook and its ancestor images)<br/>[pytorch](https://pytorch.org/){:target="_blank"} machine learning library (torch, torchaudio, torchvision) | CSU TIDE, SDSU | 
| Jupyter Stack Julia Notebook       | [julia-notebook](https://github.com/jupyter/docker-stacks/tree/main/images/julia-notebook){:target="_blank"} | (Everything in jupyter/minimal-notebook)<br/>The [Julia](https://julialang.org/){:target="_blank"} compiler and base environment<br/>[IJulia](https://julialang.github.io/IJulia.jl/stable/){:target="_blank"} to support Julia code in Jupyter notebook<br/>[Pluto.jl](https://plutojl.org/){:target="_blank"} reactive Julia notebook interface, made accessible with [jupyter-pluto-proxy](https://pypi.org/project/jupyter-pluto-proxy/){:target="_blank"}<br/>[HDF5](https://docs.h5py.org/en/stable/){:target="_blank"} package | TIDE, SDSU
| Jupyter Stack Datascience Notebook | [datascience-notebook](https://github.com/jupyter/docker-stacks/tree/main/images/datascience-notebook){:target="_blank"} | (Everything in the jupyter/scipy-notebook, jupyter/r-notebook, and jupyter/julia-notebook images and their ancestor images)<br/>[rpy2](https://rpy2.github.io/doc/latest/html/index.html){:target="_blank"} package | CSU TIDE, SDSU |

The following diagram shows the relationship of the above container images.

```mermaid
graph LR;
    A[minimum-notebook]-->B[r-notebook];
    A-->H[scipy-notebook];
    A-->G[julia-notebook];
    A-->C[scipy-notebook]-->D[tensorflow-notebook];
    C-->E[datascience-notebook];
```

## Custom Container Images

| Name                        | Image               | Software             | JupyterHub Instance             |
|:----------------------------|:--------------------|:---------------------|:--------------------------------|
| NRP R Studio Notebook       | [r-studio](https://gitlab.nrp-nautilus.io/nrp/scientific-images/rstudio){:target="_blank"} | (Everything in jupyter/r-notebook and its ancestors)<br/>R Studio | CSU TIDE, SDSU |
| Eclipse C/C++ Desktop       | [eclipse-notebook](https://github.com/SDSU-Research-CI/eclipse-notebook){:target="_blank"} | (Everything in jupyter/minimal-notebook)<br/>Eclipse IDE for C/C++ Developers 2024-06 release for Linux x86_64<br/>__build-essential__<br/>__Jupyter Desktop__<br/>[xfce4](https://www.xfce.org/about){:target="_blank"} desktop | CSU TIDE, SDSU |
| Kube Notebook               | [kube-notebook](https://github.com/SDSU-Research-CI/kube-notebook){:target="_blank"} | (Everything in jupyter/minimal-notebook)<br/>[rclone](https://rclone.org/){:target="_blank"}<br/>[kubectl](https://kubernetes.io/docs/reference/kubectl/){:target="_blank"}<br/>__Jupyter Desktop__<br/>__Code Server (VS Code)__<br/>__Globus Connect Personal__<br/>__NB Conda Kernels__ | CSU TIDE, SDSU |
| SageMath Notebook           | [sagemath-notebook](https://github.com/SDSU-Research-CI/sagemath-notebook){:target="_blank"} | (Everything in jupyter/scipy-notebook and its ancestors)<br/>[SageMath Kernel](https://doc.sagemath.org/html/en/index.html#){:target="_blank"} | CSU TIDE, SDSU |
| GIS Notebook                | [gis-notebook](https://github.com/SDSU-Research-CI/gis-notebook){:target="_blank"} | (Everything in jupyter/pytorch-notebook and its ancestors)<br/>[beautifulsoup4](https://pypi.org/project/beautifulsoup4/){:target="_blank"}<br/>__boto3__<br/>__eo-learn__<br/>[geopandas](https://geopandas.org/en/stable/docs/user_guide.html){:target="_blank"}<br/>[geoplot](https://pypi.org/project/geoplot/){:target="_blank"}<br/>[laspy](https://laspy.readthedocs.io/en/latest/){:target="_blank"}<br/>__lightgbm__<br/>__natsort__<br/>[netcdf4](https://pypi.org/project/netCDF4/){:target="_blank"}<br/>[networkx](https://networkx.org/){:target="_blank"}<br/>[psycopg2](https://pypi.org/project/psycopg2/){:target="_blank"}<br/>[pysal](https://pysal.org/){:target="_blank"}<br/>[rasterio](https://rasterio.readthedocs.io/en/stable/){:target="_blank"}<br/>[rclone](https://rclone.org/){:target="_blank"}<br/>[selenium](https://www.selenium.dev/){:target="_blank"}<br/>__sentinelhub__<br/>__xeus-python__ | CSU TIDE, SDSU |
| Health-Informatics-Notebook | [health-informatics-notebook](https://github.com/SDSU-Research-CI/health-informatics-notebook){:target="_blank"} | (Everything in jupyter/scipy-notebook and its ancestors)<br/>__bcftools__<br/>[biopython](https://biopython.org/wiki/Documentation){:target="_blank"}<br/>__bwa__<br/>__ensembl-vep__<br/>__fastp__<br/>__goalign__<br/>__gotree__<br/>__mafft__<br/>__modeltest-ng__<br/>__mummer__<br/>[pytest](https://docs.pytest.org/en/7.4.x/){:target="_blank"}<br/>__raxml-ng__<br/>__samtools__<br/>__spades__<br/>__varscan__  | CSU TIDE, SDSU |
| Astro Notebook              | [astro-notebook](https://github.com/SDSU-Research-CI/astro-notebook){:target="_blank"} | (Everything in jupyter/scipy-notebook and its ancestors)<br/>__astropy__<br/>__astroquery__<br/>__photutils__<br/>__emcee__<br/>__corner__<br/>__fsps__<br/>__lxml__<br/>__reportlab__<br/>__SKIRT__<br/>__PTS__ | CSU TIDE, SDSU
| LLM Notebook                | [llm-notebook](https://github.com/SDSU-Research-CI/LLM-Notebook){:target="_blank"} | (Everything in jupyter/pytorch-notebook and its ancestors)<br/>__rclone__<br/>__FastChat__<br/>__Ollama__<br/>__Code Server (VS Code)__<br/>__Jupyter AI__<br/>__bitsandbytes__<br/>__transformers__<br/>__peft__<br/>__accelerate__<br/>__trl__<br/>__ollama-python__<br/>__openai__<br/>__pyaudio__<br/>__portaudio__<br/>__cuda-nvcc__<br/>__deepspeed__<br/>__langchain__<br/>__huggingface_hub__<br/>__auto_gptq__<br/>__autoawq__<br/>__xformers__<br/>__dask-kubernetes__<br/>__chromadb__ | CSU TIDE, SDSU
| George Lab Notebook         | [georgelab-notebook](https://github.com/SDSU-Research-CI/georgelab-notebook){:target="_blank"} | (Everything in jupyter/scipy-notebook and its ancestors)<br/>__rclone__<br/>__VS Code Server__<br/>__opencv__<br/>__gudhi__<br/>__tabulate__<br/>__ripser__<br/>__persim__<br/>__nb_conda_kernels__<br/>__tissue-forge__ (CPU and GPU) | SDSU |
| MATLAB + Pulmonary Toolkit  | Image is available upon request | (Everything in jupyter/scipy-notebook and its ancestors)<br/>__MATLAB r2024b__<br/>[MATLAB pulmonarytoolkit](https://github.com/tomdoel/pulmonarytoolkit.git){:target="_blank"}<br/>[rclone](https://rclone.org/install/)<br/>[NBIA Data Retriever](https://wiki.nci.nih.gov/display/NBIA/Downloading+NBIA+Images+6.5.3)<br/>[Jupyter Desktop](https://github.com/jupyterlab/jupyterlab-desktop) | SDSU |
| MATLAB + Bertini            | Image is available upon request | (Everything in jupyter/datascience-notebook)<br/>__Bertini__<br/>__LikelihoodProfiler__<br/>__MATLAB r2024b__<br/>[PyTorch](https://pytorch.org/get-started/locally/)<br/>__StructuralIdentifiability__ | SDSU |
| Kaya Lab Notebook           | [kaya-notebook](https://github.com/SDSU-Research-CI/kaya-notebook){:target="_blank"} | (Everything in jupyter/minimal-notebook)<br/>[Code Server (VS Code)](https://code.visualstudio.com/docs/remote/vscode-server){:target="_blank"}<br>__torch_amr__ environment | SDSU |
| MESA Notebook               | [mesa-notebook](https://github.com/SDSU-Research-CI/mesa-notebook){:target="_blank"} | (Everything in jupyter/minimal-notebook)<br/>__binutils__<br/>__libx11-6__<br/>__libx11-dev__<br/>__make__<br/>__mesa-r24.03.1__<br/>__tcsh__<br/>__unzip__<br/>__zlib1g__<br/>__zlib1g-dev__ | SDSU | 
| PyTorch Geometric Notebook  | [torch-geometric-notebook](https://github.com/SDSU-Research-CI/torch-geometric-notebook){:target="_blank"} | (Everything in jupyter/pytorch-notebook and its ancestors)<br/>__Code Server (VS Code)__<br/>__PyTorch Geometric__<br/>__rclone__ | SDSU |
| FST3 Notebook               | [fst3-notebook](https://github.com/SDSU-Research-CI/FST3-Notebook){:target="_blank"} | (Everything in jupyter/minimal-notebook)<br/>__fst3 conda environment__ | SDSU | 
| ClimaAtmos Notebook         | [ClimaAtmos-Notebook](https://github.com/SDSU-Research-CI/ClimaAtmos-Notebook/tree/main){:target="_blank"} | (Everything in jupyter/julia-notebook and its ancestors)<br/>__ClimaAtmos__<br/>__ClimaCore__<br/>__ClimaCoupler__<br/>__cuda-runtime__<br/>__openmpi__ | SDSU |
| RStudio Desktop Notebook    | [rstudio-desktop-notebook](https://github.com/SDSU-Research-CI/rstudio-desktop-notebook){:target="_blank"} | (Everything in NRP R Studio Notebook)<br/>__RStudio__<br/>__Jupyter Desktop__ | SDSU | 
| Molecular Dynamics Notebook   | [molecular-dynamics-notebook](https://github.com/SDSU-Research-CI/md-notebook){:target="_blank"} | (Everything in jupyter/scipy-notebook and its ancestors)<br/>__LAMMPS__<br/>__Jupyter Desktop__<br/>__Quantum Espresso__<br/>__cmake__<br/>__gcc__<br/>__g++__<br/>__openmpi-bin__<br/>__ovito__<br/>__vim__ | SDSU |
| TEND Lab Notebook           | [tend-lab-notebook](https://github.com/SDSU-Research-CI/tend-lab-notebook){:target="_blank"} | (Everything in jupyter/r-notebook)<br/>__AFNI__<br/>__Code Server (VS Code)__<br/>__Jupyter Desktop__<br/>__rclone__<br/>__SUMA__<br/>__TEND Lab conda environment__ | SDSU |
| BART Notebook               | [bart-notebook](https://github.com/SDSU-Research-CI/BART-Notebook){:target="_blank"} | (Everything in jupyter/scipy-notebook)<br/>__BART__<br/>__Code Server (VS Code)__<br/>__Custom environment__<br/>__Globus Connect Personal__<br/>__Jupyter Desktop__<br/>__NB Conda Kernels__<br/>__rclone__<br/> | SDSU | 

The following diagram shows the relationship between the general and custom container images.

```mermaid
graph LR;

%% Base images
A[minimal-notebook]
B[r-notebook]
C[scipy-notebook]
D[pytorch-notebook]
E[julia-notebook]
F[datascience-notebook]

%% Derived notebooks
A --> eclipse-notebook
A --> kube-notebook
A --> kaya-notebook
A --> mesa-notebook
A --> fst3-notebook

B --> r-studio
B --> tend-lab-notebook

r-studio --> rstudio-desktop-notebook

C --> sagemath-notebook
C --> health-informatics-notebook
C --> astro-notebook
C --> georgelab-notebook
C --> molecular-dynamics-notebook
C --> bart-notebook
C --> matlab-pulmonary

F --> matlab-bertini

D --> gis-notebook
D --> llm-notebook
D --> torch-geometric-notebook

E --> climaatmos-notebook

%% Aliases for MATLAB custom images
matlab-pulmonary[MATLAB + Pulmonary Toolkit]
matlab-bertini[MATLAB + Bertini]

%% Aliases for names with hyphens not ideal as node IDs
r-studio[NRP R Studio Notebook]
rstudio-desktop-notebook[RStudio Desktop Notebook]
eclipse-notebook[Eclipse C/C++ Desktop]
kube-notebook[Kube Notebook]
sagemath-notebook[SageMath Notebook]
gis-notebook[GIS Notebook]
health-informatics-notebook[Health-Informatics-Notebook]
astro-notebook[Astro Notebook]
llm-notebook[LLM Notebook]
georgelab-notebook[George Lab Notebook]
kaya-notebook[Kaya Lab Notebook]
mesa-notebook[MESA Notebook]
torch-geometric-notebook[PyTorch Geometric Notebook]
fst3-notebook[FST3 Notebook]
climaatmos-notebook[ClimaAtmos Notebook]
molecular-dynamics-notebook[Molecular Dynamics Notebook]
tend-lab-notebook[TEND Lab Notebook]
bart-notebook[BART Notebook]
```

## Discontinued Container Images

| Name      | Alternative |
|:----------|:------------|
| Stack PRP | Jupyter Stack PyTorch Notebook in [general container images](#general-container-images)
