# Chi Square Test
## What is Chi-Square Test?

The Chi-Square Test ($\chi^2$) is a statistical method used to determine whether there is a significant association between two categorical variables.

## Real Example: Gender vs. Preference for Online Learning

Let’s say we surveyed 100 students to find out whether gender is associated with preference for online learning.

Here is the observed data (Contingency Table):

| | Prefers Online | Doesn't Prefer | Total |
|---|---|---|---|
| Male | 30 | 20 | 50 |
| Female | 10 | 40 | 50 |
| Total | 40 | 60 | 100 |

## Step-by-Step Chi-Square Test

**Null Hypothesis (H₀):** There is no association between gender and preference for online learning.  
**Alternative Hypothesis (H₁):** There is an association between gender and preference for online learning.

### Calculate Expected Frequencies

To calculate expected frequencies in a contingency table or a chi-square test for independence, the general formula is:

$$\text{Expected Frequency} = \frac{(\text{Row Total}) \times (\text{Column Total})}{\text{Grand Total}}$$

| | Expected Online | Expected Not Online |
|---|---|---|
| Male | $(50 \times 40) / 100 = 20$ | $(50 \times 60) / 100 = 30$ |
| Female | $(50 \times 40) / 100 = 20$ | $(50 \times 60) / 100 = 30$ |

### Apply Chi-Square Formula

$$\chi^2 = \sum \frac{(O - E)^2}{E}$$

Where O = Observed value, E = Expected value

$$\chi^2 = \frac{(30 - 20)^2}{20} + \frac{(20 - 30)^2}{30} + \frac{(10 - 20)^2}{20} + \frac{(40 - 30)^2}{30}$$

$$= \frac{100}{20} + \frac{100}{30} + \frac{100}{20} + \frac{100}{30}$$ 

$$= 5 + 3.33 + 5 + 3.33 = 16.66$$

### Calculate Degrees of Freedom (df)

$$df = (rows - 1)\times (columns - 1) = (2 - 1)\times (2 - 1) = 1$$

### Compare with Critical Value

At df = 1 and $\alpha$ = 0.05, the critical value is 3.841.
Since 16.66 > 3.841, we reject the null hypothesis.
There is a significant association between gender and preference for online learning in this sample.

## Chi-Square Critical Value Table (Upper-Tail Percentiles)

| df / α | 0.10 | 0.05 | 0.025 | 0.01 | 0.001 |
|---|---|---|---|---|---|
| 1 | 2.71 | 3.84 | 5.02 | 6.63 | 10.83 |
| 2 | 4.61 | 5.99 | 7.38 | 9.21 | 13.82 |
| 3 | 6.25 | 7.81 | 9.35 | 11.34 | 16.27 |
| 4 | 7.78 | 9.49 | 11.14 | 13.28 | 18.47 |
| 5 | 9.24 | 11.07 | 12.83 | 15.09 | 20.52 |
| 6 | 10.64 | 12.59 | 14.45 | 16.81 | 22.46 |
| 7 | 12.02 | 14.07 | 16.01 | 18.48 | 24.32 |
| 8 | 13.36 | 15.51 | 17.53 | 20.09 | 26.12 |
| 9 | 14.68 | 16.92 | 19.02 | 21.67 | 27.88 |
| 10 | 15.99 | 18.31 | 20.48 | 23.21 | 29.59 |

### How to Use This Table

If you're testing a hypothesis at $\alpha$ = 0.05 with df = 3, the critical value is 7.81.  
If your calculated $\chi^2$ value is greater than 7.81, you reject the null hypothesis.
If it's less, you fail to reject the null.

## What is Significance Level (α)?

Significance level ($\alpha$) is a statistical value that indicates how much risk we are willing to take that our decision might be wrong.

In simple terms:
When we perform a hypothesis test, we examine a hypothesis (for example, whether there is a relationship between two variables).
$\alpha$ represents the maximum probability we accept of making a wrong decision.

## Common Values of Alpha (α)

| $\alpha$ (Significance Level) | Probability of Wrong Decision | Confidence Level |
|---|---|---|
| 0.10 | 10% | 90% |
| 0.05 (Most common) | 5% | 95% |
| 0.01 | 1% | 99% |
| 0.001 | 0.1% | 99.9% |

**Example:**  
Suppose you are testing whether there is a relationship between student gender and preference for online classes.  
If you choose $\alpha$ = 0.05, it means you're okay with a 5% chance that you might mistakenly say "yes, there's a link" when, in reality, there isn't one.

