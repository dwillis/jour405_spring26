# Additional Statistical Concepts to Consider

## High-Value Additions for Journalists

### 1. **Effect Size and Practical Significance** ⭐ HIGH PRIORITY

**What it is:** Measures the magnitude of a difference, not just whether it's statistically significant.

**Why journalists need it:**
- A study can show statistically significant results that are practically meaningless
- Example: "Students who used the app scored 0.5 points higher (p < 0.001)" - significant but trivial
- Helps answer: "Is this difference big enough to matter?"

**What it replaces/reduces:**
- Could replace one of the chi-square or ANOVA examples
- Or integrate into HW9 (Test Scores) and HW10 (Car Thefts Significance)

**Teaching approach:**
```r
# After t-test in HW9:
cohen_d <- (mean(new_scores) - prior_mean) / prior_sd
cat("Effect size (Cohen's d):", round(cohen_d, 2))
# Interpretation:
# 0.2 = small effect, 0.5 = medium effect, 0.8 = large effect
```

**Real journalism application:**
- "The reading program raised scores by 3 points (statistically significant), which represents a moderate effect size (d = 0.6). Educational researchers consider this a meaningful improvement."

**Time required:** 1 week or integrate into existing hypothesis testing

---

### 2. **Margin of Error and Polling Fundamentals** ⭐ HIGH PRIORITY

**What it is:** Understanding and calculating margins of error for survey results, polling fundamentals.

**Why journalists need it:**
- Constantly reporting on polls
- Need to know when differences between candidates are meaningful
- Understanding "the race is within the margin of error"

**Current coverage:** Partially covered in HW11 (Survey Weights) but not explicitly

**What it enhances:** HW11 could be expanded or split

**Teaching approach:**
```r
# Sample size and margin of error relationship
sample_sizes <- c(100, 400, 1000, 2500, 5000)
margins_of_error <- 1.96 * sqrt(0.25 / sample_sizes) * 100

# Poll comparison
candidate_a <- 48  # percent
candidate_b <- 45  # percent
moe <- 3  # margin of error at 95% confidence
difference <- candidate_a - candidate_b
overlapping <- difference < (2 * moe)
```

**Real journalism application:**
- "Candidate A leads 48% to 45%, but with a margin of error of ±3 percentage points, this race is too close to call."
- "The poll surveyed 400 voters, giving it a margin of error of ±4.9 percentage points."

**Time required:** 1 week or expand HW11

---

### 3. **Logistic Regression** ⭐ MEDIUM PRIORITY

**What it is:** Predicting binary outcomes (yes/no, win/lose, pass/fail) based on multiple factors.

**Why journalists need it:**
- Many journalism questions are binary: Did the team win? Did the student graduate? Did the business fail?
- Understanding probabilities of outcomes
- Common in academic studies journalists cover

**What it replaces/reduces:**
- Could replace or follow multiple regression (HW17)
- Or reduce time on ANOVA

**Teaching approach:**
```r
# Predicting whether a school meets standards based on demographics
model <- glm(meets_standards ~ pct_low_income + avg_class_size + per_pupil_spending,
             data = schools,
             family = "binomial")

# Predict probability for a specific school
predict(model, newdata = new_school, type = "response")
```

**Real journalism application:**
- "Schools with more than 60% low-income students were three times less likely to meet state standards, even after accounting for per-pupil spending and class size."

**Time required:** 1-2 weeks

---

### 4. **Multiple Testing and False Discovery** ⭐ MEDIUM-HIGH PRIORITY

**What it is:** Understanding that testing many hypotheses increases the chance of false positives.

**Why journalists need it:**
- Data journalism often involves testing many relationships
- Understanding why "researcher looked at 100 factors and found 5 significant" is problematic
- Critical for evaluating studies with many comparisons

**What it replaces/reduces:**
- Could be a brief activity (not full homework) integrated into hypothesis testing week
- Or reduce ANOVA coverage

