# How to Build Data Visualisation Components	

You can add charts and other data visualisation elements to **pages** and **rich text fields**, using the code snippets explained below.

## Basic structure of a code snippet

![image alt text](images/image_73.png)

## Counter component

![image alt text](images/image_74.png)

![image alt text](images/image_75.png)

![image alt text](images/image_76.png)

![image alt text](images/image_77.png)

## Pie chart and list chart components

![image alt text](images/image_78.jpg)

![image alt text](images/image_79.png)

## Bar chart component

![image alt text](images/image_80.png)

![image alt text](images/image_81.png)

## Create visualizations of thesauri with groups.

Charts can be configured to display thesauri that have nested values in two ways. By default charts will display an aggregation of parent categories. If you want to visualize each individual item in a thesauri without grouping them in their parent categories you can use the `scatter` parameter. 

For example:

`<BarChart property="select_with_nested" context="60cb857034f3490ed729e34f" scatter="true" />`

This way the chart will show thesauri items individually, instead of the groups in which they are organized.


## Examples of analysis and data visualisation

Just to give you an idea of what is possible in Uwazi, please take a look at some of the public projects that are documenting human rights violations for advocacy, but please note that these require some technical proficiency in working with HTML, CSS and Javascript.

- TGEU works with 5 ProTrans partners from Eastern Europe and Central Asia on monitoring violence and human rights violations against trans people in this region. [https://tgeu.uwazi.io/](https://tgeu.uwazi.io/)

![image alt text](images/image_82.png)

- Justice Project Pakistan shares open source data sets based on existing research on death row and on age determination under the Juvenile Justice Systems Ordinance. This project marks the beginning of the process of making the information publicly available, allowing the public and academic institutions to generate their own findings and base their campaigns on verified data. [https://data.jpp.org.pk](https://data.jpp.org.pk)

![image alt text](images/image_83.png)
