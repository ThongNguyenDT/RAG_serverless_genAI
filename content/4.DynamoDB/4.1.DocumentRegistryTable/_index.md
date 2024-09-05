---
title: "Configure Document Registry Table"
date :  "`r Sys.Date()`" 
weight : 1
chapter : false
pre : " <b> 4.1. </b> "
---

### Step 3: Configure Document Registry Table

- **Name the Table:** Choose an appropriate name for the table.
- **Partition key:** Select `md5`.
- **Sort key:** Select `s3_path`.
- **Custom Index:** Choose the custom option to add an index.

![Untitled](/images/DynamoDB%207bb0aac147b1441cbce819e31ceff35d/Untitled%201.png)

- **Set Up Global Index:** Configure a global index for the **s3_path** column.

![Untitled](/images/DynamoDB%207bb0aac147b1441cbce819e31ceff35d/Untitled%202.png)

- Click **Create Table** to finish.

![Untitled](/images/DynamoDB%207bb0aac147b1441cbce819e31ceff35d/Untitled%203.png)

After creation, you will see the table configured as follows:

![Untitled](/images/DynamoDB%207bb0aac147b1441cbce819e31ceff35d/Untitled%204.png)