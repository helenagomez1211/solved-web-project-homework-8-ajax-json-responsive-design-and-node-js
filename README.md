Download Link: https://assignmentchef.com/product/solved-web-project-homework-8-ajax-json-responsive-design-and-node-js
<br>
(AJAX/JSON/HTML5/Bootstrap/Angular /Node.js/Cloud Exercise)

<h1>1. Objectives</h1>

<ul>

 <li>Get familiar with the AJAX and JSON technologies</li>

 <li>Use a combination of HTML5, Bootstrap and Angular on client side</li>

 <li>Use Node.js on server side</li>

 <li>Get familiar with Bootstrap to enhance the user experience using responsive design</li>

 <li>Get hands-on experience of Cloud services hosting NodeJS/Express</li>

 <li>Learn to use popular APIs such as Tiingo API and NewsAPI</li>

</ul>

<h1>2. Background</h1>

<h2>2.1 AJAX and JSON</h2>

AJAX (Asynchronous JavaScript + XML) incorporates several technologies

<ul>

 <li>Standards-based presentation using XHTML and CSS</li>

 <li>Result display and interaction using the Document Object Model (DOM)</li>

 <li>Data interchange and manipulation using XML and JSON</li>

 <li>Asynchronous data retrieval using XMLHttpRequest</li>

 <li>JavaScript binding everything together</li>

</ul>




See the class slides at <u>http://csci571.com/slides/ajax.pdf</u>




JSON, short for JavaScript Object Notation, is a lightweight data interchange format. Its main application is in AJAX web application programming, where it serves as an alternative to the use of the XML format for data exchange between client and server. See the class slides at:




<u>http://csci571.com/slides/JSON1.pdf</u>




<h2>2.2 Bootstrap</h2>

Bootstrap is a free collection of tools for creating responsive websites and web applications. It contains HTML and CSS-based design templates for typography, forms, buttons, navigation and other interface components, as well as optional JavaScript extensions. To learn more details about Bootstrap please refer to the lecture material on Responsive Web Design (RWD). You should use <strong>Bootstrap 4</strong> in this homework. See the class slides at:




<u>http://csci571.com/slides/Responsive.pdf</u>

<strong> </strong>

<h2>2.3 Cloud Services</h2>

<strong> </strong>

<h3><strong>2.3.1 Google App Engine (GAE) </strong></h3>

Google App Engine applications are easy to create, easy to maintain, and easy to scale as your traffic and data storage needs change. With App Engine, there are no servers to maintain. You simply upload your application and it’s ready to go. App Engine applications automatically scale based on incoming traffic. Load balancing, micro services, authorization, SQL and noSQL databases, memcache, traffic splitting, logging, search, versioning, roll out and roll backs, and security scanning are all supported natively and are highly customizable.




To learn more about GAE support for Node.js visit this page:

<strong> </strong>

<u>https://cloud.google.com/appengine/docs/standard/nodejs/</u>







<h3><strong>2.3.2 Amazon Web Services (AWS) </strong></h3>




AWS is Amazon’s implementation of cloud computing. Included in AWS is Amazon Elastic Compute Cloud (EC2), which delivers scalable, pay-as-you-go compute capacity in the cloud, and AWS Elastic Beanstalk, an even easier way to quickly deploy and manage applications in the AWS cloud. You simply upload your application, and Elastic Beanstalk automatically handles the deployment details of capacity provisioning, load balancing, auto-scaling, and application health monitoring. Elastic Beanstalk is built using familiar software stacks such as the Apache HTTP Server, PHP, and Python, Passenger for Ruby, IIS for .NET, and Apache Tomcat for Java.




To learn more about AWS support for Node.js visit this page:




<u>https://aws.amazon.com/getting-started/projects/deploy-nodejs-web-app/</u>




<h3><strong>2.3.3 Microsoft Azure </strong></h3>




Microsoft Azure is a cloud computing service created by Microsoft for building, testing, deploying, and managing applications and services through a global network of Microsoftmanaged data centers. It provides software as a service (SaaS), platform as a service (PaaS) and infrastructure as a service (IaaS) and supports many different programming languages, tools and frameworks, including both Microsoft-specific and third-party software and systems.




To learn more about Azure support for Node.js visit this page:




<u>https://docs.microsoft.com/en-us/javascript/azure/?view=azure-node-latest</u>







<h2>2.4 Angular</h2>

Angular is a toolset for building the framework most suited to your application development. It is fully extensible and works well with other libraries. Every feature can be modified or replaced to suit your unique development workflow and feature needs. Angular combines declarative templates, dependency injection, end to end tooling, and integrated best practices to solve development challenges. Angular empowers developers to build applications that live on the web, mobile, or the desktop.




For this homework, <u>Angular 7+ (Angular 7,8, 9 or 10) can be used</u>, but<u> <strong>Angular 10 is</strong></u><strong> <u>recommended</u></strong>. Please note Angular 7+ will need familiarity with Typescript and componentbased programming.




To learn more about Angular 7+, visit this page:




<u>https://angular.io/</u>







<h2>2.5 Node.js</h2>

Node.js is a JavaScript runtime built on Chrome’s V8 JavaScript engine. Node.js uses an eventdriven, non-blocking I/O model that makes it lightweight and efficient. Node.js package ecosystem, <strong>npm</strong>, is the largest ecosystem of open source libraries in the world.




