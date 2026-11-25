# Experiment 4 – Auditing Cloud Activity Using AWS CloudTrail

# Name  : SANTHOSH KUMAR V
# Reg No: 212225040381

## Objective
To audit and monitor cloud activity in AWS using AWS CloudTrail by viewing and analyzing recorded AWS events and identifying important audit information such as user identity, event name, event time, AWS service, region, and operation status.

## Requirements
- AWS Account
- Web Browser
- Internet Connection
- Amazon S3 Access
- AWS CloudTrail

## Procedure

### Part A – Access AWS CloudTrail

1. Log in to the AWS Management Console.
2. Search for **CloudTrail** in the AWS search bar.
3. Open AWS CloudTrail.
4. Navigate to **Event History**.
5. Review the recorded AWS activities.

### Part B – Analyze the First CloudTrail Event

1. Navigate to CloudTrail → Event History.
2. Select the `CreateBucket` event.
3. Open the event details.
4. Examine the event information and JSON record.


<img width="1882" height="998" alt="Screenshot 2026-11-21 215323" src="https://github.com/user-attachments/assets/532e56d3-90b1-4797-91e2-d19eab17d09f" />

<img width="1862" height="976" alt="Screenshot 2026-11-21 215350" src="https://github.com/user-attachments/assets/fa23c978-f76e-466c-abeb-c3370830c2f5" />


**Screenshot 1 – CreateBucket Event Details**

<img width="1858" height="981" alt="Screenshot 2026-11-21 215500" src="https://github.com/user-attachments/assets/287a3aaf-a805-4748-9487-a56bec8c292e" />


**Observations:**

| Parameter | Observation |
|---|---|
| Event Time | October 31, 2026, 08:17:36 (UTC+05:30) |
| User Name | root |
| Event Name | CreateBucket |
| Event Source | s3.amazonaws.com |
| AWS Region | us-east-1 |
| Read-only | false |
| Error Code | - |
| Activity | S3 bucket creation |

### Part C – Analyze the Second CloudTrail Event

1. Return to CloudTrail → Event History.
2. Select the `DeleteBucket` event.
3. Open the event details.
4. Examine the recorded event information.

**Screenshot 2 – DeleteBucket Event Details**

<img width="1852" height="983" alt="Screenshot 2026-11-21 215601" src="https://github.com/user-attachments/assets/dcca740f-c2d0-475a-955c-65d807fe5b18" />


**Observations:**

| Parameter | Observation |
|---|---|
| Event Time | October 31, 2026, 08:59:16 (UTC+05:30) |
| User Name | root |
| Event Name | DeleteBucket |
| Event Source | s3.amazonaws.com |
| AWS Region | us-east-1 |
| Read-only | false |
| Error Code | - |
| Activity | S3 bucket deletion |

### Part D – Compare the Events

| Parameter | Event 1 | Event 2 |
|---|---|---|
| Event Time | 08:17:36 | 08:59:16 |
| User Name | root | root |
| Event Name | CreateBucket | DeleteBucket |
| Event Source | s3.amazonaws.com | s3.amazonaws.com |
| AWS Region | us-east-1 | us-east-1 |
| Read-only | false | false |
| Error Code | - | - |
| Activity | S3 bucket creation | S3 bucket deletion |

### Part E – Security Audit Analysis

**1. WHO?**

Both activities were associated with the `root` user identity.

**2. WHAT?**

- Event 1: An S3 bucket creation operation was performed.
- Event 2: An S3 bucket deletion operation was performed.

**3. WHEN?**

- CreateBucket: October 31, 2026, at 08:17:36.
- DeleteBucket: October 31, 2026, at 08:59:16.

**4. WHERE?**

Both operations occurred in the AWS region `us-east-1` (US East – N. Virginia).

**5. RESULT?**

Both events have `-` as their error code, indicating that no error code was recorded. Both have `Read-only` set to `false`, meaning they were write operations that modified cloud resources.

### Part F – Final Audit Table

| Event Time | User | Event Name | Service | Region | Read-only | Result | Activity |
|---|---|---|---|---|---|---|---|
| 08:17:36 | root | CreateBucket | Amazon S3 | us-east-1 | false | No error recorded | S3 bucket creation |
| 08:59:16 | root | DeleteBucket | Amazon S3 | us-east-1 | false | No error recorded | S3 bucket deletion |

## Result

Successfully audited AWS cloud activities using AWS CloudTrail Event History. The CreateBucket and DeleteBucket events were examined based on event time, user identity, event name, event source, AWS region, read-only status, and error status.

The experiment demonstrated how AWS CloudTrail provides an audit trail for monitoring, accountability, and investigation of cloud activities.