**Remember:**  
- Small $\alpha$ → Strict decision, lower chance of error.  
- Large $\alpha$ → Flexible decision, but higher risk of error.

## Chi-Square Test: Real-Life Examples
### **Example 1: Smoking Habit vs. Lung Disease**
**Question:** Is there a relationship between smoking and lung disease?

**Observed Table:**

| | Disease | No Disease |
|---|---|---|
| Smoker | 40 | 60 |
| Non-Smoker | 20 | 80 |

**Test:** Association between smoking status and lung disease.

**Solution:**   
Observed Data (Contingency Table):

| | Disease | No Disease | Total |
|---|---|---|---|
| Smoker | 40 | 60 | 100 |
| Non-Smoker | 20 | 80 | 100 |
| Total | 60 | 140 | 200 |

**Step-by-Step Chi-Square Test:**  
**Null Hypothesis (H₀):** There is no association between smoking status and lung disease.  
**Alternative Hypothesis (H₁):** There is an association between smoking status and lung disease.

**Expected Values:**

| | Expected Disease | Expected No Disease |
|---|---|---|
| Smoker | $(100 \times 60) / 200 = 30$ | $(100 \times 140) / 200 = 70$ |
| Non-Smoker | $(100 \times 60) / 200 = 30$ | $(100 \times 140) / 200 = 70$ |

**Apply Chi-Square Formula:**  
$\chi^2 = \sum [(O - E)^2 / E]$  
Here O = Observed value, E = Expected value

$$\chi^2 = (40 - 30)^2 / 30 + (60 - 70)^2 / 70 + (20 - 30)^2 / 30 + (80 - 70)^2 / 70$$ 

$$\chi^2 = 3.33 + 1.43 + 3.33 + 1.43 = 9.52$$

Degrees of Freedom, $df = (rows - 1) (columns - 1) = (2 - 1) (2 - 1) = 1$

At df = 1 and $\alpha$ = 0.05, the critical value is 3.841.  
Since 9.52 > 3.841, we reject the null hypothesis.  
There is a significant association between smoking status and lung disease in this sample.

### **Example 2: Education Level vs. Voting Behavior**
**Question:** Does education level affect voting behavior?

**Observed Table:**

| | Voted | Didn’t Vote |
|---|---|---|
| Primary | 25 | 75 |
| Secondary | 40 | 60 |
| Higher Education | 70 | 30 |

**Test:** Association between education and voting.

**Solution:**  
Observed Data (Contingency Table):

| | Voted | Didn't Vote | Total |
|---|---|---|---|
| Primary | 25 | 75 | 100 |
| Secondary | 40 | 60 | 100 |
| Higher Education | 70 | 30 | 100 |
| Total | 135 | 165 | 300 |

**Step-by-Step Chi-Square Test:**  
**Null Hypothesis (H₀):** There is no association between education level and voting behavior.  
**Alternative Hypothesis (H₁):** There is an association between education level and voting behavior.  

**Expected Values:**

| | Expected Voted | Expected Didn't Vote |
|---|---|---|
| Primary | $(100 \times 135) / 300 = 45$ | $(100 \times 165) / 300 = 55$ |
| Secondary | $(100 \times 135) / 300 = 45$ | $(100 \times 165) / 300 = 55$ |
| Higher Education | $(100 \times 135) / 300 = 45$ | $(100 \times 165) / 300 = 55$ |

**Apply Chi-Square Formula:**  
$\chi^2 = \sum[(O - E)^2 / E]$  
Here O = Observed value, E = Expected value

$$\chi^2 = (25 - 45)^2 / 45 + (75 - 55)^2 / 55 + (40 - 45)^2 / 45 + (60 – 55)^2 / 55 + (70 - 45)^2 / 45 + (30 - 55)^2 / 55$$

$$\chi^2 \approx 8.889 + 7.273 + 0.556 + 0.455 + 13.889 + 11.364$$

$$\chi^2 \approx 42.426$$

Degrees of Freedom, $df = (rows - 1) (columns - 1) = (3 - 1) (2 - 1) = 2 \times 1 = 2$  

At df = 2 and $\alpha$ = 0.05, the critical value is 5.991.  
Since 42.426 > 5.991, we reject the null hypothesis.  
There is a significant association between education level and voting behavior in this sample.

### **Example 3: Advertisement Type vs. Product Purchase**
**Question:** Does ad type affect product purchase?

**Observed Table:**  

| | Bought | Didn't Buy |
|:---|:---|:---|
| TV Ad | 50 | 50 |
| Facebook Ad | 60 | 40 | 
| Newspaper Ad | 30 | 70 |

