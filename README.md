# python_container

Singularity container recipe(s) for Python builds with installed packages for those that have restricted access to the web/strict firewalls/lack sudo rights/or are running code/analysis on a HPC 

## About python_env_v0.1
OS:  Ubuntu version xenial  
Python version 2.7  
Libraries installed:  
* chunkypipes
* chardet v3.0.4
* Cython v0.28.2
* cycler v0.10.0
* decorator v4.3.0
* docutils v0.14
* enum v.1.1.6
* jsonschema v2.6.0
* mpmath v1.0.0
* nbformat v4.4.0 
* pandas v0.22.0
* pyparsing v2.2.0
* requests v2.18.4
* numpy v1.14.2
* matplotlib v2.2.2
* fpdf v1.7.2
* Pillow v5.1.9
* pypdf2 v1.26.0
* statistics v1.0.3.5
* traitlets v4.3.2
* xlrd v1.1.0
* nose v1.3.7
* sympy v1.1.1
* scipy v1.0.1
* pysam v0.14.1
* bx-python v0.8.1
* RSeQC v2.6.4
* nltk v3.2.5
* seaborn v0.8.1
* six v1.11.0
* plotly v2.5.2
* scikit-learn v0.19.1
* xlrd v1.1.0
* urllib3 v1.22


## Installation and Build
Singularity must be installed on your local computer with root privileges.

1.  Clone this repo and change into repo directory:
```
git clone https://github.com/tbrunetti/python_container.git
cd python_container
```  
2.  Build container (may take several minutes)
```
sudo singularity build --writable myContainer.simg python_env_v0.1_recipe.txt
```   
3.  Move container to any location **sudo not required!**  
Can be moved to:  
* different location on your local computer
* a different computer with any OS
* HPC

## Usage
To access the container shell with accessibilty to the above libraries:  
```
singularity shell myContainer.simg
```
This will activate your container and give you an interactive shell that has access to all the installed programs and libraries in your container.  

Alternatively, using the `run` command followed by the command to execute will run command call using the available programs, libraries and packages installed within the container.  
```
singularity run myContainer.simg python myProgram.py
```
