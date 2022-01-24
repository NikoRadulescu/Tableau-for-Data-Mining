# Tableau for data mining

I used [Churn Modelling](https://sds-platform-private.s3-us-east-2.amazonaws.com/uploads/P12-Churn-Modelling.xlsx) from [Visualisation > How to use Tableau for Data Mining](https://www.superdatascience.com/pages/training), a data set of 10000 rows of bank customers data for a simple data mining in Tableau. Analyse bank customer data (6 months period data) and find out why the customers are leaving the bank, using Tableau Public.

**note**: in this data set the "Exited" column: value 1 means not longer a customer / value 0 means still a customer.


###  1. First steps:
- Download the .xlsx file in the section above;
- Login into **Tableau Public**;
- Click on **My Profile**;
- Click on **Create a Viz** (a window should appear);
- Click on **Upload from computer** and choose the csv file you downloaded. The schema of your data should appear in the **Tables** area (left);

**note**: The fields marked with blue symbols are the **Dimensions** and the ones marked with green symbols are the **Measures**.


###  2. Create first Tableau sheet (a Map):
- We create an extract of the data set;
- We change the **Geography** field type to **Country/Region** by clicking the **Geography** field then **Geography role** and choosing **Country/Region**;
- Add **Geography** to the tableau working space;
- Add **Number of records** to the tableau working space;
- Drag **Number of records** to the **Label** field;
- Click on the left of the **Number of records** square (in the working space) and choose **Colour** (the countries shapes fill with colour);
- Go to the **Label** square (in the **Marks** working space) and click on **Edit Label**. Edit as you please;
- Save (or publish if you are working with Tableau Public);


###  3. Create second Tableau sheet (making an A/B test * — in this case a gender test — see which gender is more prone of leaving the bank):
- Go to **Sheet 2** at the bottom left;
- Move **Exited** field from **Measures** to **Dimensions**;
- Take the **Gender** field and drag to the **Columns** field.
- Take the **Exited** field and drag it to **Colour** (into the **Marks** working space). Two different coloured squares should appear in the top right of the working space (one with the label **0** and the second with the label **1**);
- Take the **Number of records** field and drag it into the **Rows** field. Then add the **Number of records** field into the **Label** square in the **Marks** working space;

We need to transform the **Number of records** field into a percentage:
- Click the **Number of records** field in the **Marks** working space and choose **Add Table Calculation**;
- Click on **Calculation Type** and choose **Percent of Total**;
- Choose **Table (down)** from **Compute Using** field;

To format the percentage label:
- Click the **Number of records** field in the **Marks** working space choose **Format Number** , **Percentage**;
- Click on **Decimal Places** and choose **0**;
- Press **control**(Windows) or **command**(Mac), click on **Number of records** in the **Marks** working space and drag it to the **Rows** filed above;

###  Insights:
From this test we find out that females (25%) are more likely to leave the bank than males (16%).

To validate our insights we need to add a Reference line (adding a Reference line show a bigger picture of the total number of clients that left the bank over a time period, regardless of the gender) :
- Go to **Analytics** field on the top left;
- From **Custom** field choose **Reference Line** and drag it onto the percentage axis (a rectangle with options should appear);
- Drag the **Reference Line** onto the **Table** option (other editing rectangle should appear in the working space);
- From the **Computation** dropdown choose **Constant**. A number should appear in the **Value** dropdown menu. Change it to **0.20** (this is the percentage of clients that left the bank regardless of the gender);
- Change the **Label** field from **Value** to **None**;


### Extra formating:
- Go to **Format** (top left) and click on **Worksheet** (a rectangle with format settings should appear on the right);
- Choose the font and size as you please (this will apply the same format settings to all the worksheet);
- Click on **Exited** in the **Dimensions** field and choose **Aliases**;
- Give **0** and **1** **Value (Alias)** : **Stayed** for **0** and **Exited** for **1**;
**Optional**: drag the **Exited** field from **Dimensions** to the **Label** square from the **Marks** working space.