**Test:** Association between ad type and customer buying behavior.

**Solution:**
Observed Data (Contingency Table):

| | Bought | Didn't Buy | Total |
|:---|:---|:---|:---|
| TV Ad | 50 | 50 | 100 |
| Facebook Ad | 60 | 40 | 100 |
| Newspaper Ad | 30 | 70 | 100 |
| **Total** | **140** | **160** | **300** |

**Step-by-Step Chi-Square Test:**
**Null Hypothesis (H₀):** There is no association between ad type and product purchase.  
**Alternative Hypothesis (H₁):** There is an association between ad type and product purchase.  

**Expected Values:**

| | Expected Bought | Expected Didn't Buy |
|:---|:---|:---|
| TV Ad | $(100 \times 140) / 300 \approx 46.67$ | $(100 \times 160) / 300 \approx 53.33$ |
| Facebook Ad | $(100 \times 140) / 300 \approx 46.67$ | $(100 \times 160) / 300 \approx 53.33$ |
| Newspaper Ad | $(100 \times 140) / 300 \approx 46.67$ | $(100 \times 160) / 300 \approx 53.33$ |

**Apply Chi-Square Formula:**  
$\chi^2 = \sum[(O - E)^2 / E]$

Here O = Observed value, E = Expected value

$$\chi^2 = (50 - 46.67)^2 / 46.67 + (50 - 53.33)^2 / 53.33 + (60 - 46.67)^2 / 46.67 + (40 – 53.33)^2 / 53.33 + (30 - 46.67)^2 / 46.67 + (70 - 53.33)^2 / 53.33$$

$$\chi^2 \approx 0.2376 + 0.2079 + 3.8075 + 3.3318 + 5.9542 + 5.2104$$

$$\chi^2 \approx 18.75$$

Degrees of Freedom, $df = (rows - 1) (columns - 1) = (3 - 1) (2 - 1) = 2 \times 1 = 2$

At df = 2 and $\alpha$ = 0.05, the critical value is 5.991.  
Since 18.75 > 5.991, we reject the null hypothesis.  
There is a significant association between ad type and product purchase in this sample.

### **Example 4: Gender vs. Social Media Preference**
**Question:** Do men and women prefer different platforms?

**Observed Table:**

| | Facebook | Instagram | YouTube |
|:---|:---|:---|:---|
| Male | 30 | 10 | 40 |
| Female | 50 | 30 | 20 |

**Test:** Association between gender and platform preference.

**Solution:**
Observed Data (Contingency Table):

| | Facebook | Instagram | YouTube | Total |
|:---|:---|:---|:---|:---|
| Male | 30 | 10 | 40 | 80 |
| Female | 50 | 30 | 20 | 100 |
| **Total** | **80** | **40** | **60** | **180** |

**Step-by-Step Chi-Square Test:**
**Null Hypothesis (H₀):** There is no association between gender and social media platform preference.  
**Alternative Hypothesis (H₁):** There is an association between gender and social media platform preference.

**Expected Values:**

| | Expected Facebook | Expected Instagram | Expected YouTube |
|:---|:---|:---|:---|
| Male | $(80 \times 80) / 180 \approx 35.56$ | $(80 \times 40) / 180 \approx 17.78$ | $(80 \times 60) / 180 \approx 26.67$ |
| Female | $(100 \times 80) / 180 \approx 44.44$ | $(100 \times 40) / 180 \approx 22.22$ | $(100 \times 60) / 180 \approx 33.33$ |

**Apply Chi-Square Formula:**
$\chi^2 = \sum[(O - E)^2 / E]$

Here O = Observed value, E = Expected value

$$\chi^2 = (30 - 35.56)^2 / 35.56 + (10 - 17.78)^2 / 17.78 + (40 - 26.67)^2 / 26.67 + (50 - 44.44)^2 / 44.44 + (30 - 22.22)^2 / 22.22 + (20 - 33.33)^2 / 33.33$$

$$\chi^2 \approx 0.8693 + 3.4043 + 6.6620 + 0.6956 + 2.7231 + 5.3318$$

$$\chi^2 \approx 19.69$$

Degrees of Freedom, $df = (rows - 1) (columns - 1) = (2 - 1) (3 - 1) = 1 \times 2 = 2$

At df = 2 and $\alpha$ = 0.05, the critical value is 5.991.  
Since 19.69 > 5.991, we reject the null hypothesis.  
There is a significant association between gender and social media platform preference in this sample.


_Based on the slides provided by Md. Muradul Bashir sir on 19-Jun-2025_