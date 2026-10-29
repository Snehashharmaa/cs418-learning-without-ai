# Learning With(out) AI
# Checkpoint 4: Data Documentation

**Course:** CS 418
**Group:** Learning With(out) AI

## 1. Datasheets

### Primary Dataset 1: Student AI Tool Usage

#### 1.1 Motivation
This dataset is used to understand students' experiences with AI tools in their academic lives. It helps us examine which AI tools students use, how frequently they use them, their main purposes for using AI, their satisfaction levels, and their self-reported academic performance. It supports our investigation of student AI usage patterns and perceived academic outcomes.

#### 1.2 Composition
The dataset contains 200 student survey responses and 8 columns:

timestamp: Date and time associated with the survey response.

student_id: Student identifier recorded in the dataset.

ai_tool_used: AI tool reported by the student.

usage_hours_per_week: Reported weekly AI usage hours.

purpose: Main purpose for using the AI tool.

satisfaction_level: Student satisfaction rating.

academic_performance: Self-reported academic performance response.

comments: Optional free-text comments.

The dataset includes categorical, numerical, timestamp, and free-text information. The original responses contain inconsistent capitalization, differently formatted usage-hour entries, and mixed formats for academic-performance responses. The comments field contains 10 missing values in the raw CSV.

#### 1.3 Collection Process
The dataset is described in the project as a survey of 200 students about their use of AI tools. It contains timestamps, student identifiers, reported usage patterns, satisfaction ratings, academic-performance responses, and optional comments.

The precise survey recruitment method, sampling procedure, survey platform, collection dates, and consent process must be confirmed from the original data source or data acquisition documentation. These details should not be inferred from the CSV alone.

#### 1.4 Preprocessing
The dataset required cleaning because several responses were inconsistent or could not be interpreted reliably.

Standardized inconsistent capitalization and formatting in AI tool names and purposes.

Examined weekly usage-hour responses that were stored as text.

Corrected 8 usage-hour entries and set 11 unresolved entries to missing, as documented in the EDA summary.

Set 34 inconsistent academic-performance responses to missing rather than treating incompatible answers as equivalent numerical values.

Preserved missing optional comments rather than inventing replacement text.

Verified the dataset's columns, data types, unique values, and missing-value counts using the EDA notebook.

The final analysis should use the cleaned data produced by the notebook. The exact cleaning code and final row counts should be verified against the notebook before submission.


#### 1.5 Uses
This dataset is used to summarize student AI tool usage, common academic purposes, and satisfaction levels. It also provides descriptive context for understanding students' reported academic experiences with AI tools.

The dataset can support descriptive analyses of reported behavior and perceptions. Because academic-performance responses contain inconsistent formats and missing values, conclusions involving this variable must account for those limitations. The survey alone cannot establish that AI use causes changes in academic performance.

#### 1.6 Distribution
The CSV file is maintained in the group's GitHub repository at data/student_ai_tool_usage_dataset.csv. The EDA notebook and project documentation provide supporting information about its structure and preprocessing.

Before distributing the dataset outside the course project, the team should confirm the original source, applicable license, redistribution permissions, and whether student identifiers or other information require privacy protections.


#### 1.7 Maintenance
The project team is responsible for maintaining the dataset documentation, cleaning procedures, and analysis notebook for the checkpoint. Changes to the dataset or preprocessing steps should be documented in version control so that the analysis can be reproduced.

Future updates should preserve the original data where permitted, record cleaning decisions, verify column names and data types, and update the codebook whenever variables or transformations change. Any future redistribution should follow the dataset's confirmed license and applicable privacy requirements.

### Primary Dataset 2: AI Student Impact

#### 1.1 Motivation
This dataset supports the investigation of relationships between students' generative AI usage, traditional study habits, and academic performance. It allows the team to compare pre-semester and post-semester GPA and examine whether weekly AI usage hours and tool diversity are associated with GPA change. It also includes information about students' AI use cases, perceived dependency, skill retention, exam anxiety, and burnout risk.



#### 1.2 Composition
The dataset contains 50,000 student records and 16 original columns:

