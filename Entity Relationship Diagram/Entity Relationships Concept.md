![ER Diagram](er%20diagram.png)
What is an ER diagram?

An ER diagram is a picture of how your data is stored. Each box is a table in the database. Each line inside a box is a column (one piece of information). The lines between boxes show how tables are connected to each other.

Two short words you'll see everywhere:

PK means Primary Key. It is the unique ID number of each row. Like a roll number — no two students share one.
FK means Foreign Key. It is a column that holds the ID of a row in another table. This is how two tables get connected.

The boxes, one by one

USERS - This stores every person who can log in: admins, mentors, and students, all together in one table. Why one table? Because login, password, and email work the same way for everybody. There is a column called role that says which type of person it is. When someone logs in, the system checks this column and shows them the correct dashboard.

MENTOR_PROFILES - Extra information that only mentors have, like which department they belong to and what subject they teach. It has a user_id (FK) pointing back to the USERS table, which tells us which person this profile belongs to.

STUDENT_PROFILES - Extra information that only students have, like their batch and roll number. It has two FKs: user_id (which person this is) and mentor_id (which mentor is assigned to them). That mentor_id column is very important — this single column is what creates the whole mentor-student relationship in your project.

FEEDBACK_FORMS  Each row is one feedback form that the admin created. It stores the title, the description, and who made it. The status column says whether the form is still a draft or has been published for students to see.

COMPONENT_TYPES - This is a list of all the question styles available in your form builder: star rating, emoji scale, slider, tags, open text, and so on. The admin does not create these. They are added once when the system is set up, and the form builder just reads this list to show the options.

QUESTIONS - Each row is one question inside one form. It has form_id (which form this question belongs to) and component_type_id (which style of question it is — star rating, text box, etc.). The order_index column remembers the order of the questions, so question 1 always shows before question 2.

FEEDBACK_RESPONSES - Each row is one complete submission by one student. It does not store the actual answers. It only stores who submitted, which form, and when. Think of it as the cover page of a filled answer sheet.

ANSWERS - This is where the actual answers live. Each row is one answer to one question. So if a form has 5 questions and a student fills it, you get 1 row in FEEDBACK_RESPONSES and 5 rows in ANSWERS.

SENTIMENT_ANALYSIS - After a student submits feedback, the AI reads their written comments and decides whether the feedback is positive, negative, or neutral. It saves that result here: a score, a short summary, and a flag if the feedback looks serious and needs attention.

MENTORING_SESSIONS - Each row is one meeting between a mentor and a student. It stores the date and the notes the mentor wrote.

ACTION_ITEMS - The to-do list created in a meeting. For example "finish your resume" or "practice interview questions". The student can tick them off when done.

REPORTS - When an admin downloads a PDF or Excel report, this table remembers that it was created and where the file is saved.

NOTIFICATIONS - Messages shown in the bell icon, like "A new feedback form is available".