To learn more about Node.js, visit:




<u>https://Node.js.org/en/</u>




Also, <strong>Express.js</strong> is strongly recommended. Express.js is a minimal and flexible Node.js web application framework that provides a robust set of features for web and mobile applications. It is in fact the standard server framework for Node.js.




To learn more about Express.js, visit:




<u>http://expressjs.com/</u>




<strong><u>All APIs calls should be done through your Node.JS server</u></strong>

<strong>             </strong>

<h1>3. High Level Description</h1>




In this exercise you will create a webpage that allows users to search for stocks using the Tiingo API and display the results on the details page. The application evolves from previous homework.




A user will first open a page as shown below in <strong>Figure 1</strong>, where user can enter the stock ticker symbol and select from a list of matching stock symbols using “autocomplete.” A quote on a matched stock symbol can be performed. The description of the Search Box is given in Section 3.1. Instructions on how to use the API are given in <strong>Section 4</strong>. All implementation details and requirements will be explained in the following sections.




There are 4 routes for this application:

<ol>

 <li>Homepage/ Search Route [‘/’] – It is a default route of this application.</li>

 <li>Watchlist Route [‘/watchlist’] – It displays the watchlist of the user.</li>

 <li>Portfolio Route [‘/portfolio’] – It displays the portfolio of the user.</li>

 <li>Details Route [‘/details/&lt;ticker&gt;’] – It shows the details of the &lt;ticker&gt;.</li>

</ol>







When a user initially opens your web page, the initial search page should look like in <strong>Figure 1</strong>.







<strong>Figure 1: </strong>Initial Search Page



















<h2>3.1 Search Page/ Homepage</h2>




<strong>3.1.1 Design</strong>




You must replicate the <strong>Search Bar</strong> displayed in <strong>Figure 1</strong> using a <strong>Bootstrap form</strong>. The Search Bar contains two components.




<ol>

 <li><strong>Stock Ticker</strong>: This is a text box, which enables the user to search for valid stocks by entering keywords and accept a suggestion of all possible tickers. The user needs to select one match before clicking on the search icon. Notice the “helper” text inside the search box.</li>

 <li><strong>Search Button</strong>: The “Search” button (which uses the widely used search icon), when clicked, will read the value from the textbox and send the request to the backend server. On a successful response, details for that stock will be displayed.</li>

</ol>




<strong>3.1.2 Search Execution </strong>




Once the user clicks on the “Search” button, your application should make an HTTP call to the Node.js script hosted on GA/AWS/Azure back end (the Cloud Services) . The Node.js script on Cloud Services will then make a request to the Tiingo API and NewsAPI services to get the detailed information and news.




<strong>3.1.3 Autocomplete </strong>

<strong> </strong>

<ul>

 <li>A Search Bar allows a user to enter a keyword (Stock ticker symbol / company name) to retrieve information. Based on the user input, the text box should display a list of all the matching company’s ticker symbols with company’s name (see <strong>Figure</strong> <strong>2</strong>). The autocomplete JSON data is retrieved from the <strong><em>Tiingo Search API</em></strong> (refer to Section 4.1.5). These are examples of calling this API:</li>

</ul>

<u>https://api.tiingo.com/tiingo/utilities/search/&lt;query</u>&gt;

# or

<u>https://api.tiingo.com/tiingo/utilities/search?query=&lt;query</u>&gt; For example:

<u>https://api.tiingo.com/tiingo/utilities/search/apple</u>




<ul>

 <li>The autocomplete function should be implemented using <strong>Angular Material</strong>. Refer to Section 5.3 for more details.</li>

</ul>




<strong>   </strong>

<strong>Figure 2: </strong>Autocomplete Suggestions




<h2>3.2 Details Page</h2>




<strong>3.2.1 Details of Searched Stock </strong>




After the user clicks the Search button, a page should route to /details/&lt;ticker&gt; path (example: /details/AMZN). The following components need to be displayed on successful search:




<ul>

 <li>Symbol, company name, trading Exchange (such as NASS+DAQ), and Buy button on top left;</li>

 <li>Last price, change, percent change, and date/time, on top right. The change items should be preceded by appropriately colored arrows);</li>

 <li>Indication of open / closed market;</li>

 <li>Summary, Top News and Charts tabs.</li>

</ul>




Please refer to <strong>Figure 3.1</strong> and <strong>Figure 3.2</strong> below.







<h3><strong>Figure 3.1: </strong>Detail page overview (Market is Closed)</h3>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<h3><strong>Figure 3.2: </strong>Detail page overview (Market is Open)</h3>




























<ul>

 <li>When the user clicks on the star icon, the white star turns yellow, and that ticker should be stored in local storage (see HTML5 localstorage). A self-closing alert should be displayed at the top and that stock should be visible on the Watchlist Page (see section 3.3)</li>

 <li>When the user clicks on the <strong>Buy</strong> button, a modal window should open. which will display the details (stock symbol, current price, quantity of shares to buy and total price for the shares), as shown in Figure 3.3. Note that:

  <ul>

   <li>The <strong>Buy</strong> button should be disabled if the user inputs the quantity &lt; 1 or the quantity field is empty. (see Figure 3.4);</li>

   <li>The <strong>Buy</strong> button will be enabled once the user enters a number greater than 0 (see <strong>Figure</strong>3).</li>

  </ul></li>

