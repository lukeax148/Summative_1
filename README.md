# Summative_1
Summative_1 python notebook

Introduction 

Two of the most important responsibilities carried out by the  Bank of England are maintaining monetary and financial stability and promoting economic growth in the United Kingdom. This responsibility is completed in a myriad of ways throughout the bank. One of the ways that financial stability is understood is by comparing the growth and decline of gross domestic product against other countries and respective currencies across the globe. The World Bank is an international financial institution that provides financial and technical assistance to developing countries for various development projects and initiatives. The World Bank collects vast amount of economic, social, and environmental data from several countries throughout the world. The World Bank Data covers a wide range of indicators related to global development. Some of the economic Indicators that can be retrieved from the from the World Bank Data includes Gross Domestic Product (GDP), inflation rates, and employment data. This data is crucial for researchers, analysts and the public to monitor and understand global and country-specific trends.  Therefore, I propose creating a data product using that is able to access specific data related to the maintenance of monetary and financial stability in the United Kingdom. To achieve this I plan to utilise the World Bank Data web API (application programming interface) to retrieve the data collected by the World Bank.

Design 

The project aimed to develop a data product that retrieves and visualizes data from the World Bank Data web API . For the purposes of creating a minimal viable product or prototype that could be used to demonstrate the concept of the data product as well as its future potential I chose to limit the data series that we are retrieving from the World Data web API to one data series. The chosen data series is 'NY.GDP.MKTP.CN' and is used to indicate Gross Domestic Product (GDP) data for countries across the globe. To ensure that the data product is as effective as possible for researchers and analysts alike I intend to allow the user to enter the countries they wish to review as well as the time series range they want to review the Gross Domestic Product (GDP) data for. Lastly I intend to design functionality that allows the user to view the data as a graphical visualisation. Graphical visualisations of time series data makes it considerably easier to spot trends and interpret the data when compared to time series data presented in tabular format. To achieve the objective of creating a robust and user-friendly data product that allows users to explore and understand GDP trends across the globe I have decided to utilise Jira as my project management tool and Agile planning techniques.

Effective project management is one of the key factors of successfully completing a project and the choice of a project management tool plays a pivotal role in this process. I have chosen Jira as my project management tool for several reasons. Jira offers features that align seamlessly with Agile principles. Agile boards, backlog management tools, and sprint planning capabilities make Jira an useful asset for teams adopting Agile methodologies but not having much experience with them. Furthermore, another feature of Jira that makes it stand out compared to its competitors is its robust support for customizable work flows and issue tracking. Jira allows users to design and automate work flows customised to their specific processes, ensuring that the task management platform is effective regardless of the nature of the project.

Some of the Agile planning techniques I used to plan and develop my data product included creating a product backlog. The product backlog stored in Jira contains all the necessary tasks to accomplish the or design and user goals. The main tasks that were identified in order  to create the minimal viable product included; setting up the project environment, retrieving data from the World bank Data web API and implementing some data cleaning and processing techniques so that the data can be presented in clear graphical format. Once the backlog had been set up we decided to use sprints to create the minimal viable product as efficiently as possible. In Agile project development, a sprint is a designated block of time during which a specific set of work is completed. The development stage was broken into 3 different sprints in which we focused on creating specific functionality for the data product. The first sprint was used to set up the project environment and create a function capable of retrieving Gross Domestic Product data for specific countries and time series’  and store it as a pandas data frame. The second sprint was dedicated to completing testing of the data retrieval function. Lastly, the third sprint was used to create a function capable of transforming the retrieved data stored as a data frame in tabular format into a graphical representation of that data.

Implementation

The primary objective is to develop a tool that retrieves and visualizes gross domestic product data from the World Bank web API for selected countries and time series’. In order to do this I started by importing the ‘wbgapi’, ‘pandas’, ‘seaborn’ and ‘pyplot’ python libraries as they would be essential for creating the data retrieval and graphical visualisation functions.

