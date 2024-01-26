## Scales

Scales can be ordinal or cardinal.

### Ordinal

Ordinal scales accurately reflect ranking and ordering of preferences.

### Cardinal

We can subdivide this category into two parts: interval scales and ratio scales. 

Interval scales, on top of ordinal scales, also reflect the differences between the entries.

Ratio scales are even more powerful in that they reflect the ratio between the entries.

---

An example of an interval scale would be to measure temperature using different scales (C, F, ...). We might measure the temperature in different cities. 

| city  | F  | C   | K   |
|-------|----|-----|-----|
| LA    | 82 | 28  | 291 |
| Tokyo | 64 | 18  | 280.8 |
| NYC   | 32 | 0   | 273 |
| SASK  | 0  | -18 | 256.2 |

If we go from Tokyo to NYC to SASK, we notice that all three columns decrease the same. A change of $-32$ in the F column corresponds to a change of $-18$ in the C column. Therefore, we can say that *differences are preserved*. Thus we are dealing with at least an interval scale.

But in this case, the ratios are not preserved. In the F column, it is "twice" as hot in Tokyo as it is in NYC. However, things fall apart in the C column. 

---

Here is an example of a ratio scale. We might measure the masses of some objects:

| masses| kg | lb  |
|-------|----|-----|
| $m_1$ | 1 | 2  |
| $m_2$ | 2 | 4  |
| $m_3$ | 3 | 6  |

In this case, the ratios are preserved. We can say that $m_2$ is twice as heavy as $m_1$, no matter which column we use.

---

### Analysis

Why is temperature not a ratio scale? If we look at the formula for converting Celsius to Farenheit:

$$F=1.8\cdot C+32$$

We can see that we have a coefficient of $1.8$ and an added constant of $32$. Now the constant is messing things up for us, as not everything is $0$ at the same time. In the case of the mass example, we have 

$$\text{lb}\approx 2\text{kg}$$

So we can see there is no constant to screw us over, and thus it is a ratio scale.

### Permissible transformations

A transformation refers to the function that brings the data from one column to another. (F to C, kg to lb)

Ordinal scales don't reflect differences or ratios. So the only requirement they have is that the transformation must be monotonically increasing (non-decreasing).

Interval scales need to be linear. They should not be curved.

Ratio scales must be linear AND the constant should be $0$.

