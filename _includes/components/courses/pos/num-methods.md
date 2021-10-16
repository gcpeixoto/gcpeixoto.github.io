### Numerical Methods (SEMEC0140)
---

This course is fully based on variational methods as introductory topic for application of CFD with the finite element method. In the current version, it is a 3-part course divided as follows:

- **Part 1 (Tools)**: A general overview on numerical methods, basics on Python programming, and presentation of tools like Scipy ecosystem, solvers (FENICS, OpenFOAM etc.), mesh generators (meshio, Gmsh etc.), CAE/CAD open platforms, viewers (Paraview, Mayavi etc.) and support literature.
- **Part 2 (Theory)**: Discussion of approximation theory, construction principles of FEM, topics on functional analysis, strong/weak form, n-dimensional IBVPs.
- **Part 3 (Practice)**: project-based learning oriented to student's research (generally CFD or multiphysics simulations with Gmsh/FENICS/Paraview trio), and state-of-the-art approaches.

#### Resources 

Remark: resources for this course can be forked from GDCOC0072.

##### Books

- A First Course in Finite Elements, by J. Fish and T. Belytschko
- [An Analysis of the Finite Element Method](https://www.amazon.com/Analysis-Finite-Element-Method/dp/0980232708), by G. Strang and G. Fix
- Applied Numerical Linear Algebra, by J. Demmel
- Automated Solution of Differential Equations by the Finite Element Method, The FENICS book, by A. Logg et al.
- Introduction to Applied Mathematics, by G. Strang
- [Introduction to the Finite Element Method](https://www.amazon.com/Introduction-Finite-Element-Method-4E/dp/1259861902/ref=sr_1_1?dchild=1&keywords=finite+element+reddy&qid=1631499999&sr=8-1), by J. Reddy <span>&#128077;</span>
- Introduction to Numerical Methods for Variational Problems, by H.P. Langtangen and K-A. Mardal <span>&#128077;</span>
- Numerical Linear Algebra, by L. Trefethen and D. Bau III
- [The Finite Element Method: Theory, Implementation, and Applications](https://www.amazon.com/gp/product/B00BLREC4Q?ref_=dbs_m_mng_rwt_calw_tkin_7&storeType=ebooks&qid=1631496281&sr=8-7), by M. G. Larson and F. Bengzon
- [Theory and Practice of Finite Elements](https://www.springer.com/gp/book/9780387205748), by A. Ern and J-L Guermond <span>&#128077;</span>

##### Booklets 

- [Notas em Mat. Aplic. n. 66 - Intr. Elem. Fin.](https://proceedings.science/series/23/proceedings_non_indexed/66) @SBMAC
- [Notas em Mat. Aplic. n. 92 - Intr. Méts. Variacionais](https://proceedings.science/series/23/proceedings_non_indexed/92) @SBMAC

##### Courses

- [MSc Applied Computational Science & Engineering 2020](https://acse-2020.github.io/README.html) @ICL <span>&#128077;</span>
- [ACSE 1 Modern Programming Methods](https://acse-2020.github.io/ACSE-1/README.html) @ICL
- [FEA for coupled problems](https://david-kamensky.eng.ucsd.edu/teaching/mae-207-fea-for-coupled-problems) @UC San Diego
- [Finite Elements: numerical analysis and implementation](https://finite-element.github.io) @ICL <span>&#128077;</span>
- [Practical Numerical Methods with Python](https://github.com/numerical-mooc/numerical-mooc/wiki), by L. Barba's group.
- [Python Programming Primer](http://www.southampton.ac.uk/~fangohr/training/python/) @Southampton 
- [Research Software Engineering with Python](https://alan-turing-institute.github.io/rsd-engineeringcourse/html/index.html) @Turing <span>&#128077;</span>

##### Misc

- [A History of the FEM](https://edisciplinas.usp.br/pluginfile.php/5583679/mod_resource/content/1/Historia_MEF_Babuska.pdf), by Prof. Ivo Babuska
- [Def Element: An Encyclopedia of FEM](https://defelement.com)
- [Engineering Statistics Handbook](https://www.itl.nist.gov/div898/handbook/index.htm) @NIST/SEMATECH
- [FENICS Project website](https://fenicsproject.org)
- [Prof. Gustavo Rabello's FEM notes](https://gustavorabello.github.io/teaching/) @UFRJ/Brazil
- [The Fenics X Tutorial](https://jorgensd.github.io/dolfinx-tutorial/index.html) by J. Dokken <span>&#128077;</span>

##### Papers

- [Physics-informed machine learning](https://www.nature.com/articles/s42254-021-00314-5), Karniadakis et al., Nature Reviews, 2021
	- See: i) Table 1, for a list of PINN libraries; ii) subsection "Connection to classical numerical methods"; 
- [Hybrid FEM-NN models: Combining artificial neural networks with the finite element method](https://www.sciencedirect.com/science/article/pii/S0021999121005465), Mitusch et al., JCP, 2021
	- _Takeaways_: i) may improve convergence speed; ii) fewer optimization steps; iii) generalization for spatial variability.
	- _Gaps:_ non-linearity solvable through training; PDE solvers not optimized for large batch training on GPU; iii) FEM weak form requires efficient quadrature integration over the NN, whose rules are unknown for now.


	