The function created to retrieve the data from the World Bank web API is defined as ‘GDP_data’. The ‘GDP_data’ function utilises the ‘wbgapi’ and ‘pandas’ libraries. The function is designed to accept multiple parameters including, country code or codes, start date, and end date. The function returns a Pandas data frame, using the .DataFrame() method, which contains Gross Domestic Product data for the specified countries and time series.  It specifies the indicator code for Gross Domestic Product as 'NY.GDP.MKTP.CN'. 

The data products second function was defined as ‘create_graph’. the ‘create_graph’ function utilises the ‘pandas’, ‘seaborn’ and ‘pyplot’ python libraries. Fundamentally, the function allows the users to generate line plots using the ‘seaborn’ .lineplot() method. However, before the line plot is created the function sets the index of the data frame to the 'Country' column and transposes the data for easier plotting. The line plots are created with a legend and a customized colour palette by editing the parameters offered in the .lineplot() method.

Once the functions had been created I did some manual testing of the data product’s functionality. The tools functionality is demonstrated using two examples. First, Gross Domestic Product data for the United States, Great Britain, and China is fetched from 2010 to 2022. The resulting data frame is defined as ‘x’. the data frame ‘x’ is then visualized using the ‘create_graph’ function. Second, Gross Domestic Product data for Australia and Germany is fetched from 2012 to 2023 and visualized. Furthermore, the tool incorporates automated testing using the ‘doctest’ python library, This ensures that the code is well-documented and adheres to the specified functionality. This further reinforces the data products reliability. 

Evaluation 

The design of a data product is a critical aspect of its effectiveness and user-friendliness.  There are several design choices which aided in the development and overall functionality of the data product.
The data product’s code includes informative docstrings that provide clear instructions on how to use the ‘GDP_data’ function. Examples are provided, demonstrating the expected inputs and outputs. This additional clarity helps users in understanding the purpose of the function and how to interact with it. Overall this feature makes he data product far more user friendly than it would be without the docstrings. The design of the product demonstrates modularity by separating the data retrieval function ‘GDP_data’ from the data visualization function ‘create_graph’. This modular design promotes re-usability. This will allow users to review the Gross Domestic Product data for various analyses and visualizations repeatedly and efficiently. I utilised several external python libraries, such as ‘seaborn’ and ‘plotly express’ for data visualization. This is a effective design choice as these libraries offer a set of tools and functionality for creating interactive and aesthetically pleasing visualizations without the need for difficult and long manual coding.

On the other hand there are several design choices which were not implemented that could have improved the overall functionality and effectiveness of the data product. For instance, even though I have used the docstrings to indicate how the ‘GDP_data’ function accepts input the product could be further improved by incorporating parameter validation checks. Ensuring that the user input country codes are valid and exist in the World Bank database would provided an added level of user friendly appeal. Additionally, verifying that the start and end dates are within a reasonable range would provide similar clarity for the user. Enhancing the error handling functionality to provide more informative messages in case of API request failures or incorrect input parameters will help users identify and address issues more efficiently. 

Another way of expanding the data products functionality would be to modify the ‘GDP_data’ function to allow users to select different economic indicators rather than being restricted to 'NY.GDP.MKTP.CN'. This would make the product more flexible as it would cater to more diverse analytical needs. Furthermore, the data product could be expanded to introduce additional functions for exploratory data analysis. For example, functionality could be created to calculate growth rates over time or to compare Gross Domestic Product data with other economic indicators. This would enhances the products usability and target audience.  Lastly, interactive visualization could be developed using the functionality offered by the ‘plotly.express’ library, to allow users to interact with the graphs. This can include cursor hover-over actions and the ability to select or deselect specific countries for a more interactive exploration experience.

References 

Herzog, T. (2021) Introducing WBGAPI: A new python package for accessing World Bank data. Data Blog






















