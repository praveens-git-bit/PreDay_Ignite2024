## Exercise 3: Building an AI-Powered Chatbot with Microsoft Fabric and Azure AI Studio

Contoso encountered a major issue with customer churn, especially among millennials. The executives at Contoso struggled to understand this customer segment and figure out how to earn their loyalty. Despite having extensive data from customer interactions, surveys, and market research, Contoso found it difficult to pinpoint the root cause of the churn and determine effective solutions.

The main problem was the lack of integration in their existing systems. This prevented Contoso's executives from utilizing their data for root cause analysis and strategic insights, which in turn, hampered their ability to improve marketing strategies, product offerings, and customer experiences.

To solve the data silos issue, Contoso implemented an advanced AI solution using Azure OpenAI, Azure AI Search, and Microsoft Fabric. Once the team discovered that millennials were leaving because they couldn't find products, they developed an Azure OpenAI-powered shopping assistant to help with product search and recommendations.

In this exercise, we will learn how they achieved this!

### Task 3.1: Integrate Fabric data with Azure AI Studio using Azure AI Search and Vector Indexing for Hybrid Search

Let’s step into the shoes of Eva, the Data Engineer, as she launches Azure AI Studio and leverages data stored in Microsoft OneLake as knowledge base.


1. Navigate back to the Microsoft Fabric tab on your browser.
 
2. Click on **Workspaces** and select **<inject key= "WorkspaceName" enableCopy="false"/>**.
 
![task-1.3.02.png](media/labMedia/task-1.3.02.png)
 
3. Click on **Filter** and select **Lakehouse**.
 
![task-1.3-ext-shortcut1.png](media/labMedia/task-1.3-ext-shortcut1.png)
 
4. Click on the **lakehouse**.
 
>**Note:** There are 3 options for lakehouse, namely Lakehouse, Semantic model (Default) and SQL endpoint. Make sure you select the **Lakehouse** option.
 
![task-wb11.png](media/labMedia/task-wb11.png)
 
5. Click on the three dots next to **Files** folder and select **New subfolder**.

![task-wb11.png](media/labMedia/bot1.png)
 
6. Enter name of folder as **input** and click on **Create** button.
 
![task-wb11.png](media/labMedia/bot2.png)

7. Click on the three dots next to the newly created folder **input** and select **Upload**, then **Upload files**.

![task-wb11.png](media/labMedia/bot3.png)
 
8. In the Upload files window, click on the browse icon.

![task-wb11.png](media/labMedia/bot4.png)
 
9. Copy the following path **C:\LabFiles\01_Pre_Day\artifacts\aistudio\input**, paste it into the **File Name** field, and press Enter on the keyboard.
10. Drag and select all the files in the folder and click on **Open** button.

![task-wb11.png](media/labMedia/bot5.png)
 
11. Click on **Upload** button.

![task-wb11.png](media/labMedia/bot6.png)
 
12. Wait for the files to get uploaded and click on close button.

![task-wb11.png](media/labMedia/bot7.png)
 
13. Click on the three dots next to the **input** folder and click on **Properties** then click on **Copy to clipboard** button next of the URL path, save it on your notepad and remove **/input** from the end of the URL. This will be used in the further step.

![task-wb11.png](media/labMedia/fabricurl.png)

14. Copy paste the below URL in the new browser tab to open Azure AI Studio Project and click on the **prj-ignite..**.

```BASH
<inject key= "project" enableCopy="true"/>
```
![task-wb11.png](media/labMedia/selectproject.png)

>**Note:** Click on the **Expand** icon, if the left navigation is hidden.

![Task 3.1_4.png](media/prjexpand.png)

15. To connect with data stored in Onelake, **scroll down** in the left navigation pane and click on **Data**.

![Task 3.1_4.png](media/labMedia/clickdata.png)

>**Note:** Due to the screen resolution you might see a difference in the screenshot and actual lab interface, Scroll up to proceed with the next steps.

16. Under the connect, create, or manage your data , click on **+ New Data** button

![Task 3.1_4.png](media/labMedia/newdata.png)

17. Click on the **+ New Connection**.

![Task 3.1_6.png](media/labMedia/newconnect.png)

18. In the **Service** dropdown select **Microsoft OneLake**. 
19. In the **OneLake Artifact URL** field, paste the URL that you copied in the notepad earlier (step13). 
20. In the **Authentication method** dropdown select **Microsoft Entra ID based** 
21. In the **Connection name** field enter **fabric_onelake**. Finally click on the Create connection button.

>**Note:** Ensure that you have removed **/input** from the URL to avoid connection failure.

![Task 3.1_7.png](media/labMedia/url.png)