</ul>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<h3><strong>Figure 3.3: </strong>Buy Button enabled for valid input</h3>
















<h3><strong>Figure 3.4: </strong>Buy button disabled for invalid input</h3>







As described, the page contains two major panels:




1) <strong>Stock Details</strong>: This panel displays all the values mentioned in <strong>Table 3.1</strong>. Last Timestamp should be only displayed beside the Market status if “Market is Close”.




<table width="575">

 <tbody>

  <tr>

   <td width="168">Fields</td>

   <td width="150">Sample Values</td>

   <td width="258">API reference</td>

  </tr>

  <tr>

   <td width="168">Ticker</td>

   <td width="150">NVDA</td>

   <td width="258">From table 4.1, use ‘ticker’ key</td>

  </tr>

  <tr>

   <td width="168">Company’s Name</td>

   <td width="150">Nvidia</td>

   <td width="258">From table 4.1, use ‘name’ key</td>

  </tr>

  <tr>

   <td width="168">Exchange Code</td>

   <td width="150">NASDAQ</td>

   <td width="258">From table 4.1, use ‘exchangeCode’ key</td>

  </tr>

  <tr>

   <td width="168">Last Price</td>

   <td width="150">108.22</td>

   <td width="258">From table 4.2, use ‘last’ key</td>

  </tr>

  <tr>

   <td width="168">Change</td>

   <td width="150">1.1</td>

   <td width="258">Calculation is <strong>‘last’ – ‘prevClose’</strong> from table 4.2</td>

  </tr>

  <tr>

   <td width="168">Change Percentage</td>

   <td width="150">1.03%</td>

   <td width="258">Calculation is <strong>‘Change’ * 100 / ‘prevClose’</strong> from table 4.2</td>

  </tr>

  <tr>

   <td width="168">Current Timestamp</td>

   <td width="150">2020-09-24 16:26:27</td>

   <td width="258">Use the Date() function in JavaScript to display current time.</td>

  </tr>

  <tr>

   <td width="168">Market Status</td>

   <td width="150">Open/Close</td>

   <td width="258">Section 4.2</td>

  </tr>

  <tr>

   <td width="168">Last Timestamp</td>

   <td width="150">2020-09-24 13:00:00</td>

   <td width="258">From Table 4.2, use value available for key ‘timestamp’.</td>

  </tr>

 </tbody>

</table>

<h3><strong>Table 3.1 – Stock Details </strong></h3>







2) <strong>Material Tabs</strong> – This component helps users see different stock data on the same page, and the tabs content is detailed in the following sections.




<strong>3.2.2 Summary Tab </strong>




It contains summary of the stock, which includes:




<ul>

 <li>Details are as following:

  <ul>

   <li>If market is Open: Display all the fields mentioned in <strong>Table 3.2</strong> and <strong>Table 3.3</strong>, as shown in <strong>Figure 3.2</strong>.</li>

   <li>If market is Closed: Display all the fields mentioned in <strong>Table 3.2</strong>, as shown in <strong>Figure 3.1</strong>.</li>

  </ul></li>

 <li>Company’s Description: values for ‘startDate’ and ‘description’ key from <strong>Table </strong></li>

</ul>

<strong>4.1.</strong>

<ul>

 <li>Chart for the last Working Day:

  <ul>

   <li>If market is Open: Show stock chart available in Highcharts for that day.</li>

   <li>If market is Closed: Show stock chart for the day when the market was closed. (i.e., last working day).</li>

  </ul></li>

</ul>







<table width="575">

 <tbody>

  <tr>

   <td width="108">Fields</td>

   <td width="114">Sample Values</td>

   <td width="354">API reference</td>

  </tr>

  <tr>

   <td width="108">High Price</td>

   <td width="114">110.25</td>

   <td width="354">From table 4.2, use ‘high’ key</td>

  </tr>

  <tr>

   <td width="108">Low Price</td>

   <td width="114">105</td>

   <td width="354">From table 4.2, use ‘low’ key</td>

  </tr>

  <tr>

   <td width="108">Open Price</td>

   <td width="114">105.17</td>

   <td width="354">From table 4.2, use ‘open’ key</td>

  </tr>

  <tr>

   <td width="108">Prev. Close</td>

   <td width="114">107.12</td>

   <td width="354">From table 4.2, use ‘close’ key</td>

  </tr>

  <tr>

   <td width="108">Volume</td>

   <td width="114">165893169</td>

   <td width="354">From table 4.2, use ‘volume’ key</td>

  </tr>

 </tbody>

</table>

<strong>Table 3.2: </strong>Fields used inside Summary Tab (Part 1)

<strong> </strong>

<strong> </strong>

<strong> </strong>

<table width="575">

 <tbody>

  <tr>

   <td width="108">Fields</td>

   <td width="114">Sample Values</td>

   <td width="354">API reference</td>

  </tr>

  <tr>

   <td width="108">Mid Price</td>

   <td width="114">110.1</td>

   <td width="354">From Table 4.2, use ‘mid’ key</td>

  </tr>

  <tr>

   <td width="108">Ask Price</td>

   <td width="114">110.29</td>

   <td width="354">From Table 4.2, use ‘askPrice’ key</td>

  </tr>

  <tr>

   <td width="108">Ask Size</td>

   <td width="114">200</td>

   <td width="354">From Table 4.2, use ‘askSize’ key</td>

  </tr>

  <tr>

   <td width="108">Bid Price</td>

   <td width="114">110.35</td>

   <td width="354">From Table 4.2, use ‘bidPrice’ key</td>

  </tr>

  <tr>

   <td width="108">Bid Size</td>

   <td width="114">200</td>

   <td width="354">From Table 4.2, use ‘bidSize’ key</td>

  </tr>

 </tbody>

