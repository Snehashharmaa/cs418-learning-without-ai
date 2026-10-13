Summary of Explore Data Analysis

The analysis aims to answer our question that asked how student reliance on AI tools, based on the data 
of weekly hours and tools diversity, relates to the change from pre-semester to post-semester GPA. At the 
same time, it also response our secondary question whether the type of AI tasks (including coding, writing,
brainstorm, research, other) relates to satisfactions.
We use two primary datasets:
    - Dataset 1 - Student AI Tool Usage: A 200 students survey one AI tool usage
    - Dataset 2 - AI Student Impact: A 50000 students dataset on AI's impact


The dataset 1 needed substantial cleaning. Free-text answer gave us inconsistent 
    - "tool names" (chatgpt vs ChatGPT, ClaudeAi vs claude) and "purposes" (study vs Study) (34 rows each)
    - usage hours were stored as text, such as 4 or 6 hours (19 rows, of which we fixed 8 and set 11 to missing)
    - academic performanance mixed numbers with words, for example: (75, Good, Yes) (34 rows set to missing)
The Datasert 2 was clean, with no missing values or dunplicates


In the dataset 1, 
    - ChatGPT was the most used tool: 64 students, about twice the average of the others
    - "study" was the top purposes: 80 students
    - the satisfaction was high,with 58.5% giveing a 4 or 5 
In the dataset 2,
    - AI use was strongly right-skewed: 90% use AI under 20 hours a week
    - students typplically used 3 tools
    - the average rose only mosestly: from 3.12 to 3.35, with the change centered near +0.2 and only 12%
      of students declining


Key findings:
    - Weekly GenAI hours vs GPA change (Dataset 2): No clear trend. The GPA change stays around the same small gain
      no matter how many hours students use AI. Heavy users are more spread out, with some big gains and some big drops.    
    - GPA change by tool diversity: GPA change looked nearly identical across students using 1 to 5 tools.
    - Correlation matrix (Dataset 2): Traditional study hours has the strongest link with GPA change. AI hours and tool 
      diversity are close to zero. Students who use AI more tend to study a little less the traditional way. Pre and post 
      GPA are strongly linked, which is expected.
    - Grade by weekly study hours (Secondary Dataset 2: Higher Education Students Performance): In this dataset 
      (students not focused on AI), more studying does not mean better grades. Students who study a little do about as well
      or better, and the groups who study the most are very small.

Limitations: 
Revised questions:
