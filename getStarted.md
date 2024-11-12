# Getting Started with Lab

1. Once the **Environment** is provisioned, a virtual Machine (JumpVM/Bastion) and **Lab Guide** gets loaded in your browser. Use this virtual Machine throughout the workshop to perform the lab. 


![Started.](GetStarted/Task1.png)



### Familiarize yourself with the Lab Environment, before you begin!

1. The **Lab Guide** tab contains all the steps required to complete the lab. You can use the numbers at the bottom of the **Lab Guide** to navigate between different **Exercises**.

![Started.](GetStarted/Task3.png)

2. Before starting the Lab, take a moment to explore the following tabs:

    **- Lab Guide**
    **- Environment**
    **- Help**

![Started.](GetStarted/Task4.png)


3. You can view the **Lab Guide** in a separate full window by selecting **Split Window**, or hide the **Lab Guide** by **collapsing it**, which slides it out of the right side of the screen.

![Started.](GetStarted/Task5.png)


# Login to Azure Portal

1. In the JumpVM/Bastion, **double click** on the **Azure Portal** shortcut of the Microsoft Edge browser on the desktop.

   **Note:** If the browser is not opening, **refresh** the main VM browser page.

![Started.](GetStarted/Task6.png)

2. If you see the pop-up notification to restore pages, click on  **"x"**  to close it.

![Started.](GetStarted/Task7.png)

3. On the **Microsoft Azure** browser tab, paste the provided **Username** to **Sign in** and click **Next**.

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

6. Click **No, Thanks** button on the pop-up prompting to **Sign in to Microsoft Edge**.

![Started.](GetStarted/signinpopup.png)
   
**Note:** After log into the Azure Portal, if a pop-up page titled **"Welcome to Microsoft Azure"** appears, click **Cancel** to skip the tour.

6. Now, on the **Azure Portal** Dashboard, click on Search bar to search and select the Resource Group as **<inject key= "resourcegroup" enableCopy="true"/>**.
   
![Started.](GetStarted/Task11.png)


**Note:** In the Resource Group, there are **23 resources**.

#

**Note:** If you encounter an **downloading an HTML file** issue, while accessing resources in the JumpVM/Bastion, try refreshing the main VM browser page to fix it.

![Started.](GetStarted/Issue1.png)

