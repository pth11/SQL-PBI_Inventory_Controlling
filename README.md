# SQL-PBI_Inventory_Controlling
Please see the pdf files attached above

## I. Introduction
### 1. Business question
The sales department wants to know the overview of inventory status and look up the product inventory by category and location to come up with an appropriate sales and marketing strategy.
### 2. Dataset
Dataset: **adventureworks2019** (public Google BigQuery dataset)

Dataset dictionary: Please reach file "Data Dictionary" attached above

Dataset Schema: https://i0.wp.com/improveandrepeat.com/wp-content/uploads/2018/12/AdvWorksOLTPSchemaVisio.png?ssl=1

Dataset access: 
- Log in to your Google Cloud Platform account and create a new project.
- Navigate to the BigQuery console and select your newly created project.
- In the navigation panel, select "Add Data" and then "Star a project by name".
- Enter the project name "adventurework2019"

## II. Apply design thinking mindset
**1. Empathize**

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/b4e465be-08bf-47fa-98f4-915209e6e740)

**2. Define point of view**

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/73459b34-a433-42c4-848b-f2751f9008b3)

**3. Ideate***

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/0552fc98-2ffd-49d2-8806-fbc72258edee)

**4&5. Prototype and review**

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/47280733-cfea-49fc-bb0e-7e6c30845f71)

## III. Main Process
### 1. Extract data with Google BigQuery
#### Output total produced quantity and total sold quantity by month/year/quarter (Fact_Built_&_Sold table)

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/fdf61121-d3d9-4d8a-99de-fd8a3a64668d)

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/b9fd3a39-5ce8-4c98-8e1c-693482e7858c)

#### Output product ID, product name, sub-category, category (dim_category table)

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/bd6b3277-0072-4ecb-8e2b-1f8f00dd7384)

#### Output total inventory quantity by product ID (dim_inventory_by_product table)

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/ca19f03c-fefe-4ce3-9992-b3a222ae89de)

### 2. Connect data to PBI and modelling

- Connect queries above and available tables of dataset to PBI
- Modelling

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/42095a95-ba3a-4890-8a4b-e7b57b53a7af)

### 3. Build dashboard

- Using DAX to create measures and calculated columns
- Build 2 report pages

**Overview of inventory by time/location/product**

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/1768a686-bfd8-4514-893f-2680484f4d1d)

**Look up inventory status of each product**

![image](https://github.com/thuhuongphan11/Python_RFM_Analysis/assets/141643891/b4d104b6-12f6-48bd-ab77-1f9f8f363e6f)


## IV. Insights
#### 1. Revenue - Inventory overview
- Revenue tends to increase steadily from 2011 to the end of 2013. Every year, revenue usually peaks in the third quarter and gradually declines in the fourth quarter.
- Stock to sales ratio (average inventory value/sales) tends to increase gradually => Inventory efficiency is decreasing
#### 2. Revenue - Inventory by Category
- Current revenue is only recorded from 2 categories: Bikes and Components 
- The largest revenue comes from the Bikes category at $145M (88%), 7 times more than the Components category 
- The Bikes category has the largest inventory value of 24M (70%), nearly 4 times higher than the Components industry (9M). 
- Components have a higher proportion of inventory value than revenue => Overstocking
#### 3. Revenue - Inventory by Subcategory
- Top 3 Subcategory belong to Bikes category, the rest belong to Components category 
- Subcategory Road Bikes, Mountain Bikes, Touring Bikes has a ratio of inventory value to sales ranging from 15 to 21%, higher than Mountain Frames 37% 
- The highest is Subcategory Wheels (210%) => Overstocking
#### 4. Revenue - Inventory by Product
- Top 2 products in the Components category, the rest in the Bikes category 
- These products have a high inventory-to-sales ratio: HL Mountain Frame - Black, 38 (127%), HL Mountain Frame - Silver, 38 (61%), Road-150 Red, 44 (51%) => Overstocking
- Currently, the company has 69 types of products with inventory below the safe level -> Understocking. In which, most products belong to the Other category (55 products).
#### 5. Inventory by Location
- Locations that are occupying the highest amount of inventory are Subassembly (95K units) and Miscellaneous Storage (83K units), but have low total inventory values (3.3M and 1.5M, respectively) => Store many items that are low-value 
- Location Final Assembly and Finished Goods Storage, although not having a high inventory volume (20K and 17K, respectively), have the highest total inventory value (13.6M and 12.2M respectively) => Store items that are high-value.
## V. Recommendations
- Adjusting the amount of inventory to increase or decrease in proportion to the rate of revenue fluctuations, with an increase in the third quarter of each year and a gradual decrease beginning in the fourth quarter.
- Research more about the reason the stock-to-sales ratio tends to rise in order to find solutions to lower inventory costs.
- Make a new marketing plan for Accesories, clothing, and Other categories because they are currently not bringing in revenue.
- Focus on promoting sales of HL Mountain Frame - Black, 38, HL Mountain Frame - Silver, 38 and Road-150 Red, 44 products, as well as products in Subcategory Wheels to resolve inventory backlog
- Notify and check with the production and purchasing departments about the products that are currently out of stock and adjust the Safety Stock level to suit the profitability of each product line.
- Many items are out of stock, so it is recommended to collect more opportunity cost data when an item is out of stock, which can be used to control and forecast future sales.