22. In the **Data source** dropdown select **fabric_onelake**, click on the **input** radio button and click on the **Next** button.

![Task 3.1_7.png](media/labMedia/storagepath.png)

23. In the Data name field enter **input01** and click on **Create** button.

![storagepath.png](media/labMedia/createdata.png)

24. Once the connection is created, the **files** can be viewed under the input folder.

![successdata.png](media/labMedia/successdata.png)




### Task 3.2 : Establish Azure OpenAI, Azure AI Content Safety, and AI Search Connections in Azure AI Studio.

Contoso integrated all of their data sources using Microsoft Fabric, including customer feedback, sales records, social media interactions, and encompassing internal company policy documents such as SOPs and research articles on customer behavior into Azure AI Search. This created a unified, searchable knowledge base.. Let’s step into Data Engineer, Eva’s shoes to see how.

1. Navigate back to the **Hub..** by clicking on it. To expand the sidebar, click on the **Expand icon**.

>**Note:** If any **item** on the screen is not visible as shown in the screenshot, adjust your browser screen resolution as per the need.

   ![Task-2.3_10.png](media/selecthub.png)

2. In Azure AI hub, scroll down the left navigation bar  to the **Shared resources** section and click on **Connections** and scroll up.
3. Click on the **+ New Connection** button.

>**Note:** If the left side bar is collapsed, please click on **expand** from the above of the **left side bar** and scroll below.

![Task-2.3_10.png](media/labMedia/ai_3.png)
	
4. Select **Azure OpenAI Service**.

![Task-2.3_10.png](media/labMedia/ai_4.png)

5. You will find two Azure OpenAI resources, gpt-4 (1) and gpt-4o (2). Create a connection with both by clicking on the **Add connection** button.

![Task-2.3_10.png](media/labMedia/ai_5.png)

6. Once the **OpenAI services are connected**, click on **Back to select an asset type**.

![Task-2.3_10.png](media/labMedia/ai_6.png)

7. Select **Azure AI Search**.

![Task-2.3_10.png](media/labMedia/ai_7.png)

8. Click on **Add connection**.

![Task-2.3_10.png](media/labMedia/ai_8.png)

9. Once the **AI Search is connected**, click on the **Close** button.

>**Note:** If the **close** button is not visible, please reduce the screen size of the browser.

![Task-2.3_10.png](media/labMedia/ai_9.png)

10. Notice that **Azure Open AI** and **Azure AI Search** connections are established successfully.

<img src="media/5.1.png" width="800"/>

11. Click on **All projects** in the left navigation pane and select the **pre-created Project** displayed on your screen.
  
<img src="media/2.png" width="800"/>

### Task 3.3 : Create and configure a Vector Index in Azure AI Studio with Azure AI Search and OpenAI Connections.

Contoso indexed OneLake data in Azure AI Studio to improve the efficiency of searching and retrieving large datasets, enabling faster, data-driven decision-making across the organization. This approach enhances accessibility, scalability, and workflow for data scientists and analysts, while also providing a better user experience and reducing operational costs.. Let’s see how Eva, the Data Engineer, indexed OneLake data in Azure AI Studio.

1. Scroll down in the left navigation pane, click on **Indexes** and then click on the **+ New index** button.

<img src="media/22.png" width="800"/>

2. In the Data source dropdown, select **Azure AI search**.

<img src="media/23.png" width="800"/>

3. Click on the **Next** button.

<img src="media/24.png" width="800"/>

4. In the **Select Azure AI Search service** dropdown, select **srch..**.

>**Note:** If you get an error like "Unable to load search service indexes.Request failed with status code 403." please proceed by selecting Index.

5. In the **Select Azure AI Search index** dropdown, select **cosmosdb-index** and then click on the **Next** button.

<img src="media/25_1.png" width="800"/>

6. In the **Azure OpenAI connection** dropdown, select **<inject key= "openai2" enableCopy="false"/>** (Pre-Selected OpenAI is not GPT-4o, click on the drop down and select the OpenAI starting with name **openAI2**).
   
7. Click on the **Next** button.

<img src="media/26_1.1.png" width="800"/>

8. Click on the **Next** button.

<img src="media/27_1.png" width="800"/>

9. Click on the **Create vector index** button.

<img src="media/28_1.png" width="800"/>

>**Note:** Please wait for the index to load. It takes approximately 1-2 minutes.

10. A screen similar to the screenshot below with the text **Index not found** will appear. Wait until the screen loads and click on **Indexes**.

<img src="media/28.png" width="800"/>

11. Check the Status shown as **Ready** and continue with the next task.

<img src="media/29_1.png" width="800"/>


