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

  - I added the following objects in my diagram:
    - AWS Cloud
    - Virtual Private Cloud
    - ECS EC2 Container
    - Elastic Container Service Container 1 --> Frontend, Backend
    - Load Balancing Application Load Balancer --> Load Balancer
    - Amazon Route 53 --> DNS
    - Amazon Cognito --> Authentication
    - AWS Appsync
    - Amazon DynamoDB
    - Amazon RDS
    - Momento Serverless Cache (obtained from the Momento's website)
    - Client
   
   - Code for Momento shape .svg:
   
`<?xml version="1.0" encoding="UTF-8"?>
<svg viewBox="0 0 44 40" xmlns="http://www.w3.org/2000/svg">
<path d="M12.0658 39.6447C12.201 39.788 12.3715 39.8933 12.5603 39.9498C12.749 40.0063 12.9493 40.0121 13.141 39.9666C13.3327 39.9211 13.5091 39.8259 13.6523 39.6906C13.7956 39.5553 13.9006 39.3847 13.957 39.1959L15.4636 33.7146L22.3233 7.81434C22.3556 7.6727 22.435 7.54623 22.5486 7.45564C22.6621 7.36504 22.8031 7.3157 22.9484 7.3157C23.0936 7.3157 23.2346 7.36504 23.3482 7.45564C23.4617 7.54623 23.5411 7.6727 23.5734 7.81434L24.3107 9.80173C24.5698 10.5072 24.9972 11.1388 25.5558 11.6416C26.1144 12.1443 26.7874 12.5031 27.5162 12.6867L33.9271 14.4497C34.5493 14.6203 35.1055 14.9747 35.5229 15.4666C35.9404 15.9584 36.1998 16.5648 36.2671 17.2064C36.3142 17.9744 36.1857 18.7431 35.8913 19.454C35.597 20.165 35.1445 20.7995 34.5682 21.3094L32.9655 22.6877C31.6939 23.8 30.7873 25.2699 30.3642 26.9054C29.941 28.5409 30.0209 30.266 30.5934 31.8554L33.2219 39.228C33.2841 39.395 33.3832 39.5459 33.5118 39.6693C33.6403 39.7928 33.795 39.8857 33.9644 39.9412C34.1338 39.9966 34.3135 40.0132 34.4902 39.9896C34.6669 39.966 34.836 39.9029 34.9849 39.805C38.3092 37.3573 40.8798 34.0258 42.4042 30.1893C43.9286 26.3529 44.3455 22.1656 43.6076 18.1039C42.8325 13.7662 40.7702 9.76205 37.6888 6.61212C34.6075 3.46219 30.6497 1.31222 26.3301 0.441754C23.3239 -0.169176 20.2233 -0.146199 17.2264 0.509215C14.2295 1.16463 11.4024 2.43805 8.92559 4.24812C6.44881 6.05819 4.37691 8.36507 2.8423 11.0213C1.30769 13.6776 0.34413 16.6248 0.0131988 19.6746C-0.0190388 19.9292 0.00796968 20.1879 0.0921178 20.4304C0.176266 20.6729 0.315284 20.8927 0.498329 21.0726C0.681374 21.2526 0.903489 21.3878 1.14739 21.4678C1.39128 21.5478 1.65038 21.5704 1.90444 21.5338C2.76825 21.4533 3.63935 21.5544 4.46174 21.8307C5.28413 22.1069 6.03962 22.5522 6.67964 23.1379C7.31966 23.7236 7.83004 24.4367 8.178 25.2314C8.52595 26.0261 8.70377 26.8849 8.70003 27.7524V30.9579C8.73821 34.1645 9.93348 37.2494 12.0658 39.6447V39.6447Z"></path>
<path d="M27.1956 18.6882C28.2933 18.6882 29.183 17.7984 29.183 16.7008C29.183 15.6032 28.2933 14.7134 27.1956 14.7134C26.098 14.7134 25.2083 15.6032 25.2083 16.7008C25.2083 17.7984 26.098 18.6882 27.1956 18.6882Z"></path>
</svg>`

    - Also in Lucidchart change the fill color of Momento.svg to #25392b

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

