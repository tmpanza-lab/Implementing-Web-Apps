# Implementing Web Apps

## Objective

In this lab, I learnt about Azure web apps. I learnt how to configure a web app to display a Hello World application in an external GitHub repository. I learnt how to create a staging slot and swap with the production slot. Finally I also learnt about autoscaling to accommodate demand changes.

## Architecture diagram
![image](https://github.com/user-attachments/assets/73ac4754-ddea-43ac-8ff5-e4b70589f833)

### Job Skills

- Creating and configuring an Azure web app.
- Creating and configuring a deployment slot.
- Configuring web app deployment settings.
- Swapping deployment slots. 
- Configuring and testing autoscaling of the Azure web app.


### Tools Used

- Azure portal - https://portal.azure.com


## Steps

## Task 1: Create and configure an Azure web app

In this task, I create an Azure web app. Azure App Services is a Platform As a Service (PAAS) solution for web, mobile, and other web-based applications. Azure web apps is part Azure App Services hosting most runtime environments, such as PHP, Java, and .NET. The app service plan that you select determines the web app compute, storage, and features.

1.	Sign in to the Azure portal - https://portal.azure.com.
2.	Search for and select App services.
![image](https://github.com/user-attachments/assets/2abf24c7-c890-4981-8b2c-eddae0d5b777)
 
3.	Select + Create, from drop-down menu, Web App. Notice the other choices.
![image](https://github.com/user-attachments/assets/eacf3780-b8f1-4ec2-ac84-0f80fc12253f)
 
4.	On the Basics tab of the Create Web App blade, specify the following settings (leave others with their default values):
![image](https://github.com/user-attachments/assets/69355d7c-5b4a-4138-a6e7-a47e55b6f0a1)
![image](https://github.com/user-attachments/assets/4ca9dab6-8eec-4149-b6f1-4d907a63af55)
 
 
Note: If the deployment fails, change to another region and try again. For example, switch to East US 2.
![image](https://github.com/user-attachments/assets/edd8a602-2c01-48d2-a578-b3b81f85ab14)
 
5.	Click Review + create, and then Create.
![image](https://github.com/user-attachments/assets/fbb7c3a8-4795-4ccb-8063-81e4b616609d)
 
6.	After the deployment, select Go to resource.


## Task 2: Create and configure a deployment slot

In this task, I will create a staging deployment slot. Deployment slots enable you to perform testing prior to making your app available to the public (or your end users). After you have performed testing, you can swap the slot from development or staging to production. Many organizations use slots to perform pre-production testing. Additionally, many organizations run multiple slots for every application (for example, development, QA, test, and production).

1.	On the blade of the newly deployed Web App, click the Default domain link to display the default web page in a new browser tab.
![image](https://github.com/user-attachments/assets/7abeade6-e410-4c75-b1a2-4543364cbbf2)
![image](https://github.com/user-attachments/assets/8a63c974-22e3-4e5d-b77f-fa86055ab0fc)
 
 
2.	Close the new browser tab and, back in the Azure portal, in the Deployment section of the Web App blade, click Deployment slots.
![image](https://github.com/user-attachments/assets/c87704e5-4e3f-4f95-a784-61b544037835)
 
3.	Click Add slot, and add a new slot with the following settings:
![image](https://github.com/user-attachments/assets/8b01f3d6-f20b-41e7-9c5f-4499edb1f44d)
 
4.	Select Add.
5.	Back on the Deployment slots blade of the Web App, click the entry representing the newly created staging slot.
![image](https://github.com/user-attachments/assets/497cb953-17f6-458e-b144-3488542f6dea)
 
6.	Review the staging slot blade and note that its URL differs from the one assigned to the production slot.
![image](https://github.com/user-attachments/assets/72106db5-beae-4af9-8a7e-81c27c3fb141)
 

## Task 3: Configure Web App deployment settings

In this task, I will configure Web App deployment settings. Deployment settings allow for continuous deployment. This ensures that the app service has the latest version of the application.

1.	In the staging slot, select Deployment Center and then select Settings.
![image](https://github.com/user-attachments/assets/13bf6d8d-e7d2-4dfd-80b3-0c2fabe62df3)
 
2.	In the Source drop-down list, select External Git. Notice the other choices.
![image](https://github.com/user-attachments/assets/9e064cc4-0d08-4921-8c06-384d14426564)
 

3.	In the repository field, enter https://github.com/Azure-Samples/php-docs-hello-world
![image](https://github.com/user-attachments/assets/e53114c1-20c8-444d-af5a-b9d7eafce877)
 
4.	In the branch field, enter master.
5.	Select Save.
6.	From the staging slot, select Overview.
7.	Select the Default domain link, and open the URL in a new tab.
8.	Verify that the staging slot displays Hello World.
![image](https://github.com/user-attachments/assets/a6ad3b04-d95b-4a07-8564-8cfe31f9e84f)
 



## Task 4: Swap deployment slots

In this task, I will swap the staging slot with the production slot. Swapping a slot allows you to use the code that you have tested in your staging slot, and move it to production. The Azure portal will also prompt you if you need to move other application settings that you have customized for the slot. Swapping slots is a common task for application teams and application support teams, especially those deploying routine app updates and bug fixes.

1.	Navigate back to the Deployment slots blade, and then select Swap.
![image](https://github.com/user-attachments/assets/1cce9e64-fb02-4b59-b8f6-daa913b1a0cc)
 
2.	Review the default settings and click Start Swap.
![image](https://github.com/user-attachments/assets/2c48dfc2-0d0e-4593-b401-9a64300e3e5b)
 
3.	On the Overview blade of the Web App select the Default domain link to display the website home page.
4.	Verify the production web page displays the Hello World! page.
![image](https://github.com/user-attachments/assets/4ba63162-df88-49a4-b5b7-566e971fda5d)
 

## Task 5: Configure and test autoscaling of the Azure Web App

In this task, I will configure autoscaling of Azure Web App. Autoscaling enables you to maintain optimal performance for your web app when traffic to the web app increases. To determine when the app should scale you can monitor metrics like CPU usage, memory, or bandwidth.

1.	In the Settings section, select Scale out (App Service plan).
2.	From the Scaling section, select Automatic.
![image](https://github.com/user-attachments/assets/1944c032-adf0-4008-ae44-76b2d8ee5e69)
 
Notice the Rules Based option. Rules based scaling can be configured for different app metrics.

3.	In the Maximum burst field, select 2.
![image](https://github.com/user-attachments/assets/ac5b0636-dce9-48c4-8363-30f1bd5b6fa9)
 
4.	Select Save.
5.	Select Diagnose and solve problems (left pane).
![image](https://github.com/user-attachments/assets/8e8ea433-70a7-4ed7-9e87-6b88541e0a75)
 
6.	In the Load Test your App box, select Create Load Test.
1.	Select + Create and give your load test a name. The name must be unique.
![image](https://github.com/user-attachments/assets/53a4472a-3107-42e4-8415-0519b3dbf186)
 
2.	Select Review + create and then Create.
![image](https://github.com/user-attachments/assets/9144fd9e-9a9d-46ec-9dfb-1774022c2781)
 
7.	Wait for the load test to create, and then select Go to resource.
![image](https://github.com/user-attachments/assets/75d22399-78c6-481b-b0b4-155919204b60)
 
From the Overview	Add HTTP requests, select Create.
8.	On the Test plan tab, click Add request. In the URL field, paste in your Default domain URL. Ensure this is properly formatted and begins with https://.
 ![image](https://github.com/user-attachments/assets/2f98974c-8320-4d70-be58-6f092c251bb9)

9.	Select Review + create and Create.
10.	Review the test results including Virtual users, Response time, and Requests/sec.
 ![image](https://github.com/user-attachments/assets/367de6b8-b5a6-40ae-80d8-bfbf89ecdd4b)
![image](https://github.com/user-attachments/assets/688705a1-9531-4a72-ae86-aa60e30ac0cf)
![image](https://github.com/user-attachments/assets/24ac0b6e-986a-463d-a3c2-67aeda05f580)
 
11.	Select Stop to complete the test run.