Student_ID: Student record identifier.

Major_Category: Academic major category.

Year_of_Study: Student's year of study.

Pre_Semester_GPA: GPA before the semester.

Weekly_GenAI_Hours: Reported or recorded weekly generative AI usage hours.

Primary_Use_Case: Main use case for generative AI.

Prompt_Engineering_Skill: Prompt engineering skill category.

Tool_Diversity: Number of AI tools used.

Paid_Subscription: Whether the student has a paid AI subscription.

Traditional_Study_Hours: Weekly hours spent on traditional studying.

Perceived_AI_Dependency: Recorded level of perceived dependency on AI.

Institutional_Policy: Category describing institutional AI policy.

Anxiety_Level_During_Exams: Recorded exam anxiety level.

Post_Semester_GPA: GPA after the semester.

Skill_Retention_Score: Recorded skill-retention score.

Burnout_Risk_Level: Recorded burnout-risk category.

The dataset contains numerical, categorical, and Boolean variables. The raw CSV has no missing values in the 16 columns, according to the initial verification. The source and methodology behind the records must be confirmed before interpreting them as observations from a representative student population.

#### 1.3 Collection Process
The project uses this dataset to examine AI usage and student outcomes across 50,000 records. It includes academic performance before and after a semester, AI usage patterns, traditional study hours, and additional student-related measures.

The original data source, collection dates, sampling method, recruitment process, measurement instruments, and whether the records are observed or synthetically generated must be verified using the source documentation or data acquisition notebook. These details cannot be established from the CSV structure alone.

#### 1.4 Preprocessing
According to the initial EDA verification, the raw dataset contains 50,000 rows, 16 columns, and no missing values or duplicate student identifiers.

The analysis derives a GPA-change variable:

GPA_Change = Post_Semester_GPA - Pre_Semester_GPA

Positive values represent an increase in GPA, negative values represent a decrease, and zero represents no change.

The EDA also examines the distributions of weekly generative AI hours and tool diversity, and relationships between GPA change, AI usage, and traditional study hours. The final notebook should be consulted for the exact transformations, validation checks, and analysis steps used.

#### 1.5 Uses
This dataset is used to investigate the relationship between weekly generative AI usage hours, traditional study hours, tool diversity, and changes in GPA. It also provides descriptive information about AI use cases and other student-related measures.

The dataset supports descriptive statistics, comparisons between groups, and correlation analysis. Its results should be interpreted as associations rather than proof of causation. The validity of conclusions depends on the data's provenance, variable definitions, sampling process, and measurement quality.



#### 1.6 Distribution
The CSV file is maintained in the group's GitHub repository at data/ai_student_impact_dataset (1).csv. The EDA notebook documents the dataset's initial verification and analysis.

Before distributing the dataset outside the course project, the team should confirm its original source, license, redistribution permissions, and any restrictions on sharing or reuse. If the data contains synthetic records, that fact should be clearly disclosed in the documentation.



#### 1.7 Maintenance
The project team is responsible for maintaining the dataset documentation, derived-variable definitions, and analysis procedures. Updates to the source data or transformations should be recorded in version control and reflected in the codebook and reproducibility recipe.

Future maintenance should include checking row counts, column names, data types, missing values, identifier uniqueness, and the calculation of GPA_Change. The team should also preserve source and license information and document any corrections to the dataset's provenance or interpretation.

## 2. Research Question Scope

### Research Question 1

Research Question: How do weekly generative AI usage hours and traditional study hours relate to the change in students' GPA from before to after a semester?

**Target Population:**
The population of interest is students who use generative AI tools, including students with different levels of AI usage and traditional study habits. The research aims to understand how these behaviors relate to changes in academic performance. The extent to which the dataset represents this population depends on the original data source and sampling method, which must be verified.

**Access Frame:**
The accessible data frame for this analysis is the set of records available in the AI Student Impact dataset, stored in data/ai_student_impact_dataset (1).csv. The dataset contains 50,000 records with pre-semester GPA, post-semester GPA, weekly generative AI hours, and traditional study hours. The original source and method used to obtain these records must be confirmed.