</table>

<strong>Table 3.3: </strong>Fields used inside Summary Tab (Part 2)







<strong>3.2.3</strong> <strong>Top News Tab </strong>




This tab shows top news for the given stock ticker symbol from News API (see <strong>Figure</strong> <strong>3.5</strong> and <strong>Figure 3.6</strong>). o Show cards which contains Image and Title.

<ul>

 <li>For Image use ‘urlToImage’ key from <strong>Table 4.6</strong>.</li>

 <li>For Title use ‘title’ key from <strong>Table 4.6</strong>.</li>

</ul>

<ul>

 <li>When clicked on card, open a Modal window as shown in <strong>Figure 3.6</strong>. For details regarding Modal check section 5.3. Modal contains all the fields mentioned in <strong>Table 3.4</strong>.</li>

 <li>User can share the news articles on Twitter and Facebook. For details on how to use it, check <strong>Section 4.1.3</strong>. Twitter and Facebook should open in a new browser tab, if clicked.</li>

 <li>In Twitter, it should create a post having following content:

  <ul>

   <li>Title of the news article</li>

   <li>URL of the news article.</li>

   <li>In Facebook, it should create a post, which contains URL of the news Article.</li>

  </ul></li>

 <li>Inside modal when user clicks on ‘<strong><em>here</em></strong>’ in ‘<em>For more details click <strong>here</strong></em>’, it should open the URL for the article in a new browser tab.</li>

</ul>










<table width="575">

 <tbody>

  <tr>

   <td width="144">Fields</td>

   <td width="432">API reference</td>

  </tr>

  <tr>

   <td width="144">Publisher</td>

   <td width="432">From Table 4.6, use ‘source’ key.</td>

  </tr>

  <tr>

   <td width="144">Published Date</td>

   <td width="432">From Table 4.6, use ‘publishedAt’ key.</td>

  </tr>

  <tr>

   <td width="144">Title</td>

   <td width="432">From Table 4.6, use ‘title’ key.</td>

  </tr>

  <tr>

   <td width="144">Description</td>

   <td width="432">From Table 4.6, use ‘description’ key.</td>

  </tr>

  <tr>

   <td width="144">URL</td>

   <td width="432">From Table 4.6, use ‘url’ key.</td>

  </tr>

 </tbody>

</table>

<h4><strong>Table 3.4: </strong>Fields used inside modal of Top News Tab</h4>







<strong> </strong>

<h4><strong>Figure 3.5:</strong> Top News Tab overview</h4>










<strong>Figure 3.6: </strong>Top News Detailed Modal overview.




<strong>3.2.4</strong> <strong>Charts Tab </strong>




This tab uses HighCharts to display historical stock market data on the related stock. o See <strong>Figure 3.7</strong> for reference. For more details regarding Highcharts see section 5.5. o Display SMA and Volume by Price chart for data of the last 2 years.







<strong>Figure 3.7: </strong>Charts tab overview.

<strong>Note: </strong>As user mentioned before, that user need to select one from the suggestions before clicking the search button. If user manually edits the /details/&lt;ticker&gt; route and if the &lt;ticker&gt; entered by user is invalid, then you need to display an alert on that page instead of details.

<strong> </strong>

<strong>Important note: Data mentioned in Stock Details section and Summary Tab, should autoupdate every 15 seconds. </strong><strong><sub> </sub></strong>







<h2>3.3 Watchlist Menu</h2>




This menu will display all the stocks that are added to the watchlist by the user. This watchlist will be maintained in local storage of the application. For more details on local storage, see section 5.4. (see <strong>Figure 3.9</strong>)

<ul>

 <li>If the change is positive, the color of the ‘last’, ‘change’ and ‘changePercentage’ keys should be green</li>

 <li>If the change is negative, the color of the ‘last’, ‘change’ and ‘changePercentage’ keys should be red</li>

 <li>If there is no change, the color of the ‘last’, ‘change’ and ‘changePercentage’ keys should be black.</li>

 <li>When clicked on close button at present on the right-top corner of the card, it should remove it from the watchlist and display an updated watchlist.</li>

 <li>When clicked on card, it should open the details route of that ticker (stock).</li>

 <li>If watchlist is empty, it should display the alert as shown in <strong>Figure 3.10</strong>.</li>

</ul>




‘last’ key should be used from <strong>Table 4.2</strong>. ‘change’ and ‘changePercentage’ should be calculated in a similar fashion as to the one shown in <strong>Table 3.1</strong>.










<h3><strong>Figure 3.9: </strong>Watchlist menu page</h3>










<strong> </strong>

<strong>Figure 3.10: </strong>Watchlist Empty Alert

<h2>3.4 Portfolio Menu</h2>




This menu will display all the stocks that have been bought by the user (i.e. the current portfolio of the user). This portfolio will be maintained in local storage of the application. For more details on local storage, see section 5.4 and <strong>Figure 3.11</strong>. In particular:




