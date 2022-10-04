# Machine Learning for Atomistic Simulation

This document aims to serve as a concise overview of literature that discusses the application of machine learning to the problem of atomistic simulation, an emerging field that is growing at a rapid pace:

![Mentions of "neural network force field" by publication year, from Clairivate Web of Science (Oct 2022)](img/NNFFvsYear.png)

This repository is a result of my personal attempt to parse existing literature and understand the different approaches from the various groups that are publishing in the field. I have attempted to select articles in a manner that provides some sense of the development of the field over time, as well as to characterize trends in this development. This is not intended as a comprehensive list, as there are just too many papers, and it seems unproductive to spend more time searching for papers than reading them.

I've also separated the literature based on whether the work focuses on a particular method of representing materials or molecular data, or if it focuses on specific novel architectural developments for more effective processing of such data.

Please feel free to open an issue or pull requests.

## Embeddings and Representations

Below are various techniques for representing atomic systems and materials in a manner that is intended for usage with machine learning systems.

### Atomic Cluster Expansion (ACE)

[Atomic cluster expansion for accurate and transferable interatomic potentials](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.99.014104) (Drautz) [Jan 2019]

[Atomic cluster expansion of scalar, vectorial and tensorial properties and including magnetism and charge transfer](https://arxiv.org/abs/2003.00221) (Drautz) [Feb 2020]

[[2103.00814] Performant implementation of the atomic cluster expansion (PACE): Application to copper and silicon](https://arxiv.org/abs/2103.00814) (Lysogorskiy, van der Oord, Bochkarev, Menon, Rinaldi, Hammerschmidt, Mrovec, Thompson, Csányi, Ortner, Drautz) [Mar 2021]

[Atomic cluster expansion: Completeness, efficiency and stability](https://www.sciencedirect.com/science/article/pii/S0021999122000080?via%3Dihub) (Dusson, Bachmayr, Csanyi, Drautz, Etter, van der Oord, Ortner) [Apr 2022]

[Multilayer atomic cluster expansion for semi-local interactions](https://arxiv.org/pdf/2205.08177.pdf) (Bochkarev, Lysogorskiy, Ortner, Csanyi, Drautz) [May 2022]

[Atomic cluster expansion and wave function representations](https://arxiv.org/abs/2206.11375) (Drautz, Ortner) [2022]

[Permutation-adapted complete and independent basis for atomic cluster expansion descriptors](https://arxiv.org/abs/2208.01756) (Goff, Sievers, Wood, Thompson) [Aug 2022]

### Smooth Overlap of Atomic Position (SOAP)

[On representing chemical environments](https://arxiv.org/abs/1209.3140) (Bartok, Kondor, Csanyi) [Mar 2013]

[Comparing molecules and solids across structural and alchemical space](https://pubs.rsc.org/en/content/articlelanding/2016/cp/c6cp00415f) (De, Bartok, Csanyi, Ceriotti) [Apr 2016]

[Automatic Selection of Atomic Fingerprints and Reference Configurations for Machine-Learning Potentials](https://arxiv.org/abs/1804.02150) (Imbalzano, Anelli, Giofré, Klees, Behler, Ceriotti) [Apr 2018]

[Machine-learning of atomic-scale properties based on physical principles](https://arxiv.org/abs/1901.10971) (Ceriotti, Willatt, Csányi) [Jan 2019]

[Atom-density representations for machine learning](https://aip.scitation.org/doi/10.1063/1.5090481) (Willatt, Musil, Ceriotti) [Apr 2019]

[Atomic-scale representation and statistical learning of tensorial properties](https://arxiv.org/abs/1904.01623) (Grisafi, Wilkins, Willatt, Ceriotti) [Apr 2019]

[Optimizing many-body atomic descriptors for enhanced computational performance of machine learning based interatomic potentials](https://arxiv.org/abs/1905.02142) (Caro) [May 2019]

[Efficient implementation of atom-density representations](https://arxiv.org/abs/2101.08814) (Musil, Veit, Goscinski, Fraux, Willatt, Stricker, Junge, Ceriotti) [Jan 2021]

### Gaussian Approximation Potentials (GAP)
(Many applications paper omitted; please [see here](https://arxiv.org/search/?query=%22Gaussian+Approximation+Potential%22&searchtype=all&source=header) for a more comprehensive list)

[Gaussian Approximation Potentials: the accuracy of quantum mechanics, without the electrons](https://arxiv.org/abs/0910.1019) (Bartok, Payne, Kondor, Csanyi) [Oct 2009]

[Gaussian Approximation Potential: an interatomic potential derived from first principles Quantum Mechanics](https://arxiv.org/abs/1003.2817) (Bartok) [Mar 2010]

[Accuracy and transferability of GAP models for tungsten](https://arxiv.org/abs/1405.4370) (Szlachta, Bartok, Csanyi) [May 2014]

[Localized Coulomb Descriptors for the Gaussian Approximation Potential](https://arxiv.org/abs/1611.05126) (Barker, Bulin, Hamaekers, Mathias) [Nov 2016]

[Many-Body Coarse-Grained Interactions using Gaussian Approximation Potentials](https://arxiv.org/abs/1611.09123) (John) [Nov 2016]

[Machine-learned Interatomic Potentials for Alloys and Alloy Phase Diagrams](https://arxiv.org/abs/1906.07816) (Rosenbrock, Gubaev, Shapeev, Pártay, Bernstein, Csányi, Hart) [Jun 2019]
- Combines SOAP and GAP

[Combining phonon accuracy with high transferability in Gaussian approximation potential models](https://arxiv.org/abs/2005.07046) (George, Hautier, Bartok, Csanyi, Deringer) [May 2020]

[Gaussian Moments as Physically Inspired Molecular Descriptors for Accurate and Scalable Machine Learning Potentials](https://pubs.acs.org/doi/10.1021/acs.jctc.0c00347) (Zaverkin, Kastner) [July 2020]

[Massively Parallel Fitting of Gaussian Approximation Potentials](https://arxiv.org/abs/2207.03803) (Klawohn, Kermode, Bartók) [Jul 2022]

[Atomistic structure search using local surrogate mode](https://arxiv.org/abs/2208.09273) (Rønne, Christiansen, Slavensky, Tang, Brix, Pedersen, Bisbo, Hammer) [Aug 2022]

### Moment Tensor Potentials (MTP)

[Moment Tensor Potentials: a class of systematically improvable interatomic potentials](https://arxiv.org/abs/1512.06054) (Shapeev) [Dec 2015]

[Moment tensor Potentials as a Promising Tool to Study Diffusion Processes](https://arxiv.org/abs/1812.02946) (Novoselov, Yanilkin, Shapeev, Podryabinkin) [Dec 2018]

[Machine-learning potentials enable predictive $\textit{and}$ tractable high-throughput screening of random alloys](https://arxiv.org/abs/2107.05620) (Hodapp, Shapeev) [Jul 2021]

### Atom-Centered Symmetry Functions (ACSF)

[Generalized Neural-Network Representation of High-Dimensional Potential-Energy Surfaces](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.98.146401) (Behler, Parrinello) [Apr 2007]
  - One of the first works to introduce neural network interatomic potentials

[Atom-centered symmetry functions for constructing high-dimensional neural network potentials](https://aip.scitation.org/doi/abs/10.1063/1.3553717) (Behler) [Feb 2011]

[wACSF—Weighted atom-centered symmetry functions as descriptors in machine learning potentials](https://aip.scitation.org/doi/10.1063/1.5019667) (Gastegger, Schwiedrzik, Bittermann, Berzsenyi, Marquetand) [Mar 2018]

[Optimized symmetry functions for machine-learning interatomic potentials of multicomponent systems](https://aip.scitation.org/doi/10.1063/1.5040005) (Rostami, Amsler, Ghasemi) [Sep 2018]

[Augmenting machine learning of energy landscapes with local structural information](https://aip.scitation.org/doi/10.1063/5.0012407) (Honrao, Xie, Hennig) [Aug 2020]

[Unified theory of atom-centered representations and message-passing machine-learning schemes](https://aip.scitation.org/doi/pdf/10.1063/5.0087042) (Nigam, Pozdnyakov, Fraux) [May 2022]

### FCHL
(Acronym based off of initial authors' last names)

[Alchemical and structural distribution based representation for universal quantum machine learning](https://aip.scitation.org/doi/10.1063/1.5020710) (Faber, Christensen, Huang, von Lilienfeld) [Mar 2018]

[FCHL revisited: Faster and more accurate quantum machine learning](https://aip.scitation.org/doi/10.1063/1.5126701) (Christensen, Bratholm, Faber, von Lilienfeld) [Jan 2020]

### Wavelet Scattering

[Solid harmonic wavelet scattering](https://dl.acm.org/doi/10.5555/3295222.3295400) (Eickenberg, Exarchakis, Hirn, Mallat) [Dec 2017]

[Steerable Wavelet Scattering for 3D Atomic Systems with Application to Li-Si Energy Prediction](https://arxiv.org/abs/1812.02320) (Brumwell, Sinz, Jin Kim, Qi, Hirn) [Nov 2018]

[Wavelet Scattering Networks for Atomistic Systems with Extrapolation of Material Properties](https://arxiv.org/abs/2006.01247) (Sinz, Swift, Brumwell, Liu, Jin Kim, Qi, Hirn) [Jun 2020]

### Miscellaneous
One-off representation methods that were not significantly and explicitly developed upon further.

[Fourier series of atomic radial distribution functions: A molecular fingerprint for machine learning models of quantum chemical properties](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.24912) (von Lilienfeld, Ramakrishnan, Rupp, Knoll) [Jul 2013]

[How to represent crystal structures for machine learning: Towards fast prediction of electronic properties](https://journals.aps.org/prb/abstract/10.1103/PhysRevB.89.205118) (Schutt, Glawe, Brockherde, Sanna, Muller, Gross) [May 2014]
- Representation specifically for materials

[A fingerprint based metric for measuring similarities of crystalline structures](https://aip.scitation.org/doi/10.1063/1.4940026) (Zhu, Amsler, Fuhrer, Schaefer, Faraji, Rostami, Ghasemi, Sadeghi, Grauzinyte, Wolverton, Goedecker) [Jan 2016]
- Representation specifically for materials

[Unified Representation of Molecules and Crystals for Machine Learning](https://arxiv.org/abs/1704.06439) (Huo, Rupp) [Apr 2017]
- Many-body Tensor Representation (referred to as MBTR in other literature)

[An Atomistic Fingerprint Algorithm for Learning Ab Initio Molecular Force Fields](https://arxiv.org/abs/1709.09235) (Tang, Zhang, Karniadakis) [Dec 2017]

[A novel approach to describe chemical environments in high-dimensional neural network potentials](https://aip.scitation.org/doi/10.1063/1.5086167) (Kocer, Mason, Erturk) [Mar 2019]

[Embedded Atom Neural Network Potentials: Efficient and Accurate Machine Learning with a Physically Inspired Representation](https://pubs.acs.org/doi/abs/10.1021/acs.jpclett.9b02037) (Zhang, Hu, Jiang) [Aug 2019]
- Empirical Atom Method (referred to as EAM in other literature)

[Continuous and optimally complete description of chemical environments using Spherical Bessel descriptors](https://aip.scitation.org/doi/10.1063/1.5111045) (Kocer, Mason, Erturk) [Jan 2020]
- Spherical Bessel (referred to as SB in other literature)

[TUCAN: A molecular identifier and descriptor applicable to the whole periodic table from hydrogen to oganesson](https://europepmc.org/article/ppr/ppr479842) (Brammer, Blanke, Kellner, Hoffmann, Herres-Pawlis, Schatzschneider) [Mar 2022]

### Meta-literature

[SISSO: A compressed-sensing method for identifying the best low-dimensional descriptor in an immensity of offered candidates](https://journals.aps.org/prmaterials/abstract/10.1103/PhysRevMaterials.2.083802) (Ouyang, Curtarolo, Ahmetcik, Scheffler, Ghiringhelli) [Aug 2018]

[A Performance and Cost Assessment of Machine Learning Interatomic Potentials](https://arxiv.org/abs/1906.08888) (Zuo, Chen, Li, Deng, Chen, Behler, Csányi, Shapeev, Thompson, Wood, Ong) [Jul 2019]

[DScribe: Library of descriptors for machine learning in materials science](https://www.sciencedirect.com/science/article/pii/S0010465519303042) (Himanen, Jäger, Morooka, Canova, Ranawat, Gao, Rinke, Foster) [Nov 2019]

[Descriptors representing two- and three-body atomic distributions and their effects on the accuracy of machine-learned interatomic potentials](https://aip.scitation.org/doi/10.1063/5.0009491) (Jinnouchi, Karsai, Verdi, Asahi, Kresse) [Apr 2020]

[Sensitivity and Dimensionality of Atomic Environment Representations used for Machine Learning Interatomic Potentials](https://arxiv.org/abs/2006.01915) (Onat, Ortner, Kermode) [Jun 2020]

[An assessment of the structural resolution of various fingerprints commonly used in machine learning](https://arxiv.org/abs/2008.03189) (Karamad, Magar, Shi, Siahrostami, Gates, Farimani) [Aug 2020]

[Incompleteness of Atomic Structure Representations](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.125.166001) (Pozdnyakov, Willatt, Bartok, Ortner, Csanyi, Ceriotti) [Oct 2020]

[Compressing local atomic neighbourhood descriptors](https://arxiv.org/abs/2112.13055) (Darby, Kermode, Csányi) [Dec 2021]

[Manifolds of quasi-constant SOAP and ACSF fingerprints and the resulting failure to machine learn four-body interactions](https://arxiv.org/abs/2102.06915) (Parsaeifard, Goedecker) [Feb 2021]

[The role of feature space in atomistic learning](https://iopscience.iop.org/article/10.1088/2632-2153/abdaf7) (Goscinski, Fraux, Imbalzano, Ceriotti) [Apr 2021]

## Deep Learning Architectures
These are networks that are intended to process materials (or molecular) data for the purposes of atomistic simulation (or property prediction)

### e3nn Precursor
[These works were developed independently of each other but propose very similar ideas which were mostly consolidated](https://www.youtube.com/watch?v=8CF8Grb_brE&t=1224s) into the [e3nn](https://e3nn.org/) framework.

[Tensor field networks: Rotation- and translation-equivariant neural networks for 3D point clouds](https://arxiv.org/abs/1802.08219) (Smidt, Thomas, Kearnes, Yang, Li, Kohlhoff, Riley) [Feb 2018]

[N-body Networks: a Covariant Hierarchical Neural Network Architecture for Learning Atomic Potentials](https://arxiv.org/abs/1803.01588) (Kondor) [Mar 2018]

[Clebsch-Gordan Nets: a Fully Fourier Space Spherical Convolutional Neural Network](https://arxiv.org/abs/1806.09231)(Kondor, Lin, Trivedi) [Jun 2018]

[3D Steerable CNNs: Learning Rotationally Equivariant Features in Volumetric Data](https://arxiv.org/abs/1807.02547) (Weiler, Geiger, Welling, Boomsma, Cohen) [Jul 2018]

[SE(3)-equivariant prediction of molecular wavefunctions and electronic densities](https://arxiv.org/abs/2106.02347) (Unke, Bogojeski, Gastegger, Geiger, Smidt, Müller) [Jun 2021]

### e3nn

[E(3)-Equivariant Graph Neural Networks for Data-Efficient and Accurate Interatomic Potentials](https://arxiv.org/abs/2101.03164) (Batzner, Musaelian, Sun, Geiger, Mailoa, Kornbluth, Molinari, Smidt, Kozinsky) [Jan 2021]
- Network is called 'NequIP'

[Learning Local Equivariant Representations for Large-Scale Atomistic Dynamics](https://arxiv.org/pdf/2204.05249.pdf) (Musaelian, Batzner, Johansson, Sun, Owen, Kornbluth, Kozinsky) [Apr 2022]
- Network is called 'Allegro'

[The Design Space of E(3)-Equivariant Atom-Centered Interatomic Potentials](https://arxiv.org/abs/2205.06643) (Batatia, Batzner, Kovács, Musaelian, Simm, Drautz, Ortner, Kozinsky, Csányi) [May 2022]
- Discusses relationship between prior work in atomic representation methods (see above) and E(3)-equivariant neural networks; proposes a network called BOTNet

[MACE: Higher Order Equivariant Message Passing Neural Networks for Fast and Accurate Force Fields](https://arxiv.org/abs/2206.07697) (Batatia, Kovács, Simm, Ortner, Csányi) [Jun 2022]

[e3nn: Euclidean Neural Networks](https://arxiv.org/abs/2207.09453) (Geiger, Smidt) [Jul 2022]

### SE(3)-CNN

[SE(3)-Transformers: 3D Roto-Translation Equivariant Attention Networks](https://arxiv.org/abs/2006.10503) (Fuchs, Worrall, Fischer, Welling) [Jun 2020]

### EGNN

[Geometric and Physical Quantities Improve E(3) Equivariant Message Passing](https://arxiv.org/abs/2110.02905) (Brandstetter, Hesselink, Pol, Bekkers, Welling) [Oct 2021]
- Network is called 'Steerable E(3) Equivariant Graph Neural Network', or 'SEGNN'

### SchNet

[SchNet – a deep learning architecture for molecules and materials](https://arxiv.org/pdf/1712.06113.pdf)

[SchNetPack: A Deep Learning Toolbox For Atomistic Systems](https://pubs.acs.org/doi/10.1021/acs.jctc.8b00908)

[Combining SchNet and SHARC: The SchNarc Machine Learning Approach for Excited-State Dynamics](https://pubs.acs.org/doi/full/10.1021/acs.jpclett.0c00527)


### Preferred Networks

[TeaNet: universal neural network interatomic potential inspired by iterative electronic relaxations](https://arxiv.org/abs/1912.01398) (Takamoto, Izumi, Li) [Dec 2019]

[Towards Universal Neural Network Potential for Material Discovery Applicable to Arbitrary Combination of 45 Elements](https://arxiv.org/pdf/2106.14583.pdf) (Takamoto, Shinagawa, Motoki, Nakago, Li, Kurata, Watanabe, Yayama, Iriguchi, Asano, Onodera, Ishii, Kudo, Ono, Sawada, Ishitani, Ong, Yamaguchi, Kataoka, Hayashi, Charoenphakdee, Ibuka) [Jun 2021]

### Miscellaneous

[Informing Geometric Deep Learning with Electronic Interactions to Accelerate Quantum Chemistry](https://arxiv.org/pdf/2105.14655.pdf) (Qiao, Christensen, Welborn, Manby, Anandkumar, Miller III) [May 2021]
- Network is called 'OrbNet-Equi'



[Equivariant graph neural networks for fast electron density estimation of molecules, liquids, and solids](https://www.nature.com/articles/s41524-022-00863-y) (Jørgensen, Bhowmik) [Aug 2022]

### Meta-literature

[Forces Are Not Enough: Benchmark and Critical Evaluation for Machine Learning Force Fields with Molecular Simulations](https://openreview.net/pdf?id=_V-nKeWvs7p)



[Learning Atomic Multipoles: Prediction of the Electrostatic Potential with Equivariant Graph Neural Networks](https://pubs.acs.org/doi/10.1021/acs.jctc.1c01021)

[SpookyNet: Learning force fields with electronic degrees of freedom and nonlocal effects](https://www.nature.com/articles/s41467-021-27504-0#Abs1)



[Cormorant: Covariant Molecular Neural Networks](https://arxiv.org/abs/1906.04015)

[NewtonNet: a Newtonian message passing network for deep learning of interatomic potentials and forces](https://pubs.rsc.org/en/content/articlehtml/2022/dd/d2dd00008c)

[TorchMD-NET: Equivariant Transformers for Neural Network based Molecular Potentials](https://arxiv.org/abs/2202.02541)

[E(n) Equivariant Graph Neural Networks](https://arxiv.org/abs/2102.09844)

[A Universal Graph Deep Learning Interatomic Potential for the Periodic Table](https://arxiv.org/abs/2202.02450)

[Equiformer: Equivariant Graph Attention Transformer for 3D Atomistic Graphs](https://arxiv.org/abs/2206.11990)


[Graph dynamical networks for unsupervised learning of atomic scale dynamics in materials](https://www.nature.com/articles/s41467-019-10663-6)

[GemNet: Universal Directional Graph Neural Networks for Molecules](https://arxiv.org/pdf/2106.08903.pdf)


[Towards exact molecular dynamics simulations with machine-learned force fields](https://www.nature.com/articles/s41467-018-06169-2)

[Generalized Neural-Network Representation of High-Dimensional Potential-Energy Surfaces](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.98.146401)

[Simultaneous fitting of a potential-energy surface and its corresponding force fields using feedforward neural networks](https://aip.scitation.org/doi/10.1063/1.3095491)

[ANI-1: an extensible neural network potential with DFT accuracy at force field computational cost](https://pubs.rsc.org/en/content/articlelanding/2017/SC/C6SC05720A)

[Accurate Interatomic Force Fields via Machine Learning with Covariant Kernels](https://arxiv.org/abs/1611.03877)

[Machine learning of accurate energy-conserving molecular force fields](https://www.science.org/doi/10.1126/sciadv.1603015)

[Neural network potentials for metals and oxides – First applications to copper clusters at zinc oxide](https://onlinelibrary.wiley.com/doi/abs/10.1002/pssb.201248370)

[Machine learning for interatomic potential models](https://aip.scitation.org/doi/10.1063/1.5126336)

[DP-GEN: A concurrent learning platform for the generation of reliable deep learning based potential energy models](https://arxiv.org/abs/1910.12690)

[Ab-Initio Solution of the Many-Electron Schrödinger Equation with Deep Neural Networks](https://arxiv.org/abs/1909.02487)

[A fourth-generation high-dimensional neural network potential with accurate electrostatics including non-local charge transfer](https://www.nature.com/articles/s41467-020-20427-2)

[Deep Potential Molecular Dynamics: A Scalable Model with the Accuracy of Quantum Mechanics](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.120.143001)

[Accurate and scalable graph neural network force field and molecular dynamics with direct force architecture](https://www.nature.com/articles/s41524-021-00543-3)

[A fast neural network approach for direct covariant forces prediction in complex multi-element extended systems](https://www.nature.com/articles/s42256-019-0098-0)

[Convergence acceleration in machine learning potentials for atomistic simulations](https://pubs.rsc.org/en/content/articlehtml/2022/dd/d1dd00005e)

[NNP/MM: Fast molecular dynamics simulations with machine learning potentials and molecular mechanics](https://arxiv.org/abs/2201.08110)

[A fast neural network approach for direct covariant forces prediction in complex multi-element extended systems](https://www.nature.com/articles/s42256-019-0098-0)
