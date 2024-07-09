# tpower3_coefficient_calculation
This is the code repository of the paper entitled "Expected Signature on a Riemannian Manifold and Its Geometric Implications". In particular, it contains the code that calculates the coefficient of $t^3$ in Section 5.4 of the paper. The codes are implemented in Mathematica (version 14.0.0.0).

## Overview
In section 5.4 of the paper, we try to explicitly calculate the coefficient $\hat{\Xi}_x$ of $t^3$ in the the third-order small-time expansion equation (5.6) which should encode the curvature properties. Following the fundamental decomposition structure (5.19) and the order counting rule illustrated before section 5.4.1, we consider three scenarios: 
1. total degree 3 case,
2. total degree 2.5 case,  
3. total degree 2 case. 

The total degree 2 case is too complex for manual calculation. Therefore, we used Mathematica to implement the codes and perform the calculations for this case. This implementation serves as a computer-assisted proof for the calculations.

We then used the Mathematica building blocks to verify the results of the total degree 3 case and the total degree 2.5 case. These results were consistent with our manual calculations.
    
Finally, we integrated the results of all three cases and simplified them to obtain the result presented in Proposition 5.16 of the paper.

## Directory Layout
### top-level directory layout
    .
    ├── lyx                   # total degree 2 case expressions
    ├── pdf                   # total degree 3 and total degree 2.5 results
    ├── src                   # Mathematica source code files
    └── README.md

### src file layout
This is the directory that contains all the Mathematica source code files that implement the building blocks, the calculations for the total degree 2 case, total degree 3 case, and total degree 2.5 case. The final result is also obtained in this directory. 

    .
    ├── ...
    ├── src 
        ├── caseCalculation_desktop.nb  # codes for builiding blocks
        ├── case_xxxx.nb                # codes for each case
        ├── result_2_data.nb            # codes to integrate all the results for total degree 2 case
        ├── result_3_and_2dot5.nb       # codes to integrate all the results for total degree 3 case and total degree 2.5 case
        ├── result.nb                   # codes for simplification and final result
        ├── casexxxx.mx                 # binary files produced by Mathematica to store the results
        ├── ItosLemma.m                 # the Mathematica package we use to calculate Itô's formula
    ├── ...
The naming convention for the case_xxxx files and their relation to the paper: 1 means term I, 2 means term J, 3 means term K, 4 means term L, 5 means term P. 

For instance, "case_1113.nb" means the term (II;IK) in the paper. "case_135" means the term (IK;P) in the paper.

### lyx file layout
This is the directory that contains the Lyx files that records the manual calculation processes to get the expression that can be evaluated using Mathematica building blocks in "caseCalculation_desktop.nb".

    .
    ├── ...
    ├── lyx 
        ├── caseCalculation.lyx         # explains the details of each function in caseCalculation_desktop.nb
        ├── case_xxxx.lyx               # manual calculation processes for each case
    ├── ...

The naming convention for case_xxxx files follows the same rule as the src file layout.

### pdf file layout
This directory contains the PDF file that documents the results of the total degree 3 case and total degree 2.5 case.

    .
    ├── ...
    ├── pdf 
        ├── result_3_and_2dot5.pdf     # results for total degree 3 case and total degree 2.5 case
    ├── ...

## The final result
To get and see the final result, follow these steps in sequence:

1. Run "\src\caseCalculation_desktop.nb", which builds the building blocks for the evaluation of the coefficients of different cases.

2. Run "\src\result.nb".

3. In the "The full final simplified result" section of "result.nb", one may get the final result.

## References
For the package "ItosLemma.m", one may refer to Mark Fisher's documentation https://library.wolfram.com/infocenter/ID/1170/ for full details.