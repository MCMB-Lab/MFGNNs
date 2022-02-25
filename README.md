## Multiscale Computational Mechanics and Biomechanics LAB (MCMB Lab)
Department of Mechanical Engineering and Mechanics

Drexel University, Philadelphia, Pennsylvania 

Director: Ahmad Raeisi Najafi (Ph.D.)

All rights reserved.

Developer: Nolan Black 10/2020

Created in: 10/2020

Last modified in: 2022

Graph Formulation Incoporated via the GraphNets Library and the Encode-Process-Decode Model structure:

```
@misc{battaglia2018relational,
      title={Relational inductive biases, deep learning, and graph networks}, 
      author={Peter W. Battaglia and Jessica B. Hamrick and Victor Bapst and Alvaro Sanchez-Gonzalez and Vinicius Zambaldi and Mateusz Malinowski and Andrea Tacchetti and David Raposo and Adam Santoro and Ryan Faulkner and Caglar Gulcehre and Francis Song and Andrew Ballard and Justin Gilmer and George Dahl and Ashish Vaswani and Kelsey Allen and Charles Nash and Victoria Langston and Chris Dyer and Nicolas Heess and Daan Wierstra and Pushmeet Kohli and Matt Botvinick and Oriol Vinyals and Yujia Li and Razvan Pascanu},
      year={2018},
      eprint={1806.01261},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```

```
@misc{sanchezgonzalez2020learning,
      title={Learning to Simulate Complex Physics with Graph Networks}, 
      author={Alvaro Sanchez-Gonzalez and Jonathan Godwin and Tobias Pfaff and Rex Ying and Jure Leskovec and Peter W. Battaglia},
      year={2020},
      eprint={2002.09405},
      archivePrefix={arXiv},
      primaryClass={cs.LG}
}
```

# MFGNNs
This repository is presented in parallel with my paper "Learning Finite Element Convergence with the Multi-fidelity Graph Neural Network (MFGNN)"

The code is presented in .ipynb format and is intended to illustrate design decisions and key performance of the MFGNN. **The code is appropriate for researchers of physics-based machine learning and is not intended for widespread distribution, however it is my hope that this repository increases the transparency and approachability of the MFGNN framework.**

This work builds on the graph_nets library (https://github.com/deepmind/graph_nets) and the encode-process-decode model presented by Sanchez-Gonzales et al. (arXiv:2002.09405).

The finite element method presented here is developed in part from the experience of the MCMB Lab at Drexel University's College of Engineering under Professor Ahmad R. Najafi. Additional material and fundamental algorithms are developed from the work of Professor Daniel A. Tortorelli.

## Included Here:
`Funtions.ipynb` is a notebook outlining key functions used to augment and expand the GraphNets library.

`Demo.ipynb` provides a demo of the input processing and model execution. Various models can be loaded and compared for multiple 2D beam cases. 

`DataGeneration.ipynb` may be used to build training datasets for either GNNs or MFGNNs to learn various FEA quantities (displacement, stress, etc.)

`GNN.ipynb` may be used to train and/or evaluate GNNs.

`GNN_EnergyLoss.ipynb` may be used to train and/or evaluate GNNs with augments objective functions including strain energy term. 

`MFGNN.ipynb` may be used to train and/or evaluate MFGNNs. 

## Getting Started:
I recommend starting with `Demo.ipynb`. Ensure that `Functions.ipynb` and the pickled files in `MFGNNs/Models` and `MFGNNs/Documents_Records` are in the same directory as `Demo.ipynb`. This demo should provide enough insight into the processing and execution of these models to ensure reproducibility, even if the code is not suited for widespread distribution.

## A note on Models:
The Models referenced in "Learning Finite Element Convergence with the
Multi-fidelity Graph Neural Network (MFGNN)" can be loaded and evaluated in their appropriate ipynb. Although the training data is not included in this repository, the necessary information to duplicate the training dataset is mentioned in each model's directory as a file `DataGeneration_params`

Each model can be loaded and evaluated for accuracy in its displacement outputs and L2 finite element convergence relative to element size. The results for such evaluations are all included in "Learning Finite Element Convergence with the Multi-fidelity Graph Neural Network (MFGNN)".

Loading and/or training models in `GNN.ipynb`, `GNN_EnergyLoss.ipynb`, and `MFGNN.ipynb` will require pre-computation of training data into appropriate directories. `DataGeneration.ipynb` is a good starting point for this process and is design to generate training examples and pickle the data structures. **Note**: this process requires significant memory and may be considered a work in progress in terms of software development. 


