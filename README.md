# PSG CVaR and bPOE Optimization
These PSG files are a series of optimization problems that allow for comparisons between CVaR and bPOE (buffered probability of exceedance) constraints. It is also a study of infeasibilty in optimization problems.

## P1 Files
The CVaR P1 problem imposes a constraint on CVaR at the 90% confidence level, requiring that it must not exceed a value of 5.339%, meaning that the average loss in the worst 
10% of scenarios must not be worse than 5.339%. The bPOE P1 problem constrains the bPOE for a loss of 5.339% to be less than or equal to 10%. Requiring that the CVaR at 
the 90% confidence level does not exceed 5.339% is equivalent to requiring that the bPOE of a loss of 5.339% is at most 10%. 

Since both optimization problems are equivalent, it would be expected that the solution vectors are also equivalent. This is indeed found to be true, as all four elements of each vector are equivalent when rounded to three significant figures (**x** = [0.168, 0.0325, 0.189, 0.611]). Both optimal objective values were also found to be equivalent.

## P2 Files
The CVaR P2 problem minimzes CVaR while constraining the budget to 1, which is in contrast to the CVaR P1 problem which maximizes return while constraining CVaR. The optimal solution vector was found to be **x** = [0.486, 0.514, 0, 0], while the optimal objective value obtained was 0.0386 and will be denoted by C_bar. This value indicates that the optimal objective value when minimizing CVaR at the 90% confidence level is 0.0386. For bPOE P2, variable C was intialized to be 0.03 so that C < C_bar. This value 0.03 is lower than the minimum achievable CVaR for an alpha of 0.90, so it is expected that optimization problem bPOE P2 is infeasible.

In bPOE P2, the bPOE of losses exceeding 3% is specified to be no greater than 10%. However, the bPOE obtained for a 3% loss was 0.187, indicating that 18.7% of scenarios experience losses worse than 3%. This value of 18.7% clearly exceeds the constraint of 10%, which shows that problem P4 is infeasible.

## Summary
The first two P1 optimization problems show that constraining bPOE and CVaR while maximizing return are equivalent optimization problems. The first of two P2 problems outputs the minimum possible CVaR, which is found to be 0.0386. For the second P2 problem, a bPOE constraint of 0.10 for a loss lower than 0.0386 (i.e., 0.03) is set. However, this problem is infeasible and the bPOE output of 0.187, which is much greater than the constraint of 0.10, shows this.
