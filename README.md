# tpower3_coefficient_calculation
This is the code repository of the paper entitled "Expected Signature on a Riemannian Manifold and Its Geometric Implications". In particular, it contains the code that calculates the coefficient of $t^3$ in Section 5.4 of the paper. The codes are implemented in Mathematica (version 14.0.0.0).

## Overview
In section 5.4 of the paper, we calculate explicitly the coefficient $\hat{\Xi}_x$ of $t^3$ in the the third-order small-time expansion equation (5.6), which turns out to encode the curvature properties. Following the fundamental decomposition structure (5.19) and the order counting rule illustrated before section 5.4.1 in the paper, we have three scenarios to consider: 
1. total degree 3 case,
2. total degree 2.5 case,  
3. total degree 2 case. 

We managed to calculate by hand the results of total degree 3 case and total degree 2.5 case, but for total degree 2 casse, the calculation is too complicated to be done manually. Therefore, we use Mathematica to calculate the coefficients of this case. We also use Mathematica to integrate the results of all the three cases and do the simplification to get the result shown in Proposition 5.16 in the paper.

## Directory Layout
### top-level directory layout
    .
    ├── lyx                   # 
    ├── pdf                   # 
    ├── src                   # Mathematica source code files
    └── README.md

### src file layout
    .
    ├── ...
    ├── src 
        ├── caseCalculation_desktop.nb  # codes for builiding blocks
        ├── case_xxxx.nb                # codes for each case
        ├── result_2_data.nb            # codes to integrate all the results for 
                                          total degree 2 case
        ├── result_3_and_2dot5.nb       # codes to integrate all the results for total 
                                          degree 3 case and total degree 2.5 case
        ├── result.nb                   # codes for simplification and final result
        ├── casexxxx.mx                 # binary files produced by Mathematica to 
                                          store the results
        ├── ItosLemma.m                 # the Mathematica package we use to 
                                          calculate Itô's formula
    ├── ...

### lyx file layout
This is the directory that contains the Lyx files that records the manual calculation processes to get the expression that can be evaluated using Mathematica building blocks in "caseCalculation_desktop.nb".

    .
    ├── ...
    ├── lyx 
        ├── caseCalculation.lyx         # explains the idea of each function 
                                          in caseCalculation_desktop.nb
        ├── case_xxxx.lyx               # manual calculation process for each case
    ├── ...

## The final result .
To get and see the final result, one needs to run in sequence the following.
1. Run "\src\caseCalculation_desktop.nb", which builds the building blocks for the evaluation of the coefficients of different cases.
2. Run "src\result.nb".
3. In the "The full final simplified result" section in "result.nb", one can see the final result.

## Additional Remarks

1. The critically important file is "caseCalculation_desktop.nb". It contains all the building blocks needed to evaluate the coefficients of different cases in the total order 2 scenario. For a detailed explanation of what total order 2 cases and different cases mean, refer to the "General Introduction" section in this notebook and Section 5.4 of the paper. Additionally, the LyX file "caseCalculation.lyx" provides further explanations.

2. For the package "\src\ItosLemma.m", one may read "\src\ItosLemma.nb" or refer to Mark Fisher's documentation https://library.wolfram.com/infocenter/ID/1170/.

3. The results for the total order 3 case and total order 2.5 case are derived through manual calculation. The file "\src\result_3_and_2dot5.nb" translates these results into Mathematica language. The manual calculation results are documented in "\pdf\result_3_and_2dot5_.pdf".

4. The naming convention for the files and their relation to the paper: 1 means term I, 2 means term J, 3 means term K, 4 means term L, 5 means term P. For instance, "case_1113.nb" means the term (II;IK) in the paper. 