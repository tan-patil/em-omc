# Logging Analytics Basics

## Introduction

In this Lab, you will learn to monitor the health, performance, uptime and availability of the E-Business Suite application and related infrastructure for a large enterprise application.

Estimated Lab Time: 5 minutes

### Objectives
In this lab, our goal is to answer the following questions:

* How many systems are being monitored and their deployment topology?
* What is the log trend by log types, entity, problem priority etc?
* What are the current KPIs and their trends?
* Are there any specific keywords appearing in logs?

Now we will walk through monitoring of E-Business Suite application and related infrastructure.

## **Task 1:**  Monitoring of E-Business Suite application and related infrastructure

Note: If at any point you want to come to the initial screen - you can use your browser back button or "Action" --> "Create New"

1. Click on the field "Entity Type" in the Fields Panel in Log Explorer to bring up a faceted view of all the monitored entities.

   ![](images/entity-facet.png "UIdescription")

2. Click on "Show Trend Chart" in Facet view to visualize the logs trend of these entity types.

   ![](images/facet-with-trend-chart.png "UIdescription")


3. Repeat steps 1 & 2 to visualize log trends for the field "Entity"

   ![](images/entity-trend.png "UIdescription")

   At this point you know different types of logs being ingested, Entity types  and specific entities being monitored.

   We are monitoring a complex packaged apps with multiple application tiers so its important and useful to visualize this complex deployment.

4. Click on the 'Scope Filter' icon in Log Explorer to invoke filter view

   ![](images/filter.png "UIdescription")

   ![](images/scope-filter.png "UIdescription")

5. Search for the keyword "ebsvm\_onprem" in the Entity search box. "ebsvm_onprem" is the top level entity of Entity Type E-Business Suite.

   ![](images/entity-scope-filter.png "UIdescription")

6. In the Scope Filter, select "ebsvm\_onprem" entity from the drop-down to set the analysis scope to this ebsvm_onprem entity.

   ![](images/entity-scope-filter-enter.png "UIdescription")

7. Click "Apply"

   ![](images/ebs-filtered.png "UIdescription")

  You can also visualize the topology of the this EBS deployment by clicking on the "Topology" icon in the scope filter. Topology view can be used to filter logs from a specific Entity.

   ![](images/invoke-topo.gif "UIdescription")

  Click "Close" to close the Scope Filter. Next, let's look at the log trends over time.

8. Click on the Visualizations dropdown in the Visualization Panel to select **Records with Histogram** visualization.

  ![](images/histogram.png "Dropdown")

  ![](images/histogram1.png "Histogram")

  Here you see the distribution of different logs in last 60 minutes. Next we want to see the trend over last 24 hours.

9. Select 'Last 24 Hours' from the Time Range picker

  ![](images/time-picker.png "UIdescription")

  Here you see the volume of logs generated by different Log Sources along with the log records. This visualization shows the top three log sources by their log volume and remaining log sources are grouped in "All Others". Line charts can give more visibility. Lets change to 'Line Chart' Visualization and increase the time-range to Last 14 Days

10. Click on the visualization drop-down and select "Line" visualization and use the "Time Range" picker to select **Last 14 Days**.

  ![](images/line-chart-14-days.png "UIdescription")

   Logging Analytics enriches logs with problem labels and error categories for easy problem identification along their severity. Next, we want to find out problem severities across different Log Sources.

11. Select "Tree Map" visualization from the visualization drop down.

  ![](images/tree-chart-log-source1.png "UIdescription")

  Drag and drop the field "Entity" from the Fields Panel into the "Group by" input box in Visualization Panel and change the order of 'Entity' and 'Log Source' by dragging Entity above Log Source. Click 'Apply'

  ![](images/tree-map-entity-log-source1.png "UIdescription")

12. Next replace the Group-by current inputs with the Field "Label" & "Problem Priority" in that order and select "Word Cloud" visualization.

  ![](images/prep-for-word-cloud.png "UIdescription")

  ![](images/word-cloud.png "UIdescription")

  Here you see different actions and problems labels color-coded by their problem priority.

  Let's go back to 'Records with Histogram' visualization in the context of Entity **ebsvm_onprem** and time-range **Last 14 Days**. You are working with millions of log records and next we want to use Machine Learning techniques to analyze these records.

  ![](images/cluster-start.png "UIdescription")

## Acknowledgements
* **Author** - Gurusamy Poosamalai, Logging Analytics Development Team
* **Contributors** -  Kumar Varun, Logging Analytics Product Management, Jolly Kundu - Logging Analytics Development Team
* **Last Updated By/Date** - Aug 24 2022
