This code calculates the resonance contribution to the electronic continuum of a Raman spectrum by implementing the Kramers-Heisenberg formula on the output of Wannier90. It is a Jupyter notebook written in Python. 

A few caveats:
- I wrote this code specifically for Co3Sn2S2, a Kagome-lattice material. Some of the code will need to be modified for other systems
- Similarly, I have hard-coded some parameters to fit my Wannier90 calculations. This will also need to be adapted to more general use
- For large numbers of k-points, the calculations can take several hours. I recommend saving the data immediately so that the code doesn't have to be rerun if the notebook is reset.

Some key assumptions:
- I make the assumption that the Wannier orbitals have the same symmetry as their initial projections as atomic orbitals. In general, this is not the case unless num_iter = 0 in your Wannier90 calculation. It often is good enough even if num_iter > 0
- I only include q=0 excitations in this calculation, meaning that is may underestimate the low-energy part of the spectrum, especially for metals
- I only include d-electrons in my Wannier90 calculation. For the intermediate states, I consider constant-energy p-orbitals (i.e. flat bands), that I label with the (ml, ms) basis
  
