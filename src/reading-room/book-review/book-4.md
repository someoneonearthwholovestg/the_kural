---
layout: post
title: "Maths OPEN elective"
author: "Nabil A Navab"
year: 2001
permalink: /book-review/post-4/
image: "https://picsum.photos/seed/book1/400/600"
description: "We Need To Study Right.."
---

> **How to use this guide:** Read every section in order. Each concept builds on the previous one. Every topic here maps directly to a question in your two assignment papers.

---

## Table of Contents

1. [Foundations: Counting & Arrangements](#1-foundations-counting--arrangements)
2. [Basic Probability](#2-basic-probability)
3. [Conditional Probability & Bayes' Theorem](#3-conditional-probability--bayes-theorem)
4. [Random Variables & Probability Mass Functions](#4-random-variables--probability-mass-functions-pmf)
5. [Expected Value & Variance](#5-expected-value--variance)
6. [Continuous Random Variables, PDF & CDF](#6-continuous-random-variables-pdf--cdf)
7. [The Normal Distribution](#7-the-normal-distribution)
8. [Moment Generating Functions (MGF)](#8-moment-generating-functions-mgf)
9. [Joint & Marginal Distributions](#9-joint--marginal-distributions)
10. [Sampling Distributions & Standard Error](#10-sampling-distributions--standard-error)
11. [The Chi-Square Distribution](#11-the-chi-square-distribution)
12. [Hypothesis Testing](#12-hypothesis-testing)

---

## 1. Foundations: Counting & Arrangements

Before probability, you need to know **how to count** outcomes.

### 1.1 Factorial

The factorial of a number n (written **n!**) means multiply all whole numbers from 1 up to n.

```
5! = 5 × 4 × 3 × 2 × 1 = 120
3! = 3 × 2 × 1 = 6
0! = 1  (by definition)
```

**Why it matters:** When you arrange n distinct objects, there are **n!** ways to do it.

### 1.2 Permutations (Arrangements where ORDER matters)

**Permutation = arrangement in a specific order.**

- Arranging all n distinct objects: **n!** ways
- Arranging r objects chosen from n: **P(n,r) = n! / (n−r)!**

**Example:** How many 3-letter words from {A, B, C, D}?
P(4,3) = 4! / (4−3)! = 24 / 1 = 24

### 1.3 Combinations (Selection where ORDER does NOT matter)

**Combination = choosing a group, order doesn't matter.**

$$C(n, r) = \binom{n}{r} = \frac{n!}{r!(n-r)!}$$

**Example:** Choose 3 balls from 10:
C(10,3) = 10! / (3! × 7!) = 120

### 1.4 Arrangements with Repeated Letters

If a word has repeated letters, total arrangements = **n! / (product of factorials of each repeated count)**

**Example — "MATHEMATICS" (11 letters):**

Letters: M(2), A(2), T(2), H(1), E(1), I(1), C(1), S(1)

Total arrangements = 11! / (2! × 2! × 2!) = 39,916,800 / 8 = **4,989,600**

### 1.5 "Treated as One Block" Trick

When a problem says "all vowels together," glue all vowels into ONE block and treat them as a single unit.

**Assignment 3, Q1 — "MATHEMATICS", all vowels together:**

Step 1: Identify vowels → **A, E, A, I** (4 vowels, A repeated)

Step 2: Treat {AEAI} as one block → arrange [AEAI block] + M, M, T, T, H, C, S = **8 units** (M×2, T×2)

Arrangements of 8 units = 8! / (2! × 2!) = 40320 / 4 = **10,080**

Step 3: Arrange letters INSIDE the vowel block → {A, E, A, I} = 4! / 2! = **12** ways

Total favourable = 10,080 × 12 = **120,960**

Total arrangements of MATHEMATICS = 11! / (2! × 2! × 2!) = **4,989,600**

**P(all vowels together) = 120,960 / 4,989,600 = 2/33**

---

## 2. Basic Probability

### 2.1 What is Probability?

Probability measures **how likely** an event is. It's always a number between 0 and 1.

```
P(event) = Number of favourable outcomes / Total possible outcomes
```

- P = 0 means impossible
- P = 1 means certain
- 0 < P < 1 means somewhere in between

### 2.2 Key Terms

| Term | Meaning |
|------|---------|
| **Sample Space (S or Ω)** | All possible outcomes |
| **Event** | A subset of the sample space |
| **Complementary Event (A')** | Everything NOT in A. P(A') = 1 − P(A) |

### 2.3 Addition Rule

For **any two events** A and B:

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

If A and B are **mutually exclusive**, P(A ∩ B) = 0, so:

$$P(A \cup B) = P(A) + P(B)$$

### 2.4 Divisibility Problems

**Assignment 3, Q2 — Divisible by 6 or 8 from 1 to 200:**

- Multiples of 6: floor(200/6) = **33**
- Multiples of 8: floor(200/8) = **25**
- Multiples of both (LCM = 24): floor(200/24) = **8**

P(div by 6 or 8) = (33 + 25 − 8) / 200 = **50/200 = 1/4**

### 2.5 Combinations in Probability (Urn Problems)

**Assignment 3, Q9 — Urn with 6 white, 4 red, 9 black (total 19), draw 3:**

Total ways: C(19,3) = 969

**(i) Two white:** C(6,2) × C(13,1) = 15 × 13 = 195 → P = **65/323**

**(ii) One of each colour:** C(6,1) × C(4,1) × C(9,1) = 216 → P = **72/323**

**(iii) None is red:** C(15,3) = 455 → P = **455/969**

**(iv) At least one white:** 1 − P(no white) = 1 − 286/969 = **683/969**

---

## 3. Conditional Probability & Bayes' Theorem

### 3.1 Conditional Probability

**"Given that B happened, what's the probability that A also happens?"**

$$P(A | B) = \frac{P(A \cap B)}{P(B)}$$

### 3.2 Law of Total Probability

If B₁, B₂, ..., Bₙ are exhaustive and mutually exclusive:

$$P(A) = P(A|B_1)P(B_1) + P(A|B_2)P(B_2) + \cdots$$

### 3.3 Bayes' Theorem

$$P(B_i | A) = \frac{P(A | B_i) \cdot P(B_i)}{P(A)}$$

### 3.4 Worked Example — Mohan & the Bus

- P(bus) = 0.80, P(father) = 0.20
- P(late\|bus) = 0.5, P(late\|father) = 0.2

P(late) = 0.5×0.8 + 0.2×0.2 = **0.44**

P(father\|late) = (0.2 × 0.2) / 0.44 = **1/11 ≈ 0.0909**

### 3.5 Worked Example — Rare Disease Test

- P(disease) = 0.0001, P(positive\|disease) = 0.98, P(positive\|no disease) = 0.03

P(positive) = 0.98×0.0001 + 0.03×0.9999 = **0.030095**

P(no disease\|positive) = 0.029997 / 0.030095 ≈ **0.9967**

> **Key insight:** When a disease is very rare, even a good test gives many false positives. Most "positive" people are actually healthy!

---

## 4. Random Variables & Probability Mass Functions (PMF)

### 4.1 What is a Random Variable?

A **random variable** X assigns a number to each outcome of a random experiment.

- **Discrete RV:** Countable values (0, 1, 2, 3, ...)
- **Continuous RV:** Any value in an interval (height, weight, time)

### 4.2 Probability Mass Function (PMF)

**Rules a valid PMF must satisfy:**
1. p(x) ≥ 0 for all x
2. **Σ p(x) = 1**

### 4.3 Finding the Constant — Assignment 3, Q4

Given: p(0) = 3c², p(1) = 4c − 10c², p(2) = 5c − 1

Using Σp(x) = 1 → **7c² − 9c + 2 = 0** → c = 1 or c = 2/7

c = 1 gives p(2) = 4 > 1 ✗ → **c = 2/7** ✓

- P(X < 2) = 12/49 + 16/49 = **4/7**
- P(1 < X ≤ 2) = **3/7**

---

## 5. Expected Value & Variance

### 5.1 Expected Value E(X)

$$E(X) = \sum x \cdot p(x) \quad \text{(discrete)}$$
$$E(X) = \int x \cdot f(x)\, dx \quad \text{(continuous)}$$

### 5.2 Variance

$$\text{Var}(X) = E(X^2) - [E(X)]^2$$

### 5.3 Key Properties

| Property | Rule |
|----------|------|
| E(aX + b) | aE(X) + b |
| Var(aX + b) | a²Var(X) |
| Var(aX ± bY) | a²Var(X) + b²Var(Y) — if independent |

---

## 6. Continuous Random Variables, PDF & CDF

### 6.1 Probability Density Function (PDF)

For a continuous RV, f(x) is the PDF. Rules:
1. f(x) ≥ 0
2. **∫ f(x) dx = 1** (over all x)
3. P(a ≤ X ≤ b) = ∫ₐᵇ f(x) dx

### 6.2 Cumulative Distribution Function (CDF)

$$F(x) = P(X \leq x) = \int_{-\infty}^{x} f(t)\, dt$$

To get PDF from CDF: **f(x) = F'(x)**

---

## 7. The Normal Distribution

### 7.1 Standard Normal Z

$$Z = \frac{X - \mu}{\sigma} \sim N(0, 1)$$

### 7.2 Key Properties

- Symmetric about mean μ
- Mean = Median = Mode = μ
- 68% of data within ±1σ, 95% within ±2σ, 99.7% within ±3σ

### 7.3 Using Z-Tables

To find P(X ≤ x): convert to Z, then look up in table.
To find P(a ≤ X ≤ b): P(Z ≤ b') − P(Z ≤ a') where a', b' are standardised values.

---

## 8. Moment Generating Functions (MGF)

### 8.1 Definition

$$M_X(t) = E(e^{tX})$$

### 8.2 Why MGFs are Useful

- **r-th moment:** E(Xʳ) = M_X^(r)(0) (r-th derivative at t=0)
- **Sum of independent RVs:** M_{X+Y}(t) = M_X(t) · M_Y(t)
- **Uniquely identifies** a distribution

### 8.3 Key MGFs

| Distribution | MGF |
|---|---|
| N(μ, σ²) | exp(μt + σ²t²/2) |
| χ²(n) | (1 − 2t)^(−n/2) |
| Poisson(λ) | exp(λ(eᵗ − 1)) |

---

## 9. Joint & Marginal Distributions

### 9.1 Joint PMF / PDF

For two RVs X and Y:
- **Discrete:** p(x, y) = P(X = x, Y = y)
- **Continuous:** f(x, y) such that ∬ f(x,y) dx dy = 1

### 9.2 Marginal Distributions

$$P_X(x) = \sum_y p(x, y) \quad \text{(discrete)}$$
$$f_X(x) = \int f(x, y)\, dy \quad \text{(continuous)}$$

### 9.3 Conditional Distribution

$$P(X = x | Y = y) = \frac{p(x,y)}{P_Y(y)}$$

### 9.4 Independence

X and Y are independent if and only if:

$$p(x, y) = P_X(x) \cdot P_Y(y) \quad \text{for ALL x, y}$$

**Quick check for a table:** If even ONE cell fails p(x,y) = Pₓ(x)·Pᵧ(y), they are NOT independent.

---

## 10. Sampling Distributions & Standard Error

### 10.1 Sample Mean x̄

$$\bar{X} = \frac{1}{n}\sum_{i=1}^n X_i$$

- E(x̄) = μ
- Var(x̄) = σ²/n
- **SE(x̄) = σ/√n**

### 10.2 Sample Variance S²

$$S^2 = \frac{1}{n-1}\sum_{i=1}^n (X_i - \bar{X})^2$$

E(S²) = σ² — unbiased estimator. We divide by (n−1) not n for this reason.

### 10.3 Central Limit Theorem (CLT)

> For large n, x̄ is approximately normally distributed regardless of the original distribution:

$$\bar{X} \approx N\!\left(\mu, \frac{\sigma^2}{n}\right)$$

---

## 11. The Chi-Square Distribution

### 11.1 Definition

$$X = Z_1^2 + Z_2^2 + \cdots + Z_n^2 \sim \chi^2_n$$

**Properties:** Mean = n, Variance = 2n, always ≥ 0.

### 11.2 MGF

$$M_X(t) = (1 - 2t)^{-n/2} \quad t < \frac{1}{2}$$

For large n: χ² ≈ N(n, 2n) by CLT.

### 11.3 Chi-Square Test for Variance

$$\chi^2 = \frac{(n-1)s^2}{\sigma_0^2} \sim \chi^2_{n-1}$$

**Assignment 4, Q12:** n=25, s²=0.0384, σ₀²=0.015006 → χ²=61.42 > critical 36.42 → **Reject H₀**

---

## 12. Hypothesis Testing

### 12.1 The 5-Step Framework

1. **State hypotheses** — H₀ (null) and H₁ (alternative)
2. **Choose α** — usually 0.05 or 0.01
3. **Calculate test statistic**
4. **Find critical value or p-value**
5. **Decide** — if |stat| > critical value → Reject H₀

### 12.2 Z-Test for a Single Mean

$$Z = \frac{\bar{X} - \mu_0}{\sigma / \sqrt{n}}$$

| Test type | α = 0.05 | α = 0.01 |
|-----------|---------|---------|
| Two-tailed | ±1.96 | ±2.576 |
| Right-tailed | 1.645 | 2.326 |
| Left-tailed | −1.645 | −2.326 |

**Assignment 4, Q13:** n=49, x̄=87.3, s=12.73, H₁: μ<95
Z = (87.3−95)/(12.73/7) = **−4.23** < −2.326 → **Reject H₀**

**Assignment 4, Q14:** n=36, x̄=816, s=70, H₁: μ>800
Z = (816−800)/(70/6) = **1.37** < 1.645 → **Fail to reject H₀**

### 12.3 Two-Sample Z-Test

$$Z = \frac{\bar{X}_1 - \bar{X}_2}{\sqrt{SE_1^2 + SE_2^2}}$$

**Assignment 4, Q10 (Two firms):** Z = 5/2.079 = **2.41** > 1.96 → **Reject H₀**

**Assignment 4, Q11 (Two universities):** Z = −0.8/0.1857 = **−4.31** > 1.96 → **Reject H₀**

---

## Quick Reference Summary

| Concept | Formula |
|---------|---------|
| Combinations | C(n,r) = n! / (r!(n−r)!) |
| Bayes' Theorem | P(B\|A) = P(A\|B)·P(B) / P(A) |
| E(X) | Σ x·p(x) or ∫ x·f(x)dx |
| Var(X) | E(X²) − [E(X)]² |
| Var(aX+bY) | a²Var(X) + b²Var(Y) [if independent] |
| Z-score | Z = (X − μ)/σ |
| SE of mean | σ/√n |
| Z-test statistic | Z = (x̄ − μ₀)/(s/√n) |
| Chi-square test | χ² = (n−1)s²/σ₀² |
| Marginal PMF | Pₓ(x) = Σᵧ p(x,y) |
| Marginal PDF | fₓ(x) = ∫ f(x,y) dy |
| Independence | p(x,y) = Pₓ(x)·Pᵧ(y) |
| MGF of N(μ,σ²) | exp(μt + σ²t²/2) |
| χ²ₙ MGF | (1−2t)^(−n/2) |

### Which Test to Use?

```
Is σ known?
├── YES → Z-test always
└── NO
    ├── n ≥ 30 → Z-test (use s for σ)
    └── n < 30 → t-test

Testing variance? → Chi-square test
Comparing two means? → Two-sample Z-test
```

---

*Good luck with your exams! Work through the examples in each section carefully — the same logic repeats across all the questions.*
