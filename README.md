# P002-Data-Engineering-Project

<img src="Images/ecommerce.png" width=70% height=70%/>

This repository contains web scraping of an e-commerce project. <br>

The script below is a fictional creation focused on data collection and data cleaning.

## P002 - Data Engineering Project for an E-Commerce

The aim of this project is:
* Perform web scraping of e-commerce
* Determine the raw materials needed to make the pants
* Determine the types of jeans pants and their colors
* Determine the best price to sell jeans pants

---
## 1. Business Problem

Two businessmen, named Eduardo and Marcelo, wanted to start an e-commerce company called Star Jeans to sell men's jeans pants. The data scientist is responsible for determining the raw materials, types, colors, and best price to sell jeans pants. <br>

## 2. Business Results

Based on the business criteria, a script is running to collect data from the website for a period. After that, the results will be analyze. <br>

## 3. Business Assumptions

* The data will be collected for two weeks at two different hours of the day
* The objective is to keep the company's initial operating costs low considering a small amount of jeans types
* Star Jeans' main competitors are H&M and Macy's
* Pocket material data were not considered
* "Product safety" attribute excluded for having 80 percent of NA values
* "More sustainable materials" attribute excluded for having 59 percent of NA values
* In the composition, when products with different percentages occur, was selected the material with the highest value


<br>

* The variables collected from website are:<br>

Variable | Definition
------------ | -------------
|product_id| Identification number of each product|
|fit| How the product fits on the body |
|product_name| The type of jeans pants |
|product_price| The price of jeans pants |
|color_name| The colors of jeans pants |
|style_id| The product code based on SKU (Stock Keeping Unit) |
|color_id| The id colors of jeans pants based on SKU (Stock Keeping Unit) |
|scrapy_datetime| The information from both date and time from when it was collected |
|size_number| Body heigt in centimeters |
|size_model| The first number is the waist circumference, and the second number is the inseam length, both in inches |
|cotton| Percent of cotton in the jeans pants |
|polyester| Percent of polyester in the jeans pants |
|spandex| Percent of spandex in the jeans pants |
|elasterell| Percent of elasterell in the jeans pants |

<br>

## 4. Solution Strategy

My strategy to solve this challenge was:
1. Understanding the business model 
2. Understanding the business problem
3. Collecting the data
4. Cleaning the data
5. Insert the data on a database
6. Webscraping [script](https://github.com/almirgouvea/P002-Data-Engineering-Project-E-commerce/blob/main/webscraping_hm.py)

<br>

* The data collection process focuses on:

   * Scrapy the website using Beautiful Soup
   * Collect product data considering the raw materials, types, colors, price and scrapy datetime
   * Generate style id and color id based on SKU (Stock Keeping Unit) 
   * Excludes the following pocket material data: "Pocket", "Pocket lining", "Shell" and "Lining"
   
<br>

* The data cleaning process focuses on:

   * Specifies a default format for values in the dataframe: lowercase and underscore between words
   * Generate "size number" and "size model" attributes based on size value
   * Split the composition attribute based on materials
   * Determine the percentage of each material in the composition: "cotton", "polyester", "spandex", "elasterell"
   * Excludes "Product safety" and "More sustainable materials" attributes

<br>

* The data insert process focuses on:
   
   * Create a routine on Cronjob to execute the web scraping script
   * Execute the web scraping script for two weeks at two different hours of the day
   * Insert the web scraping values on the SQLite database
      
<br>


## 5. Conclusion

Based on the business criteria, a script is running to collect data from the website for a period. After that, the results will be analyze. <br>

## 6. Next Steps

Based on the business criteria, a script is running to collect data from the website for a period. After that, the results will be analyze. <br>

----
**References:**
* Comunidade [DS](https://www.comunidadedatascience.com/) 
* Dataset from [H&M](https://www2.hm.com/en_us/men/products/jeans.html)
* Image available free on [Shutter Stock](https://www.shutterstock.com//)