**Teaching approach:**
```r
# Demonstrate the problem
set.seed(123)
# Generate 20 completely random variables
random_data <- data.frame(
  outcome = rnorm(100),
  var1 = rnorm(100),
  var2 = rnorm(100),
  # ... var3 through var20
)

# Test each variable
p_values <- sapply(random_data[,-1], function(x) {
  cor.test(random_data$outcome, x)$p.value
})

# How many are "significant" at p < 0.05?
sum(p_values < 0.05)  # Expect about 1 out of 20 by chance!
```

**Real journalism application:**
- "The study examined 47 possible risk factors for the disease. By chance alone, we'd expect to find about 2-3 'significant' factors even if none truly mattered."

**Time required:** 1 activity or half-week

---

### 5. **Bootstrapping and Resampling** ⭐ MEDIUM PRIORITY

**What it is:** Using resampling to estimate uncertainty without assuming a specific distribution.

**Why journalists need it:**
- Works with small samples where traditional methods fail
- More intuitive than mathematical formulas
- Increasingly common in data journalism

**What it replaces/reduces:**
- Could replace some ANOVA content
- Or supplement existing confidence interval work

**Teaching approach:**
```r
# Bootstrap confidence interval for median (which doesn't have a simple formula)
observed_median <- median(data$salary)

bootstrap_medians <- replicate(1000, {
  resample <- sample(data$salary, replace = TRUE)
  median(resample)
})

ci_lower <- quantile(bootstrap_medians, 0.025)
ci_upper <- quantile(bootstrap_medians, 0.975)

# Visualize
hist(bootstrap_medians, breaks = 50)
abline(v = c(ci_lower, ci_upper), col = "red", lwd = 2)
```

**Real journalism application:**
- "The median salary in the district was $52,000. Using bootstrap resampling, we estimate the true median falls between $49,000 and $55,000 with 95% confidence."

**Time required:** 1 week

---

### 6. **Causal Inference Basics** ⭐ HIGH PRIORITY

**What it is:** Understanding what types of evidence support causal claims vs. just correlation.

**Why journalists need it:**
- Avoiding "correlation equals causation" errors
- Understanding randomized experiments vs. observational studies
- Evaluating claims like "X causes Y" in studies

**What it replaces/reduces:**
- Doesn't need to replace anything - can be integrated into existing content
- Add causal thinking questions to existing assignments

**Teaching approach:**
```r
# Not much R code needed - more conceptual

# Example: confounding variable
# Observed: Ice cream sales correlate with drowning deaths
# Confound: Temperature drives both

# Activity: Given a correlation, identify:
# 1. Could X cause Y?
# 2. Could Y cause X?
# 3. Could Z cause both X and Y?
# 4. What would you need to observe to distinguish these?
```

**Real journalism application:**
Integration into existing assignments:
- HW9 (Test Scores): "What other factors might explain score changes besides the reading program?"
- HW17 (Multiple Regression): "Does income cause higher turnout, or do both result from education?"

**Time required:** No additional time - integrate into existing assignments

---

### 7. **Time Series Basics** ⭐ MEDIUM PRIORITY

**What it is:** Understanding trends, seasonality, and autocorrelation in data over time.

**Why journalists need it:**
- Crime statistics, economic indicators, election polls change over time
- Distinguishing real trends from seasonal patterns
- Understanding "this is the worst [month] since..."

**Current coverage:** Some time series in HW8 (GDP/DJIA) and HW10 (Car Thefts), but not systematic

**What it replaces/reduces:**
- Expand existing time series content rather than add new

**Teaching approach:**
```r
# Decompose time series
crime_ts <- ts(crime_data$total, frequency = 12)
decomposed <- decompose(crime_ts)
plot(decomposed)

# Remove seasonality to see real trend
crime_data$deseasonalized <- crime_data$total - decomposed$seasonal

# Compare: "Crime rose 10% in December" vs "Crime rose 2% after adjusting for typical seasonal patterns"
```

