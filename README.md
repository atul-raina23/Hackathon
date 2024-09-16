Polynomial Secret Reconstruction using Lagrange Interpolation
Overview
This project implements a simplified version of Shamir's Secret Sharing algorithm. The goal is to determine the constant term 
𝑐
c of a polynomial function given a set of polynomial evaluations at specific points. The polynomial is represented as:

𝑓
(
𝑥
)
=
𝑎
𝑚
𝑥
𝑚
+
𝑎
𝑚
−
1
𝑥
𝑚
−
1
+
.
.
.
+
𝑎
1
𝑥
+
𝑐
f(x)=a 
m
​
 x 
m
 +a 
m−1
​
 x 
m−1
 +...+a 
1
​
 x+c

Where:

𝑓
(
𝑥
)
f(x) is the polynomial function.
𝑚
m is the degree of the polynomial.
𝑎
𝑚
,
𝑎
𝑚
−
1
,
.
.
.
,
𝑎
1
,
𝑐
a 
m
​
 ,a 
m−1
​
 ,...,a 
1
​
 ,c are the coefficients of the polynomial.
𝑐
c is the constant term which we need to find.
The polynomial is evaluated at certain points, and these points are provided in various base-encoded formats. This project converts these encoded values to decimal format and uses Lagrange interpolation to compute the constant term 
𝑐
c.

Problem Statement
You are given multiple points where a polynomial function has been evaluated. Each point is specified with:

An integer 
𝑥
x which represents the point at which the polynomial is evaluated.
A base-encoded string representing the polynomial's value at that point.
Your task is to reconstruct the polynomial and determine the constant term 
𝑐
c of the polynomial.

Usage
The project is implemented in TypeScript and includes functions to:

Convert Base-Encoded Strings: Convert values from various bases (e.g., binary, hexadecimal) to decimal.
Calculate Polynomial Constant: Use Lagrange interpolation to compute the constant term 
𝑐
c from the given polynomial evaluations.
Parse JSON Input: Extract and convert shares from JSON format.
Process the Secret: Combine all steps to find the constant term 
𝑐
c.
Example
Input
json
Copy code
{
    "keys": {
        "n": 4,
        "k": 3
    },
    "1": {
        "base": "10",
        "value": "4"
    },
    "2": {
        "base": "2",
        "value": "111"
    },
    "3": {
        "base": "10",
        "value": "12"
    },
    "6": {
        "base": "4",
        "value": "213"
    }
}
Output
csharp
Copy code
The constant term (c) of the polynomial is: 4
Files
polynomialSecret.ts: Contains the TypeScript code to solve the problem.
package.json: Includes project dependencies and scripts.
Running the Code
Install Dependencies:

sh
Copy code
npm install
Compile TypeScript:

sh
Copy code
tsc polynomialSecret.ts
Run the Compiled Code:

sh
Copy code
node polynomialSecret.js
The code will process the provided JSON inputs and print the computed constant term 
𝑐
c for each test case.

Test Cases
Two test cases are provided to validate the solution:

Test Case 1: Includes evaluations in decimal, binary, decimal, and base-4.
Test Case 2: Includes evaluations in decimal, hexadecimal, base-12, base-11, hexadecimal, decimal, base-14, base-9, and base-8.
Contributions
Feel free to contribute by:

Reporting bugs
Suggesting improvements
Adding new features
License
This project is licensed under the MIT License. See the LICENSE file for details.

