# Exploring AWS Services Lab - Solution

**Student Name:** Anderson   
**Date Completed:** 20/04/206

---

## Exercise 1: Console Navigation

### Part A: Service Discovery

**EC2 (Compute):**
- Purpose: Is a service that lets you create virtual servers in the cloud instead of using physical computer
- Screenshot: ![EC2 Dashboard](screenshots/console-navigation/ec2-dashboard.png)

**S3 (Storage):**
- Purpose: its a service that stora files like images, videos  and data from anywhere for static websites or store backups.
- Screenshot: ![S3 Dashboard](screenshots/console-navigation/s3-dashboard.png)

**RDS (Database):**
- Purpose: Its used to store and organize application data.
- Screenshot: ![RDS Dashboard](screenshots/console-navigation/rds-dashboard.png)

**VPC (Networking):**
- Purpose: Is used to create a private network inside AWS where you can securely run resources.
- Screenshot: ![VPC Dashboard](screenshots/console-navigation/vpc-dashboard.png)

**IAM (Security):**
- Purpose: Is a service to control who can acces your AWS resources and what are they allowed to do.
- Screenshot: ![IAM Dashboard](screenshots/console-navigation/iam-dashboard.png)

### Part B: Console Features

**Lambda Category:** Compute category

**Pinned Services:**
![S3 Pinned](screenshots/console-navigation/s3-pinned.png)

**Recently Visited:**
![Recently Visited](screenshots/console-navigation/recently-visited.png)

**Region Selector:**
![Region Changed](screenshots/console-navigation/region-selector.png)
- Original region: us-east-1
- Changed to: eu-south-2
- Changed back: Yes

---

## Exercise 2: Service Categorization

### Completed Service Matrix:

| Category | Services | Primary Use Case |
|----------|----------|------------------|
| Compute | [List 3-5 services] | [Use cases] |
| Storage | [List 3-5 services] | [Use cases] |
| Database | [List 3-5 services] | [Use cases] |
| Networking | [List 3-5 services] | [Use cases] |
| Security | [List 3-5 services] | [Use cases] |
| Management | [List 3-5 services] | [Use cases] |

### Research Question Answers:

**1. What's the difference between EC2 and Lambda?**

EC2 is like a server you manage online that is running all the time until you stop it and Lambda runs code without managing a server.

---

**2. When would you use S3 vs EBS?**

S3 is for store files not tied to a single server and EBS is attached to a server to run apliccations that need low latency storage

---

**3. What's the difference between RDS and DynamoDB?**
rds is a sql database with a structure dynamo is nosql and more simple


---

**4. Why do you need a VPC?**

To create a secure and isolated network in amazon aws.

---

**5. What does CloudWatch monitor?**

Monitors resources in aws and alert you if something exceed the limits you put or if something goes wrong.

---

## Exercise 3: AWS CLI

### CLI Version:
```
aws-cli/2.34.25 Python/3.14.3 Windows/11 exe/AMD64```

### Configuration:
```
NAME       : VALUE                    : TYPE             : LOCATION
profile    : <not set>                : None             : None
access_key : ****************     : shared-credentials-file :
secret_key : ****************     : shared-credentials-file :
region     : eu-west-1                : config-file      : ~/.aws/config
PS C:\Users\dieci\ce-lab-exploring-aws-services\ce-lab-exploring-aws-services>```

### CLI Outputs:

See attached `cli-outputs.txt` file for all command outputs.

**Key findings:**
- My AWS Account ID: [account-id]
- Default region: [region]
- Number of regions available: [number]

---

## Exercise 4: Pricing Research

### Pricing Worksheet:
aws sts get-caller-identity
{
    "UserId": "AIDARPJHLATRIP4LIQOTA",
    "Account": "101551113442",
    "Arn": "arn:aws:iam::101551113442:user/Dieciocho"
}

PS C:\Users\dieci>
 aws ec2 describe-regions --output table
-------------------------------------------------------
|                   DescribeRegions                   |
+-----------------------------------------------------+
||                      Regions                      ||
|+---------------+-----------------------------------+|
||  Endpoint     |  ec2.ap-south-1.amazonaws.com     ||
||  OptInStatus  |  opt-in-not-required              ||
||  RegionName   |  ap-south-1                       ||
|+---------------+-----------------------------------+|
|||                    Geography                    |||
||+----------------------+--------------------------+||
|||  Name                |  India                   |||
||+----------------------+--------------------------+||
||                      Regions                      ||
|+---------------+-----------------------------------+|
||  Endpoint     |  ec2.eu-north-1.amazonaws.com     ||
||  OptInStatus  |  opt-in-not-required              ||
||  RegionName   |  eu-north-1                       ||
|+---------------+-----------------------------------+|
|||                    Geography                    |||
||+---------------------+---------------------------+||
|||  Name               |  Sweden                   |||
||+---------------------+---------------------------+||
||                      Regions                      ||
|+---------------+-----------------------------------+|
||  Endpoint     |  ec2.eu-west-3.amazonaws.com      ||
||  OptInStatus  |  opt-in-not-required              ||

 aws configure get region
