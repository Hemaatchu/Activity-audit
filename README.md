## EXPERIMENT 4
## ASSET-ORIENTED RISK ASSESSMENT OF STORAGE ASSETS IN AWS AND AZURE
## Objective:
   To identify storage assets in AWS S3 and Microsoft Azure Blob Storage, identify possible vulnerabilities and threats, and assess their likelihood, impact, and risk level.

## 1. Software / Cloud Services Required
•	AWS Account 
•	Microsoft Azure Account 
•	Web Browser 
•	Internet Connection
## Cloud Services Used
## Cloud Platform	Storage Service
AWS	Amazon S3
Microsoft Azure	Azure Blob Storage
PART A — AWS S3 STORAGE ASSESSMENT
## Step 1: Login to AWS
1.	Open the AWS Management Console. 
2.	Sign in using your AWS account. 
3.	Search for S3. 
4.	Select Amazon S3. 

## Step 2: Select the S3 Bucket
1.	Click Buckets. 
2.	Select the S3 bucket created in the previous experiment. 
3.	Record: 
o	Bucket name 
o	AWS Region 
o	Number/type of objects 
Screenshot: S3 bucket overview.

## Step 3: Check Block Public Access
1.	Open the S3 bucket. 
2.	Select Permissions. 
3.	Locate Block public access (bucket settings). 
4.	Check Block all public access. 
Record:
•	ON → Secure configuration 
•	OFF → Potential public-access risk 
Screenshot: Block Public Access settings.

## Step 4: Check Bucket Versioning
1.	Select the Properties tab. 
2.	Locate Bucket Versioning. 
3.	Record whether it is: 
o	Enabled 
o	Disabled 
Security purpose
Versioning helps recover previous versions of objects after accidental deletion or modification.
Screenshot: Bucket Versioning.

## Step 5: Check Default Encryption
1.	Stay in the Properties tab. 
2.	Locate Default encryption. 
3.	Record the encryption type. 
Possible configurations include:
•	SSE-S3 
•	SSE-KMS 
•	DSSE-KMS 
Security purpose
Encryption protects stored data from unauthorized disclosure.
Screenshot: Default Encryption.

## Step 6: Check Bucket Policy
1.	Select Permissions. 
2.	Locate Bucket policy. 
3.	Check whether a bucket policy exists. 
Record:
•	Policy exists 
•	No policy 
Note
A missing bucket policy is not automatically a vulnerability. Access may be controlled through IAM and other AWS security mechanisms.
Screenshot: Bucket Policy section.

## Step 7: Check Object Ownership and ACL
1.	In Permissions, locate Object Ownership. 
2.	Record the current configuration. 
A common secure configuration is:
Bucket owner enforced
This means:
•	ACLs are disabled. 
•	Objects are owned by the bucket owner. 
•	Access is controlled using policies. 
Screenshot: Object Ownership.

## Step 8: Check Server Access Logging
1.	Go to Properties. 
2.	Locate Server access logging. 
3.	Record whether it is: 
o	Enabled 
o	Disabled 
Security purpose
Logging helps investigate suspicious or unauthorized access to the bucket.
Screenshot: Server Access Logging

## OUTPUT:

<img width="1917" height="922" alt="lab4_2bucket" src="https://github.com/user-attachments/assets/a717eaad-3115-4957-8bba-2c69a1705c31" />

<img width="1917" height="872" alt="lab4_block" src="https://github.com/user-attachments/assets/18ff77fc-e090-4ab3-a040-0617fe05e850" />

<img width="1917" height="866" alt="lab4_bucketVersioning" src="https://github.com/user-attachments/assets/e7a93897-8c1a-4764-aa12-86100b181a9a" />

<img width="1902" height="867" alt="lab4_encryption" src="https://github.com/user-attachments/assets/2aa7b6b7-2be1-437d-9a8c-5312dd4f4944" />

<img width="1917" height="872" alt="lab4_policy" src="https://github.com/user-attachments/assets/03788f8a-7224-4464-8720-6f3a275d86f7" />

<img width="1917" height="857" alt="lab4_oown" src="https://github.com/user-attachments/assets/bc027ff3-1c8e-4409-b16c-8f233bc1f50b" />


<img width="1917" height="877" alt="lab4_last" src="https://github.com/user-attachments/assets/1efb328c-16e8-433b-9b32-fb3da448bebf" />

## Result:
All AWS user activities, including volume creation, deletion, and permission changes, were successfully audited using CloudTrail.
