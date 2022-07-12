---
layout: page
title: Optimizing Gradient Profiles for Liquid Chromatography - A comparison of Optimization Algorithms
description: By Céline Kattenberg (Bachelor Kunstmatige Intelligentie, UvA)
img: assets/img/celine_project.png
importance: 1
category: Bachelor students 
---

### In a Nutshell
Gradient elution liquid chromatography is a valuable tool in analytical chemistry.
However, with the traditional trial-and-error approach, the search for an optimal
gradient profile for a given sample can take several weeks. For this reason, opti-
mization algorithms have been applied to this problem. In this thesis, the perfor-
mances of 5 different optimization algorithms on the task of gradient optimization
for multi-segment linear gradient chromatography are compared. Bayesian opti-
mization (BO), a genetic algorithm (GA), and, differential evolution (DE) were
benchmarked against random search (RS) and grid search (GS). The performance
of the algorithms was tested on 8 different computer-generated samples. It was
found that BO exhibits better data efficiency than the other algorithms with a
budget of 100 objective function evaluations. This likely makes it the most suit-
able of the considered algorithms for wet gradient optimization. DE performed
the best in terms of time efficiency with a budget of 10,000 search runs. This
likely makes DE the most suitable of the considered algorithms for dry gradient
optimization. BO, GA, and DE generally outperformed RS. GS was generally
outperformed in terms of time efficiency by DE and GA. GS is not suitable when
more than 1 gradient segment is used, because the search space becomes too large
to search exhaustively. With a budget of up to 10,000 search runs, multi-segment
gradients can produce small improvements in separation quality compared with
single-segment linear gradients, for separations that are not otherwise optimized
for other variables.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/100_iters.jpeg" title="100 iterations" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/10000_iters.jpeg" title="10 000 iterations" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
</div>



