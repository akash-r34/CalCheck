# CalCheck: A Diet planner app

A project done for the course CSE3020 - Data Visualization under <b>Dr. Parvathi. R</b>

<h3>Team members</h3>
<ul>
<li><b>AKASH R 20BCE1501</b> Github: <a href="https://github.com/akash-r34">akash-r34</a></li>
<li><b>ABRAR AHAMED 20BCE1437</b> Github: <a href="https://github.com/Abrar-Ahamed">Abrar-Ahamed</a></li>
</ul>

<h2>Abstract</h2>

<p>This project aims to develop a mobile app that assists users in achieving their health and fitness goals by recommending default diets based on their BMI and enabling them to build customized diets. The app will also provide users with insights into the nutrient content of various foods through visualizations, helping them make informed decisions about their dietary choices. To achieve this, the app will leverage Tableau to create interactive and informative visualizations of food and nutrient data. The app will be designed to be user-friendly and accessible to people of all ages and backgrounds. By providing users with personalized diet recommendations and valuable nutritional information, the app aims to help users make healthier choices and improve their overall health and well-being.</p>


<h2>Dataset</h2>

<p>You can find all the datasets used in this project here -> <a href="https://github.com/akash-r34/CalCheck/tree/main/Dataset">Datasets</a></p>

<p>First we construct the <a href="https://github.com/akash-r34/CalCheck/blob/main/Dataset/Food_data_generated.xlsx">Indian food dataset</a> with the help of a <a href="https://github.com/akash-r34/CalCheck/blob/main/Dataset/Mining%20food%20data/Mining_food_and_diet_data.ipynb">python code</a> that uses the requests library to make HTTP requests to the <a href="https://fdc.nal.usda.gov/">USDA FoodData Central (FDC)</a> API to extract data on various food items. The code creates a dataset of Indian food items by specifying a list of FDCIDs of those items available in the FDC database. It extracts information such as the name of the food item and its nutrient composition in a JSON format. The extracted information is stored in a list of dictionaries, where each dictionary corresponds to a single food item. The code also includes a step to mine 10 items per code block to identify faulty API requests, if any. We also assign a dietID to every food item to create <a href="https://github.com/akash-r34/CalCheck/blob/main/Dataset/Food_data_generated_with_dietIDs.xlsx">Default diet plan dataset</a>.</p>

<p>Next, we use another <a href="https://github.com/akash-r34/CalCheck/blob/main/Dataset/Mining%20min.%20macros%20for%20users%20and%20recommend%20diet%20plans/Mining_user_macros_based_on_BMI.ipynb">python code</a> that generates data for 100 users in the form of height and weight. It then calculates the BMI of each user and categorizes them into four categories based on BMI - "Underweight", "Normal", "Overweight", "Obesity". The code then mines the website "https://www.calculator.net/macro-calculator.html" to find the minimum macro intake data for each user based on their height and weight. It merges the BMI and macro intake data into a single pandas dataframe and exports it to an excel file to create a <a href="https://github.com/akash-r34/CalCheck/blob/main/Dataset/Min_macros_for_height_and_weight.xlsx">User and recommended minimum macros intake dataset</a>.</p>

<p>Finally, we use a <a href="https://github.com/akash-r34/CalCheck/blob/main/Diet_recommendation.ipynb">python code</a> for assigning diet IDs to users based on their minimum nutrient intake level. The code reads in two datasets, the first being a user macros dataset and the second being a diet plan dataset containing diet IDs and their corresponding macro levels. The code then aggregates the diet plans by their macro levels and creates a heatmap for better interpretation. The aggregated data is then converted into a pandas dataframe. Next, the code assigns recommended diet IDs to all users based on their minimum macro levels intake. If the minimum macro levels intake of the user is less than or equal to a diet plan's macro level, then recommend that plan to the user. Finally, the resulting dataset is exported as an Excel file to create a <a href="https://github.com/akash-r34/CalCheck/blob/main/Dataset/Diet_recommendation_based_on_user.xlsx">User diet recommendation dataset</a>.</p>

<h2>Data Visualization</h2>

<p><b>Software used: Tableau</b><br>
  You can find all the visualizations done in this project here -> <a href="https://github.com/akash-r34/CalCheck/tree/main/Visualization%20images">Visualization images</a><br>
  You can find all the Tableau workbooks used in this project here -> <a href="https://github.com/akash-r34/CalCheck/tree/main/Data%20Visualization%20-%20Tableau">Visualization workbooks</a><br>
  </p>