<ul>

 <li>If the current rate is greater than the rate at which user bought it, then color of the ‘Change’, ‘Current Price’ and ‘Current Total’ keys should be green;</li>

 <li>If the change is negative, the color of the ‘Change’, ‘Current Price’ and ‘Current Total’ keys should be red;</li>

 <li>If there is no change, the color of the ‘Change’, ‘Current Price’ and ‘Current Total’ keys should be black;</li>

 <li>When clicking on <strong>Buy</strong> button, modal should open as shown in <strong>Figure 3.13</strong>. The Buy button inside modal should be disabled if the quantity entered by user is not valid as shown in <strong>Figure 3.14</strong>. Valid input should be greater than 0 and must be non-empty;</li>

 <li>When clicking on <strong>Sell</strong> button, modal should open as shown in <strong>Figure 3.15 and 3.16</strong>. Sell button inside modal should be disabled if the quantity entered by user is not valid. Input is Valid if, 0&lt;input&lt;=Quantity and must be non-empty. Quantity is described in <strong>Table 3.5;</strong></li>

 <li>When clicked on card’s header part, it should open the details route of that ticker (stock);</li>

 <li>If portfolio is empty, it should display the alert as shown in <strong>Figure 3.12</strong>.</li>

</ul>




<strong>‘last’ key should be used from Table 4.2 for ‘Current Price’.</strong> ‘Current Change’ and ‘Current Total’ should be calculated as shown in <strong>Table 3.5</strong>.










<table width="623">

 <tbody>

  <tr>

   <td width="312">Quantity</td>

   <td width="312">Total Number of stocks bought by user. It should be more than 0, else remove it from the portfolio local storage.</td>

  </tr>

  <tr>

   <td width="312">Total Cost</td>

   <td width="312">Total cost is sum of the total cost paid for all the purchases of the stock. For Example, if user has bought 10 stocks of AAPL in past, at the rate of 200, and today if user buys another 10 stocks of AAPL at the current price, i.e. 300, then the Total Cost for the user will be (10*200) + (10*300) = 5000.So Quantity is 20 and Total Amount is 5000.</td>

  </tr>

  <tr>

   <td width="312">Average Cost per Share</td>

   <td width="312">(Total Cost / Quantity)</td>

  </tr>

  <tr>

   <td width="312">Current Price</td>

   <td width="312">‘last’ key from the table 4.2</td>

  </tr>

  <tr>

   <td width="312">Change</td>

   <td width="312">(Average Cost per Share – Current Price) of the stock. Here, Current Price is ‘last’ key from the table 4.2</td>

  </tr>

  <tr>

   <td width="312">Market Value</td>

   <td width="312">(Current Price * Qty), here Current Price is ‘last’ key from <strong>Table 4.2</strong> and Qty is the number of stocks present in user’s portfolio.</td>

  </tr>

 </tbody>

</table>

<strong>Table 3.5: </strong>Fields used in Portfolio Cards.










<h3><strong>Figure 3.11: </strong>Portfolio</h3>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<h4><strong>Figure 3.12: </strong>Portfolio Empty Alert</h4>

<strong> </strong>

<strong>Figure 3.13: </strong>Modal for Buying Stock



















<strong>Figure 3.14: </strong>Input is invalid in Modal for Buying Stock







<h4><strong>Figure 3.15: </strong>Modal for Selling Stock</h4>










<strong>Figure 3.16: </strong>Input is invalid in Modal for Selling Stock







<strong>Note: Portfolio and Watchlist must be sorted in ascending order based on Ticker.</strong>

<h2>3.5 Responsive Design</h2>

The following are a few snapshots of the web app opened with Google Chrome on a OnePlus mobile device.


































You must watch the video carefully to see how the page looks like on mobile devices. All functions must work on mobile devices.

<u>One easy way to test for mobile devices is to use Google Chrome Responsive Design Mode and</u> <u>Safari Develop – User Agent menu.</u>




<h2>3.5 Navbar</h2>




The Navigation bar must be present on top of the page, and visible at all times as shown in all the figures above. You can use Bootstrap to create a navbar. It consists of following menu options:

<ol>

 <li><u>Search</u></li>

 <li><u>Watchlist</u></li>

 <li><u>Portfolio</u></li>

</ol>

<h2>3.6 Footer</h2>




The Footer must be present at the end of each page, as shown in above figures. It should contain following line:

<strong><em>“Powered by Tiingo. Developed by &lt;student’s name&gt;”</em></strong> Here &lt;student’s name&gt; must be replace with your name.




<h1>4. API’s description</h1>




<strong>4.1 Tiingo API calls, similar to Homework 6</strong>




In this homework, we will use the Tiingo API. A comprehensive reference about this API is available at:




<ul>

 <li><u>https://api.tiingo.com/documentation/end-of-day</u></li>

 <li><u>https://api.tiingo.com/documentation/iex</u></li>

 <li><u>https://api.tiingo.com/documentation/utilities/search</u></li>

</ul>







<strong>4.1.1 Company’s Description  </strong>

<strong> </strong>

<strong>             </strong>

For <strong>Company’s Description</strong>, use the following API. For more details refer <strong>Figure 4.1</strong>:

<u>https://api.tiingo.com/tiingo/daily/&lt;ticker&gt;?token=&lt;APIKeyTiingo</u>&gt;
















<strong>URL parameter in API Call: </strong>

