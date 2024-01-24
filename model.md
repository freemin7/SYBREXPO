# Modeling a single threaded toy Binary-MILP solver

We assume we have access to an interior point LP solver which minimizes an LP problem. The solver is tasked to find an integer feasible globally minimal solution.

The solver recieves a Binary-MILP problem. 
It see there are n binary variables and m non negative real variables. It could solve the MILP by solving 2^n LPs each time with the binary variables fixed taking 2^n poly(m) time to certify global optimality. It also considers the possibility of relaxing the MILP into an LP and enforcing the Integerness over a branch and bound procedure. It could take between (2^{n+1}-1) poly(m+n)  (relax every node and in the end having solve the every root in the worst case) and poly(m+n) (root relaxation leads to feasible optimal solution) operations. It decides to try both approaches simulateneously. As there is no preference for iteration order when bruteforcing it will let the branch and bound pick the iteration order for the beginning and should it be not very successful at cutting of bad parts of the search tree it might switch back to a brute forces approach. It decides that a 2^n bit map fits in RAM and that maintaining a data structure to do the look up is worth not resolving them. At every node it branches and bounds and draws random integer samples and lps those as a feasibility pump

...

This is the miniumum functionality for this code base to do something interesting.

## Recording traces

A trace in this model would be a recoding what LPs are solved.

## Reodering of traces

Traces can not only be replayed but also replayed in different order. If the calculation time for every solve is recorded we can try different strategies without solving any LPs just by looking up calculation times. We don't even need to store the objective, we would only need to store between which integer feasible real optimal objectives it is. Since we could calculate the chance or sample the chance) of the feasiblity pump reaching a certain objective we could even write down a formula for the optimal ratio of compute time spent on pumping vs branching and bounding for this instance. A new feasibility pump could be trialed or tuned on old traces to evaluate and be better characterized using that.

