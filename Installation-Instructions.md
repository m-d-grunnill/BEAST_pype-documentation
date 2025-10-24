

You should only need to carry out the following steps the first time you run the pipeline 
1. Clone the beast_pype repo: 
  ```bash
    git clone https://github.com/m-d-grunnill/BEAST_pype.git
 ```
OR:
  ```bash
    git clone git@github.com:m-d-grunnill/BEAST_pype.git
 ```

2. Install the beast_pype conda environment via conda or mamba:
```bash
conda env create -f requirements.yml
```
OR if you have access mamba (much faster):
```bash
mamba env create -f requirements.yml
```
3. For Jupyter you will need to add a beast_pype environment **python** kernel and a **bash** kernel:
```bash
conda activate beast_pype
python -m ipykernel install --user --name=beast_pype
python -m bash_kernel.install --user
```
4. The beast_pype package itself will need to be installed:
```bash
cd LOCATION_YOU_CLONED_THE_BEAST_PYPE_REPO_TO
pip install -e .
```
5. You will need to install BEAST 2 packages for the BEAST that a template BEAST 2 xml uses (see https://www.beast2.org/managing-packages/)
    The command below demonstrates how to install the BDSKY package used in the [BDSKY Serial Workflow](BDSKY-Serial-Workflow.md):
    ```
    packagemanager -add BDSKY
    ```
6. For using the widgets (interactive GUI) in Phase-5-Diagnosing_Outputs_and_Generate_Report.ipynb notebook you **MAY** need to run the commands below:
    ```
    jupyter nbextension enable --py --sys-prefix widgetsnbextension
    jupyter labextension install @jupyter-widgets/jupyterlab-manager
    ```