<ul>

 <li>Ticker: Ticker symbol of the stock. E.g.: MSFT</li>

 <li>Token: The API access Token. It is private, please do not share with anyone. See Homework 6.</li>

</ul>







An example URL constructed from the parameters will look similar to this:




<u>https://api.tiingo.com/tiingo/daily/AAPL?token=12PrIvA32tEmYtEmpToKeN23</u>




Response:

<table width="570">

 <tbody>

  <tr>

   <td width="258"><strong>Response Keys </strong></td>

   <td width="312"><strong>Details </strong></td>

  </tr>

  <tr>

   <td width="258">ticker</td>

   <td width="312">Ticker symbol.</td>

  </tr>

  <tr>

   <td width="258">name</td>

   <td width="312">Company’s Name</td>

  </tr>

  <tr>

   <td width="258">description</td>

   <td width="312">Company’s Description</td>

  </tr>

  <tr>

   <td width="258">startDate</td>

   <td width="312">Company’s Start Date</td>

  </tr>

  <tr>

   <td width="258">exchangeCode</td>

   <td width="312">Company’s Exchange Code</td>

  </tr>

 </tbody>

</table>

<strong>Table 4.1: </strong>Response received for Company’s Meta Data API call.










<strong> </strong>

<h2>Figure 4.1: Details regarding Company’s Meta Data</h2>




<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>4.1.2 Company’s Latest Price of the stock </strong>

<strong> </strong>

For <strong>Company’s Latest Price</strong>, use the following API. For more details refer Figure 4.2:

<u> https://api.tiingo.com/iex/?tickers=&lt;ticker&gt;&amp;token=&lt;APIKeyTiingo</u>&gt;







<strong>URL parameter in API Call: </strong>

<ul>

 <li>Ticker: Ticker symbol of the stock. E.g.: AAPL</li>

 <li>Token: The API access Token. It is private, please do not share with anyone.</li>

</ul>







An example URL constructed from the parameters will look similar to:




<u>https://api.tiingo.com/iex?tickers=AAPL&amp;token=12PrIvA32tEmYtEmpToKeN23</u>













Response:

<table width="570">

 <tbody>

  <tr>

   <td width="156"><strong>Response Keys </strong></td>

   <td width="414"><strong>Details </strong></td>

  </tr>

  <tr>

   <td width="156">ticker</td>

   <td width="414">Ticker symbol.</td>

  </tr>

  <tr>

   <td width="156">timestamp</td>

   <td width="414">Timestamp of the data.</td>

  </tr>

  <tr>

   <td width="156">last</td>

   <td width="414">Company’s latest price based on timestamp</td>

  </tr>

  <tr>

   <td width="156">prevClose</td>

   <td width="414">Company’s previous closing based on timestamp</td>

  </tr>

  <tr>

   <td width="156">open</td>

   <td width="414">Company’s open price based on timestamp</td>

  </tr>

  <tr>

   <td width="156">high</td>

   <td width="414">Company’s high price based on timestamp</td>

  </tr>

  <tr>

   <td width="156">low</td>

   <td width="414">Company’s low price based on timestamp</td>

  </tr>

  <tr>

   <td width="156">mid</td>

   <td width="414">Company’s mid price based on timestamp</td>

  </tr>

  <tr>

   <td width="156">volume</td>

   <td width="414">Company’s volume based on timestamp</td>

  </tr>

  <tr>

   <td width="156">bidSize</td>

   <td width="414">Company’s bid size based on timestamp</td>

  </tr>

  <tr>

   <td width="156">bidPrice</td>

   <td width="414">Company’s bid price based on timestamp</td>

  </tr>

  <tr>

   <td width="156">askSize</td>

   <td width="414">Company’s ask size based on timestamp</td>

  </tr>

  <tr>

   <td width="156">askPrice</td>

   <td width="414">Company’s ask price based on timestamp</td>

  </tr>

 </tbody>

</table>

<strong>Table 4.2: </strong>Response received for Company’s Latest Price of the Stock.







Value of ‘mid’, ‘bidPrice’, ‘bidSize’, ‘askPrice’, ‘askSize’ will be null when market is closed.

Value of mid can be null even when the market is open, if this happens then you should display

‘-’ instead of null. Market Status must be open if the difference between current Timestamp (current Timestamp will be of the created using new Date() in javascript) and ‘timestamp’ key is less than 60 seconds.

<strong> </strong>

<h2>Figure 4.2: Details regarding Company’s Meta Data</h2>




<strong> </strong>

<strong>4.1.3 Company’s Historical Data: </strong>

<strong> </strong>

For <strong>Company’s Historical data</strong>, use the following API. For more details refer to <strong>Figure 4.3</strong>:

<u>https://api.tiingo.com/tiingo/daily/&lt;ticker&gt;/prices?startDate=&lt;startDate&gt;&amp;resampleFreq= &lt;resampleFreq&gt;&amp;token=&lt;APIKeyTiingo</u>&gt;







<strong>URL parameter in API Call: </strong>

<ul>

 <li>Ticker: Ticker symbol of the stock. E.g.: AAPL</li>

 <li>startDate: the date from which we need data.</li>

 <li>resampleFreq: the interval between 2 data lists/ arrays.</li>

 <li>Token: The API access Token. It is private, please do not share with anyone.</li>

</ul>







An example URL constructed from the parameters will look similar to this:




<u>https://api.tiingo.com/tiingo/daily/AAPL/prices?startDate=2019-09-</u>

