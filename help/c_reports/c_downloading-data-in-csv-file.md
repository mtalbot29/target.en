---
description: Download data in a .csv format for quick import into Excel, Access, or other data analysis programs.
keywords: reports;download reports;csv;success metrics;order details
seo-description: Download data in a .csv format for quick import into Excel, Access, or other data analysis programs.
seo-title: Downloading Data in a CSV File
solution: Target
subtopic: Multivariate Test
title: Downloading Data in a CSV File
topic: Standard
uuid: 649cbede-7427-4b0e-9ec6-c47f8538fbb1
index: y
internal: n
snippet: y
translate: y
---

# Downloading Data in a CSV File

To download data in a CSV file: 


1. Click [!DNL  Activities], then click the desired activity from the list. 

   If you have many activities, you can filter the list by selecting options from the [!UICONTROL  Type], [!UICONTROL  Status], [!UICONTROL  Reporting Source], [!UICONTROL  Experience Composer], [!UICONTROL  Metrics Type], and [!UICONTROL  Activity Source] drop-down lists. 

1. Click the ** [!UICONTROL  Reports] ** tab. 

1. Click the [!UICONTROL  Download] icon (  ![](../assets/icon download report.png) ), then select a report type to download for analysis in Excel and other tools. 



The section contains the following information: 


* [ Export Report to CSV](c_downloading-data-in-csv-file.md#section_38BD9743EB254453B5F4A0A6F2720CD3)
* [ Export Order Details to CSV](c_downloading-data-in-csv-file.md#section_96B3F578F91F4CA3AFE38BACA2A0F11E)
* [ Caveats](c_downloading-data-in-csv-file.md#section_49B9590904A645B18E694B4EFFFC1DEF)


## Export Report to CSV {#section_38BD9743EB254453B5F4A0A6F2720CD3}

The Success Metrics report shows you information about your success metrics, as well as the following metrics that are not available in the Target UI: 


* Mean time to conversion in hours, so you can see how long it takes the average visitor to reach the conversion point 

* Sum of revenues, squared, for offline statistical confidence calculations 



Data is saved until the end of the activity. 


>[!NOTE]
>
>The CSV report includes only raw data and does not include calculated metrics like revenue per visitor, lift, or confidence used for A/B tests. To calculate these calculated metrics, download the[ Target's Complete Confidence Calculator](https://marketing.adobe.com/resources/help/en_US/target/target/complete_confidence_calculator.xlsx) Excel file to input the activity's value, or review the [ statistical calculations used by Target](https://marketing.adobe.com/resources/help/en_US/target/target/Statistical Calculations.pdf). 



## Export Order Details to CSV {#section_96B3F578F91F4CA3AFE38BACA2A0F11E}

The Order Details report (known as the Audit report in [!DNL  Target Classic]) shows you information about your orders, including: 


* Order date and time 

* Order amount (if you inserted a Place Order mbox) 

  The Order Details report works only if you have orders. 

* Order flag (duplicate or extreme orders) 

  An order is flagged as extreme if it is more than +/- 3 standard deviations from the average order value using the last month of data (up to the point in time in which the calculation was made). An activity will have its extreme orders excluded once the activity has run for an hour or until after 15 orders, whichever comes first. For more information, see [ Excluding Extreme Orders](t_excluding_extreme_orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA). 

* Product ID 

  The total length of product IDs, concatenated with commas, should not exceed 255 characters or the IDs will not display properly in the report. For example, if your order had products with IDs "aa, bb" then the total length is "aa,bb" = 5. 

* Experience 

  In the [!UICONTROL  Order Details] report for [!UICONTROL  A/B Test], [!UICONTROL  Experience Targeting] (XT), and [!UICONTROL  Multivariate Test] (MVT) activities, the [!UICONTROL  Experience] column contains the experience ` localId`. This is the value output from the ` $campaign.recipe.id` in offer tokens. 

  There is not an [!UICONTROL  Experience] column for [!UICONTROL  Automated Personalization] (AP) activities. The current [!UICONTROL  Algorithm Name] column has been replaced with "Control" versus "Targeted" terminology, as shown elsewhere in [!DNL  Target]. 

  There was no impact on [!UICONTROL  Recommendations] activities. 



Keep the following information in mind when analyzing downloaded reports: 


* Revenue metrics that are set to "Increment count and keep the user in the activity" log order details only for the first order made by the same visitor. All subsequent orders increase conversion count, but will not add revenue to RPV/AOV/Sales, and will not be included in the Order Details report. 

* In order to record an order record, the ` orderTotal` parameter must be passed. 

* Values passed via the ` ProductPurchasedId` mbox parameter are listed in the Order Details report. 

* Order report data includes four weeks of data for the default environment (host group) and two weeks for all non-default environments. 

* Best practice is to include an ` orderID` as well as an ` orderTotal`. This allows duplicate orders to automatically be ignored. 



## Caveats {#section_49B9590904A645B18E694B4EFFFC1DEF}

The following information applies to the Download option: 


* You can download both reports for A/B, Automated Personalization, Experience Targeting, and Multivariate activities. You cannot download the Success Metrics report for Recommendation activities. 

* The Download option is not available for A/B and Experience Targeting activities created before Target version 15.7.1 (July, 2015). 

* Experiences with no associated data are not recorded in the downloaded report. 

