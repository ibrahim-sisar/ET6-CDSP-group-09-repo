# 📊 Retrospective — Milestone 3: Data Analysis

## ✅ What Went Well

- **Modular Workflow Success**  
Splitting the analysis into five focused notebooks greatly enhanced clarity,
reproducibility, and parallel progress. Each notebook served a distinct purpose
and helped maintain a clean structure.

- **Iterative and Feedback-Driven Development**  
Our step-by-step process allowed us to integrate feedback rapidly and refine
outputs at each stage. This made our final analysis both technically sound and
narratively coherent.

- **Strategic Model Pivot**  
Choosing to abandon an overfitted baseline model and pivot toward using the
Socio-Demographic Index (SDI) was a key moment. This led to a more interpretable
and scientifically grounded result.

- **Effective Collaboration**  
Once decisions were made, mutual communication improved significantly and work
flowed smoothly, especially when resolving modeling decisions and visual
presentation strategies.

- **Team Support and Planning**  
The team created a clear plan and followed it effectively. Every member was
helpful and supportive whenever needed, and the collaborative atmosphere
contributed to steady progress. Exploring multiple datasets and testing diverse
approaches helped strengthen the final model.

---

## ⚠️ What Was Challenging

- **Initial Visualization Missteps**  
Our early visualizations, based on global averages, masked important trends. It
took several iterations to identify that stratified, faceted plots revealed more
meaningful patterns.

- **Model Interpretation Challenges**  
Explaining why a lower R-squared was actually a positive outcome (indicating
better generalizability) proved difficult, especially when expectations
leaned toward “higher is better.”

- **CI/CD Workflow Learning Curve**  
Integrating Ruff for code linting initially led to confusion and failed CI
pipelines. Understanding and applying proper formatting took a few
trial-and-error cycles.

- **Dataset Refinement Delays**  
Exploring alternative datasets initially caused some delays and uncertainty.
However, once a decision was made and we committed to working with the selected
data, the analysis progressed smoothly and rapidly.

- **Technical and Conceptual Hurdles**  
Recognizing and resolving issues within the data was time-consuming. Applying
and interpreting advanced modeling techniques in a meaningful way also
presented a steep learning curve.

---

## 💡 What We Learned

- **R² Isn’t Everything**  
A high R² value is not inherently good—especially in complex datasets where
overfitting is a real risk. A lower R² that reflects better generalization
across diverse contexts is often preferable.

- **Stratification is Powerful**  
Starting exploratory data analysis with stratification (e.g., by development
level) helps uncover clearer, more relevant insights early in the process.

- **Automation Enhances Consistency**  
Tools like Ruff and continuous integration workflows save time in the long run
and help enforce team-wide code quality standards.

- **Data Compatibility Matters**  
We were reminded that choosing datasets that align not just in topic but also
in structure and granularity is essential to reduce rework during analysis.

- **Focus on Core Research Question**  
Multiple types of analysis and modeling can be applied, but what truly matters
is how effectively the work addresses the core research question. Keeping that
focus is essential for impactful results.

---

## 🔄 What We’ll Improve Next

- **Start with Stratified EDA**  
Future projects should begin with stratified visualizations to avoid misleading
patterns and reduce rework later.

- **Adopt Local Pre-Commit Hooks**  
Setting up local hooks to auto-format code before commits will prevent
unnecessary CI errors and improve development speed.

- **Expand Modeling Techniques**  
We plan to experiment with more advanced models (e.g., Mixed-Effects Models or
Gradient Boosting) to better handle the structure of global datasets with
hierarchical features.

- **Clarify Roles and Set Internal Deadlines Early**  
To maintain momentum and avoid duplicated efforts, we’ll aim to establish
clearer ownership of tasks and set internal checkpoints earlier in the
milestone. This approach will help reduce stress and provide more time for
refining the final product.

- **Encourage Consistent Participation**  
Building in regular, structured opportunities for all team members to weigh in
on decisions will help keep alignment strong as the project scales.

---

## 🎯 Strategy vs. Board

- **What parts of your plan went as expected?**  
The core milestone flow—Data Preparation → EDA → Modeling → Interpretation—was
followed effectively. Feature engineering and notebook handoffs were well
executed. Task division and team-based decisions also unfolded smoothly.

- **What parts of your plan did not work out?**  
We made a major pivot from the old project's modeling strategy. It wasn’t just
revised; it was replaced altogether to better fit our research goals and data
characteristics. Some tasks also took longer than expected due to technical or
conceptual complexity.

- **Did you need to add things that weren't in your strategy?**  
Yes. We created extra visualization stages in response to feedback, added a
dedicated section explaining the drop in R², explored additional datasets and
alternative analysis methods to strengthen our conclusions, and spent time
debugging CI formatting issues—which wasn't originally planned but proved
essential for project quality.