**Real journalism application:**
- "Retail sales appear to drop sharply in January, but this is typical after holiday shopping. Adjusted for seasonal patterns, sales actually held steady."

**Time required:** Expand existing content, maybe +1 week

---

### 8. **Statistical Power and Sample Size** ⭐ LOW-MEDIUM PRIORITY

**What it is:** Understanding how likely a study is to detect an effect if it exists; calculating needed sample size.

**Why journalists need it:**
- Evaluating studies: "Was this study large enough to detect a real effect?"
- Understanding negative results: "They found no effect" vs "The study was too small to detect an effect"

**What it replaces/reduces:**
- Could integrate into HW9 (Test Scores) or HW11 (Survey Weights)

**Teaching approach:**
```r
# Power calculation
power.t.test(
  n = NULL,  # What sample size do we need?
  delta = 3,  # We want to detect a 3-point difference
  sd = 4.8,
  sig.level = 0.05,
  power = 0.80  # 80% chance of detecting the effect
)
```

**Real journalism application:**
- "The study of 30 patients found no significant difference, but researchers say they'd need at least 120 patients to reliably detect the effect size they expected."

**Time required:** Half-week or integrate into existing content

---

## Summary Recommendation: What to Add and What to Reduce

### Top Priority Additions (Choose 2-3):

1. **Effect Size** - Critical for interpreting significance tests properly
2. **Margin of Error/Polling** - Expand HW11 or make it more explicit
3. **Causal Inference Basics** - Integrate throughout, no time cost

### Medium Priority (Choose 1-2):

4. **Multiple Testing** - Brief activity, helps with research evaluation
5. **Logistic Regression** - Natural extension of linear regression
6. **Time Series** - Expand existing content rather than add new

### Could Add Later:

7. **Bootstrapping** - Nice to have, less essential
8. **Statistical Power** - Good for research evaluation, less critical

---

## What to Reduce or Consolidate

### Option A: Reduce ANOVA Emphasis
**Current:** HW12 (Car Thefts ANOVA)

**Reasoning:**
- ANOVA is essentially an extension of t-tests
- Less commonly used in journalism than regression
- Could be covered more briefly or as an activity rather than homework

**Trade-off:**
- Lose: Systematic comparison of 3+ groups
- Gain: Time for effect size, polling, or logistic regression

**Verdict:** Reasonable trade-off. Most journalism comparisons are two-group (before/after, treatment/control) or continuous (regression).

---

### Option B: Consolidate Early Data Wrangling
**Current:** HW2 (PG Crime), HW3 (WH Salaries), HW4 (MD City Crime)

**Reasoning:**
- Three separate homeworks on similar skills
- Could consolidate to two more comprehensive assignments

**Trade-off:**
- Lose: Repetition for skill-building
- Gain: 1 week for additional statistical concept

**Verdict:** Less ideal - students need practice with data wrangling

---

### Option C: Reduce Chi-Square Coverage
**Current:** HW15 (Car Accidents) - Chi-square test

**Reasoning:**
- Chi-square is useful but less fundamental than other concepts
- Could be covered as an activity or brief example

**Trade-off:**
- Lose: Testing independence between categorical variables
- Gain: Time for logistic regression (which handles similar questions but more powerfully)

**Verdict:** Reasonable if adding logistic regression. Chi-square is simpler but less flexible.

---

### Option D: Combine HW13 and HW14
**Current:** HW13 (Grade Distribution), HW14 (Diversity Index)

**Reasoning:**
- Both deal with distributions
- Could potentially combine concepts

**Trade-off:**
- Lose: Depth on each topic
- Gain: 1 week

**Verdict:** Worth exploring if both assignments exist

---

## My Specific Recommendations

### Scenario 1: Minimal Changes (Add 1-2 concepts, no major cuts)