### Task 3.4 : Setup and use Prompt Flow in Azure AI Studio.

Prompt flow in Azure AI Studio offers a comprehensive, streamlined environment for creating AI applications. It provides a visual interface for orchestrating flows, and enables iterative prompt engineering. Azure AI Studio includes built-in evaluation tools, seamless deployment options, and integration with Azure's ecosystem. It also offers enterprise-level security and scalability, making it ideal for developing, testing, and deploying sophisticated AI solutions efficiently. Let’s explore how Contoso deployed and tested a Prompt flow.

1. Click on **Prompt flow** from the left navigation pane and then click on the **+ Create** button.

<img src="media/30.png" width="800"/>

2. Scroll down and click on the **Upload** button in the Upload from local section.

<img src="media/31.png" width="800"/>

3. Click on the **Zip file** radio button and then click on **Browse**.

<img src="media/32.1.png" width="800"/>

4. Copy paste the following path **C:\LabFiles\01_Pre_Day\artifacts\aistudio** in the **File name** field and hit **Enter** on the Keyboard.

5. Click on **shopping-assistant-prompt-flow** zip folder and then click on the **Open** button.

   ![promptziploc.png](media/labMedia/promptziploc.png)

6. In the **Select flow type** dropdown, select **Chat flow** and then click on the **Upload** button.

>**Note:** If clicking on the Upload button doesn't redirect you to the Prompt Flow screen, click the Upload button again twice or thrice. If it still doesn't work, refresh the page and try uploading again.

<img src="media/34_1.png" width="800"/>


7. Click on the **Start compute session** button.

>**Note:** It will take approximately 2-3 minutes to start the compute session. Please wait for some time.

<img src="media/35_1.png" width="800"/>

8. Scroll down to the **lookup** node in the Prompt flow graph and click on it.

9. Click on the **Validate and prase input** button in the flow.

10. Once it is validated, click on edit option for **mlindex_content** as shown in the below screenshot.

<img src="media/35_2.1.png" width="800"/>

11. Click on the **acs_index_connection** dropdown and select the **srch....**.

12. Click on the **acs_index_name** dropdown and select the **cosmosdb-index**.

13. Click on the **embedding_type** dropdown and select the **Azure OpenAI**.

14. Click on the **aoai_embedding_connection** dropdown and select the **<inject key= "openai2" enableCopy="false"/>**.

15. Click on the **Save** button.

<img src="media/35_4.1.png" width="800"/>

16. Click on **prompt_for_looks** in the Graph and then click on the **Validate and prase input** button in the **Flow** under input sections.

>**Note:** If the **Validate and Parse Input** button is not visible on the screen, scroll down to locate it.

<img src="media/35_5.1.png" width="800"/>

17. Once it is validated, click on the **Connection** dropdown and then select **<inject key= "openai" enableCopy="false"/>**.

>**Note:** Scroll up to the heading **prompt_for_looks** to find the **Connection** drop-down below it.

<img src="media/35_5.2.png" width="800"/>

18. Click on **max_token**, remove the preset token, and set it to **100**.

<img src="media/max_token.png" width="800"/>

19. Click on the **Chat** button.

<img src="media/36_1.png" width="800"/>

>**Note:** Close any pop-up appears on the screen as seen in the below screenshot.

![popup.png](media/chatpop.png)

20. Paste the **below question** in chat box replacing the default question.

```
Can you show me some yellow indian dresses for a wedding in Udaipur?
```
21. Click on the **send** icon.

<img src="media/37_1.png" width="800"/>

22. Observe the **response**.

<img src="media/39_1.png" width="800"/>

Once the Prompt flow is deployed as an endpoint, It can be consumed in the webapplication. Let's see how the response look like in the webapp.
 
23. Open a new tab and Copy-paste the below URL in the broswer address bar, and then press **Enter**.

```BASH
<inject key= "shoppingcopilotwebapp" enableCopy="false"/>
```

24. Click on the **terms and conditions checkbox** and then click on the **Login** button.

![Contosoterms.png](media/labMedia/Contosoterms.png)
 
25. Click on the **Copilot icon** at the bottom right of the page.
 
![Copiloticonwebapp.png](media/labMedia/Copiloticonwebapp.png)

26. Click on any of the **pre-populated questions**.
 
![question1webapp.png](media/labMedia/question1webapp.png)
 
27. Observe the **response**.
  
![Answer1webapp.png](media/labMedia/Answer1webapp.png)
 
With their new Shopping Copilot, Contoso was able to provide their customers with an online shopping experience that has an in-store feel. This simulates a personalized shopping experience that helps increase customers’ engagement with enhanced data insights.