**Sample:**

The initial dataset contains 50,000 records and 16 columns, with no missing values reported during the initial verification. The analysis derives GPA_Change by subtracting Pre_Semester_GPA from Post_Semester_GPA. The final analytical sample should be confirmed from the EDA notebook after all filtering and transformations.

**Missing Populations and Limitations:**
The dataset may not represent all students, institutions, academic disciplines, or educational systems. The source and sampling method must be verified before generalizing results. GPA change may be influenced by factors not included in the dataset, such as course difficulty, prior academic preparation, socioeconomic circumstances, and access to academic support. Observational relationships cannot establish that AI usage or traditional study hours caused a change in GPA. The analysis should also consider that GPA change is calculated from two measurements and may be affected by measurement differences.

### Research Question 2
Research Question: Does the type of task for which students use AI (such as coding, writing, brainstorming, or research) relate to their satisfaction with AI tools?
**Target Population:**
The population of interest is students who use AI tools for academic tasks, including writing, coding, studying, research, brainstorming, and other purposes. The research focuses on whether satisfaction differs across reported AI-use purposes. The extent to which the available survey represents this population is unknown without further information about recruitment and sampling.

**Access Frame:**

The accessible data frame is the set of 200 survey responses in data/student_ai_tool_usage_dataset.csv. The dataset records AI tools used, usage hours, reported purposes, satisfaction ratings, academic-performance responses, and optional comments. The original survey recruitment process and collection method should be verified from the project's source documentation.

**Sample:**

The raw dataset contains 200 survey responses and 8 columns. The purpose field identifies reported uses of AI, while satisfaction_level contains integer ratings. The EDA summary reports that 58.5% of respondents gave a satisfaction rating of 4 or 5. The final sample size for this question should be calculated from the cleaned data after excluding any records that cannot be used in the relevant analysis.

**Missing Populations and Limitations:**

The survey may not represent students who do not use AI, students who chose not to participate, or students from institutions and backgrounds not included in the survey. The sample size is relatively small, and the recruitment method is not yet confirmed. Satisfaction is self-reported and may be affected by individual expectations, experience, and response bias. The purpose categories may not capture every way students use AI, and inconsistent or missing responses may affect comparisons. An association between task type and satisfaction does not demonstrate that the task type caused a particular satisfaction level.

## 3. Codebook

### Primary Dataset 1

| Column | Data Type | Units | Meaning | Range / Allowed Values | Missing Values | Origin |
|---|---|---|---|---|---|---|
| `timestamp` | String | Date/time | Timestamp associated with the survey response | Recorded timestamp strings | 0 in raw data | Original CSV |
| `student_id` | String | Identifier | Identifier associated with a student response | 200 unique identifiers | 0 in raw data | Original CSV |
| `ai_tool_used` | String | Category | AI tool reported by the student | 11 distinct raw values; capitalization standardized during cleaning | 0 in raw data | Original survey response |
| `usage_hours_per_week` | String in raw data; numeric after cleaning | Hours/week | Reported weekly AI usage hours | Nonnegative numeric hours after cleaning | 0 in raw data; 11 set to missing during cleaning | Original survey response; cleaned in EDA |
| `purpose` | String | Category | Main reported purpose for using AI | 7 distinct raw values; capitalization standardized during cleaning | 0 in raw data | Original survey response |
| `satisfaction_level` | Integer | Rating points | Student's reported satisfaction with AI use | Five distinct values; verify exact range in EDA | 0 in raw data | Original survey response |
| `academic_performance` | String in raw data | Self-reported performance | Student's reported academic-performance response | Mixed numerical and text formats in raw data | 0 in raw data; 34 set to missing during cleaning | Original survey response; cleaned in EDA |
| `comments` | String | Free text | Optional comments about AI use | Free-text responses | 10 in raw data | Original survey response |

### Primary Dataset 2

