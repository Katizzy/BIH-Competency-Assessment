# BIH-Competency-Assessment

# Edu-ca-te Tutoring Resource Allocation Analysis

## Project Overview

This project analyzes learner data, tutoring engagement, and demand patterns to provide data-driven recommendations for allocating additional tutoring resources across subjects. The analysis combines data cleaning, exploratory analysis, and key performance indicator (KPI) development to support strategic decision-making.

## Key Objectives

1. **Data Standardization**: Clean and normalize inconsistent data across learner profiles, engagement metrics, assessments, and capacity records
2. **Demand Analysis**: Understand inquiry volume, conversion rates, and prospective demand relative to current participation
3. **Capacity Assessment**: Evaluate tutoring capacity, waiting lists, and tutor-to-learner ratios by subject
4. **Learning Outcomes**: Correlate engagement metrics with assessment gains
5. **Strategic Recommendation**: Identify which subject merits additional tutoring resources based on combined evidence

## Data Processing

### Data Cleaning Workflow

The project standardizes three core datasets:

- **Learners Dataset**: Standardized learner IDs, gender categories, grades, and registration dates
- **Engagement Dataset**: Cleaned tutoring attendance percentages, video watching metrics, and watch time
- **Assessments Dataset**: Normalized baseline and latest mark records with duplicate handling
- **Support/Capacity Dataset**: Subject-level tutor counts, hours, waiting lists, and costs
- **Enquiry Dataset**: Prospect demand and conversion tracking by subject and grade

### Data Quality Improvements

- Converted inconsistent date formats to ISO 8601 standard (YYYY-MM-DD)
- Standardized gender values and handled "Prefer not to say" entries
- Cleaned numeric fields by removing negative values and capping percentages at 100%
- Resolved ambiguous categorical values (e.g., "Sci" classification using machine learning imputation)
- Deduplicated records and removed invalid learner IDs

## Key Analyses

### 1. Engagement vs. Assessment Outcomes

- **Correlation Analysis**: Examined relationships between tutoring attendance, video engagement, watch time, and assessment improvement
- **Subject Comparisons**: Visualized patterns by subject and grade level
- **Trend Analysis**: Polynomial trend lines show engagement-to-outcome relationships

### 2. Demand vs. Current Participation

- **Enquiry Conversion Rates**: Measured effectiveness of converting prospects to registrations by subject and grade
- **Unmet Demand**: Identified subjects with high inquiries relative to registered learners
- **Demand-to-Registration Ratio**: Quantified prospective demand pressure

### 3. Capacity Pressure Assessment

- **Waiting List Metrics**: Calculated waiting lists per 100 learners to standardize pressure across subjects
- **Tutor Utilization**: Analyzed learners per active tutor and weekly hours per learner
- **Cost Scenarios**: Estimated incremental costs to reduce waiting list pressure by 10%, 25%, and 50%

### 4. KPI Framework

Decision-relevant KPIs built for subject-level management:

| KPI | Definition | Business Use |
|-----|-----------|--------------|
| **Conversion Rate** | Enquiries converted to registrations (%) | Measures sales effectiveness |
| **Demand per Registered** | Enquiries ÷ registered learners | Indicates unmet demand or market appetite |
| **Waiting per 100 Learners** | (Waiting list ÷ registered learners) × 100 | Standardizes capacity pressure |
| **Learners per Tutor** | Registered learners ÷ active tutors | Operational strain indicator |
| **Avg. Assessment Gain** | Mean change in learner marks | Learning impact metric |
| **Cost per Learner** | Weekly capacity cost ÷ registered learners | Efficiency and budget planning |

## Recommendation

**Mathematics is the subject that merits prioritization for additional tutoring resources**, based on:

### Supporting Evidence

1. **Strong Demand Signal**: High enquiry volume relative to current registered learner base suggests unmet demand
2. **Capacity Strain**: Elevated waiting lists and high learner-to-tutor ratios indicate operational bottleneck
3. **Learning Sensitivity**: Stronger assessment gains where tutoring attendance is higher
4. **Cost-Benefit Alignment**: Cost of expansion is justified by the combination of demand and impact

### Key Trade-Offs

- High demand alone does not justify expansion; must also show capacity strain and learning impact
- Resource decisions should balance cost, capacity pressure, and educational outcomes
- Subjects with strong outcomes but lower demand may not merit additional resources

## Limitations and Assumptions

### Key Assumptions

- Cleaned data is reasonably accurate after standardization
- Subject labels are consistent across tables
- Enquiry data represents valid proxy for latent demand
- Assessment gain is meaningful measure of learning quality

### Important Caveats

- **Observational data**: Association only, not causal proof
- **Cross-sectional nature**: Cannot establish causation without time-series or experimental evidence
- **Cost data gaps**: May not capture training, scheduling, or quality-control overhead
- **Subject comparisons**: May be influenced by learner profiles, grade distribution, and historical performance differences

## Recommendations for Future Data Collection

Before committing to multi-term resource allocation, collect:

1. **Time-Series Data**: Weekly/monthly demand, capacity, and waiting list trends
2. **Tutor Productivity Data**: Experience, qualifications, retention, and learner satisfaction scores
3. **Learner-Level Outcomes**: Individual baseline/follow-up scores and completion tracking
4. **Cost-to-Outcome Data**: Cost per learner served and per successful outcome
5. **Granular Demand Data**: Conversion rates by learner segment (grade, gender, prior achievement)
6. **Service-Level Metrics**: Tutor utilization, session attendance, wait times, and satisfaction feedback

## Technologies Used

- **Python 3**: Data processing and analysis
- **Pandas**: Data manipulation and aggregation
- **NumPy**: Numerical computations
- **Scikit-learn**: Machine learning imputation and modeling
- **Matplotlib & Seaborn**: Static visualizations
- **Plotly**: Interactive charts
- **Openpyxl**: Excel file output

## Files

- **BIH.ipynb**: Main analysis notebook
- Input: `educate_linked_challenge_dirty_assessment.xlsx`

## How to Use

1. Load the Jupyter notebook
2. Execute cells sequentially to run data cleaning and analysis pipeline
3. Review visualizations and KPI tables
4. Reference markdown cells for interpretation and business context
5. Use cleaned datasets and KPIs for strategic planning
