# sales-data-analysis
<p align="justify">
Sales analytics is the process used to identify, model, understand and predict sales trends and sales results while helping in the understanding of these trends and finding improvement points. In this project I will do a sales analysis by answering 5 important questions that have a correlation with company goals
</p>

<h6>
Author&ensp;&ensp;&ensp;&nbsp; : &ensp;Achmad Adyatma Ardi <br>
Email&ensp;&ensp;&ensp;&ensp;&ensp;&nbsp;: &ensp;adyatmaardi@gmail.com <br>
LinkedIn&ensp;&ensp; :&ensp; https://www.linkedin.com/in/adyatmaardi/ <br>
</h6>
<hr>

<div align="justify">
  <h4>Prerequisites :</h4>
  <ol>
    <li>Install Jupyter Notebook</li>
    <li>Install necessary Python-module
        <ul>
          <li><a href ="https://pypi.org/project/os-sys/">OS</a> module - it provides for creating and removing a directory (folder), fetching its contents, changing and identifying the currect directory, etc. <br>install >>> [pip install os-sys]</li>
          <li><a href ="https://pypi.org/project/pandas/">pandas</a> module - it makes you to use high-performance data structures and data analysis tools. <br>install >>> [pip install pandas]</li>
          <li><a href ="https://pypi.org/project/DateTime/">DateTime</a> module - it supplies classes for manipulating dates and times.  <br>install >>> [pip install DateTime]</li>
          <li><a href ="https://matplotlib.org/stable/users/installing/index.html">matplotlib</a> module - it used to create 2D graphs and plots by using python scripts. It makes things easy for plotting by providing feature to control line styles, font properties, formatting axes etc. <br>install >>> [python -m pip install -U matplotlib]</li>
          <li><a href ="https://seaborn.pydata.org/">seaborn</a> module - it used for making statistical graphics in python. It builds on top of matplotlib and integrates closely with pandas data structures. Seaborn helps you explore and understand your data. <br>install >>> [pip install seaborn]</li>
          <li><a href ="https://docs.python.org/3/library/itertools.html">From itertools import [combinations]</a> module - it is a collection of the element where the order doesn't matter. Python itertools module provide the combination() method to calculate the combination of given data. <br>install >>> [pip install combination-py]</li>
          <li><a href ="https://docs.python.org/3/library/collections.html">From collections import [Counter]</a> module - it is a subclass of dict that's specially designed for counting hashable objects in Python. It's a dictionary that stores objects as keys and counts as values. To count with Counter, you typically provide a sequence or iterable of hashable objects as an argument to the class's constructor. <br>install >>> [pip install Counter]</li>
           <li><a href ="https://pypi.org/project/warn/">warnings</a> module - it used to control how the warnings should be treated. <br>install >>> [pip install warn]</li>
        </ul>
    </li>
  </ol>
  </div>
<hr>

<div align="justify">
  <h4>Objectives :</h4>
  <ol>
    <li>To do analysis for sales purposes</li>
    <li>Task :<br>
    &ensp;&ensp;(1) task 1 | Merge 12 months of sales data into one csv file<br>
    &ensp;&ensp;(2) task 2 | Clean up data<br>
    &ensp;&ensp;&ensp;&ensp;(2.1) Remove of NaN (Not a Number) values<br>
    &ensp;&ensp;&ensp;&ensp;(2.2) Dealing with datetime column 'Order Date'<br>
    &ensp;&ensp;&ensp;&ensp;(2.3) Convert original dataset columns to the correct type<br>
    &ensp;&ensp;&ensp;&ensp;(2.4) Augmenting data with additional needed columns<br>
    &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;(2.4.a) Month column - int64<br>
    &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;(2.4.b) Sales column - float64<br>
    &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;(2.4.c) City column - 'string'<br>
    &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;(2.4.d) Hour column - int64<br>
    &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;(2.4.e) Minute column - int64<br>
    &ensp;&ensp;&ensp;&ensp;&ensp;&ensp;(2.4.e) Count column - int64<br>
    &ensp;&ensp;(3) task 3 | Analysis - Answer 5 important questions<br>
    &ensp;&ensp;&ensp;&ensp;(3.1) Question 1 | What the best month for sales ?<br>
    &ensp;&ensp;&ensp;&ensp;(3.2) Question 2 | What city had the highest number of values ?<br>
    &ensp;&ensp;&ensp;&ensp;(3.3) Question 3 | What time should we display advertisements to maximize the likelihood of customer's buying product<br>
    &ensp;&ensp;&ensp;&ensp;(3.4) Question 4 | What products are most often sold together ?<br>
    &ensp;&ensp;&ensp;&ensp;(3.5) Question 5 | What product sold the most ? why do you think it sold the most ?<br>
    </li>  
  </ol>
  </div>
  <hr>
  