- **Or remove extra steps?**  
Yes. The initial modeling approach was fully discarded in favor of a new
SDI-driven model that offered more robust and interpretable outputs.

---

## 👥 Individual Reflections

### 👤 Linah Khayri  

- 🧠 **What I learned**  
  - Multifactorial health outcomes require contextual modeling
  We learned that analyzing national COVID-19 mortality involves not only
  environmental exposures like PM₂.₅, but also socio-demographic factors and a
  lot of confounding variables.

  - MLR and ML each offer distinct value
  Traditional regression models gave us interpretable but modest associations,
  while machine learning methods revealed more complex patterns that were less
  transparent but potentially more powerful.

  - Accounting for age-standardized rates made a big difference
  Adjusting for age-standardized rates strengthened the results and helped with
  comparisons across countries.

  - Model performance vs. interpretability
  Balancing interpretability and predictive performance is tricky, especially
  in public health research where clear communication is key.

- ✅ **What went well**  
  - Well-documented code and structured notebooks
  Jupyter notebooks were organized and well-commented, which made it easier to
  revisit and build on models.

  - Diverse modeling approaches
  We used a mix of statistical methods (MLR, interaction terms, spline
  regression) and machine learning (random forest, quantile regression), which
  gave us a broader view of the data.

- ⚠️ **What could be improved**  
  - More robust feature selection
  We could have added more variables like comorbidities, population density,
  healthcare capacity, or mobility data to better account for confounding.

  - Improve team collaboration
  Team coordination was okay, but there’s room to improve communication and
  workflow, especially in early planning stages

### 👤 Falaq Majeed  

- 🧠 **What I learned**  
  - Health outcomes are shaped by multiple, interacting factors
  We learned that analyzing global COVID-19 mortality requires more than just
  looking at PM₂.₅ levels—socio-demographic factors, health disparities, and
  confounding variables must be considered together.

  - Each modeling approach reveals different layers
  Spline regression helped capture non-linear relationships between PM₂.₅ and
  mortality, while random forest modeling uncovered deeper, more complex
  interactions that weren’t visible in traditional methods.

  - Standardizing by age matters
  Using age-standardized death rates allowed us to make fairer comparisons
  across countries with different population structures and improved the
  reliability of our findings.

  - Interpretability vs. complexity is a trade-off
  Spline regressions and interaction models were more transparent, while random
  forests offered stronger predictive insights but less clarity in
  interpretation—highlighting a key tension in health data science.

- ✅ **What went well**  
  - Clear, well-structured notebooks
  Our Jupyter notebooks were clean, organized, and well-annotated—making it
  easier to troubleshoot, share, and revisit models.

  - Diverse modeling techniques
  We applied a strong mix of analytical tools—spline regression, interaction
  terms, and machine learning (random forest, quantile regression)—which gave us
  richer, more nuanced insights.

- ⚠️ **What could be improved**  
  - More comprehensive variable selection
  - We could enhance our models by adding variables like comorbidity prevalence
  healthcare system capacity, or population density to better account for known confounders.

  - Earlier alignment on team planning
  Our collaboration was effective overall, but earlier alignment on goals,
  roles, and timelines could’ve prevented delays and made the workflow smoother.

### 👤 Said Abualroos  

- 🧠 **What I learned**  
  - Model Building: The Universal AI modules and recitations were invaluable
  for understanding how to properly build, test, and interpret models. I learned
  that a high R-squared score can be a red flag for overfitting, and a
  more generalizable model with a lower score is often superior.  
  - Insightful EDA: Stratifying exploratory data analysis by development level
  (SDI) from the beginning is critical. Global averages can mask the most
  important underlying trends in diverse datasets.  
  - Explanatory Power: Replacing hundreds of country-specific dummy variables
  with a single, powerful explanatory variable like SDI leads to a more robust
  and scientifically valid model.  

- ✅ **What went well**  
  - Literature Review: The foundational knowledge gained from the WHO, IDMI, and
  A State of Global Air reports was instrumental in guiding the feature
  engineering and analysis phases.  
  - Modular Workflow: Breaking the analysis into five focused notebooks created
  a clean, reproducible pipeline that was easy to debug and manage.  
  - Iterative Refinement: The step-by-step process of developing the analysis
  allowed for immediate feedback and course correction, which significantly
  improved the final outcome.  

- ⚠️ **What could be improved**  
  - Initial Visualizations: My first attempts at creating time-series plots were
  not insightful. I need to start with stratified or faceted plots in the future
  to get to the core story faster.  
  - Local Automation: I could improve my workflow by using local pre-commit hooks
  to automatically format code. This would prevent CI/CD pipeline
  failures and streamline the development process.  
  - Advanced Modeling: While Random Forest provided a strong baseline, I could
  explore more advanced techniques like Mixed-Effects Models in the future to
  better account for the data's hierarchical structure.  

---

### 👤 Mohamed Tilal  