| Column | Data Type | Units | Meaning | Range / Allowed Values | Missing Values | Origin |
|---|---|---|---|---|---|---|
| `Student_ID` | Integer | Identifier | Student record identifier | 50,000 unique identifiers | 0 | Original CSV |
| `Major_Category` | String | Category | Academic major grouping | 5 distinct categories | 0 | Original CSV |
| `Year_of_Study` | String | Academic year | Student's year of study | 5 distinct categories | 0 | Original CSV |
| `Pre_Semester_GPA` | Float | GPA points | GPA before the semester | Numeric; exact observed range to be verified | 0 | Original CSV |
| `Weekly_GenAI_Hours` | Float | Hours/week | Weekly generative AI usage hours | Numeric; exact observed range to be verified | 0 | Original CSV |
| `Primary_Use_Case` | String | Category | Main use case for generative AI | 5 distinct categories | 0 | Original CSV |
| `Prompt_Engineering_Skill` | String | Category | Prompt engineering skill classification | 3 distinct categories | 0 | Original CSV |
| `Tool_Diversity` | Integer | Number of tools | Number of AI tools used | 5 distinct values; exact range to be verified | 0 | Original CSV |
| `Paid_Subscription` | Boolean | True/False | Whether a paid AI subscription is recorded | `True`, `False` | 0 | Original CSV |
| `Traditional_Study_Hours` | Float | Hours/week | Weekly time spent studying without AI assistance | Numeric; exact observed range to be verified | 0 | Original CSV |
| `Perceived_AI_Dependency` | Integer | Rating points | Recorded level of perceived AI dependency | 10 distinct values; exact range to be verified | 0 | Original CSV |
| `Institutional_Policy` | String | Category | Recorded institutional AI policy | 3 distinct categories | 0 | Original CSV |
| `Anxiety_Level_During_Exams` | Integer | Rating points | Recorded exam anxiety level | 10 distinct values; exact range to be verified | 0 | Original CSV |
| `Post_Semester_GPA` | Float | GPA points | GPA after the semester | Numeric; exact observed range to be verified | 0 | Original CSV |
| `Skill_Retention_Score` | Float | Score points | Recorded skill-retention score | Numeric; exact observed range to be verified | 0 | Original CSV |
| `Burnout_Risk_Level` | String | Category | Recorded burnout-risk classification | 3 distinct categories | 0 | Original CSV |

### Secondary and Derived Variables

| Column | Data Type | Units | Meaning | Range / Allowed Values | Missing Values | Origin |
|---|---|---|---|---|---|---|
| `GPA_Change` | Float | GPA points | Change in GPA from before to after the semester | `Post_Semester_GPA - Pre_Semester_GPA`; exact observed range to be verified | None expected when both input GPAs are present | Derived from Dataset 2 |
| `Study_Hours_Group` | Category, if created | Hours/week group | Groups students according to traditional study hours for comparison | Categories and cutoffs must match the analysis notebook | Depends on source variable and transformation | Derived variable, only if present in the analysis |

## 4. Reproducibility Recipe


### Raw Data Sources

The project includes two primary datasets stored in the repository:

data/student_ai_tool_usage_dataset.csv — survey responses about students’ AI tool usage, purposes, and satisfaction.

data/ai_student_impact_dataset (1).csv — student records containing AI usage, study hours, GPA, and related measures.

The original external sources, collection methods, and licensing terms should be verified using the dataset source documentation. The files alone do not establish whether the data are observational, synthetic, or collected through a particular sampling method.

### Download Instructions

Clone the project repository from GitHub.

Open the project directory in VS Code.

Confirm that both primary CSV files are present in the data/ directory.

Use the analysis notebook and project documentation to reproduce the reported data preparation and analysis.

### Data Cleaning

For the student AI tool usage dataset, the documented cleaning steps include standardizing inconsistent capitalization in tool names and purposes, converting interpretable usage-hour responses into a consistent format, and setting 11 ambiguous usage-hour responses and 34 inconsistent academic-performance responses to missing values. Ten comments are missing in the raw dataset.

The AI student impact dataset contains 50,000 rows and 16 columns. The initial inspection found no missing values. The project documentation reports no duplicate records; this should be confirmed by rerunning the notebook's duplicate checks.

