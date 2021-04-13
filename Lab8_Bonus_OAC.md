#Bonus Lab: Use Analytics Cloud on MySQL Database Service powered by Heatwawe

Click the _**hamburger menu**_ in the upper left corner and click on _**Analytics -> Analytics Cloud**_.
![](./images/one.png)

Click _**Create instance**_ and in the new window, fill out the fields as shown in the image below. Make sure to select 2 OCPUs, the Enterprise version and the _**License Included**_ button. Finally click _**Create**_ to start the provisioning of the instance.
_**Note:**_ It takes about _**15-20 minutes**_ to create the OAC instance so go get a coffee in the meantime!
![](./images/two.png)

When the status of the instance changes to _Active_, click on the button _**Configure Private Access Channell**_ to create a private access to the MySQL Database Service Instance.
![](./images/three.png)

In the next window you first need to chose a name for the channel. Then, fill in the VCN name with the same one where you provisioned the MySQL Database Service and the Heatwawe cluster. Make sure you select the correct subnet! (In lab 1 you had the option to select Private Subnet or Public Subnet) make sure you select the correct one otherwise you won't be able to connect!
_**Note:**_ It will take about _**50 minutes**_ to create the private channell so go get a nice tea this time to kill the time! 
![](./images/four.png)

When the status of the instance changes to _Active_, click on the button _**Analytics Home Page Channell**_ to access Oracle Analytics Cloud!
![](./images/five.png)

We now want to connect to our MySQL Database Service, so from the top right corner click _**Create**_ and then _**Connection**_ as shown in the picture below. From the list of connectors, select _**MySQL**_
![](./images/six.png)

In the new window we have a lot of information we need to provide. The host name we need to provide is a little bit tricky, we need to provide the Internal FQDN of the MySQL Database Instance. To find this out, you need to go back to the MySQL instance details.

In the section Endpoint you'll find all the information required. See the following images if you need guidance. After you filled out everything, click on _**Save**_

You Oracle Analytics Instance is now connected to your MySQL Database Service powered by Heatwawe.

_**Note:**_ As database name, you need to use _**tpch**_, the database we used in the previous labs.
![](./images/seven.png)

![](./images/eight.png)

Let's now use this connection to create a very simple dashboard! From the top right corner click _**Create**_ and this time click on _**Dataset**_ as shown in the picture below.
![](./images/nine.png)

From the new window seletc the connection we just created and then click on the _**tpch**_ database as shown below.
![](./images/ten.png)
![](./images/eleven.png)

Now, you'll see all the database's tables and views. Select the view we created for this lab called _**myAnalyticsView**_. Then on the button, _**Add All**_ to add all the columns and then on the top right corner, _**Add**_

We are creating a Dataset based on all the columns of the view _**myAnalyticsView**_

![](./images/twelve.png)
![](./images/thirteen.png)
![](./images/fourteen.png)

Now you can see the data that has been retrieved. From the _**Reccomendations**_ column on the right we could use the suggestions to clean the data. We'll leave this topic for another time but feel free to check Oracle's documentation on how to use this useful feature!

To move forward click on _**Create Project**_  button on the top right corner. You will see the Visualisation screen where you can start building your dashboards!
![](./images/fifhteen.png)

CREATE YOUR FIRST DASHBOARD

From the left, select the column _**N_NAME**_ and then, while pressing CTRL (or Comamnd if you are on Mac) _**O_TOTALPRICE**_, right click and select _**Create Best Visualisation**_.
![](./images/sixteen.png)
![](./images/seventeen.png)


A nice histogram will appear after few seconds and we'll see that every country contributes equally to the company's revenues.

You now have all the tools to discover insights in your data!

If you want to discover more on how to use Oracle Analytics Cloud check our tutorials and Live Labs!