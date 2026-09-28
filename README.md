# cs418-learning-without-ai
Group Name: Learning With(out) AI  
Group Members: Sneha Sharma, Honey Patel, Mahi Patel

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

2. **[CS 418 Pre-Curated Course Performance Dataset](https://dodatascience.fun/datasets/)**
   * **Source / Link:** CS 418 Course Datasets
   * **Join / Comparison Plan:** We will use historical course grade distributions to establish a pre-AI baseline for student performance across STEM majors.



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