<u>10</u><u>&amp;resampleFreq=4min&amp;token=12PrIvA32tEmYtEmpToKeN23</u>










Response: We receive an array of objects, where each object contains following keys. We only need the following keys from the response.




<table width="570">

 <tbody>

  <tr>

   <td width="168"><strong>Response Keys </strong></td>

   <td width="402"><strong>Details </strong></td>

  </tr>

  <tr>

   <td width="168">date</td>

   <td width="402">Date and time of the data.</td>

  </tr>

  <tr>

   <td width="168">open</td>

   <td width="402">Open Price at the specific date and time.</td>

  </tr>

  <tr>

   <td width="168">high</td>

   <td width="402">High Price at the specific date and time.</td>

  </tr>

  <tr>

   <td width="168">low</td>

   <td width="402">Low Price at the specific date and time.</td>

  </tr>

  <tr>

   <td width="168">close</td>

   <td width="402">Close Price at the specific date and time.</td>

  </tr>

  <tr>

   <td width="168">volume</td>

   <td width="402">Volume at the specific date and time.</td>

  </tr>

 </tbody>

</table>

<strong>Table 4.3: </strong>Details regarding Company’s Historical Data.






















<strong> </strong>

<h2>Figure 4.3: Details regarding Company’s Historical Data</h2>




<strong> </strong>

<strong> </strong>

<strong>4.1.4 Company’s Daily Chart Data: </strong>




For <strong>Company’s Last day’s chart data</strong>, use the following API. For more details refer to <strong>Figure 4.4</strong>:




<u>https://api.tiingo.com/iex/&lt;ticker&gt;/prices?startDate=&lt;startDate&gt;&amp;resampleFreq=&lt;resamp leFreq&gt;&amp;token=&lt;APIKeyTiingo</u>&gt;







<strong>URL parameter in API Call: </strong>

<ul>

 <li>Ticker: Ticker symbol of the stock. E.g.: AAPL</li>

 <li>startDate: the date from which we need data.</li>

 <li>resampleFreq: the interval at which you need data.</li>

 <li>Token: The API access Token. It is private, please do not share with anyone.</li>

</ul>







An example URL constructed from the parameters will look similar to this: <u>https://api.tiingo.com/iex/AAPL/prices?startDate=2019-09-</u>

<u>10</u><u>&amp;resampleFreq=4min&amp;token=12PrIvA32tEmYtEmpToKeN23</u>










<h2>Response: We receive array of objects, where each object contains following keys</h2>

<table width="570">

 <tbody>

  <tr>

   <td width="168"><strong>Response Keys </strong></td>

   <td width="402"><strong>Details </strong></td>

  </tr>

  <tr>

   <td width="168">date</td>

   <td width="402">Date and time of the data.</td>

  </tr>

  <tr>

   <td width="168">open</td>

   <td width="402">Open Price at the specific date and time.</td>

  </tr>

  <tr>

   <td width="168">high</td>

   <td width="402">High Price at the specific date and time.</td>

  </tr>

  <tr>

   <td width="168">low</td>

   <td width="402">Low Price at the specific date and time.</td>

  </tr>

  <tr>

   <td width="168">close</td>

   <td width="402">Close Price at the specific date and time.</td>

  </tr>

  <tr>

   <td width="168">volume</td>

   <td width="402">Volume at the specific date and time.</td>

  </tr>

 </tbody>

</table>

<strong>Table 4.4: </strong>Details regarding Company’s Historical Data.










<strong> </strong>

<strong>Figure 4.4: </strong>Details regarding Company’s Historical Data for the latest working day.




<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong> </strong>

<strong>4.1.5 Autocomplete: </strong>

<strong> </strong>

For <strong>Autocomplete</strong>, use the following API. For more details refer Figure 4.5:

<u>https://api.tiingo.com/tiingo/utilities/search?query=&lt;query&gt;&amp;token=&lt;APIKeyTiingo</u>&gt;




<strong>URL parameter in API Call: </strong>

<ul>

 <li>Query: query means the combination of letters for which you want results for autocomplete. E.g.: AA</li>

 <li>Token: The API access Token. It is private, please do not share with anyone.</li>

</ul>







An example URL constructed from the parameters will look similar like:




<u>https://api.tiingo.com/tiingo/utilities/search?query=AA&amp;token=12PrIvA32tEmYtEmpTo KeN23</u>




Response: We receive a response in the form of array of objects. From those objects we only need the following keys:

<table width="570">

 <tbody>

  <tr>

   <td width="258"><strong>Response Keys </strong></td>

   <td width="312"><strong>Details </strong></td>

  </tr>

  <tr>

   <td width="258">Ticker</td>

   <td width="312">Ticker symbol.</td>

  </tr>

  <tr>

   <td width="258">Name</td>

   <td width="312">Company’s Name</td>

  </tr>

 </tbody>

</table>

<strong>Table 4.5: </strong>Response received for autocomplete API call.










<strong> </strong>

<strong>Figure 4.5: </strong>Details regarding Autocomplete Response.




<strong> </strong>

<strong>4.2 News API: </strong>

<strong>                                      </strong>For reference, check the following link: <u>https://newsapi.org/docs/endpoints/everything</u>

<strong> </strong>

For News related to Company, use the following API. For more details refer Figure 4.6: <u>https://newsapi.org/v2/everything?apiKey=&lt;APIkey&gt;&amp;q=&lt;Query</u>&gt;




