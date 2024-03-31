# Week 0 — Billing and Architecture
## Conceptual Archetictural Diagram
![image](https://github.com/Ash01512/aws-bootcamp-cruddur-2023/assets/159699976/43376c37-8fe2-41e6-a9f3-dde3f3bc2be5)
## Logical Diagram
## I created this logical diagram through Lucidchart
![image of the Logical Diagram](https://github.com/Ash01512/aws-bootcamp-cruddur-2023/assets/159699976/ce270818-8de2-4c4e-a0ca-bcbc1674d035) or ![Image of Logical diagram using Amazon ElastiCache](Assets/Logical%20diagram%20(using%20aws%20new%20serverless%20cache%20service%20aws%20ElastiCache).png)
[Lucid Charts Shared Link](https://lucid.app/lucidchart/fe68fd0e-6952-45eb-9b03-0f113d338626/edit?viewport_loc=-641%2C-176%2C3517%2C1627%2C0_0&invitationId=inv_309329e2-5c96-4814-9f05-129cd182aa33)
### AWS CLI, creating a budget and billing alarm
Project included creating an admin user and AWS credentials, as well as installing AWS CLI on Gitpod.

The budget was created through AWS CLI on Gitpod based on the budget and budget notifications JSON-files on the AWS/JSON-folder. There is also a JSON file for the billing alarm. It required first a new SNS topic for which the subscription had to be confirmed via email. After that, the actual Cloudwatch alarm could be created through AWS CLI.

### Create a Budget Alarm
I created my own Budget for $1 because I was concerned of budget spending going over the 2 Budget free limit.

![Image of the Budget Alarm I created](Assets/Budget.jpg)