- 🧠 **What I Learned**  
  - I learned new ML models and applied some modeling techniques like Linear
  Regression and Random Forest, and I practiced doing exploratory data analysis
  (EDA) independently. This helped me better understand the connection
  between data and insights.  

- ✅ **What Went Well**  
  - I contributed to the data analysis, helped in reviewing the old dataset and
  collecting new ones, and reviewed reports to support our modeling decisions.
  The team was mostly active and supportive, which made collaboration
  smooth and productive.  

- ⚠️ **What Could Be Improved**  
  - Applying the models and understanding their outputs was a bit challenging
  at first, but it became easier with practice. Also, a few team members were
  inactive, which slightly affected the overall team flow. I know some of them
  have difficult circumstances and I am totally okay with it, just let the team
  know and stay following the process.  

---

### 👤 Saliha Kalender  

- 🧠 **What I Learned**  
  - Thanks to the Universal AI modules and recitations, I was able to better
  understand and apply machine learning analyses. This process was highly
  valuable for me.  
  - Through the feedback provided by my teammates, I learned how to
  improve analyses.  
  - I learned the importance of balancing interpretability and performance,
  - especially when clear communication is key.  
  - I also saw how early data stratification in EDA helps reveal clearer
  patterns and avoid misleading trends.

- ✅ **What Went Well**  
  - After team decisions were made, communication became more fluent, which
  helped tasks proceed quickly and smoothly.  
  - Working iteratively and receiving feedback at each step improved the quality
  of the analysis.  
  - The strategic decisions we made regarding the data and model strengthened
  the scientific soundness of the project.  
  - We responded to feedback by creating new visualizations and explanations,
  which made our results more communicable and easier to interpret.

- ⚠️ **What Could Be Improved**  
  - I should deepen my knowledge and practice of advanced modeling techniques.  
  - I would benefit from spending more time on preliminary data exploration
  before jumping into modeling.
  - Gaining more experience in model optimization and parameter tuning would
  be beneficial.  
  - Clarifying roles and task distributions earlier would help improve
  workload management and increase overall efficiency.  

---

### 👤 Salih Adam  

- 🧠 **What you learned**  
  - Understanding the dataset and its measurements is critical: Deeply exploring
  what each metric means, how it is measured, and how it relates to real-world
  phenomena is essential for drawing valid conclusions in data analysis.  
  - Practiced computing and interpreting statistical relationships: Learned how
  to calculate and interpret correlation coefficients and p-values, and
  understood their role in identifying potential associations between variables.
  - Recognized the importance of temporal dynamics in data analysis: Became
  aware that outcomes in many datasets may not occur simultaneously with their
  causes or exposures, and that considering time lags is crucial when analyzing
  trends over time.  

- ✅ **What went well**  
  - Clear trend visualizations and correlations computed: The analysis revealed
  meaningful insights about how PM₂.₅ levels relate to health burdens,
  particularly for cardiovascular and respiratory outcomes.  
  - Reproducible pipeline built: The class-based approach allowed for systematic
  data handling, making extraction and analysis flexible and scalable.  

- ⚠️ **What could be improved**  
  - Gain deeper insight into data analysis by completing the Universal AI
  module: Advancing knowledge in machine learning, modeling, and advanced
  analytics will help extend this work beyond basic correlations.  
  - Improve team coordination and communication: Streamlining how the team
  shares progress, discusses findings, and aligns on next steps can enhance
  efficiency and collaboration.  

---

### 👤 Obay Salih  

- 🧠 **What You Learned**  
  - I learned that understanding the type of dataset and its structure is a key
  starting point in any data analysis process. It allows you to identify patterns
  and relationships between variables more effectively.  
  - I also recognized how statistical parameters such as means, correlations,
  and variability are essential tools in exploring and interpreting data,
  especially when working with environmental and health-related indicators.  

- ✅ **What Went Well**  
  - One of the successes during this milestone was being able to translate
  results into clear visualizations. This helped in making
  connections between different variables more intuitive and accessible.  
  - It was rewarding to see how data trends can be communicated visually to
  tell a compelling story.  

- ⚠️ **What Could Be Improved**  
  - I would like to improve my ability to work with different types of data,
  including structured and unstructured datasets.  
  - Understanding how to clean, manipulate, and analyze various data
  formats is something I plan to continue learning.  
  - I also aim to dive deeper into the Universal AI (UAI) course to gain more
  knowledge about advanced data analysis techniques and build more
  confidence in handling complex datasets.  

## 🚀 Next Steps

- 📘 Complete remaining UAI lessons to deepen modeling expertise.
- 📊 Experiment with advanced model types (e.g., mixed-effects, time-series models).
- 🤝 Maintain clear team channels and timelines in future collaborations.
- 🛠️ Set up local development tools (e.g., auto-formatters, linters)
  for smoother pipelines.
