# 23 compact DNPs spanning the peroidic table
DFT datasets for training machine learning atomistic potentials, final verision of all DNPs, LAMMPS/VASP validation calculation scripts and structure files.

We trained deep neural network potentials (DNPs) using the [deepMD-kit]( https://github.com/deepmodeling/deepmd-kit/releases/tag/v2.1.2 ) for 23 elements across the periodic table.

Three randomly seeded DNPs were generated for each potential.  Up to three iterations of adaptive learning refinement were applied to reduce standard deviations amoung these randomly seed DNPs. The final iterations of these DNPs can be located in the "[DNPs](https://github.com/saidigroup/23DNPs_and_me/tree/main/DNPs )" directory

The "[Training_Data](https://github.com/saidigroup/23DNPs_and_me/tree/main/Training_Data)" directory contained all of the training data used for fitting of the DNPs for each element.  Both the VASP trajectories and the *.npy files are located in these compressed files.

All of the structures used for validation of these DNPs can be found in the "[Valdiation](https://github.com/saidigroup/23DNPs_and_me/tree/main/LAMMPS_VASP_Scripts%20for%20Calculations)" directories for each element.  The [relaxed.in](https://github.com/saidigroup/23DNPs_and_me/blob/main/LAMMPS_VASP_Scripts%20for%20Calculations/relaxed.in_lammps_script) is the LAMMPS script for generating relaxed structures and calulating the energies of these structures as well and reporting the cell dimensions.  The [heat.in](https://github.com/saidigroup/23DNPs_and_me/blob/main/LAMMPS_VASP_Scripts%20for%20Calculations/Heating/heat.in) LAMMPS script was used to heat 10x10x10 supercell from 0 to the melting temperature for each element to demonstrat the DNP's stability for the solid phase.  The [INCAR](https://github.com/saidigroup/23DNPs_and_me/blob/main/LAMMPS_VASP_Scripts%20for%20Calculations/INCAR_general) file is the VASP input script we used to generate the corresponding VASP reference data and compare with the LAMMPs-DNP results. Lastly, the [LAMMPS](https://github.com/saidigroup/23DNPs_and_me/tree/main/LAMMPS_VASP_Scripts%20for%20Calculations/Elastic_constants) and [VASP](https://github.com/saidigroup/23DNPs_and_me/blob/main/LAMMPS_VASP_Scripts%20for%20Calculations/Elastic_constants/INCAR_elastic) scripts for elastic calcuations are supplied.  

We utilized the [LAVA](https://github.com/lanl/LAVA) code for calculating the DNP surface energys for these elements using the DNPs and LAMMPs do to the code's ease of use for this application (there are many other interesting tools in this package as well for LAMMPS and VASP validations of atomistic potentials).

The data used to produce figures are located in the "[Figures](https://github.com/saidigroup/23DNPs_and_me/tree/main/Figures)" directories along with the python scripts to generate these plots.  
