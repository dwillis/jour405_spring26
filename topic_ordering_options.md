# Topic Ordering Options for JOUR405

## Current Observed Sequence (Based on homework numbers)

1. R Basics
2. Data loading and exploration (PG Crime, WH Salaries, MD City Crime)
3. Data manipulation (Spotify Songs)
4. Descriptive statistics and probability (M&Ms)
5. Time series visualization (GDP/DJIA)
6. Hypothesis testing (Test Scores)
7. Statistical significance (Car Thefts)
8. Survey methodology (Survey Weights)
9. ANOVA (Car Thefts ANOVA)
10. Distributions (Grade Distribution, Diversity Index)
11. Chi-square (Car Accidents)
12. Simple regression (School Math Scores)
13. Multiple regression (Multiple Regression)

## Option 1: Traditional Statistics Foundation (Conservative approach)

**Philosophy:** Master fundamental statistics before applying them to LLMs

**Sequence:**

### Weeks 1-3: Foundation
1. R Basics (HW1)
2. Data loading/wrangling (HW2-4)
3. Descriptive statistics (mean, median, SD)

### Weeks 4-6: Probability
4. Introduction to probability
5. Sampling activity + M&Ms (HW7)
6. **NEW: Text Prediction and Probability** ← First LLM connection
7. Probability distributions

### Weeks 7-9: Inference
8. Confidence intervals
9. Hypothesis testing (HW9: Test Scores)
10. Statistical significance (HW10: Car Thefts)
11. **NEW: Understanding LLM Uncertainty** (homework)

### Weeks 10-12: Advanced Methods
12. Survey weights (HW11)
13. ANOVA (HW12)
14. Chi-square (HW15)
15. **NEW: Bias in Training Data** (homework)

### Weeks 13-15: Regression & Integration
16. Correlation
17. Simple regression (HW16)
18. Multiple regression (HW17)
19. **NEW: Context Windows and Probability** (wraps up with how context affects predictions)

**Pros:**
- Students have solid statistical foundation before tackling LLM concepts
- Traditional progression matches most stats textbooks
- Lower risk of confusion between classical statistics and LLM applications

**Cons:**
- LLM content comes late when students are already familiar with other AI tools
- May lose opportunity to use LLM concepts to motivate probability learning
- Less immediately relevant to current journalism landscape

---

## Option 2: Early LLM Integration (Modern approach)

**Philosophy:** Use LLM concepts to motivate probability, then deepen both together

**Sequence:**

### Weeks 1-2: Foundation
1. R Basics (HW1)
2. Data loading/wrangling (HW2-3)

### Weeks 3-5: Probability Through LLMs
3. **NEW: Text Prediction and Probability** ← Hook students with familiar tech
4. Sampling activity + M&Ms (HW7)
5. **NEW: Token Probability Chains**
6. Probability distributions (now motivated by LLM examples)

### Weeks 6-8: Statistical Inference
7. Confidence intervals
8. **NEW: Temperature and Randomness**
9. Hypothesis testing (HW9: Test Scores)
10. Statistical significance (HW10: Car Thefts)

### Weeks 9-11: Advanced Inference & LLM Critique
11. Survey weights (HW11)
12. **NEW: Understanding LLM Uncertainty** (homework)
13. ANOVA (HW12)
14. **NEW: Bias in Training Data** (homework)
15. Chi-square (HW15)

### Weeks 12-15: Relationships & Context
16. Correlation
17. Simple regression (HW16)
18. **NEW: Context Windows and Probability**
19. Multiple regression (HW17)

**Pros:**
- Engages students immediately with technology they use
- LLM examples make abstract probability concrete
- Students learn critical AI evaluation skills early
- More relevant to current journalism practice

**Cons:**
- Risk of superficial understanding if probability foundation isn't solid
- Harder to teach (requires instructor comfort with both statistics and LLMs)
- May need to revisit probability concepts later

---

## Option 3: Parallel Tracks (Integrated approach)

**Philosophy:** Build statistical concepts and LLM applications simultaneously

**Sequence:**

### Weeks 1-3: Foundation (Both tracks)
1. R Basics (HW1)
2. Data loading/wrangling (HW2-4)
3. Descriptive statistics
4. **NEW: Text Prediction and Probability** (introduces LLM track)

