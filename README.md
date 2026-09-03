# EXPERIMENT 4 - AUDITING CLOUD ACTIVITY USING AWS CLOUDTRAIL

## OBJECTIVE

To audit and monitor cloud activity in AWS using AWS CloudTrail by viewing and analyzing recorded AWS events and identifying important audit information such as user identity, event name, event time, AWS service, region, and operation status.

---

## REQUIREMENTS

* AWS Account
* Web Browser
* Internet Connection
* Amazon S3 Access
* AWS CloudTrail

---

# PART A - ACCESS AWS CLOUDTRAIL

## Step 1: Login to AWS

1. Open the AWS Management Console.
2. Sign in using your AWS account.
3. In the AWS search bar, type **CloudTrail**.
4. Select **AWS CloudTrail**.

<img width="1905" height="872" alt="cloudtrail_dashboard" src="https://github.com/user-attachments/assets/a9e55850-ae9d-4500-9c26-b1dcbeb48aac" />


## Step 2: Open Event History

1. In the CloudTrail navigation menu, select **Event history**.
2. CloudTrail displays recent AWS activity.
3. Review the available events.

The Event History page displays information such as:

* Event time
* Username
* Event name
* Event source
* Resource type
* Resource name

<img width="1917" height="910" alt="cloud_history" src="https://github.com/user-attachments/assets/65b9d27a-764e-44f5-b3a2-22ba68bbaaaa" />


---

# PART B - ANALYZE A CLOUDTRAIL EVENT

## Step 3: Select an Event

From the Event History list, an S3-related event was selected.

The event selected was:

**CreateBucket**

The event details were opened and analyzed.

<img width="1917" height="915" alt="cloud_createbucket" src="https://github.com/user-attachments/assets/79b438d5-733e-4d3b-868c-87d54bd60396" />

---

## Step 4: Analyze the CreateBucket Event

The **CreateBucket** event indicates that an Amazon S3 bucket creation operation occurred.

| Parameter        | Observation                           |
| ---------------- | ------------------------------------- |
| **Event Time**   | August 05, 2026, 11:21:44 (UTC+05:30) |
| **User Name**    | root                                  |
| **Event Name**   | CreateBucket                          |
| **Event Source** | s3.amazonaws.com                      |
| **AWS Region**   | us-east-1                             |
| **Read-only**    | false                                 |
| **Error Code**   | -                                     |
| **Activity**     | S3 bucket creation                    |

### Meaning of Important Fields

| Field            | Meaning                                                                    |
| ---------------- | -------------------------------------------------------------------------- |
| **Event Time**   | Time at which the activity occurred                                        |
| **User Name**    | User or identity associated with the activity                              |
| **Event Name**   | AWS operation that was performed                                           |
| **Event Source** | AWS service that generated the event                                       |
| **AWS Region**   | Region where the activity occurred                                         |
| **Read-only**    | Indicates whether the event was only a read operation or involved a change |
| **Error Code**   | Indicates whether an error occurred during the operation                   |

---

# PART C - IDENTIFY ANOTHER CLOUDTRAIL EVENT

## Step 5: Select Another Event

1. Return to **CloudTrail → Event history**.
2. Select another event.
3. Open its details.
4. Record the important fields.

The second event selected was:

**AutomatedDefaultVpcCreation**

<img width="1917" height="900" alt="cloud_automated" src="https://github.com/user-attachments/assets/3c2053f4-1682-42a1-bc8d-4b2536d369a8" />


---

## Step 6: Analyze the Second Event

| Parameter        | Observation                           |
| ---------------- | ------------------------------------- |
| **Event Time**   | August 05, 2026, 11:30:23 (UTC+05:30) |
| **User Name**    | root                                  |
| **Event Name**   | AutomatedDefaultVpcCreation           |
| **Event Source** | ec2.amazonaws.com                     |
| **AWS Region**   | us-east-1                             |
| **Read-only**    | false                                 |
| **Error Code**   | -                                     |
| **Activity**     | Automated default VPC creation        |

<img width="1919" height="1079" alt="Screenshot 2026-09-02 221346" src="https://github.com/user-attachments/assets/6f6cba7f-dea5-4c7d-8941-09d3f5ddaaf1" />

---

# PART D - COMPARE THE EVENTS

## Step 7: Prepare the Audit Comparison

The two CloudTrail events were compared as follows:

| Parameter        | Event 1                   | Event 2                        |
| ---------------- | ------------------------- | ------------------------------ |
| **Event Time**   | August 05, 2026, 11:21:44 | August 05, 2026, 11:30:23      |
| **User Name**    | root                      | root                            |
| **Event Name**   | CreateBucket              | AutomatedDefaultVpcCreation     |
| **Event Source** | s3.amazonaws.com          | ec2.amazonaws.com               |
| **AWS Region**   | us-east-1                 | us-east-1                       |
| **Read-only**    | false                     | false                           |
| **Error Code**   | -                         | -                               |
| **Activity**     | S3 bucket creation        | Automated VPC creation          |

---

# PART E - SECURITY AUDIT ANALYSIS

## Step 8: Identify Who, What, When and Where

### Event 1 — CreateBucket

| Question    | Answer                            |
| ----------- | --------------------------------- |
| **WHO?**    | root                              |
| **WHAT?**   | CreateBucket — S3 bucket creation |
| **WHEN?**   | August 05, 2026, 11:21:44         |
| **WHERE?**  | us-east-1                         |
| **RESULT?** | Successful — No error code        |

### Event 2 — AutomatedDefaultVpcCreation

| Question    | Answer                                                       |
| ----------- | ------------------------------------------------------------ |
| **WHO?**    | root                                                        |
| **WHAT?**   | AutomatedDefaultVpcCreation — Automated VPC creation        |
| **WHEN?**   | August 05, 2026, 11:30:23                                    |
| **WHERE?**  | us-east-1                                                   |
| **RESULT?** | Successful — No error code                                   |

---

# Step 9: Final Audit Table

| Parameter      | Event 1                   | Event 2                        |
| -------------- | ------------------------- | ------------------------------ |
| **Event Time** | August 05, 2026, 11:21:44 | August 05, 2026, 11:30:23      |
| **User**       | root                      | root                            |
| **Event Name** | CreateBucket              | AutomatedDefaultVpcCreation     |
| **Service**    | Amazon S3                 | Amazon EC2                     |
| **Region**     | us-east-1                 | us-east-1                       |
| **Read-only**  | false                     | false                           |
| **Result**     | Successful                | Successful                     |
| **Activity**   | S3 bucket creation        | Automated VPC creation          |

---

# RESULT

The cloud activities in AWS were successfully audited using **AWS CloudTrail Event History**. Two different AWS events, **CreateBucket** and **AutomatedDefaultVpcCreation**, were examined and compared based on event time, user identity, event name, event source, AWS Region, read-only status, and error status.

The experiment demonstrated how **AWS CloudTrail provides an audit trail for monitoring, accountability, security auditing, and investigation of cloud activities**.
