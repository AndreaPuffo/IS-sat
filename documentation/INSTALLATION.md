## Installation

In the presented paper, we used `Python 3.11.11`, `jax 0.4` and `mosek 10.2.`. The following steps ensure that you install the same setup for future reproducibility.  
These instructions entail the automatic installation of the required packages, and will require the registration of the Mosek license (free). You should be able to complete these instructions and run the IS-sat code in approximately 30 minutes.  

The code was tested on OS: Linux Ubuntu 20.04 and Linux Ubuntu 24.04.  


### 0) Clone the repository
First, clone the repository:
```
git clone https://github.com/AndreaPuffo/IS-sat.git
cd IS-sat
```

Next, 3 methods are hereby provided to install the following main dependencies. Select the one that best suit your needs, we suggest method 1.2).

  
### 1.1) Approach 1: install the requirements at system level (not recommended)
If Python3.11 is available on your machine, you can install the required packages at system level with:
```  
pip3 install -r ./documentation/requirements.txt  
```

As a last step, you need to activate a Mosek license. As Mosek installation instructions might vary over time, please refer to the most up to date instructions: https://docs.mosek.com/latest/install/installation.html  
At the time of writing these instructions, a free personal license can be requested at this address: https://www.mosek.com/products/academic-licenses/  
After having activated a valid Mosek license, copy the license file `mosek.lic` (do not rename the file) inside the code folder as: `IS-sat/src/mosek_license/mosek.lic`.  
  
Installation of `jax`: the following instructions are tested on a system employing only CPUs. If you have a GPU, `jax` might require an alternative version. TODO: test on a GPU.      
   
Move to step 2).


### 1.2) Approach 2: clone the Anaconda environment
If [Anaconda](https://docs.anaconda.com/free/anaconda/install/) is installed on your system, you can clone the environment with: 

```
conda env create -f documentation/env_is_sat.yml
conda activate env_is_sat
```
  
As a last step, you need to activate a Mosek license. As Mosek installation instructions might vary over time, please refer to the most up to date instructions: https://docs.mosek.com/latest/install/installation.html  
At the time of writing these instructions, a free personal license can be requested at this address: https://www.mosek.com/products/academic-licenses/  
After having activated a valid license, copy the license file `mosek.lic` (do not rename the file) inside the code folder as: `IS-sat/src/mosek_license/mosek.lic`.       
  
(use `conda deactivate` upon completion.)

Move to step 2).



### 1.3) Approach 3: create a Python virtual environment
  
If Python3.11 is installed on your system, the code can be run in a [virtual environment](https://docs.python.org/3/library/venv.html). Start as follows:
```
pip3 install virtualenv
python3.11 -m venv venv_is_sat
source venv_is_sat/bin/activate
python -V
pip3 install -r documentation/requirements.txt  
```
    
As a last step, you need to activate a Mosek license. As Mosek installation instructions might vary over time, please refer to the most up to date instructions: https://docs.mosek.com/latest/install/installation.html  
At the time of writing these instructions, a free personal license can be requested at this address: https://www.mosek.com/products/academic-licenses/  
After having activated a valid license, copy the license file `mosek.lic` (do not rename the file) inside the code folder as: `IS-sat/src/mosek_license/mosek.lic`.  
   
(use `deactivate` upon completion.)

Move to step 2).


### 2) Test IS-sat successful installation
These commands will run the training for the *nonlinear AUV* system:
```
cd IS-sat/src
python3 main_train_is_sat.py  
```
    