### Weeks 4-7: Probability & Uncertainty (Interleaved)
5. Sampling activity + M&Ms (HW7) ← Classical statistics
6. **NEW: Token Probability Chains** ← LLM application
7. Probability distributions ← Classical statistics
8. **NEW: Temperature and Randomness** ← LLM application
9. Confidence intervals ← Classical statistics

### Weeks 8-11: Inference & Evaluation (Interleaved)
10. Hypothesis testing (HW9: Test Scores) ← Classical statistics
11. **NEW: Understanding LLM Uncertainty** ← LLM application
12. Statistical significance (HW10: Car Thefts) ← Classical statistics
13. Survey weights (HW11) ← Classical statistics
14. **NEW: Bias in Training Data** ← LLM application (connects to survey weights)

### Weeks 12-15: Relationships & Complex Models
15. ANOVA (HW12)
16. Chi-square (HW15)
17. Correlation + Simple regression (HW16)
18. **NEW: Context Windows and Probability**
19. Multiple regression (HW17)

**Pros:**
- Each statistical concept immediately gets a modern application
- Students see statistics isn't just historical - it's current
- Reinforces concepts through varied examples
- Natural connections (survey weights → training data bias)

**Cons:**
- Requires careful scheduling to avoid overload
- More prep work for instructor
- Students may struggle to distinguish when to apply which approach

---

## Option 4: Problem-First Discovery (Inductive approach)

**Philosophy:** Start with journalism problems, discover statistical concepts as needed

**Sequence:**

### Weeks 1-3: Tools & Exploration
1. R Basics (HW1)
2. Data loading/wrangling (HW2-4)
3. Descriptive statistics + visualization

### Weeks 4-6: "Is this real?" (Uncertainty)
**Problem:** How do we know if a change/difference is real or just random?
4. Sampling activity (introduces the problem)
5. **NEW: Text Prediction and Probability** (LLMs have the same problem)
6. Probability distributions (tools to answer the question)
7. Hypothesis testing (HW9: Test Scores)
8. Statistical significance (HW10: Car Thefts)

### Weeks 7-9: "Who's represented?" (Sampling)
**Problem:** How do we make sure our sample represents reality?
9. Survey weights (HW11)
10. **NEW: Bias in Training Data** (LLMs have sampling problems too)
11. M&Ms (HW7) - deeper exploration now that they understand weights

### Weeks 10-12: "What's random and what matters?" (Prediction)
**Problem:** Can we predict outcomes? Which factors actually matter?
12. **NEW: Temperature and Randomness** (introduces the trade-off)
13. **NEW: Token Probability Chains** (how predictions build)
14. Correlation
15. Simple regression (HW16)
16. **NEW: Understanding LLM Uncertainty** (when to trust predictions)

### Weeks 13-15: "What drives the outcome?" (Complex relationships)
**Problem:** Multiple factors interact - how do we untangle them?
17. ANOVA (HW12)
18. Chi-square (HW15)
19. Multiple regression (HW17)
20. **NEW: Context Windows and Probability** (synthesis)

**Pros:**
- Highly motivating - starts with "why do I need this?"
- Concepts stick better when solving real problems
- Natural integration of classical and modern statistics
- Prepares students for real reporting scenarios

**Cons:**
- More chaotic - may feel less structured
- Some students prefer linear concept building
- Requires students to tolerate ambiguity early
- Harder to create assessments

---

## Option 5: Quick Start, Deep Dive (Spiral approach)

**Philosophy:** Light coverage of all topics early, then deep dive into each

**Sequence:**

### Weeks 1-4: Survey of the Landscape
1. R Basics (HW1)
2. Data wrangling (HW2-4)
3. "Statistics in 2 weeks" - quick intro to all major concepts:
   - Descriptive stats
   - Probability basics
   - Hypothesis testing overview
   - Regression in 20 minutes
4. **NEW: Text Prediction and Probability** (quick version)
5. "What can go wrong" - common errors and misinterpretations

### Weeks 5-7: Deep Dive - Probability & Sampling
6. Sampling activity + M&Ms (HW7)
7. **NEW: Token Probability Chains** (full version)
8. Probability distributions
9. **NEW: Temperature and Randomness**

### Weeks 8-10: Deep Dive - Inference
10. Hypothesis testing (HW9)
11. Statistical significance (HW10)
12. **NEW: Understanding LLM Uncertainty**
13. Survey weights (HW11)
14. **NEW: Bias in Training Data**

