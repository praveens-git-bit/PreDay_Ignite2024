# Getting Started with Lab

1. Once the **environment** is provisioned, a virtual machine (JumpVM/Bastion) and **lab guide** will get loaded in your browser. Use this virtual machine throughout the workshop to perform the lab. 


![Started.](GetStarted/Task1.png)


### Know the right side of the tab, before performing the lab.

1. The Lab Guide tab contains all the steps required to complete the lab. You can use the numbers at the bottom of the Lab Guide to navigate between different **Exercises**.

![Started.](GetStarted/Task3.png)

2. Before starting the lab, take a moment to explore all the tabs.

    - Lab Guide
    - Environment
    - Help

![Started.](GetStarted/Task4.png)


3. You can view the lab guide in a separate full window by selecting **Split Window**, or hide the lab guide by **collapsing it**, which slides it out of the right side of the screen.

![Started.](GetStarted/Task5.png)


# Login to Azure Portal

1. In the JumpVM/Bastion, **double click** on the **Azure portal shortcut** of the Microsoft Edge browser, which is created on the desktop.

   Note: If the browser is not opening, please **refresh the main VM browser page**.

![Started.](GetStarted/Task6.png)

2. If you see the popup notification to Restore pages, click on  **"x"** close.

![Started.](GetStarted/Task7.png)

3. On the **Sign in to Microsoft Azure tab**, you will see the login screen. Paste the provided **Username** and click Next.

```BASH
 <inject key= "AzureAdUserEmail" enableCopy="true"/>
```

![Started.](GetStarted/Task8.png)

4. Now paste the following **Password** and click on **Sign in**.

```BASH
 <inject key= "AzureAdUserPassword" enableCopy="true"/>
```

![Started.](GetStarted/Task9.png)

5. Click on **Yes**.

![Started.](GetStarted/Task10.png)

6. Click **No, Thanks** button on the popup prompting to **Sign in to Microsoft Edge**.

![Started.](GetStarted/signinpopup.png)
   
**Note:** After signing in to the Azure portal, if a popup page titled **"Welcome to Microsoft Azure"** appears, click **Cancel** to skip the tour.

6. Now you will see the Azure Portal Dashboard, Click on search bar and search for **<inject key= "resourcegroup" enableCopy="true"/>** Resource Group and select the Resource Group.

![Started.](GetStarted/Task11.png)


**Note:** In the Resource Group there will be **23 resources**.

#

**Note:** If you encounter any issues while accessing resources in the JumpVM/Bastion, such as **downloading an HTML file**, try **refreshing the main VM browser** page to resolve the problem.

![Started.](GetStarted/Issue1.png)

