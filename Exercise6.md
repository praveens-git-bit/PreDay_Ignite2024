### Exercise 6: Explorer Data Science experience in Microsoft Fabric
 
Microsoft Fabric offers Data Science experiences to empower users to complete end-to-end data science workflows for data enrichment and business insights. You can complete a wide range of activities across the entire data science process, all the way from data exploration, preparation and cleansing to experimentation, modeling, model scoring and serving predictive insights to BI reports.

### Task 6.1: Build ML models and experiments using Copilot in Fabric

![task-3.1.1.png](media/labMedia/exercise5_1.1.png)

To understand the cause behind Contoso’s declining revenue, the team needed to dive deeper into their customers’ spending pattern.

Copilot responds to queries in natural language or generates customized code snippets for tasks like creating charts, filtering data, applying transformations, and building machine learning models.

Let’s see how Copilot for Notebook helps you, as a Data Engineer, quickly create Data Science Notebooks.

1. Switch to the **Data Science** experience using the experience switcher icon in the left corner.

   ![task-3.1.1.png](media/labMedia/exercise5_1.2.png)

2. Click on **Import notebook** button.

   ![task-3.1.2.png](media/labMedia/exercise5_1.3.png)

3. Click on the **Upload** button.

   ![task-3.1.2.png](media/labMedia/exercise5_1.3.1.png)

4. Browse to the fabricnotebooks folder **"C:\LabFiles\01_Pre_Day\artifacts\fabricnotebooks"** in the VM and select **Build ML models and experiments using Copilot for Data Science in Fabric** notebook.

5. Click on the **Open** button.

![task-3.1.2.png](media/labMedia/exercise5_1.3.2.png)

6. Wait for the notebook to **upload**.

![task-3.1.2.png](media/labMedia/exercise5_1.3.3.png)

7. Click on the **<inject key= "WorkspaceName" enableCopy="false"/>** workspace from the left navigation pane.

![task-3.1.2.png](media/labMedia/exercise5_1.3.4.png)

8. Click on **Filter**, expand **Type** and select **Notebook**.

![task-3.1.2.png](media/labMedia/exercise5_1.3.5.png)

9. Click on the **Build ML models and experiments using Copilot for Data Science in Fabric** notebook.

![task-3.1.2.png](media/labMedia/exercise5_1.3.6.png)

10. Click on **Lakehouses** in the Explorer pane.

![task-3.1.2.png](media/labMedia/exercise5_1.3.7.png)

11. Click on **Missing Lakehouses** and then click on **Remove all Lakehouse**.

![task-3.1.2.png](media/labMedia/exercise5_1.3.8.png)

12. Click on the **Continue** button.

![task-3.1.2.png](media/labMedia/exercise5_1.3.9.png)  

13. Click on the **+ Lakehouse** button.

![task-3.1.2.png](media/labMedia/exercise5_1.3.10.png) 

14. Select **Existing Lakehouse with Schema** and then click on the **Add** button.

![task-3.1.2.png](media/labMedia/64.6.png)

15. Select the **lakehouse** checkbox.

![task-3.1.2.png](media/labMedia/exercise5_1.3.12.png)

16. Click on the **Add** button.

![task-3.1.2.png](media/labMedia/exercise5_1.3.13.png)

17. Click on the **Copilot** button and then click on the **Get Started** button.
 
>**Note:** If the Copilot is not visible please click on eclipse **":"** and select Copilot.

![task-3.1.2.png](media/labMedia/exercise5_1.6.png)

18. Run the **first cell** of the notebook to install the copilot packages.

>**Note:** Note: This may take a while to execute, please wait till this loads completely as seen by the **Play button** becoming visible again.

![task-3.1.2.png](media/labMedia/exercise5_1.7.png)

19. Copy and paste the following **prompt** in the textbox.

```
Load the "customerchurndata" table from the lakehouse into a Spark DataFrame. Then convert that into pandas dataframe as df
```

20. Click on the **send** button.

![task-3.1.2.png](media/labMedia/exercise5_1.8.png)

21. Click on the **Copy code** icon.

>**Note:** The new cell will be created right above the cell.

![task-3.1.2.png](media/labMedia/exercise5_1.8.2.png)

22. Hover above the first cell and then click on a **+ Code** icon.

![task-3.1.2.png](media/labMedia/exercise5_1.8.1.png)

23. Paste the copied **query** and run the new **cell**.

![task-3.1.2.png](media/labMedia/exercise5_1.9.png)

>**Note:** Copilot may not respond as expected, please copy and paste the following code to obtain the result:

