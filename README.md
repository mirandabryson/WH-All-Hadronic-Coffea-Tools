# WH All-Hadronic Coffea Tools
---
## Checkout Instructions 

    git clone https://github.com/mirandabryson/WH-All-Hadronic-Coffea-Tools.git
    
## Set Up

Install Jupyter Notebook
    
    pip install jupyterlab
    
Set Up Coffea and other tools    

    source setup.sh
    
## Running Jupyter Hub locally (credit to Nick)

# Set Up

    curl -O -L https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
    bash Miniconda3-latest-Linux-x86_64.sh -b 

    # adds conda to the end of ~/.bashrc, so relogin after executing this line
    ~/miniconda3/bin/conda init

    # stops conda from activating the base environment on login
    conda config --set auto_activate_base false
    conda config --add channels conda-forge

    conda create --name analysisenv uproot matplotlib pandas jupyter numba dask dask-jobqueue -y

    # activate environment and install some packages once
    conda activate analysisenv
    pip install git+git://github.com/aminnj/yahist.git#egg=yahist -U
    pip install tqdm coffea jupyter-server-proxy autopep8 jupyter_nbextensions_configurator
    

# Start Jupyter Notebook

    conda activate analysisenv 
    jupyter notebook --no-browser

    # then execute this on your local computer to forward the port, and visit the url in your browser (1234 will be replaced with the four digits produced by the above command)
    ssh -N -f -L localhost:1234:localhost:1234 uaf-10.t2.ucsd.edu


## Running notebooks

These script use the coffea processor module to produce plots for NanoAOD files. Paths to the fileset and outdir are set by user. 

## Other Resources

General Coffea Information: https://coffeateam.github.io/coffea/index.html

Documentation for NanoAOD: https://cms-nanoaod-integration.web.cern.ch/integration/master-102X/mc102X_doc.html

