
# **CS3930/CS4920/CS5930 Computational Finance: Coursework**

**Yuri Kalnishkan**
**February 16, 2023**

---

This assignment must be submitted by the 3rd of March, 10:00.
Feedback will be provided by the 23rd of March.
This coursework contributes 20% to the final mark.

---

## Learning outcomes assessed
- demonstrate an understanding of mathematical and computational models of underlying and derivative securities;
- master techniques for pricing derivatives;
- apply these models and techniques for creating computer programs.

## Instructions
The coursework consists of four parts:
- Common assignment (should be done by all students):
	- Practical part;
	- Theoretical part;
- MSc assignment (should be done only by CS5930 students).
	- Practical part;
	- Theoretical part

The programming part can be done using any of the following languages: Python, MATLAB, R, Java, C, C++. 
If you want to use a different language, please contact the course lecturer. 
You programs should work with the version of the programming language presently installed on the `linux.cim.rhul.ac.uk` server.

Submission should be done electronically on the CS3930/5930 moodle page.
You should submit files with the following names:

 - `bs.java` (or, e.g., `bs.py` if you use Python) should contain the source code you used for the Black–Scholes formula; 
 - `trees.java` should contain the source code you used for option pricing using binomial trees; 
 - `montecarlo.java` should contain the source code you used for the Monte Carlo method; if you use Python, you can submit a Jupyter notebook `pricing.ipynb` with the functions named `bs`, `trees`, and `montecarlo` instead;
 - `results.txt` should contain all the values which you are asked to find and all the comments you would like to add; use the template from the course Moodle page and fill in the prices where question marks are (do not change the layout of the file because it will be processed by a script);
 - `theory.txt` or `theory.rtf` or theory.pdf should contain the answers to the theoretical problem.

The theoretical part can be submitted as scanned handwritten text. 
It is your responsibility to make sure your file is legible!

> **NOTE**: The coursework assignment is strictly individual. Plagiarism will be prosecuted. Coursework submissions are routinely checked for plagiarism. Note that using someone else’s code with altered variable names is still a case of plagiarism and is not acceptable.

You must not use existing library functions implementing the Black-Scholes formulas. 
You can use an existing library function to calculate the distribution function $N(x)$. 
If in doubt about the use of a library function, ask the lecturer.

## Marking Criteria
In the practical part full marks are awarded only when the code is correct and applied to the input data in a correct way. 
The results should be close to the correct values (usually within 0.1).

In the theoretical part full marks are awarded only when it is clear how you have arrived at the final answer. 
Simply giving a result without any justification is unlikely to get you full marks.

## 1. Common Assignment: Practical Part
The objective of this part of the coursework is to implement three different ways of valuing put and call options.

Take two numbers, $X1 = 120$ and $X2$ calculated as follows. 
Take your student number, remove zeros and use the remaining digits to make the number closest to 100. 
For example, if your student number is $100966240$, after dropping $0$s you get $196624$ and can make the number $96$. 
Do not put your student number on your submission to preserve anonymity.

Consider options with strike prices $X1$ and $X2$ of $4$ types (European and American puts and calls) with the time to maturity equal to 6 months ($\frac{1}{2}$ of a year).

- In total, this amounts to 8 different options.
- Suppose the following holds:
  - Current stock price $S_0$ is 100p.
  - Annual volatility is 20%.
  - Money can be invested at the annual interest rate (with continuous compounding) of 5% and the investment is virtually riskless.
  - Money can be borrowed at the same rate.

You should code up the Black–Scholes formula, binomial trees, and Monte Carlo algorithm, and find the following 20 numbers:

- The prices of the European call and put options computed from the Black–Scholes formula (4 numbers);
	 > [10 marks]

- The prices of the European and American call and put options computed using the binomial tree method (with approximately 1 day as the time step) (8 numbers);
	>[15 marks]

- The prices of the European call and put options computed using the Monte Carlo method (with approximately 1 day as the time step) (4 numbers).
	>[15 marks]

In the lectures, several variations of each method were considered (e.g., different types of trees or simulations based on different SDEs). It is sufficient to choose one variant. Doing several variants will be considered an extra advantage, but it is not required.

- **Hint 1**: It is easier to measure time in years (fractions of a year), rather than in days.
- **Hint 2**: Different methods should return similar values for the same price. For example, the prices of European options calculated using the Black-Scholes formula, binomial trees, and Monte Carlo should be the same (or very close, usually within 0.1p).
- **Hint 3**: If you use Java, you will need to calculate the distribution function $N$ of the Gaussian distribution $\phi(0, 1)$. You can use the method from the file `CNDF.java` provided on Moodle.

## 2. Common Assignment: Theoretical Part

### 1
A company is considering whether to launch a new product. The sum of £$170,000$ should be spent now on new equipment. It is estimated that there will be a market for the new product for three years and the product will bring £$60,000$ of profit per year (assume for simplicity that the yearly profit is received at the end of the year as a single payment). Should this project be pursued if the current risk-free interest rate is $5$%? Justify your answer.
> [4 marks]

### 2
A bond with the face value of £$200$ matures in $3$ years and makes yearly coupon payments at the coupon rate of $15$%. The payments are made at the end of each year.

- (a) List all payments (with dates and amounts) the bond makes. 
	> [3 marks]
	
- (b) Assuming the effective interest rate of $10\%$ per annum, calculate the value of the bond. 
	> [5 marks]

### 3
A European call option with the strike of $40$p maturing in half a year on a share is worth $13$p. Suppose that the share is currently worth $45$p and the risk-free interest rate (with continuous compounding) is $10\%$. Calculate the price eliminating arbitrage opportunities of a European put option with the same strike of $40$p maturing in half a year on the same share. You do not need to give a complete proof.
> [4 marks]

### 4
Suppose that the price of a share on the spot market is $50$p, while the price of a European put option on this share that matures in one month and has the strike price of $55$p is $3$p. Assume that the risk-free interest rate (with continuous compounding) is $5\%$ per annum and the share will not be paying any dividends during the coming two months. This situation implies an arbitrage opportunity. Describe an arbitrage strategy and show that it brings profit.
> [5 marks]

### 5
Suppose that the underlying asset in Question 4 above is a metal rather than a share. Let all the prices be the same as above: the spot price per ounce of the metal is $50$p and the price of a European put option on an ounce that matures in one month and has the strike price of $55$p is $3$p. The metal can be bought or sold with no overhead costs, but its storage incurs the cost of $2$p per ounce per month payable up front. Does the arbitrage strategy you described in your answer to Question 4 above still bring profit?
> [4 marks]

### 6
Suppose that the option from Questions 4 and 5 is American. Is there an arbitrage opportunity? If so, describe an arbitrage strategy and show that it brings profit in the case when:

- (a) the underlying asset is a share as in Question 4;
> [4 marks]

- (b) the underlying asset is a metal as in Question 5.
> [4 marks]

### 7
A generalised Wiener process $x(t)$ starts from the point $x(0) = 10$ and satisfies the stochastic differential equation $dx = 5 , dt + 3 , dz$, where $z$ is the Wiener process.

- (a) What is the distribution of the increment $x(4) - x(0)$? Calculate its parameters.
> [3 marks]

- (b) What is the probability that $x(4) < 0$? Express the probability in terms of $N(x)$, the cumulative distribution function for $\phi(0, 1)$, and then use Python or any other tool to calculate it.
> [4 marks]

---

The total number of marks for CS3930 students is 80. 
Your result will be scaled to make 20% of the final mark.

> **Masters questions were skipped** 
