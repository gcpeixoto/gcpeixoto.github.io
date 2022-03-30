---
title: G-η - Scientific computing
---

## How to verify numerical convergence rates

- Copy the text below and paste it [here](https://stackedit.io/app#).

```
- From $|u_h - u| \leq Ch^p$, write  $u - u_h = Ch^p + \mathcal{O}(h^{p+1})$. Transform it to a log-log plot to have the straight line $\log|u_h - u| = p\log(h) +\log|C| + \mathcal{O}(h)$. 
- The convergence rate $p$ is the slope. If exact solution is known, just like that; otherwise, choose $u_h$ as a reference solution by making $h$ as small as possible so that we have a fine mesh (high refinement level). Then, follow the steps above.
- Log-log plots usually relate _refinement factor_ x _L2-norm error_.
```
- For a broader explanation, see [here](https://www.csc.kth.se/utbildning/kth/kurser/DN2255/ndiff12/ConvRate.pdf).
- To plot beautiful order triangles, see this [discussion](https://tex.stackexchange.com/questions/245686/annotate-plot-triangle-with-slope-in-pgfplots-log-log-axis-environment).


## How to compute L2-norm relative error

- Copy the text below and paste it [here](https://stackedit.io/app#).

```
- Consider the rel. error the vector ${\bf e} = \frac{ {\bf u} - {\bf u}_h}{\bf u}$. 
- Assume ${\bf u}$ a vector whose $j$-th component is the L2-norm of the mesh quantity over the $n$-dimensional space, i.e. $u_j = \big(\sum_{i=1}^n u_i^2\big)^{1/2}$. Repeat for ${\bf u}_h$, the approximate solution.
- Then, for each mesh node $j$, the $j$-th component of ${\bf e}$ is $e_j = \frac{u_j - u_{h,j}}{u_j}$, for $i = 1,2,\ldots,N$, where $N$ is the number of mesh nodes.
- Finally, we can compute the L2-norm integral error in terms of nodal values by doing $\big( \int_{\Omega} {\bf e}^2 \, d\Omega \big)^{1/2} \approx \big( \sum_{j=1}^N e_j^2 \big)^{1/2}$.
```

## MATLAB help functions of interest

- For full support of functions and operators for SciComp, replaces `X` below by one of the following: `elmat`, `specmat`, `elfun`, `specfun`, `matfun`, `general`, `funfun`, `polyfun`, `ops`, `lang`, `plotxy`, `plotxyz`, `strfun`.

```
>> help X
```

## Python utility snippets

- Write data to file directly from `print`.

{% highlight python %} 
with open('t.txt',mode='w') as f:
  for i in ['a','b','c']:
    for j in range(3):
      print(i,j,sep=':',end='\t',file=f) # stream to file

cat t.txt
a:0  a:1  a:2  b:0  b:1  b:2  c:0  c:1  c:2
{% endhighlight %} 


## Paraview workarounds

- To make it work on new Apple M1 chips, switch off some vars and call it from the Terminal.
- It worked fine to me on v. 5.10.1.

{% highlight shell %} 

export VTK_DISABLE_VISRTX=1
export VTK_DISABLE_OSPRAY=1
/Applications/ParaView-5.10.1.app/Contents/MacOS/paraview 
{% endhighlight %} 

Reference: see [here](https://discourse.paraview.org/t/paraview-on-new-macs-with-m1-chips/5909/18).