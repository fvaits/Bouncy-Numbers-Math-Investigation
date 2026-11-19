# Bouncy Numbers: Math Investigation

**Deriving a Formula to Count the Number of Bouncy Numbers within a Range**
IB Mathematics: Analysis and Approaches HL, Internal Assessment (19 pages)

This is my Mathematics AA HL IA submission as a May 2026 graduate for the IB. I wanted to share it because I found the content of the research I carried out to be interesting.

## About

A *bouncy number* is a non-negative integer whose digits are neither entirely increasing nor entirely decreasing (e.g. 192 is bouncy; 289 and 8521 are not). Telling whether one number is bouncy is easy, but counting how many exist in a range is much harder.

This investigation derives a closed-form formula for counting the n-digit bouncy numbers whose leading digit is k, that is, those in the range $[k \cdot 10^{n-1},\ (k+1) \cdot 10^{n-1} - 1]$.

## Approach

1. **Exploration:** a C++ program counted bouncy numbers up to 10⁶, and the results were graphed in MATLAB. This showed that the density of bouncy numbers grows with the number of digits.
2. **Setup:** it is easier to count the non-bouncy numbers (increasing, decreasing or all digits equal) and take the complement. A symmetry between increasing and decreasing numbers relates the two counts.
3. **Pattern:** computing small cases (n = 1 to 4) revealed a pattern in the count of increasing numbers.
4. **Proof:** the pattern was proved for all n by induction.

## Result

For $1 \le k \le 9$ and $n \ge 1$:

$$g_n(k) = 10^{n-1} + 1 - \frac{1}{(n-1)!}\left(\prod_{i=1}^{n-1}(i-k+9) + \prod_{j=1}^{n-1}(k+j)\right)$$

where $g_n(k)$ is the number of n-digit bouncy numbers with leading digit k.

## Limitations

- The formulas do not give meaningful results for k = 0, because leading zeros are counted as digits.
- Ranges with other boundaries can be handled by summing the results, but this is not as direct. Extensions to other number bases and to the limiting density of bouncy numbers are discussed in the paper.

## Contents

- The paper (PDF), including the C++ and MATLAB code in its appendix

## Tools

C++, MATLAB, LaTeX