```
# Load the table into a Spark DataFrame
spark_df = spark.table('lakehouse.customerchurndata')
 
# Convert the Spark DataFrame to a pandas DataFrame
df = spark_df.toPandas()
```

>**Note:** It may take some time for the copilot to generate query.

With the data prepared with the help of Copilot, Data Scientists like you can explore the data to understand the patterns it contains.

The rest of the notebook has similar PySpark queries to explore customer churn prediction.


### Task 6.2: Leverage AI skills

AI Skill, a new capability in Fabric, allows Data Analysts like Serena to create their own generative AI experiences. Serena believes that generative AI offers a transformative way to interact with data, significantly boosting data-driven decision-making in organizations worldwide. 

In this exercise, you’ll step into Data Analyst, Serena’s shoes and leverage AI Skill to create conversational question-and-answer (Q&A) systems. 

1. From the left navigation pane select **Data Science** experience.

![task-5.2](media/labMedia/AIskill1.png)

2. Select **AI Skill**. If it is not visible, scroll down the page.

![task-5.2](media/labMedia/AIskill2.png)

3. Enter Name as **Contoso-Assistance**  as the Create AI Skill name.

![task-5.2](media/labMedia/AIskill3.png)

4. Click on **lakehouse** and then click on the **Confirm** button.

![task-5.2](media/labMedia/AIskill4.png)

5. Click on **refresh** and Expand **Tables** then select the following tables.

- dimcustomer
- dimdate
- dimproduct
- dimreseller
- factinternetsales
- factresellersales

![task-5.2](media/labMedia/AIskill5.png)

6. Click on **Get Started** button.

![task-5.2](media/labMedia/AIskill6.png)

7. Past the following question **What is the most sold product?** in the chatbox and click on the **Send** button.

```
What is the most sold product?
```

![task-5.2](media/labMedia/AIskill7.png)

>**Note:** This may take some time; please wait until a response is received.

8. AI Skill answered the question fairly well based on the selected tables.

However, the SQL query needs some improvement, it orders the products by order quantity, when total sales revenue associated with the product is the most important consideration, as shown in the above screenshot.

To improve the query generation, let's provide some instructions, as shown in these examples:

```
Whenever I ask about "the most sold" products or items, the metric of interest is total sales revenue and not order quantity.

The primary table to use is FactInternetSales. Only use FactResellerSales if explicitly asked about resales or when asked about total sales.
```

9. Copy the above notes and paste it in **Notes for model** box.
    
10. Type **What is the most sold product ?** in the chatbox and then click on the **Send** button.  

```
What is the most sold product ?
```
Asking the question again returns a different answer, **Mountain-200 Black, 46**, as shown in the below screenshot:

![task-5.2](media/labMedia/AIskill8.png)

In addition to instructions, examples serve as another effective way to guide the AI. If you have questions that your AI skill often receives, or questions that require complex joins.

10. In the example SQL queries click on **edit** icon.

![task-5.2](media/labMedia/AIskill9.png)

>**Note:** Make sure you have allowed copy to clipboard in the browser lock.

11. Click on **+ Add example** and enter the following question and their respective SQL queries.

|Question| SQL query|
|--------|----------|
|who are the top 5 customers by total sales amount?|SELECT TOP 5 CONCAT(dc.FirstName, ' ', dc.LastName) AS CustomerName, SUM(fis.SalesAmount) AS TotalSpent FROM factinternetsales fis JOIN dimcustomer dc ON fis.CustomerKey = dc.CustomerKey GROUP BY CONCAT(dc.FirstName, ' ', dc.LastName) ORDER BY TotalSpent DESC;|
|what is the total sales amount by year?|SELECT dd.CalendarYear, SUM(fis.SalesAmount) AS TotalSales FROM factinternetsales fis JOIN dimdate dd ON fis.OrderDateKey = dd.DateKey GROUP BY dd.CalendarYear ORDER BY dd.CalendarYear;|

>**Note:** This may take some time; please wait until the SQL query is copied to the box.

![task-5.2](media/labMedia/AIskill10.png)

12. Click on **close(X)** button.

![task-5.2](media/labMedia/AIskill11.png)

13. Type  the following **prompt** in the chatbox and click on **Send** button.

```
who are the top 5 customers by total sales amount?
```

![task-5.2](media/labMedia/AIskill12.png)

14. Click on **Publish** button.

![task-5.2](media/labMedia/AIskill13.png)

15. In the pop-up screen click on **Publish** button.

![task-5.2](media/labMedia/AIskill14.png)

16. Notice that AI skill is **published successfully**.

![task-5.2](media/labMedia/AIskill15.png)
