---

---
Descriptions:
	A Job Portal Website made with  Expressjs applications where 
	recruiters can CRUD jobs, RD applicants for job
	applicants can apply for jobs, upload resume on job post, see job postings

features:
- Register/Login for Recruiter/Applicant
- (Recruiter) CRUD Jobs
- (Recruiter) RD Applicants in a posted job
- (Applicant) upload Resume
- (Recruiter) Session based authentication 
- (Applicant) Send confirmation mail after applying
- Use Cookies to save LastVisit
- Middlewares for form validations

Requirements:
- express
- mutler
- express-session
- express-validator
- nodemailer
- cookies-parser
- express-ejs-layouts

Steps:
- npm init
- set-up basic server. js
- set-up (get/post/put/delete) routes
- set-up views
- add middlewares
- let the data flow