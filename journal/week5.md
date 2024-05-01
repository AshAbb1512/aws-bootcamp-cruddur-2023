Week 5 — DynamoDB and Serverless Caching
Quick Links

Weekly Summary
Key Takeaways
Required Homework
Weekly Outcome
Be able to data model using single table design
Basic knowledge of working with a cloud SDK
Basic implementation of read-aside cache in front of a database
Interact with a production NoSQL database
Basic knowledge of working with an OLTP
Weekly Summary
Reflection
I thought the content about DynamoDB was really interesting. I enjoyed the concepts and learning about how to do data modelling for dynamodb. There's so much to information there that I'm not really sure how to summarize it, but I think I understand the basics.

Challenges
This week I was ready to throw my computer out the window getting the dynamodb seed to run properly through the local postgres connection. In a final attempt after trying several things on stackoverflow, I decided to change localhost to 127.0.0.1 in the postgres connection url and it worked. I can't say I'm happy about it, but at least it works now.

dynamodb seed error in postgres

dynamodb seed working after postgres url change

I couldn't get my backend to find the boto3 module without running pip install -r requirements.txt from the development environment first. But it showed up as installing in the build logs in docker compose. I searched through stackoverflow to see if I had done it incorrectly and tried to install the requirements using the --user flag and also specifying python3 / pip3. It didn't work so I was starting to look into using Poetry pyproject.toml for managing dependencies in the multi-stage build. After a couple hours I decided that I should take the L and just manually run pip install -r requirements.txt from the development environment every time until I learn more about building python docker images and have more time. I should probably focus on the actual content of the course, but the dependency management offered by Poetry looks interesting and I've seen it elsewhere, so I'll have to look more into that later.

Another problem I had was having new messages add to the existing message group. It would throw no errors because it was posting to a new message group. Changing the seed data so the seeded messages were from the past instead of showing up as a created at date in the future (incorrect timestamps) fixed the issue.

Also the token expiring for my user made it a bit difficult when I thought something wasn't working, but it was. I have to more carefully read the backend logs to find the line if the token had expired.

Knowledge Transfer
Key Takeaways
The primary key can be a single or composite key. The composite key is formed of a partition key (pk) and a sort key (sk).
The items within the PK/SK don't have to follow the same data format/type as the other items in their field. Such as strings, uuids, numbers, etc. e.g) you can store message group ids 'GRP#message_group_uuid' and message ids 'MSG#message_uuid' in the partition key.
Local Secondary Indexes must be created at the time of database creation.
It's important to know what data you are accessing and how you want it returned before implementing patterns and tables in Dynamodb.
Consider which data will be accessed most frequently when designing your data model.
Sometimes storing json in a field in a NoSQL database and accessing that is faster than building that data from a query.
