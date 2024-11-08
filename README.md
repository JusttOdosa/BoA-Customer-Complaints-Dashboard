# BoA-Customer-Complaints-Dashboard
This analysis examines customer complaints data from Bank of America spanning 2017-2023. The project focuses on understanding complaint patterns, response effectiveness, and providing actionable insights for improving customer service.
OVERVIEW
Bank of America (BoA), a financial institution based in the United States, has received numerous customer complaints over the years.To address this, BoA has decided to analyze consumer complaints related to its financial products and services from 2017 to 2023. A comprehensive dataset has been provided, containing detailed information on each complaint, including submission and receipt dates, associated products and issues, and BoA’s responses. This case study invites analysts and policymakers to explore the dataset to uncover insights and develop strategies for addressing customer complaints more effectively.

OBJECTIVE
The primary goal of this case study is to analyze the data, identify patterns, and propose informed, data-driven recommendations that BoA can implement to effectively address and reduce customer complaints.

Here's the text without the image references:

Importing Data
The CSV file containing the data set was opened in google sheets to get an overview of the data.

The CSV file was also imported into Jupyter notebook to facilitate writing python codes to help in the analysis of the data which contained 62516 rows × 12 columns.
 
Data Cleaning
Before further analysis can take place the Data has to be ready for analysis, which is where Data cleaning comes in, to clear out all inaccuracies, empty cells etc present in the dataset to be analyzed.

With python empty cells were discovered in 4 columns out of the 12 columns in the Data.

Checking the empty cells of the "Sub-Product", the empty cells all had the same "Product" categories -  Checkings or Savings Account. The MAX (most occurring)  "Sub-Product" category of values with the  "Product" categories -  Checkings or Savings Account was "Checking account".

Thus, we will be replacing the empty cells in the "Sub-Product" column with "Checking account". 

The 'Sub-Issue" column recorded 10858 empty cells, and from the column description, possible values are dependent on Product and Issue, and not all Issues have corresponding Sub-issues. Since the 'Sub-Issue' values are dependent on the 'Product' and 'Issue' columns, I created a mapping of unique 'Product-Issue' combinations to their corresponding 'Sub-Issue' values. I use a defaultdict to efficiently store and retrieve this information.

For each row with a missing 'Sub-Issue' value, the would check if the 'Product-Issue' combination for that row exists in the mapping. If it does, it would assign the first 'Sub-Issue' value from the list associated with that 'Product-Issue' combination. If the 'Product-Issue' combination is not found in the mapping, it would assign a value of 'Unknown' to the 'Sub-Issue' column.

There were 2175 null values for the "Company public response" column, this being the company's optional, public-facing response to a consumer's complaint, Companies can choose to select a response from a pre-set list of options that will be posted on the public database.

Since the "Company public response" column is optional and designed to provide public-facing responses to consumer complaints, missing values are likely due to companies choosing not to respond publicly. Therefore, the absence of data here is meaningful in itself and may indicate something about the company's communication strategy, customer engagement practices, or the severity of complaints.

Since companies commonly select from a predefined set of responses, all nulls for the "Company public response" column be replaced "Response Not Provided" to maintain the integrity of the data.

With 1494 null values in the "Timely response?" column stating Whether the company gave a timely response (Yes/No), all null values will be replaced with "Not Recorded", If nulls indicate cases where timeliness wasn't recorded, imputing with "Not Recorded" preserves this ambiguity and avoids assuming timeliness where it may not apply.

The "State" column of the dataframe showing the state of the mailing address provided by the consumer was in the abbreviated format which was then cleaned to display the full name of the states.

Exploratory Data Analysis
Exploratory Data Analysis (EDA) is an important first step in data science projects. It involves examining and visualizing data to understand its main features, find patterns, and see how different variables are connected. This process helps in spotting unusual data points, understanding the overall structure of the data, and identifying relationships between different factors.(Credits geeksforgeeks). 

Shows how the total number of complaints has fluctuated over the years, with a general upward trend peaking in 2022. 

Further exploration showed that the top complaint products are Credit card, Mortgage, and Bank account or service while the top complaint issues are Transaction issue, Incorrect information on credit report, and Problem with a credit reporting company's investigation.

With an average response time of 1.22 days with over 90% of responses being considered timely.

The purpose of the analysis is to identify the most common complaint issues for each product, so that BoA can prioritize addressing these recurring problems and improve their overall customer service.

Data Visualization
Cleaned Data was imported into Tableau for visualization and creation of the dashboard.

The very first visualization shows the number of customer complaints overtime, with the highest and lowest number being highlighted.

Recurring Issues were visualized with bar charts to highlight the most common problems faced by consumers and BoA's effectiveness in addressing them. The Top 5 Issue, Sub Issue, Product and Sub Product were visualized.

Hovering above the visual gives extra information about it.

The Complaints by State was also displayed, showing the number of complaints from each state (Alaska and Hawaii included). It was displayed in a map format.

The dashboard contains a year drop down. This acts as a filter for the dashboard, getting insights for each year for better understanding of the data.

Recommendations
Customer Service Enhancement: Special teams of experts are created to focus only on handling the most recurring complaints drivers. An automatic system that immediately sends a message to customers when they submit a complaint, so they know their complaint was received can be set up to enhance customer service.

Process Improvement: Ready-to-use message templates can be created  for common customer problems (like billing issues or account problems), so staff can respond quickly and consistently without writing everything from scratch each time. 
A rule can be made that every customer must get some kind of first response within two days (48 hours) of making their complaint, even if it's just to let them know someone is working on it.

Preventive Measures: Creation of helpful guides, videos, and training materials to teach customers how to use bank services correctly and avoid common problems before they happen, like explaining how credit card fees work or how to avoid overdraft charges. 
Examination of the bank fees and rules that customers complain about the most (like overdraft fees or minimum balance requirements) in order to determine if changes can be made to them to be more customer-friendly and easier to understand.

Culture and Training: Bank employees can be treated to better and more frequent training to help them understand customer problems, handle difficult situations, and provide excellent service, like teaching them new skills through real-world examples and practice sessions.
Set up a rewards program that gives employees recognition or bonuses when they help prevent complaints from happening in the first place, like when they spot and fix a potential problem before a customer needs to complain about it.
