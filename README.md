# Quantum Topological Data Analysis <img width=300 align="right" src="https://user-images.githubusercontent.com/67575757/116423376-eba89780-a840-11eb-843d-00e75ad735bc.jpg">
Implementation of a quantum algorithm to compute topological features of generic (high-dimensional) data clouds in Qiskit.

Topological and geometric features of data are of increasing interest in data analysis to "understand" data and provide complementary global information for modern machine learning pipelines. Therefore, we implement a quantum algorithm to compute such topological features of data clouds, which yields exponential speed-up over all known classical algorithms.

We implement a topological algorithm (https://arxiv.org/abs/1408.3106) on Qiskit to calculate persistent spectra (and from it Betti numbers) of simplicial complexes representing arbitrary (high-dimensional) data. The algorithm builds on the phase estimation algorithm. After successful implementation we apply the algorithm to real datasets on IBM quantum backends. 

<img width=500 src="https://user-images.githubusercontent.com/67575757/119673446-a4abc300-be3b-11eb-9e98-e7a26e5fc358.png">

## Describe repo
The implementation of the algorithm can be found in Code/. The base file Code/qtda_module.py contains basic functions and classes to define the quantum circuit and analyse data filtrations. The quantum algorithm side is based on the `IBM Qiskit` library, while the library `gudhi` (add links????) is used as a base implementation of (classical) topological data analysis. Several **Jupyter-notebooks** are provided (how many??) to explain the basic functionalities of the `QTDA`-implementation and the topological algorithm.

## How does TDA work?
As an example TDA is applied to a simple point cloud as shown below.
<img width=300 align="left" src="https://user-images.githubusercontent.com/67575757/119681678-91e8bc80-be42-11eb-8af8-c75030be022f.png">

On this point cloud a filtration is done by expanding spheres with radius ε. Points are connected for overlapping spheres. This changes the topology of the data. A simplicial complex is used to represent the topological characteristics of objects. Examples of k-dimensional simplices are: 0 simplex: vertex (point), 1-simplex:edges, 2-simplices are triangles, etc.

To distinguish topoligical spaces based on the connecitvity of k-dimensional simplicial complexes, Betti numbers are used