### Data Transformations

The analysis derives GPA change by subtracting pre-semester GPA from post-semester GPA:

GPA_Change = Post_Semester_GPA - Pre_Semester_GPA

Any additional grouping, category standardization, or variable conversion should follow the transformations implemented in EDA.ipynb. The codebook should be updated if the analysis creates additional derived variables.

### Dataset Joins and Match Counts

The two primary datasets have different structures and sample sizes. No join between them is assumed for the reported analysis. If a join is introduced, document the matching keys, records before and after joining, unmatched records, and duplicate-key handling.

### Final Analysis Dataframe

The final analysis dataframes are produced by the cleaning and transformation steps in EDA.ipynb. The first dataset begins with 200 survey responses; the second begins with 50,000 student records. The exact final row counts and columns should be confirmed by rerunning the notebook after cleaning and any filtering.

## 5. Data Access and Reuse

### FAIR Principles

Findable: The datasets are stored in the project's GitHub repository under the data/ directory. Descriptive filenames and this datasheet help identify their contents.

Accessible: The CSV files and analysis materials are available through the repository to users who can access it. Continued access depends on the repository's availability and any applicable data restrictions.

Interoperable: Both primary datasets use CSV format, which can be read by common data-analysis tools, including Python and pandas. Consistent variable names, documented data types, and the codebook help users interpret the data.

Reusable: This datasheet, the codebook, and EDA.ipynb document the variables and analysis workflow. Reuse also depends on confirming the datasets' original sources, licenses, and any applicable privacy restrictions.

### Dataset Sources and Licenses

The primary dataset files are included in the project repository:

data/student_ai_tool_usage_dataset.csv

data/ai_student_impact_dataset (1).csv

The original publishers, source URLs, and license terms have not yet been verified from the information currently documented in the project. Their provenance and permissions should be confirmed before redistributing the files or using them beyond the course project. The presence of a file in a public repository does not, by itself, establish permission for unrestricted reuse.


### Processed Data Reuse Permissions

The cleaned data and derived variables are used for this CS 418 course project. Before sharing processed data outside the project, users should verify the original datasets' licenses and any applicable terms of use. Cleaning and analysis steps should remain documented in EDA.ipynb and DATASHEET.md so that others can understand how the processed data were produced.

## 6. Representation and Ethics

### Student Representation

The primary datasets describe student AI usage, academic performance, study habits, and related experiences. Dataset 1 contains 200 survey responses, while Dataset 2 contains 50,000 student records. The available files do not establish whether either dataset represents the broader student population. Results should therefore be interpreted as patterns in these datasets rather than universal conclusions about students.

### Missing or Underrepresented Groups

The datasets do not provide enough verified information to determine which student groups may be missing or underrepresented. Dataset 1 contains missing comments and inconsistent responses about academic performance and usage hours. Dataset 2 contains several student-related categories, but the original sampling process and population coverage have not been verified. Students from institutions, backgrounds, or educational settings not represented in the data may have different experiences.

### CARE Principles

The CARE Principles—Collective Benefit, Authority to Control, Responsibility, and Ethics—emphasize responsible data governance, especially when working with data about people and communities.

For this project, the team should document data provenance, respect any original collection terms, avoid unsupported claims about individual students, and ensure that conclusions are appropriately limited. The available documentation does not establish whether the datasets were collected with informed consent or whether participants had control over subsequent reuse; these details should be verified with the original sources.

### Ethical Limitations

The project examines associations between AI use, traditional study habits, satisfaction, and academic outcomes. Observational data cannot establish that AI use caused a change in academic performance. Self-reported answers may contain recall errors, inconsistent wording, or subjective judgments. The datasets may also contain sampling bias or other unmeasured confounding factors.

The team should avoid identifying individual students, making unsupported claims about specific groups, or treating the results as proof that AI use is universally beneficial or harmful. Findings should be reported with appropriate uncertainty, and the original datasets' privacy conditions and reuse permissions should be checked before sharing data outside the course project.
