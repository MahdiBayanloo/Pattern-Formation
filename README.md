*Course: Computational Sciences 23/24*
* | Institute: Freie Universit¨at Berlin*
* | Lecturer: Sebastian Matera, Feliks N¨uske*

***PATTERN FORMATION***

1. Introduction
Alan Turing’s ground breaking work of 1952 [1] provides an explaination for
spontanous formation of patterns in reaction diffusion systems. Although the direct
proof of the actual biological mechanisms are still missing, Turing’s explaination is
one of the central working hypotheses how morphogenesis actually takes place. [2, 3]
2. Model
Let Ω = [0, 1]2 and let u(t, x, y), v(t, x, y) be concentrations of substances satisfying periodic boundary conditions, then the initial problem for a reaction diffusion
system is given by
∂tu = δ1∆u + f(u, v)
∂tv = δ2∆v + g(u, v).
3. Tasks
Tasks marked by * are optional. You need to solve all mandatory assignments.
Please use the Wiki of the repository for documentation and answering the questions
or provide a LATEX report. The final software should be a python package including
a setup.py, contain a Readme.md explaining the usage as well as a file tracking the
dependencies named requirements.txt.
3.1. Project management. Apart from the scientific content you should work on
the following organizational assignments.
• Setup a development process. For this purpose do research on the matter,
document and report your findings. You do not have to use an existing
one, but they could serve as a blueprint for your own.
• Maintain a proper git history for each project member in line with the
chosen development process.
* Use GitLab for issue management.
* Setup and utilize GitLab’s continuous integration tools for your tests.
3.2. Introduction.
• Explain the theory of the Turing instability. (5 pts)
• Implement a second order finite difference approximation on a cartesian
grid for arbitrary f, g. For this purpose define an interface and implement
unit test. Subsequently implement an appropriate explicit discretization.
1
2PATTERN FORMATION [0.25EM] PROJECT ASSIGNMENTS FOR 4 – 6 STUDENTS
• Reuse the interface and adopt the tests from before. Subsequently implement the Crank – Nicolson finite difference approximation on a cartesian
grid for general f, g.
• Test both implementations using the Grey – Scott model [4]. Validate the
order of the method and benchmark their performance.
f(u, v) = −uv2 + α(1 − u)
g(u, v) = uv2 − (α + β)v
Visualize your output.
3.3. Fur pattern. Use the previous codes to simulate fur patterns of animals.
• Find a reaction model which produces the markings of a Giraffe. [5] Solve
the model with both algorithms and visualize the output. Compare the
quality and runtime.
• Find a reaction model which produces the markings of a Leopard fur. [6]
Solve the model with both algorithms and visualize the output. Compare
the quality and runtime.
3.4. Parallelization. We want to make sure to leverage all (or at least more) of the
computational resources on your computer hardware efficiently. For this purpose
• determine and explain the time critical parts in your code by benchmarks.
Discuss the different parallelization options fitting to your code. Can you
implement all of them in python?
Apply one or more of following strategies. Test and benchmark your code against
unoptimized results. Report and explain your findings.
* Parallelize both numerical methods using DASK. How can you parallelize
the implicit part?
* Implement a matrix free version of the linear solver. Compare the performance to your first implementation.
* Improve performance by offloading the code to accelerators via PyOpenCL
or PyCuda. Optionally you can visualize from GPU memory directly via
PyOpenGL.
References
[1] A. M. Turing, “The chemical basis of morphogenesis,” Philosophical Transactions of the Royal
Society of London. Series B, Biological Sciences, vol. 237, pp. 37–72, Aug. 1952.
[2] P. Ball, “Forging patterns and making waves from biology to geology: a commentary on Turing
(1952) ‘The chemical basis of morphogenesis’,” Philosophical Transactions of the Royal Society
B: Biological Sciences, vol. 370, p. 20140218, Apr. 2015.
[3] S. Kondo and T. Miura, “Reaction-Diffusion Model as a Framework for Understanding Biological Pattern Formation,” Science, vol. 329, pp. 1616–1620, Sept. 2010.
[4] J. E. Pearson, “Complex Patterns in a Simple System,” Science, vol. 261, pp. 189–192, July
1993.
[5] J. Murray, Mathematical biology II, II,. New York [etc.: Springer, 2003. OCLC: 773466801.
[6] R. T. Liu, S. S. Liaw, and P. K. Maini, “Two-stage Turing model for generating pigment
patterns on the leopard and the jaguar,” Physical Review E, vol. 74, p. 011914, July 2006.