<div align="justify">
  <h4>Analytical Approach :</h4>
  <ol>
    <li>Question 1 | What the best month for sales ?<br>
    &ensp;&ensp;(-) we use groupby() method to split data into groups based on 'Month' column that has been added using sum() method<br>
    &ensp;&ensp;(-) we use bar plot to visualize the results<br>
    &ensp;&ensp;(-) number of Months act as X - axis, meanwhile amount of sales act as Y - axis<br>
    &ensp;&ensp;(-) target the highest value from bar plot then give the different color to it<br>
    &ensp;&ensp;(-) interpret the results<br>
    </li>
    <li>Question 2 | What city had the highest number of values ?<br>
    &ensp;&ensp;(-) we use groupy() method to split data into groups based on 'City' column that has been added using sum() method <br>
    &ensp;&ensp;(-) we use for loop to iterating over a list sequence from df_sales.groupby('City') as 'cities' variable<br>
    &ensp;&ensp;(-) we use bar plot to visualize the results<br>
    &ensp;&ensp;(-) name of city act as X - axis, meanwhile amount of sales act as Y - axis<br>
    &ensp;&ensp;(-) target the highest value from bar plot then give the different color to it<br>
    &ensp;&ensp;(-) interpret the results<br>
    </li>
    <li>Question 3 | What time should we display advertisements to maximize the likelihood of customer's buying product<br>
    &ensp;&ensp;(-) we use groupby() method to split data into groups based on 'Hour' column that has been calculated using count() method<br>
    &ensp;&ensp;(-) we use for loop to iterating over a list sequence from df_sales.groupby('Hour') as 'hours' variable<br>
    &ensp;&ensp;(-) we use line plot to visualize the results<br>
    &ensp;&ensp;(-) Hour act as X - axis, meanwhile number of orders act as Y - axis<br>
    &ensp;&ensp;(-) peak in X - axis of line graphs can be interpreted as results (see red X plot)<br>
    &ensp;&ensp;(-) interpret the results<br>
    </li>
    <li>Question 4 | What products are most often sold together ?<br>
    &ensp;&ensp;(-) we use duplicated ()(keep=False) method from Order ID columns. It marks all duplicates as true and allows us to see all duplicate rows<br>
    &ensp;&ensp;(-) We create 'Grouped' column from df_sales.groupby('Order Id')['Product'].transform(lambda x: ','.join())<br>
    &ensp;&ensp;(-) we use drop_duplicates() method from df_sales[['Order ID', 'Grouped']]<br>
    &ensp;&ensp;(-) we determine how many products to display using for loop in df_sales['Grouped'] then update data using update() method from Counter and Combinations class<br>
    </li>
    <li>Question 5 | what product sold the most ? why do you think it sold the most ?<br>
    &ensp;&ensp;(-) we use groupby() method to split data into groups based on 'Product' column as 'product_group' <br>
    &ensp;&ensp;(-) we use sum() method to add values from list 'Quantity Ordered' in 'product_group' as 'quantity_ordered' variable <br>
    &ensp;&ensp;(-) we use for loop to iterating over a list sequence 'Product' from product_group as 'products' variable<br>
    &ensp;&ensp;(-) we use bar plot to visualize the results<br>
    &ensp;&ensp;(-) name of Product act as X - axis, meanwhile amount of Quantity Ordered act as Y - axis<br>
    &ensp;&ensp;(-) target the highest value from bar plot then give the different color to it<br>
    &ensp;&ensp;(-) interpret the results<br>
    &ensp;&ensp;(-) correlation with deeper analysis using 'Price Each' column as line graphs from df_sales.groupby('Product').mean()['Price Each'] as Y2 - axis<br>
    </li>
</ol
 </div>
 
 <hr>
 
 <div align="justify">
   <h4>Results :</h4>
 <ol>
  <li>The best selling month occurs in the 12th month (December) : 4613443.34</li>
  <li>The best selling city occurs in San Fransisco (CA) : 10304443952</li>
  <li>13 and 20 pm are the right time to display advertisements</li>
  <li>Iphone and lightning charging cable are products that most often sold together</li>
  <li>AAA Batteries (4 - Pack) is best selling product, it because cheap and mostly needed</li>
 </ol>
 </div<
