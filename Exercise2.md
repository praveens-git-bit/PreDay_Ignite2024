### Exercise 2: Azure Databricks integration with Fabric: DLT Pipelines, Unity Catalog (Data governance), Mirrored Azure Databricks Catalog

This exercise shows how Microsoft Fabric with Databricks enabled Contoso to solve their integration challenges. The acquired company, Litware Inc., was already using Databricks heavily and they stored their churn and sales data in ADLS Gen2. We’ll see how Unity Catalog benefited Contoso’s data architects so they could quickly get up to speed on all Litware Inc.’s data.

### Task 2.1: Create Delta Live Table pipeline for Data Transformation

Delta Live Tables (DLT) allow you to build and manage reliable data pipelines that deliver high-quality data in Lakehouse. DLT helps data engineering teams simplify ETL development and management with declarative pipeline development, automatic data testing, and deep visibility for monitoring and recovery.

1. Go back to the browser tab of Resource Group **<inject key= "resourcegroup" enableCopy="false"/>**.

2. Search for the Azure Databricks in the Resource group search field and click on **adb-ignite...**.

 <img src="media/databrickssearch.png" width="800"/> 

3. Click on the **Launch Workspace**.

 <img src="media/launchdatabricks.png" width="800"/>

>**Note:** Click on the **Sign in with Microsoft Entra ID** if it appears.

![databrickssignin.png](media/labMedia/databrickssignin.png)

4. Scroll down in the left navigation pane and click on **Delta Live Table**.

![task-2.2.2new.png](media/labMedia/task-2.2.2new.png)

5. Click on the **Create pipeline** button.

![task-2.2.3.1new.png](media/labMedia/task-2.2.3.1new.png)

6. Enter the name of the pipeline as **"DLT_Pipeline"** , scroll down to the **Paths** and click on the **file icon** to browse the notebook.

```BASH
DLT_Pipeline
```
![task-2.2.3new.png](media/labMedia/task-2.2.3new.png)

7. Click on **Shared**.
8. click on **Analytics with ADB**.
9. click on the **01 DLT Notebook** and then click on the **Select** button.

 <img src="media/labMedia/task-2.2.4new.png" width="800"/> 

10. Click on the **Create** button.

 <img src="media/labMedia/task-2.2.5new.png" width="800"/> 

11. Click on **Start** button.

![Databricks](media/startDLT.png)
    
>**Note:** The pipeline will take 5-7 minutes to complete. In the meantime, you can move on to the next section and return to this one afterward.

11. Once the **execution is completed**, we will see a result similar to the one in the following screenshot.


 <img src="media/labMedia/task-2.2.7.png" width="800"/> 

This beautiful lineage view showing the Medallion Architecture is a data design pattern commonly used in Databricks to organize and optimize data processing workflows in a lakehouse architecture. It structures data into three logical layers—Bronze, Silver, and Gold—ensuring data quality, accessibility, and scalability for analytics and machine learning.

---

### Task 2.2: Explore the data in the Azure Databricks environment with Unity Catalog (unified governance solution for data and AI).

We saw how Contoso utilized DLT pipelines to create a Medallion architecture on their data. Now let’s look at how data governance was managed on this curated data across the organization and made easy with Unity Catalog.

With the acquisition of Litware Inc., Contoso had a lot of data integration and interoperability challenges. They wanted to make sure that the transition was smooth, and their data engineers and data scientists could easily assimilate the data processed by Databricks. Thankfully, they were able to leverage Gen AI features right within Azure Databricks to understand and derive insights from this data.

>**Note**: Due to time constraints, the following steps will be completed via an online Click-by-Click exercise.

>Please follow the green beacons for this exercise.
- This exercise will be performed outside the VM browser.
- Please return back to the VM browser once you see the **End of Task 2.2** screen.
- Once you press the **Agree** button, press the **A** key on your keyboard if you do not see the annotations.
	
1. Click on the [**hyperlink**](https://regale.cloud/Microsoft/viewer/3066/task-22-explore-the-data-in-azure-databricks-environment-with-unity-catalog/index.html#/0/1)

2. Continue with next excercise.


### Task 2.3: Create mirrored Azure Databricks catalog in Fabric and analyze data using T-SQL

Mirroring the Azure Databricks Catalog structure in Fabric allows seamless access to the underlying catalog data through shortcuts. This means that any changes made to the data are instantly reflected in Fabric, without the need for data movement or replication. Let’s step into Data Engineer, Eva’s shoes to create a Mirrored Azure Databricks Catalog and analyze the data using T-SQL.

>**Note:** Due to time constraints, the following steps will be completed via an online Click-by-Click exercise. 

>Please follow the green beacons for this exercise.
- This exercise will be performed outside the VM browser.
- Please return back to the VM browser once you see the **End of Task 2.2** screen.
- Once you press the **Agree** button, press the **A** key on your keyboard if you do not see the annotations.

1. Click on the [**hyperlink**](https://regale.cloud/microsoft/play/3781/modern-analytics-with-microsoft-fabrikam-copilot-and-azure-databricks-dream-lab-#/7/0)
 
2. Continue with next exercise.