eu-west-1
 aws s3 ls
PS C:\Users\dieci> EMPTY
**1. EC2 t3.micro (Linux, us-east-1):**
- On-Demand: $0.0104 per hour
- Monthly (730 hours): $8.04
- Free Tier eligible: Yes
- Free Tier details: 750hours/month

**2. S3 Standard Storage:**
- 100 GB monthly cost: $2.30
- Free Tier: First 5 GB free for 12 months
- Cost per GB: $0.023

**3. RDS db.t3.micro (MySQL):**
- Monthly cost: $1.90
- Storage (20 GB): $0.95
- Total: $1.90
- Free Tier eligible: Yes

**4. Data Transfer OUT:**
- 100 GB cost: $9
- First 100GB free per month

### AWS Pricing Calculator Estimate:

![Pricing Calculator](screenshots/pricing-calculator.png)

**Estimate Link:** https://us-east-1.console.aws.amazon.com/costmanagement/home?region=us-east-1#/pricing-calculator/saved-estimates/workload-estimate/0d420281-9b57-469f-849f-4f8e868f554d/ec2t3micro

**Total Estimated Monthly Cost:** $21.23

---

## Exercise 5: Documentation Hunt

### EC2 Instance Types:
- Documentation URL: https://aws.amazon.com/ec2/instance-types/
- t3.medium vCPUs: 2
- t3.medium memory: 4 GB

### S3 Storage Classes:
- Documentation URL: https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html?utm_source=chatgpt.com
- All storage classes:
S3 Standard
S3 Intelligent-Tiering
S3 Standard-IA (Infrequent Access)
S3 One Zone-IA
S3 Glacier Instant Retrieval
S3 Glacier Flexible Retrieval
S3 Glacier Deep Archive
S3 Express One Zone
 
- Cheapest for archive: Glacier deep archive

### IAM Best Practices:
- Documentation URL: https://docs.aws.amazon.com/IAM/latest/UserGuide/best-practices.html
- Three best practices:
Give only the permissions users need)
Enable multi factor authentication MFA 
Use roles instead of long term access keys
 

### Free Tier Limits:
- Documentation URL: https://aws.amazon.com/free/
- EC2 t2.micro hours/month: 750h
- S3 storage free: 5GB

---

## Exercise 6: Regions and Availability Zones

### Your Current Region:
- Region Name: eu-north-1 Estocolmo
- Region Code:  eu-north-1
- Number of AZs: 3

### Concept Questions:

**What is the difference between a Region and an Availability Zone?**
A region contains multiple data center and availability zone is an insolated data center hith high availability


---

**Why does AWS have multiple regions?**
To reduce latency meet data residency or legalal requirments

---

**How many Availability Zones does each region typically have?**

3 or more

---

**Can you deploy resources in multiple regions simultaneously?**

Yes

---

### Region Selection Analysis:

| Scenario | Best Region | Reasoning |
|----------|-------------|-----------|
| Serving users primarily in Europe | eu-west-1 | [servers close to europe and reduce latency |
| Lowest cost for non-critical workloads | us-east-1 | the most commonly used and usually cheapest regions |
| GDPR compliance required | eu-west-1 | [an European Region helps ensure compliance with data protection laws |
| Serving users in Asia-Pacific | ap-southeast-1 | it places your resources close to users in Asia |
| Need newest AWS services | ap-south-1 | newer Regions are usually the first to get latest AWS services and features |

---

## Bonus Challenges

### Challenge 1: Cost Estimate

**Architecture:**
- 1x t3.medium EC2 (24/7)
- 1x db.t3.micro RDS (24/7)
- 50 GB S3
- 100 GB data transfer

**Estimated Monthly Cost:** $______

**Calculator Link:** [URL]

---

### Challenge 2: Service Comparison

| AWS | Azure | GCP |
|-----|-------|-----|
| EC2 | [Azure service] | [GCP service] |
| S3 | [Azure service] | [GCP service] |
| RDS | [Azure service] | [GCP service] |
| Lambda | [Azure service] | [GCP service] |

---

### Challenge 3: CLI Advanced

[Paste outputs of advanced commands here]

---

## Reflection

**What surprised you most about AWS services?**

The cheap they are for the things it offers 

---

**Which AWS service are you most excited to learn about?**

About the cost of the servicies

---

**How comfortable do you feel navigating the AWS Console now?**

7 Because i learned a lot but there are still a lot of more servicies

---

## Checklist

- [ ] All service dashboards visited and documented
- [ ] All CLI commands executed successfully
- [ ] All pricing research completed
- [ ] All documentation URLs found
- [ ] Region analysis completed
- [ ] All screenshots captured
- [ ] All questions answered
- [ ] Work committed to Git
- [ ] Pull request created

---

**Completed By:** Anderson  
**Date:** 20/04/2026
