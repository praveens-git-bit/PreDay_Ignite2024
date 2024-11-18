### Exercise 1: Data Engineering/Data Factory experience - Data ingestion from a spectrum of analytical data sources into OneLake

*Before we start executing the steps, we will open a backup Click-by-Click lab using the following hyperlink in a new tab and navigate back to the VM browser:* 

[Click-by-Click](https://regale.cloud/Microsoft/viewer/3088/modern-analytics-with-microsoft-fabric-copilot-and-azure-databricks-dream-lab-fu/index.html#/0/0)

*Now, let's trigger the Simulator App to start streaming data to EventHub (**to be used later in exercise 4**).*

Open the new tab in the browser and copy paste the below URL to verify app service streaming data.

|                                               |
 ------------------------------------------------
|<inject key= "WebAppBrowse" enableCopy="true"/> |
 ------------------------------------------------

**Wait** for the page to load. You will see a page like the one shown below.


![task-1.3.png](media/labMedia/task-1.3.png)


### Task 1.1: Create a Microsoft Fabric enabled workspace

In this exercise, you will act as the Data Engineer, Eva, to transfer Contoso's data from Azure SQL Database into the Lakehouse and initiate data preparation for the upcoming merger between Contoso and Litware Inc.

1. Open **Microsoft Fabric** in a new tab by copy pasting the below link.

```BASH
https://app.fabric.microsoft.com/home
```
>**Note:** After pasting the link into the browser, the page will automatically log in if the user has completed the earlier steps of the **Get Started** instructions. In some cases, **Microsoft Fabric** may prompt the user to enter their **login details** to verify the account.

>**Note:** Wait for the Microsoft Fabric page to load and *close* the top bar for a better view.

2. Scroll down below to the, **"Synapse Data Engineering"** and click on it.

   <img src="media/dataengineer.png" width="800"/>   

3. Click on **+ New Workspace**.

>**Note:** The screenshots in the exercises might differ slightly from the actual lab interface. Adjust your screen resolution as needed to locate and select the required items.

 <img src="media/newworkspace.png" width="800"/> 


4. Copy paste the Worksapce name **<inject key= "WorkspaceName" enableCopy="false"/>** in the **Name** field and click on **Apply** to create the workspace.


|                                               |
 -------------------------------------------------
|<inject key= "WorkspaceName" enableCopy="true"/> |
 -------------------------------------------------

>**Note:** Only use the workspace name provided above.

![works-apply.png](media/labMedia/works-apply.png)

>**Note:** Close any pop-up that appears on the screen.

![gotit-popup.png](media/labMedia/gotit-popup.png)

![gotit-popup.png](media/labMedia/gotit-popup.1.png)



### Create/Build a Lakehouse

Now, let's see how each department can easily create a Lakehouse in the Contoso workspace without any provision. They simply provide a name, given the proper access rights of course!

>**Note:** Verify that you are in the **<inject key= "WorkspaceName" enableCopy="false"/>** **Workspace** created in the earlier steps.

1. Click on **+ New item** button.
   
![task-wb1.png](media/labMedia/lhnew-item.png)

2. In the pop-up window search for **Lakehouse** in the search bar and click on **Lakehouse**.

![task-wb2.png](media/labMedia/lakehousesearch.png)

3. Copy the name **lakehouse** from the following and paste it in the **Name** field.

4. Click on the **Lakehouse schemas** checkbox and then click on the **Create** button.
   
```BASH
lakehouse
```

![task-1.2.3.png](media/labMedia/task-1.2.3.png)


In just a few seconds, the Lakehouse is ready. With the right access, you, as a Data Engineer, can effortlessly create a new Lakehouse. There is no need to set up any storage accounts or worry about network, infrastructure, key vault, Azure subscriptions, etc.


---

### Task 1.2: Use the ‘New Shortcut’ option from external data sources

Now, this is something exciting! This section shows how easy it is to create Shortcuts without moving data. That is the power of OneLake! In this exercise, you will ingest the curated bounce rate data for Litware from ADLS Gen2 using the New Shortcut option. Let’s see how!

1. Click on the **three dots (ellipses)** on the right side of Files.

2. Click on **New shortcut**.

>**Note:** Make sure you create a shortcut under **files** and not under **tables** in the lakehouse explorer pane.

![task-wb5.png](media/labMedia/task-wb5.png)

3. In the pop-up window, under **External sources**, select the **Azure Data Lake Storage Gen2** source.

![task-1.3-ext-shortcut4.png](media/labMedia/task-1.3-ext-shortcut4.png)

>**Note:** Wait for the screen to load.

4. Select **Create new Connection**

5. In the screen below, we need to enter the connection details for the **ADLS Gen2** shortcut, For this, we need to get the details from the Storage Account resource.

![task-1.3-ext-shortcut11.png](media/labMedia/task-1.3-ext-shortcut11.png)

6.Copy the **Data Lake Storage endpoint** from the below and paste it into the **URL** field. Select **Organization account** for the **Authentication Kind**, and then click on **Sign in**.

|                                                    |
-----------------------------------------------------
| <inject key= "storageEndpoint" enableCopy="true"/> |
-----------------------------------------------------

![task-1.3-ext-shortcut-11.png](media/labMedia/task-1.3-ext-shortcut-11.png)

7. Click on your ID to complete the Sign in.

![task-1.3-ext-shortcuts-11.png](media/labMedia/task-1.3-ext-shortcuts-11.png)

8. Click on **Next** button.

![task-1.3-ext-shortcut9.png](media/labMedia/task-1.3-ext-shortcut9.png)

9. Select the **data** and **litwaredata** checkbox and then Click on the **Next** button.

![task-wb6.png](media/labMedia/task-wb6.png)

10. Click on the **Create** button.

![task-1.3-ext-shortcut10.png](media/labMedia/task-1.3-ext-shortcut10.png)

11. And there you go! Your shortcut is now ready! Simply click (do not expand) on the newly created shortcut named **litwaredata**.

![task-wb7.png](media/labMedia/64.1.png)

Prior to Microsoft Fabric, departments in Contoso had to move the data they needed from other departments via time-consuming ETL processes. But look, now they have created shortcuts. No need to move any of this data. That is the power of OneLake!

### Task 1.3: Create Delta tables using Spark Notebook

Now, let’s see how Data Engineer, Eva, got the remaining data into OneLake by creating Delta tables using Spark Notebook. By using a Spark Notebook to create Delta tables, Eva can ensure more reliable, scalable, and efficient data management, which is essential for handling big data workflows.

1. Click on **Workspace** 

![task-wb8S.png](media/labMedia/64.2.png)

2. Click on **New Item** and then select **Notebook**

![task-wb8S.png](media/labMedia/64.3.png)

>**Note:**  If the **Pop-up** appears click on **Skip tour**
 
<img src="media/labMedia/64.4.png" width="800"/>  

3. Click on the **+ Data Sources** button and then select **Lakehouses**

![task-wb8S.png](media/labMedia/64.5.png)

4. Select **Existing Lakehouse with Schema** and then click on ***Add***.

![task-wb8S.png](media/labMedia/64.6.png)

5. Select the **lakehouse** and then click on **Add**

![task-wb8S.png](media/labMedia/64.7.png)

6. Once the notebook is created, paste the **below code** in the existing cell and run the cell by clicking on the **Run cell** icon.

```BASH
import os
import pandas as pd
 
# List all CSV files in the 'litwaredata' folder
file_path = '/lakehouse/default/Files/litwaredata/'
csv_files = [file for file in os.listdir(file_path) if file.endswith('.csv')]
 
# Load each CSV file into a table
for file in csv_files:
    table_name = file.split('.')[0]
    df = pd.read_csv(file_path + file)
    spark.createDataFrame(df).write.mode("ignore").format("delta").saveAsTable(table_name)
```

![task-wb8S.png](media/labMedia/64.8.png)

7. Once a **Green tick** appears in the cell below, **execution is successful**.
8. **Stop the Spark session** from the above.
9. Click on **Lakehouse** in the left navigation bar.

![task-wb8S.png](media/64.9.png)

10. Expand **Tables** and expand **dbo** under Tables. Click on the **three dots** (Ellipses) next to dbo and click **Refresh** from dropdown options.

![task-wb8S.png](media/labMedia/64.10.1.png)

11. View the successfully **loaded tables**.

![task-wb8S.png](media/labMedia/64.10.png)

12. Click on **website_bounce_rate** delta table and view the website bounce rate data.

![StloadtableNew.png](media/labMedia/64.11.png)


You now have all the table in **OneLake** for Contoso to leverage. Next, we proceed with data transformation using Dataflow Gen2 to transform the sales data ingested from Litware. 


### Task 1.4: Leverage Dataflow Gen2 and Data pipelines for a "No Code-Low Code" experience to quickly ingest data with Fast Copy and transform it using Copilot

Using another great feature in Fabric’s Data Factory, called Fast Copy, Contoso’s Data Engineer, Eva, quickly ingests terabytes of data with dataflows, thanks to the scalable Copy Activity in the pipeline. With so much data from Litware, there is bound to be a lot of clean up needed. Let’s step into Eva’s shoes to explore how she used fast copy to ingest data and Copilot to transform it, just in time to derive meaningful customer insights before their big Thanksgiving Sale!

You will experience how easy it is to use Fast Copy to transform 100M rows of Litware's sales data into the Lakehouse.

1. Click on the **experience** button at the **bottom left** corner of the screen (In this screenshot, **Data Engineering** is selected as an "Experience") and then select **Data Factory**.

![task-1.3.1.png](media/labMedia/task-1.3.1.png)

2. Click on **Dataflow Gen2**.

![task-1.2.02.png](media/labMedia/task-1.2.02.png)

3. Click on the drop down of the **New Query** icon and click on the **Get data**.

>**Note:** If **New Query** is not visible due to the screen resolution, please click directly on top part of the **Get data**.

![getdataSs.png](media/labMedia/getdataSs.png)

4. In the pop-up window, scroll down to **OneLake data hub** and click on **lakehouse**.

![task-1.2.04.S1.png](media/labMedia/task-1.2.04.S1.png)

5. If you see a screen similar to the one shown below, click on the **Next** button otherwise move to the next step.

![task-1.2.05.1.png](media/labMedia/task-1.2.05.1.png)

6. Expand **lakehouse**, expand **Files** and expand **data** then scroll down.

![task-wb9.S.png](media/chosedata001.png)

7. Select the **sales_data.csv** checkbox, then **click** on the **Create** button.

![task-wb9.S.png](media/labMedia/chosesalesdata.png)

8. Collapse the **Queries** pane and take a look at the sales dataset (**note that the first row of this dataset is not a header**).

![DFData.png](media/labMedia/DFData.png)

**Let's use Copilot to perform data cleansing.**

9. Click on the **Copilot** button, paste the **prompt** provided below in the following text box and click on the **send** icon.

```BASH
  In the table sales_data csv, apply first row as headers.
```

![df1a2.png](media/labMedia/df1a2.png)


>**Note:** If Copilot needs additional context to understand your query, consider rephrasing the prompt to include more details.

10. Scroll to the right-hand side and observe the **GrossRevenue** and **NetRevenue** columns. You notice that some rows contain empty or null values.

![DFData12.png](media/labMedia/DFData12.png)

>**Let's use Copilot to remove empty rows.**

11. Similarly, paste the prompt below in Copilot and click on the **send** icon.

```BASH
Remove empty rows from GrossRevenue and NetRevenue columns.
```
![DFData12.png](media/rememptyrow.png)

12. Scroll to the right hand side and observe the **GrossRevenue** and **NetRevenue** columns (**there are no empty rows with null values**).

![DFData13.png](media/labMedia/DFData13.png)

>**Note:** Expand the queries pane collapsed earlier.

13. Right-click on the query **sales_data.csv**, and select **Require Fast Copy**.

<img src="media/55.png" width="800"/>  

>**Note:** **Fast copy** enhances the data handling capabilities within Fabric, making **data transfers** faster and more seamless across the platform.

>**Note:** Due to time constraints, we will not publish and run the Dataflow from the Pipeline.

>**Note:** If a pop-up page **Options** appears, scroll down to select **Scale** and tick **Allow use of fast copy connectors** checkbox then click on **OK**.

<img src="media/56.png" width="800"/> 

14. Click on the **close** icon at top right of the **Dataflow** window.

<img src="media/dataflowclose.png" width="800"/> 

15. Click on **Yes.**

![dataflowclose.png](media/closeyes.png)

<!-- 14. click on **Query** dropdown and click on **Add destination** to select "Lakehouse".
  
>**Note:** Click on **Add destination**, select **Lakehouse** if Query is not seen on the screen.

<img src="media/57.png" width="800"/> 

15. Select the connection and click on **Next** button.

  <img src="media/58.png" width="800"/> 

16. Expand Lakehouse, expand the workspace **<inject key= "WorkspaceName" enableCopy="false"/>**, then select **lakehouse**.

17. Copy the table name **sales_data_updated** from below and paste it into the **Table Name** field. Then, click on the **Next** button.

```BASH
sales_data_updated
```

   <img src="media/labMedia/59.png"/> 


18. Click on the **Save settings** button.

<img src="media/60.png" width="800"/> 

19. Click on the **Publish** button.

<img src="media/61.png" width="800"/> -->

Congrats on completing this data transformation exercise!
<!--
### Task 1.5: Explore Task Flows in Microsoft Fabric

To streamline collaboration and project management for the entire team, IT admin Chou set up a task flow within the Microsoft Fabric workspace. Fabric task flow is a workspace feature that enables you to build a visualization of the workflow in the workspace. It helps you understand how items are related and work together, making it easier to navigate your workspace, even as it becomes more complex over time. 
In this exercise, you’ll step into the shoes of each of the IT admins to see how easy it is to set up a task flow in Microsoft Fabric.

1. Click on workspace **<inject key= "WorkspaceName" enableCopy="false"/>** and drag the **bar down** to view Taskflow feature tab.
  
  <img src="media/41.png" width="800"/>
  
2. Click on the **Select a predesigned task flow** button.

>**Note:** If **Select a predesigned task flow** button is not visible, try to reduce the browser size to make it visible.

  <img src="media/42.png" width="800"/>

3. Select **Medallion**, and then click on the **Select** button.

  <img src="media/43.png" width="800"/>

4. The empty Task Flow is created successfully.

  <img src="media/44.png" width="800"/>

5. Click on the **attach** icon on the Bronze data tile.

>**Note:** Please zoom in, if the tiles are not visible.

![databrickssignin.png](media/labMedia/task15.2.png)

6. Select the lakehouse **checkbox** and then click on the **Select** button.

![databrickssignin.png](media/labMedia/task15.1.png)

7. Click on the **attach** icon on the Initial process tile.

![databrickssignin.png](media/labMedia/task15.3.png)

8. Select the lakehouse **checkbox** and then click on the **Select** button.

![databrickssignin.png](media/labMedia/task15.4.png)

**Note:** Similarly, you can attach other fabric items for any taskflow activities.

As you know, Litware was primarily using Azure Databricks with their data stored in ADLS Gen2 before the acquisition. Post merger, as one unified company – Contoso – they decided to leverage Azure Databricks to build and manage reliable data pipelines via Delta Live Tables (DLT). Now, you will see the amazing power of Unity Catalog that Contoso’s data architects used to quickly learn all about Litware's data without having to go through tons of documents. And all by simply leveraging AI and data intelligence.
-->