### Weeks 11-13: Deep Dive - Relationships
15. ANOVA (HW12)
16. Chi-square (HW15)
17. Correlation
18. Simple regression (HW16)

### Weeks 14-15: Deep Dive - Complex Models
19. **NEW: Context Windows and Probability**
20. Multiple regression (HW17)
21. Synthesis project

**Pros:**
- Students see the whole picture early
- Can connect concepts from the start
- Reduces "when will I use this?" questions
- Second exposure deepens understanding

**Cons:**
- Initial survey might overwhelm some students
- Risk of superficial first pass
- Requires discipline to not go too deep in week 3

---

## Recommendation Matrix

| Approach | Best For | Requires | Risk Level |
|----------|----------|----------|------------|
| **Option 1: Traditional Foundation** | Instructors new to teaching statistics; students with no stats background | Standard stats textbook | Low |
| **Option 2: Early LLM Integration** | Tech-savvy students; instructors comfortable with AI | Good LLM knowledge | Medium |
| **Option 3: Parallel Tracks** | Mixed-level classes; showing contemporary relevance | Careful planning | Medium |
| **Option 4: Problem-First** | Motivated students; project-based learning | Instructor flexibility | High |
| **Option 5: Spiral** | Students who like big picture; covering lots of ground | Strong pacing discipline | Medium |

## My Recommendation: **Option 3 (Parallel Tracks)**

**Reasoning:**

1. **Reinforcement through variety:** Each statistical concept gets reinforced with both traditional and LLM applications. Students see probability through M&Ms AND through text prediction.

2. **Maintains structure:** Unlike Option 4, this keeps a clear progression while adding modern relevance.

3. **Immediate relevance:** Unlike Option 1, students don't wait 10 weeks to see how statistics applies to AI tools they're already using.

4. **Manageable complexity:** Unlike Option 2, students aren't thrown into LLM concepts before they understand basic probability.

5. **Natural connections:** The pairing works well:
   - Survey weights ↔ Training data bias (both about representation)
   - Hypothesis testing ↔ LLM uncertainty (both about confidence)
   - Regression ↔ Context windows (both about prediction from multiple factors)

**Suggested Week-by-Week for Option 3:**

```
Week 1: R Basics
Week 2: Data wrangling (PG Crime)
Week 3: Data wrangling (WH Salaries, MD City Crime)
Week 4: Descriptive statistics + Text Prediction activity
Week 5: Sampling + M&Ms (HW7)
Week 6: Token Probability Chains activity
Week 7: Probability distributions
Week 8: Temperature and Randomness activity + Confidence intervals
Week 9: Hypothesis testing (HW9: Test Scores)
Week 10: Statistical significance (HW10: Car Thefts)
Week 11: Understanding LLM Uncertainty (homework)
Week 12: Survey weights (HW11)
Week 13: Bias in Training Data (homework)
Week 14: ANOVA (HW12) + Chi-square (HW15)
Week 15: Correlation + Simple regression (HW16)
Week 16: Context Windows activity
Week 17: Multiple regression (HW17)
```

**Adjustments for different contexts:**

- **If students are already strong in statistics:** Use Option 2 (Early LLM Integration)
- **If time is limited:** Use Option 5 (Spiral) but cut the deep dives shorter
- **If students need more structure:** Use Option 1 (Traditional Foundation)
- **If class is project-based:** Use Option 4 (Problem-First)

## Implementation Tips

**Regardless of which option you choose:**

1. **Make connections explicit:** When teaching survey weights, point forward to training data bias. When teaching training data bias, reference survey weights.

2. **Use consistent terminology:** Use "sample" and "population" language in both classical statistics and LLM contexts.

3. **Assign paired readings:** When covering a concept, assign one traditional statistics reading and one AI/LLM reading that uses the same concept.

4. **Create a concept map:** Give students a visual showing how all the topics connect, update it weekly.

5. **Include both in assessments:** Midterm could have questions like:
   - "Calculate a confidence interval for these poll results"
   - "An LLM gives you an answer with 0.85 confidence. Explain what this means and what you would do before using it in a story"

6. **Guest speakers:** Invite both traditional data journalists AND AI/computational journalists to show both applications.

7. **Final project options:** Let students choose to do either a traditional data analysis OR an LLM evaluation project OR a hybrid.
