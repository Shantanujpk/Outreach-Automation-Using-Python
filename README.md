# 📬 Automated Recruiter Email Outreach App

This Python-based automation script streamlines personalized outreach to recruiters for job applications. It reads recruiter details from an Excel file, dynamically generates custom emails with tailored content, and sends them with your resume as an attachment — all automatically every day at 10 AM EST using Windows Task Scheduler.
---

## 💡 Features

- 📊 Reads recruiter details from an Excel sheet
- ✍️ Auto-generates personalized emails using:
  - Company name and domain
  - Job role and Job ID
  - Recruiter name and job link
  - Tailored experience + project inserts
- 📎 Attaches your resume to each email
- 📧 Sends emails via your Gmail account (using App Passwords)
- 🗓️ Can be scheduled to run daily using `.bat` file and Task Scheduler
- 📓 Maintains a log of already contacted companies to avoid duplicates

---

## 📁 Folder Structure

Automation Email/
│
├── Script.py # Main email automation script
├── Recruitor_Details.xlsx # Excel file with recruiter/job info
├── Shantanu Jaipurkar.pdf # Resume file to attach
├── sent_log.csv # Log of sent emails
├── run_email.bat # Windows batch file for automation


---

## 📥 Excel File Format

Your Excel file should be named: `Recruitor_Details.xlsx`  
It must contain the following columns:

| Column Name     | Description                              |
|----------------|------------------------------------------|
| Company         | Name of the company                     |
| Recruiter_Name  | Full name of the recruiter              |
| Email           | Email address of the recruiter          |
| Role            | Job title you're applying for           |
| Job ID          | ID of the job posting                   |
| Company_Work    | Company's domain/area of work           |
| Location        | Job location                            |
| Link            | Direct job posting link (optional)      |
---
## ⚙️ Setup Instructions
1. **Install Required Libraries**
pip install pandas openpyxl
Enable Gmail App Passwords

Go to your Google Account → Security → 2-Step Verification → App Passwords
Generate one and use it in the script
Update Config in Script.py

EMAIL_ADDRESS = "your_email@gmail.com"
APP_PASSWORD = "your_generated_app_password"
Schedule Script to Run Daily

Use the provided run_email.bat file
Open Windows Task Scheduler → Create Basic Task → Trigger: Daily at 10 AM → Action: Start a program → Choose run_email.bat

🧠 How It Works
Checks the Excel file for new entries
Skips companies already emailed (using sent_log.csv)
For each new row:
Composes a professional, humanized email
Attaches the resume
Sends the email
Logs the job ID and company to prevent duplicate contact

Note: There are couple of future enhancements need to be done and also the task schedular is specifically for windows os


