# Week 0 — Billing and Architecture
## Watched Week 0 - Live Streamed Video
https://www.youtube.com/watch?v=SG8blanhAOg&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=12

Done!

## Watched Chirag's Week 0 - Spend Considerations	
https://www.youtube.com/watch?v=OVw3RrlP-sI&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=13

- Pricing (of services) varies according to the region
- Bills are in USD and sometimes in local currency. In my case, USD is used and I have only charges for registering my domain in Route 53:

  ![image](https://user-images.githubusercontent.com/125397350/219414908-1e5fa9e1-02f4-4768-b6d4-5c17aac3f05e.png)


- AWS Free Tier, here you can monitor the usage of the Free Tier services. Also based on this, you can create a billing alert:

  ![image](https://user-images.githubusercontent.com/125397350/219424327-ec89953e-1e11-4ffc-9fc6-0de99689b3ee.png)


- Setting up billing preferences:

  ![image](https://user-images.githubusercontent.com/125397350/219425313-afb86bf2-2aca-49d2-a691-162af1897e3c.png)


- **Creating a Billing alert using CloudWatch**

  To create a Billing alert, first you need to make sure you are in North Virginia Region, then go to **Alarms** --> **In alarm** --> **Create alarm** ,  then complete the 4 steps.

  ![image](https://user-images.githubusercontent.com/125397350/219428423-84eaad4a-d60e-4ef4-afa6-71583f7e552d.png)

  **STEP 1: Specify metric and conditions**
    
  Select **Billing** --> **Total Estimated Charge** --> **USD** --> **Select metric**
  
  ![image](https://user-images.githubusercontent.com/125397350/219429048-59b13ebb-4fe4-4727-a7ed-5418f1d6bd39.png)
  
  Complete the **Metric** and **Conditions** and click **Next**. In my case I chosed a threshold of 10 dollars.
  
  ![image](https://user-images.githubusercontent.com/125397350/219430941-6152d366-8bf4-4c37-9dd5-af392fb36c2e.png)
  ![image](https://user-images.githubusercontent.com/125397350/219431001-489cf5c7-23d9-4774-9491-b949e9e01b5d.png)

  **STEP 2: Configure actions**
  
   Here you can configure some actions related to **Notifications**, **Auto Scaling**, **EC2** and **System Manager**. I will just configure a notification and create a new topic as shown:
   
   ![image](https://user-images.githubusercontent.com/125397350/219434144-ba25ac13-62bf-4ff9-9bef-06ed5d0836d6.png)

  **STEP 3: Add name and description**
  
  Then, I give my alarm a **Name** and **Description** and click **Next**
  
  ![image](https://user-images.githubusercontent.com/125397350/219434820-f8ec0487-ddab-4ec9-9ee0-b5e5ad05c861.png)

  **STEP 4: Preview and create**
  
   Finally, create your alarm.
   
   ![image](https://user-images.githubusercontent.com/125397350/219436685-58b03754-a581-4827-9260-0dd12f7f7fe9.png)

  
- **Creating a Budget**

  Go to **Budgets**, select **Monthly cost budget** and complete the **Monthly cost budget - Template** 
  
  ![image](https://user-images.githubusercontent.com/125397350/219901725-d10c829d-2c97-4730-802b-9a4655b1f935.png)

- Cost allocation tags

- Cost explorer (AWS Cost Manager) and reports
  
  
## Watched Ashish's Week 0 - Security Considerations	
https://www.youtube.com/watch?v=4EMWBYVggQI&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=16

 - CloudTrail
 - IAM is the service that allows us to manage access to services and resources within Cloud Service Provider through users, groups, roles and Policies.
    - This service does not have a specific region (global)
    - 3 types of **IAM User** Accounts: Root/Owner, User, Service/Programmatic
    - **IAM Policies** are what provide the authorization to access different resources within AWS environment.They can be attached to Users, Roles, Groups. There are 2 Types: Created/managed by AWS, "Job Function" specific policies
    - **IAM Group** is a logical organization for Users. Using this groups allows to understand what permission an IAM User will have based on their Group Membership and reviewing the IAM Policies attached to that IAM Group.
    - **IAM Roles** are used to assign specific permissions to either cloud services or external entities. Iam Roles are meant to be assumed by either a Federal User (using Single Sign-on), or resource (EC2, Lambda, etc). The benefits of using IAM Roles are the temporary, short-lived tokens that are generated to provide the authorized resource or user access to perform functions within AWS. Roles consist of:
      - Attached Policies for Permissions
      - Trust relationship. Who is trusted to assume this role. This can be a federated identity, an AWS resource, or another AWS Account.
      - Tags
      - Access Advisor. It allows us to audit what Services a role has permissions to, and when the last time the role accessed that service. This can help scope down permissions to roles.


  - Service Control Policies --> https://github.com/hashishrajan/aws-scp-best-practice-policies

  - TOP 5 Security Best Practices
    - Data Protection & Residency in accordance to Security Policy
    - Identity & Access Management with Least Privilege
    - Governance & Compliance of AWS Services being used
      - Global vs Regional Services
      - Compliant Services
    - Shared Responsability of Threat Detection
    - Incident Response Plans to include Cloud

## Recreate Conceptual Diagram in Lucid Charts or on a Napkin	
https://www.youtube.com/watch?v=K6FDrI_tz0k&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=17

## Recreate Logical Architectual Diagram in Lucid Charts	
https://www.youtube.com/watch?v=K6FDrI_tz0k&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=17

  - **Link to LucidChart Diagram:** 
  
    https://lucid.app/lucidchart/51fdb550-9ef3-459c-8413-5e55a94800cf/edit?viewport_loc=-413%2C-15%2C2649%2C1349%2C0_0&invitationId=inv_7a4f0200-9c7c-47eb-8a05-bff0186ccce5
    
    ![image](https://user-images.githubusercontent.com/125397350/220191046-2398ba0a-84a2-4869-9f50-16cdc4076fb4.png)


## Create an Admin User	
https://www.youtube.com/watch?v=OdUnNuKylHg&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=14

## Use CloudShell	
https://www.youtube.com/watch?v=OdUnNuKylHg&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=14

## Generate AWS Credentials	
https://www.youtube.com/watch?v=OdUnNuKylHg&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=14

## Installed AWS CLI	
https://www.youtube.com/watch?v=OdUnNuKylHg&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=14

## Create a Billing Alarm	
https://www.youtube.com/watch?v=OdUnNuKylHg&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=14

## Create a Budget	
https://www.youtube.com/watch?v=OdUnNuKylHg&list=PLBfufR7vyJJ7k25byhRXJldB5AiwgNnWv&index=14




------------------------------------------------------------------
# Homework Challenges

## Destroy your root account credentials, Set MFA, IAM role

  **MFA added**
  
  ![image](https://user-images.githubusercontent.com/125397350/219907309-c7a0bfc5-d15d-4074-9bdb-1dbb32d80721.png)


## Use EventBridge to hookup Health Dashboard to SNS and send notification when there is a service health issue.

## Review all the questions of each pillars in the Well Architected Tool (No specialized lens)

## Create an architectural diagram (to the best of your ability) the CI/CD logical pipeline in Lucid Charts

## Research the technical and service limits of specific services and how they could impact the technical path for technical flexibility. 

## Open a support ticket and request a service limit

