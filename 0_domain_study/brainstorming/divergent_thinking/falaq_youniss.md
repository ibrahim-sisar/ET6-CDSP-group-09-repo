# Domain Suggestion

## Do introverts or extroverts achieve more?

Exploring whether introverts or extroverts are more likely to successfully complete
long-term goals using existing personality and goal achievement data.  

Research question: Are introverts more likely to finish long-term goals than
extroverts?  
Data
Personality Data: Big Five – Including Extraversion  
Dataset: IPIP–Big Five Factor Markers (Cleaned)
Available in cleaned form on Kaggle: “IPIP-Big-Five Factor Markers_Cleaned”  
Also available in larger versions (120- and 300-item) via GitHub/Kaggle  
What it includes:  
Scores for all Big Five traits (including extraversion)  
Often comes with age, gender, and other demographics  

2️⃣ Goal Completion Data  
Option A: MOOC/Digital Course Completion  

Example dataset: Predict Online Course Engagement by Rabie El
Kharoua on Kaggle  
Tracks user behavior and completion outcomes in online courses  
Can be used as a proxy for long-term goal completion  
Another MOOC dataset (student behavior & performance) on Kaggle  

Option B: College Completion Rates  

Kaggle dataset tracking college graduation rates across demographics  
Graduation count (yes/no) acts as a clear long-term goal completion instance  

How to Use Them Together  
Download both datasets:  

Big Five personality scores dataset with extraversion  
A goal-related dataset (MOOC or college completion)  
Analyze separately, then merge results using demographic fields
(e.g., age, gender, location).  
Compare extroversion between those who completed (learners/graduates) and those
who didn’t.  
Use statistical tests and visualizations to uncover meaningful patterns.  

System Thinking Aspect  
This project applies systemic thinking by examining how personality traits
(a complex human factor) interact with goal completion outcomes, considering
multiple influencing variables (motivation, behavior patterns, personality) as
parts of an interconnected system rather than isolated factors.  

Constraints  
Data Matching Across Sources  
Challenge: The personality and goal-completion data come from different
studies.  
Impact: They don’t belong to the same individuals, which makes direct correlation
impossible.  
Workaround: You can only compare group-level trends, not individual-level
predictions  
2. No Causal Inference  
Challenge: This project is observational, not experimental.  
Impact: You can’t prove that extroversion causes higher or lower completion
rates—only that there’s a pattern or correlation.  
Workaround: Frame your conclusion carefully (e.g., “This suggests...” rather
than “This proves…”).  
3. Limited Demographic Overlap  
Challenge: The two datasets may not have matching age, region,
or gender distributions.  
Impact: It may be hard to control for external factors
(like age or education).  
Workaround: You may need to filter the datasets to focus on
  comparable subgroups.
4. Indirect Goal Proxies  
Challenge: "Goal completion" is interpreted via proxies
(like course completion or graduation).  
Impact: These are not perfect representations of all long-term goals.  
Workaround: Be explicit in defining what kind of
“goals” you're analyzing.  
5. Assumption of Stable Traits  
Challenge: You assume that extraversion is stable and accurately captured.  
Impact: Real-life personality is complex and may shift over
time or across contexts.  
Workaround: Rely on the validated IPIP dataset, and acknowledge
this in limitations.  
6. Ethical Use of Public Data  
Challenge: You must ensure the datasets are openly licensed for analysis.  
Impact: Any restrictions in the data license could affect your ability to
share results.  
Workaround: Only use datasets from platforms like Kaggle that provide
explicit
data use terms.  
7. No Experimental Validation  
Challenge: Without primary data or simulations, you can't “test” your hypothesis
directly.  
Impact: You’ll rely heavily on statistical interpretation and literature
review.  
Workaround: Emphasize the strength of patterns and back your insights with theory
from OB or psychology research.
