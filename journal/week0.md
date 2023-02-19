# Week 0 — Billing and Architecture
## Watched Week 0 - Live Streamed Video
Done!

## Watched Chirag's Week 0 - Spend Considerations	

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

 - Done!

## Recreate Conceptual Diagram in Lucid Charts or on a Napkin	

## Recreate Logical Architectual Diagram in Lucid Charts	

## Create an Admin User	

## Use CloudShell	

## Generate AWS Credentials	

## Installed AWS CLI	

## Create a Billing Alarm	

## Create a Budget	

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

