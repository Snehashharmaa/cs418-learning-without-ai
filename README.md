# cs418-learning-without-ai
Group Name: Learning With(out) AI  
Group Members: Sneha Sharma, Honey Patel, Mahi Patel, Viet Ho

## 1. Group Research Questions

* **Primary Question:** How does student reliance on Generative AI tools (e.g., weekly usage hours and tool diversity) correlate with changes in academic performance (pre-semester vs. post-semester GPA)?
* **Secondary Question:** Do specific types of AI tasks (e.g., coding vs. writing vs. brainstorming) lead to higher user satisfaction and session completion rates compared to traditional study habits?



## 2. Primary Datasets

1. **[Student AI Tool Usage Dataset](https://www.kaggle.com/datasets/zohairbaloch/student-ai-tool-usage-dataset)**
   * **Source / Link:** Kaggle Open Datasets
   * **Description:** Survey data detailing student AI tool choices, weekly usage hours, purpose of use, academic performance categories, and satisfaction levels.

2. **[AI Impact on Students Dataset](https://www.kaggle.com/datasets/laveshjadon/ai-impact-on-students)**
   * **Source / Link:** Kaggle Open Datasets
   * **Description:** Comprehensive records tracking student GPAs, Generative AI usage hours, study habits, prompt engineering proficiency, and perceived dependency across 50,000 students.

---

## 3. Secondary Datasets

1. **[AI Assistant Usage in Student Life](https://www.kaggle.com/datasets/ayeshasal89/ai-assistant-usage-in-student-life-synthetic)**
   * **Source / Link:** Kaggle Open Datasets
   * **Join / Comparison Plan:** We will analyze session-level granular details (prompt counts, session lengths, task types) to compare interaction complexity against the high-level GPA outcomes in our primary datasets.

2. ### Secondary Dataset 2: Higher Education Students Performance

**Source:** UCI Machine Learning Repository – Higher Education Students Performance Evaluation(https://archive.ics.uci.edu/dataset/856/higher+education+students+performance+evaluation?utm_source=chatgpt.com)

**Dataset:** data/higher_education_students_performance.csv

**Purpose:** This dataset provides student-level information about higher education students' characteristics, course-related responses, and academic performance. It will be used as a traditional academic-performance comparison dataset alongside the AI-focused datasets.

**Row meaning:** Each row represents one student enrolled in a course.

**Key columns:**
- `STUDENT ID` – unique identifier for each student
- `1`–`30` – questionnaire/feature variables describing student responses
- `COURSE ID` – course identifier
- `GRADE` – student's course grade

**How it supports our research:** This dataset provides a non-AI-focused student performance dataset that can be used to examine relationships between student characteristics/study-related factors and academic performance. We can compare its academic-performance patterns with the AI-focused datasets without assuming that the datasets contain identical variables.



## 4. Data Confirmation & Verification

All datasets have been successfully downloaded, loaded into Python pandas DataFrames, and verified via `data_acquisition.ipynb`.


## 5. Dataset Shapes & Characteristics

### Primary Dataset 1: Student AI Tool Usage
* **Rows:** 200
* **Columns:** 8
* **Unit of Observation:** A single student's survey response regarding AI tool habits.
* **Key Columns & Types:**
  * `ai_tool_used` (`object`): Name of the AI tool used (e.g., ChatGPT, Copilot).
  * `usage_hours_per_week` (`object`): Categorical range of weekly hours spent using AI tools.
  * `purpose` (`object`): Intended task (e.g., studying, coding, writing, research).
  * `satisfaction_level` (`int64`): Student satisfaction score.
  * `academic_performance` (`object`): Self-reported academic outcome category.
* **Temporal & Geographic Coverage:** Higher education student survey respondents.

### Primary Dataset 2: AI Student Impact
* **Rows:** 50,000
* **Columns:** 16
* **Unit of Observation:** An individual student's academic profile and AI interaction metrics.
* **Key Columns & Types:**
  * `Student_ID` (`int64`): Unique student identifier.
  * `Pre_Semester_GPA` (`float64`): Student GPA at the start of the semester.
  * `Weekly_GenAI_Hours` (`float64`): Average weekly hours spent using Generative AI.
  * `Primary_Use_Case` (`object`): Main function (Copywriting, Summarizing, Debugging, Ideation).
  * `Prompt_Engineering_Skill` (`object`): Self-assessed skill level (Beginner, Intermediate, Advanced).
  * `SatisfactionRating` (`float64`): Overall satisfaction rating.
* **Temporal & Geographic Coverage:** Multi-major academic evaluation tracking 50,000 university students.

### Secondary Dataset 1: AI Assistant Usage in Student Life
* **Rows:** 10,000
* **Columns:** 11
* **Unit of Observation:** A single student AI interaction session.
* **Key Columns & Types:**
  * `SessionID` (`object`): Unique identifier for the interaction session.
  * `SessionLengthMin` (`float64` / `int64`): Duration of session in minutes.
  * `TotalPrompts` (`int64`): Count of prompts sent during the session.
  * `TaskType` (`object`): Category of task (Coding, Writing, Studying).
* **Temporal & Geographic Coverage:** Synthetic interaction logs across high school, undergraduate, and graduate levels.
  
## Secondary Dataset 2: Higher Education Students Performance

**Shape:** 145 rows × 33 columns

### Data Types

| Column | Type |
|---|---|
| STUDENT ID | str |
| 1 – 30 | int64 |
| COURSE ID | int64 |
| GRADE | int64 |

### First 5 Rows

| | STUDENT ID | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | ... | 23 | 24 | 25 | 26 | 27 | 28 | 29 | 30 | COURSE ID | GRADE |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| 0 | STUDENT1 | 2 | 2 | 3 | 3 | 1 | 2 | 2 | 1 | 1 | ... | 1 | 1 | 3 | 2 | 1 | 2 | 1 | 1 | 1 | 1 |
| 1 | STUDENT2 | 2 | 2 | 3 | 3 | 1 | 2 | 2 | 1 | 1 | ... | 1 | 1 | 3 | 2 | 3 | 2 | 2 | 3 | 1 | 1 |
| 2 | STUDENT3 | 2 | 2 | 2 | 3 | 2 | 2 | 2 | 2 | 4 | ... | 1 | 1 | 2 | 2 | 1 | 1 | 2 | 2 | 1 | 1 |
| 3 | STUDENT4 | 1 | 1 | 1 | 3 | 1 | 2 | 1 | 2 | 1 | ... | 1 | 2 | 3 | 2 | 2 | 1 | 3 | 2 | 1 | 1 |
| 4 | STUDENT5 | 2 | 2 | 1 | 3 | 2 | 2 | 1 | 3 | 1 | ... | 2 | 1 | 2 | 2 | 2 | 1 | 2 | 2 | 1 | 1 |

*Pandas truncated columns 10–22 in the preview.*


 
## 6. Processing and Reproducibility
 
### 6.1 What the publishers did
Neither Kaggle dataset documents how it was collected or cleaned (that we could find), and raw data such as original form responses is not available for either. We only have the published CSV files.
 
| Dataset | Publisher cleaning | Raw data available? |
|---|---|---|
| Student AI Tool Usage | Not documented. The raw file had inconsistent capitalization, mixed formats for usage hours and academic performance, and 10 missing comments. | No, only the CSV |
| AI Student Impact | Not documented. The raw file has no missing values and no duplicate student IDs. | No, only the CSV |
| AI Assistant Usage in Student Life | Synthetic data, so there was no collection from people | No raw logs |
| Higher Education Students Performance | Answers are integer-coded; UCI reports no missing values | No, only the coded table |
 
**Dataset 1 size:** A third-party analysis reports 230 raw entries for this dataset, but our file has 200 rows. We do not know whether the uploader or a different version explains this. 
 
**Dataset 2 origin:** Whether its records are observed or synthetic is not documented in the sources we found. We therefore interpret results as patterns in this dataset, not as findings about students in general.
 
### 6.2 Our processing steps (in `EDA.ipynb`)
 
**Student AI Tool Usage**
 
| Step | What we did | Result |
|---|---|---|
| 1 | Inspected columns, types, unique values, and missing values | 200 rows, 8 columns; 10 missing `comments` in the raw file |
| 2 | Standardized capitalization and spelling of `ai_tool_used` (e.g., chatgpt vs. ChatGPT, ClaudeAi vs. claude) and `purpose` (e.g., study vs. Study) | 34 rows affected in each column; 11 raw tool values and 7 raw purpose values before standardizing |
| 3 | Converted interpretable text entries in `usage_hours_per_week` (stored as text, e.g., "4 hours") to numeric hours | 19 rows were stored as text; 8 corrected |
| 4 | Set the remaining uninterpretable `usage_hours_per_week` entries to missing | 11 set to missing (the other 11 of the 19 text rows) |
| 5 | Set inconsistent `academic_performance` responses to missing instead of treating different formats as equivalent (answers mixed numbers and words, e.g., 75, Good, Yes) | 34 set to missing |
| 6 | Kept missing comments as missing | 10 missing, nothing invented |
 
**Final size:** 200 rows. Cleaning changed or blanked cell values only, and no rows were removed. (Confirm with `df.shape` in the cleaned dataframe.)
 
**AI Student Impact**
 
| Step | What we did | Result |
|---|---|---|
| 1 | Inspected columns, types, and missing values | 50,000 rows, 16 columns, no missing values |
| 2 | Checked for duplicate records and duplicate `Student_ID` | No duplicates |
| 3 | Created `GPA_Change = Post_Semester_GPA - Pre_Semester_GPA` | Positive means GPA increased; negative means it decreased |
 
**Final size:** 50,000 rows and 17 columns (the 16 originals plus `GPA_Change`). No rows were filtered out. (Confirm with `df.shape`.)
 
**Joins:** The primary datasets have different structures and no shared identifier, so we do **not** join them. Each question uses one dataset (RQ1: AI Student Impact; RQ2: Student AI Tool Usage). Secondary datasets are compared at the group level only.
 
### 6.3 How to reproduce
 
```bash
# 1. Get the project
git clone <(git@github.com:Snehashharmaa/cs418-learning-without-ai.git)>
cd <repository folder>
 
# 2. Install requirements (Python TODO: version)
pip install -r requirements.txt        # TODO: create with: pip freeze > requirements.txt
 
# 3. Confirm the CSV files are in data/
ls data/
 
# 4. (Optional) re-download the originals from Kaggle (free account + API token needed)
kaggle datasets download -d zohairbaloch/student-ai-tool-usage-dataset -p data/ --unzip
kaggle datasets download -d laveshjadon/ai-impact-on-students -p data/ --unzip
kaggle datasets download -d ayeshasal89/ai-assistant-usage-in-student-life-synthetic -p data/ --unzip
 
# 5. Check the files are the same as ours
sha256sum data/*.csv                   # Windows PowerShell: Get-FileHash data\*.csv
 
# 6. Open and run EDA.ipynb from top to bottom

```
 
## 7. Access and Reuse (FAIR)
 
| Dataset | Persistent link | Version / date accessed | Format | License / terms |
|---|---|---|---|---|
| Student AI Tool Usage | https://www.kaggle.com/datasets/zohairbaloch/student-ai-tool-usage-dataset (URL only, no DOI) |  | CSV |  |
| AI Student Impact | https://www.kaggle.com/datasets/laveshjadon/ai-impact-on-students (URL only, no DOI) | Kaggle version 1;  | CSV | A third-party mirror lists "Other";  |
| AI Assistant Usage in Student Life (secondary) | https://www.kaggle.com/datasets/ayeshasal89/ai-assistant-usage-in-student-life-synthetic (URL only) | | CSV | |
| Higher Education Students Performance (secondary) | https://doi.org/10.24432/C51G82 | UCI page checked 2026-10-28; | CSV | CC BY 4.0 |
 
- **Findable:** Only the UCI dataset has a DOI. The Kaggle datasets are identified by URL, which can change or be removed, so we record the access date and checksums. Our repository copy is not a permanent identifier. *Optional:* archive a release of the repository on Zenodo to get a DOI for our code and documentation.
- **Accessible:** UCI is an open download. Kaggle needs a free login or API token. Our own files are available through the repository to whoever can open it.
- **Interoperable:** All files are CSV and load directly into pandas. Column names, types, units, and allowed values are in the codebook in `DATASHEET.md`. The Kaggle datasets use free-form categories rather than a standard vocabulary.
- **Reusable:** Reuse depends on the licenses above. We document provenance, every cleaning step, and the checks above so others can repeat the analysis and see what we changed.
 
### Licenses and reuse of our processed data
 
| What | License | Notes |
|---|---|---|
| Our code and notebooks | MIT  |  |
| Our documentation (README, datasheet) | | |
| Kaggle datasets and our processed copies | Source license applies |  |
| UCI dataset and processed copies |  | Credit Yilmaz & Şekeroğlu (2019) and say that we changed the data |
 
**Rule for the Kaggle data:** We have not confirmed that any Kaggle license allows redistribution. A license that is "Other", unclear, or missing is treated as all rights reserved. Until it is confirmed, the CSV files in this repository are for course evaluation only and must not be redistributed, and **our processed (cleaned) data is not offered for reuse**. Our code, documentation, and download instructions can be reused, and anyone can regenerate the processed data by downloading the originals and running `EDA.ipynb`. 
 
## 8. People in the Data and CARE
 
### Who is in the data
* **Student AI Tool Usage:** 200 students who answered a survey about AI tools. Recruitment method, dates, institution, and demographics are not documented. The file has `student_id`, `timestamp`, and optional free-text comments.
* **AI Student Impact:** 50,000 student records across five major categories and five years of study, with GPA, study habits, exam anxiety, and burnout risk. Country, institution, gender, and how the records were produced are not documented.
* **Secondary datasets:** The AI Assistant dataset is synthetic and contains no real people. The UCI data covers 145 students from two faculties in 2019.
 
### Who could be (mis)represented
* Students who do not use AI, or use it rarely, who are needed for the "without AI" side of the comparison.
* Students without reliable devices, internet, or paid subscriptions.
* Students at other institutions, in other countries or education systems, and students outside higher education.
* Students whose GPA is a weaker measure of their learning (different grading systems, disabilities).
* Small groups (particular majors, years, or tools) that cannot support separate analysis.
 
### CARE principles
* **Collective benefit:** The project aims to help students and instructors understand how AI use relates to learning. We avoid presenting results in ways that serve tool vendors or support punishing students.
* **Authority to control:** We found no statement on consent or on participants' control over reuse for either primary dataset. We use the data only within this course project, do not try to re-identify anyone, and treat this as a limitation.
* **Responsibility:** We document provenance and each processing step, report associations only, state the limits of the data, and credit the sources. Before quoting `comments`, we check that they contain no personal details. 
* **Ethics:** We do not label students as "cheaters" or "dependent," do not report results for very small groups, and treat anxiety, burnout, and dependency variables as sensitive.