<strong>URL parameter in API Call: </strong>

<ul>

 <li>Query: Ticker symbol of the stock. E.g.: AAPL</li>

 <li>APIkey: The API access Key. It is private, please do not share with anyone.</li>

</ul>







An example URL constructed from the parameters will look similar to:




<u>https://newsapi.org/v2/everything?apiKey=12PrIvA32tEmYtEmpToKeN23</u>&amp;q=app




Response: We receive the response in the form of array of objects. From those objects we only need the following keys:







<table width="570">

 <tbody>

  <tr>

   <td width="258"><strong>Response Keys </strong></td>

   <td width="312"><strong>Details </strong></td>

  </tr>

  <tr>

   <td width="258">url</td>

   <td width="312">url for the article.</td>

  </tr>

  <tr>

   <td width="258">title</td>

   <td width="312">Article’s Title</td>

  </tr>

  <tr>

   <td width="258">description</td>

   <td width="312">Article’s brief description</td>

  </tr>

  <tr>

   <td width="258">source</td>

   <td width="312">Source of the Article. E.g. Business Insider</td>

  </tr>

  <tr>

   <td width="258">urlToImage</td>

   <td width="312">Image URL for the article.</td>

  </tr>

  <tr>

   <td width="258">publishedAt</td>

   <td width="312">Date when the article was published</td>

  </tr>

 </tbody>

</table>

<strong>Table 4.6: </strong>Response received from News API call.




<strong> </strong>

<strong>Figure 4.6: </strong>Details regarding Company News

<strong> </strong>

<h2>4.3 Socials</h2>




<h3><strong>4.3.1 Twitter  </strong></h3>

Refer the following link for details: <u>https://developer.twitter.com/en/docs/twitter-for-websites/tweet-button/overview</u>

<strong> </strong>

<h3><strong>4.3.2 Facebook </strong></h3>

Refer the following link for details:

<u>https://developers.facebook.com/docs/plugins/share-button/</u>




<h1>5. Implementation Hints</h1>




<h2>5.1 Bootstrap Library</h2>




To get started with the Bootstrap toolkit, please see:

<u>https://getbootstrap.com/docs/4.0/getting-started/introduction/</u>.




Bootstrap can be imported to Angular in couple of ways. See:

<u>https://www.techiediaries.com/angular-bootstrap/</u>

<strong> </strong>

<h2>5.2 Bootstrap UI Components</h2>




Bootstrap provides a complete mechanism to make Web pages responsive for different mobile devices. In this exercise, you will get hands-on experience with responsive design using the Bootstrap Grid System.




<u>https://getbootstrap.com/docs/4.0/layout/grid/</u>




At a minimum, you will need to use Bootstrap Forms, Alerts, Cards and Buttons to implement the required functionality.




Bootstrap Forms         <u>https://getbootstrap.com/docs/4.0/components/forms/</u>

Bootstrap Alerts <u>https://getbootstrap.com/docs/4.0/components/alerts/</u>     Bootstrap Cards  <u>https://getbootstrap.com/docs/4.0/components/card/</u>

Bootstrap Buttons       <u>https://getbootstrap.com/docs/4.0/components/buttons/</u>

<strong> </strong>

<h2>5.3 Angular</h2>




<ul>

 <li>Angular Set up – <u>https://angular.io/</u></li>

</ul>




<ul>

 <li>Angular Material Installation – <u>https://material.angular.io/guide/getting-started</u></li>

</ul>




<ul>

 <li>Angular Material Tabs – <u>https://material.angular.io/components/tabs/overview</u></li>

</ul>




<ul>

 <li>Angular Material Spinner – <u>https://material.angular.io/components/progress-spinner/overview</u></li>

</ul>

<strong> </strong>

<ul>

 <li>Angular Bootstrap Modal – <u>https://ng-bootstrap.github.io/#/components/modal/examples</u></li>

</ul>

<strong> </strong>

<ul>

 <li>Angular Material Autocomplete:</li>

</ul>

<u>https://material.angular.io/components/autocomplete/overview</u>

<strong> </strong>

<h2>5.4 Local Storage</h2>

<strong> </strong>

Refer the following documentation for detailed understanding on Local Storage and how to use it.

<u>https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage</u>




<h2>5.5 Highcharts</h2>

<strong> </strong>

Refer the following documentation on Highcharts and how to use it.

<u>https://api.highcharts.com/highstock/</u>




For using Highchart in Angular you can use highcharts-angular package. Refer following link for more details:

<u>https://www.npmjs.com/package/highcharts-angular</u>




<strong> </strong>

<h2>5.6 Icons</h2>

<strong> </strong>

<ul>

 <li><u>https://icons.getbootstrap.com/icons/caret-up-fill/</u></li>

 <li><u>https://icons.getbootstrap.com/icons/caret-down-fill/</u></li>

 <li><u>https://icons.getbootstrap.com/icons/star/</u></li>

 <li><u>https://icons.getbootstrap.com/icons/star-fill/</u></li>

</ul>







<strong>5.6 Deploy Node.js application on Cloud Services </strong>

<strong> </strong>

Since Homework #8 is implemented with Node.js on Cloud Services, you should <strong><u>select Nginx as</u> <u>your proxy server (if available)</u></strong>, which should be the default option.





