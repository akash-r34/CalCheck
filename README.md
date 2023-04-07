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

<h2>CalCheck app</h2>
<p>The CalCheck app is a useful tool for individuals looking to track their calorie intake and monitor their progress towards their weight loss or fitness goals. The project includes a mobile application developed using Flutter, a web application developed using Flask, and a database to store user information.

The mobile application allows users to track their calorie intake by scanning food items or manually entering their food intake. The app also provides users with personalized recommendations based on their weight, height, and activity level.

The application provides a dashboard for users to view their progress towards their goals and visualize their calorie intake through charts and graphs.</p>

<h2>Connect Tableau with Calcheck</h2>
<blockquote><b>Note: This part of our project is still under construction. We will add this in future work.</b></blockquote>
<p>
To connect CalCheck with Tableau, we will the Tableau JavaScript API, which allows us to embed visualizations in web pages and applications.

Here are the steps we will use to connect a CalCheck app with Tableau:
<ol>
<li>Publish your Tableau visualization: You can publish your Tableau visualization to Tableau Server, Tableau Online, or Tableau Public, depending on your requirements.</li>

<li>Get the Tableau JavaScript API: You can get the Tableau JavaScript API from the Tableau Developer Portal.</li>

<li>Integrate the Tableau JavaScript API in your Flutter app: You can use a WebView in Flutter to display the Tableau visualization. The WebView will load an HTML file that includes the Tableau JavaScript API.</li>

<li>Create a Tableau viz: You can create a Tableau viz using the Tableau JavaScript API. You can pass parameters to the viz, such as filters and values.</li>

<li>Connect the Flutter app to the Tableau viz: You can use the postMessage() method of the WebView to send messages to the Tableau viz, and receive messages from the viz.</li>

<li>Display the Tableau viz in your Flutter app: You can display the Tableau viz in your Flutter app using the WebView. The Tableau viz will be responsive, and will adjust to the size of the WebView.</li>
</ol>
<blockquote>Note that embedding Tableau visualizations in a mobile app can be challenging, and may require advanced JavaScript and Flutter skills. We may also need to optimize the Tableau viz for mobile devices, by using appropriate chart types and layouts.</blockquote>
</p>

<h2>Conclusion</h2>
<p>From the visualization results we can see that this app is well-designed and user-friendly, and it can be a valuable tool for anyone looking to improve their health and fitness. The visualizations used in the CalCheck project are effective in presenting the user's calorie intake and macronutrient breakdown in an easy-to-understand format, and the interactive features allow for a more detailed analysis of the data. However, future improvements could include integrating more advanced features such as machine learning algorithms for more personalized recommendations and adding social sharing features to encourage users to share their progress with friends and family</p>

<h2>Future work</h2>
<p><b>'Connect Tableau with Calcheck'</b> section will be completed in future.
We also plan on integrating more advanced features such as machine learning algorithms for more personalized recommendations and adding social sharing features to encourage users to share their progress with friends and famil</p>
