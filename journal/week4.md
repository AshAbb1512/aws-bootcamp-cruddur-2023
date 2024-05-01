Week 4 — Postgres and RDS
Quick Links

Weekly Summary
Key Takeaways
Required Homework
Weekly Outcome
Be able to data model using 3rd normal forms
Practical working knowledge of utilizing a Postgres database
Basic knowledge of working with an Online Analytical Processing (OLAP)
Weekly Summary
Reflection
I really liked using the coloring for the terminal print statements. I'm going to use that in the future for readability. Postgres wasn't that different from what I remember using sqlite, so the concepts weren't that difficult for me.

Challenges
Connecting to the RDS was somewhat challenging, but I figured it out quickly enough. I wasn't able to connect at first because I didn't create the inbound security group rule for postgres.

Knowledge Transfer
Key Takeaways
Creating a Database:

explicitly set both the character set and the timezone
Questions
Q. How do SQL injections work and how do sanitized SQL statements help?

Required Homework
Added precompiled psycopg2 lambda layer for my region.

arn:aws:lambda:us-west-2:898466741470:layer:psycopg2-py38:1
Connect to RDS
Connection from Gitpod to RDS

Register Cognito User Into Database
User in Postgres Database
