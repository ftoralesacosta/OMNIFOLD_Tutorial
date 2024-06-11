# PHYSTAT 2024 OmniFold Tutorial

This Repository is an OminFold tutorial meant to walk through the steps of using Omnifold for unfolding at the [PHYSTAT 2024](https://indico.cern.ch/event/1357972/) conference. 

[OmniFold](https://arxiv.org/abs/1911.09107), we use ML-based deconvolution (called “unfolding” in particle/nuclear physics) to measure moments defining properties of collisions. By iteratively reweighting a set of simulated events with deep learning, we can correct entire datasets for detector effects. 

We first repurpose a classifier as a [likelihood-ratio estimator](https://link.springer.com/article/10.1007/JHEP02(2024)136) to reweight synthetic data to match real data.  A second step acts on the synthetic data prior to detector simulation to locally average over the phase space.  The key aspect of this approach is that it can process unbinned (and high-dimensional) inputs, unlike classical methods like Lucy-Richardson deconvolution (called “iterative Bayesian unfolding” in particle/nuclear physics).  

## Data
The data used for this tutorial is a [Pythia/Herwig + Delphes Jet Datasets for OmniFold](https://zenodo.org/records/3548091). You can load it easily using the [EnergyFlow python package](https://energyflow.network/docs/datasets/#z-jets-with-delphes-simulation)This dataset has the advantage of having small file sizes, as well as having detector and particle level events from different event generators. The tutorial notebook will step through the structure of the data, but please refer to the link for any confusion on the dataset. If you use this data, please give credit to the original authors!

## Main Requirements
- TensorFlow
- numpy
- matplotlib
- Jupyter

## Environment
- `python -m venv OMNIFOLD_venv`
- `source OMNIFOLD_venv/bin/activate`
- `pip install -r requirements.txt`
- `python -m ipykernel install --user --name=OMNIFOLD_venv`
- `jupyter-lab` # or notebook