**Add:**
1. **Causal inference thinking** - integrate throughout (no time cost)
2. **Effect size** - add to HW9 and HW10 (30 min per assignment)
3. **Explicit margin of error section** - expand HW11 slightly

**Reduce:**
- Nothing major - just add 30-45 minutes to existing assignments

**Result:** More sophisticated interpretation without structural changes

---

### Scenario 2: Moderate Changes (Add 2-3 concepts, consolidate 1-2 existing)

**Add:**
1. **Effect size** - integrate into hypothesis testing
2. **Polling/margin of error** - expand HW11 to full 2-week unit
3. **Multiple testing** - 1 activity during hypothesis testing week
4. **Causal inference** - integrate throughout

**Reduce:**
- **ANOVA (HW12)** - Convert to brief activity rather than full homework
- **Chi-square (HW15)** - Brief example rather than full homework

**Gain:** 1.5-2 weeks

**Use for:**
- Deeper coverage of polling (critical for journalists)
- Effect size throughout

**Result:** Stronger focus on practical interpretation skills

---

### Scenario 3: Significant Restructure (Add 3-4 concepts, rebalance)

**Add:**
1. **Effect size** - systematic coverage
2. **Polling fundamentals** - full 2-week unit
3. **Logistic regression** - 1.5 weeks (after linear regression)
4. **Multiple testing** - 1 activity
5. **Causal inference** - integrated throughout

**Reduce:**
- **ANOVA (HW12)** - brief activity only
- **Chi-square (HW15)** - brief example only
- **Consolidate HW2-4** - reduce from 3 to 2 homeworks

**Gain:** 3-4 weeks

**Result:** More modern, applied statistics curriculum focused on common journalism scenarios

---

## Decision Matrix

| Concept | Journalism Value | Student Difficulty | Time Required | Replace What? |
|---------|-----------------|-------------------|---------------|---------------|
| Effect Size | ⭐⭐⭐⭐⭐ | Low | +30 min to existing | Nothing |
| Polling/MOE | ⭐⭐⭐⭐⭐ | Low | +1 week | Expand HW11 |
| Causal Inference | ⭐⭐⭐⭐⭐ | Medium | Integrated | Nothing |
| Multiple Testing | ⭐⭐⭐⭐ | Medium | 1 activity | Brief |
| Logistic Regression | ⭐⭐⭐⭐ | High | 1.5 weeks | ANOVA, Chi-square |
| Bootstrapping | ⭐⭐⭐ | Medium | 1 week | ANOVA |
| Time Series | ⭐⭐⭐⭐ | Medium | Expand existing | Nothing |
| Statistical Power | ⭐⭐⭐ | Medium-High | 0.5 weeks | Integrate |

**Legend:**
- ⭐⭐⭐⭐⭐ = Essential for journalists
- ⭐⭐⭐⭐ = Very useful
- ⭐⭐⭐ = Nice to have

---

## My Final Recommendation

**Implement Scenario 2 (Moderate Changes):**

**Definite additions:**
1. **Effect size** - essential for proper interpretation
2. **Explicit polling/MOE section** - critical journalism skill
3. **Causal inference thinking** - prevents major errors
4. **Multiple testing awareness** - brief but important

**Reduce:**
1. **ANOVA** - make it an activity, not homework
2. **Chi-square** - brief example rather than full assignment

**Why this balance:**
- Adds most critical concepts for journalists
- Minimal disruption to existing structure
- Focuses on interpretation (effect size, causation) over additional test types
- Polling is constantly in the news - worth deep coverage
- ANOVA and chi-square are good to know but less essential than regression

**Implementation:**
- Week 9-10: Hypothesis testing + effect size + multiple testing activity
- Week 11-12: Expanded polling unit (2 weeks)
- Throughout: Add causal inference questions to existing assignments
- Brief ANOVA and chi-square coverage (examples in class, not homework)
- Use freed time to deepen coverage of core concepts
