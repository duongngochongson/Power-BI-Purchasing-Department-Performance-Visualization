# Power BI Purchasing Department Dashboard
The project aims to visualize overall and in-depth information on the purchasing department for managers and business analysts.

## Table of Contents:
1. [Overall](#overall)
2. [Design Thinking](#dt)
3. [Visualization Process](#vis)
4. [How to Use Dashboard](#how)

<div id='overall'/>
  
## Overall

**Approach & Platform**: Apply **design thinking** to identify key metrics, then pull relevant data from BigQuery.

**Main Techniques**: Clean and transform data in **Power Query, develop models, and employ DAX** for calculations.

**Context**: AdventureWorks database supports standard online transaction processing scenarios for a fictitious bicycle manufacturer. The purchasing department will be responsible for purchasing goods, raw materials, and semi-finished products for production. Management expects that the ordered goods are sufficient for sales, on time, and at optimal import prices.

**Result**: Based on the context, I will create an **operational dashboard** for vendor performance, including 2 visuals: an overview and a detailed information. Which enable data-driven decisions on vendor selection, product purchases, optimal cost and timing.
  
**Links to data dict:** https://dataedo.com/download/AdventureWorks.pdf

<div id='dt'/>

## Design Thinking

### Step 1 - Empathize

| 5W1H | |
| - | - |
| Who will be viewing this Dashboard?                                | Purchasing Manager, accountant |
| If we had to choose only one key Stakeholder, who would it be? | Purchasing Manager |
| What problem does this Dashboard solve?                            | It enhances vendor oversight, promotes data-driven decisions, and helps optimize vendor relationships and costs.|
| Describe the problem in one sentence                               | Provide the Purchasing Manager with necessary information about the overview situation, as well as the performance details of the vendor in particular. |
| When and where will Stakeholders view this Dashboard?        | The Dashboard can be viewed during monthly meetings or managers alone.|
| Why do stakeholders need this Dashboard?                   | Understand vendor overview performance and evaluate decisions|
| How stakeholders achievie their goals?           | Understand the situation to make decisions |


|Stakeholder Empathy | |
| -- | -- |
| Pains  | A large amount of info that need to be analyzed as well as identify important information |
| Thinking and feeling  | Worry about the effectiveness of the purchasing department in general. As well as have opinions about vendors |
| Seeing  | Dashboard of the company's purchasing department and each vendor's info for comparison and contrast |
| Saying and doing   | The dashboard system is quite intuitive to grasp the overview information to see the big picture. Also the vendor detail dashboard is full of information to see in depth|
| Gains | See the overview change and the details of how the vendors are operating to make the right choice|

### Step 2 - Define POV

|       | NORTHSTAR METRIC     |
|----|---|
| **What VALUE you want to measure?** | The effectiveness of orders |
| **WHEN the value DELIVERY SUCCESS?** | Orders are completed with no errors (such as number of receive products or stockable products) |
| **Northstar Metric Name**  | % No-error Orders (no-error order is order that the number of products in the order is equal to the number of stocked products) |
| **WHY do you choose this metric?** | Because the goal is to provide enough goods for the production department. |

### Step 3 - Ideate

| Layer 0 Dimension: Total Metrics   | Layer 1 Dimension: Breakdown by 1 Dimension |
|----|----|
| % no-error orders, % receive products, % reject products, % fee | % above over time, by ship method, and sub-category type |

**Next, I repeat Step 4 - Prototype and Review several times to achieve the final result**

<div id='vis'/>

## Visualization Process

### Data Modeling

Data imported to Power BI from Google BigQuery public dataset, then data is transformed in Power Query, finally modeled as below.

![purchasing modeling](https://github.com/user-attachments/assets/018bbf03-71f5-439c-8f31-ad95a0716f28)

### Dashboard Building

Visual 1: Vendor Performance Overview

![purchasing overview](https://github.com/user-attachments/assets/69ae5ca4-c2e0-42f1-ab58-f8e1ed54af4b)

Visual 2: Vendor Performance Detail

![purchasing detail](https://github.com/user-attachments/assets/b93e0fe5-e5f6-458b-97a8-5b3db8691e75)

<div id='how'/>

## How to Use Dashboard

Below is workflow suggestion:

| **Action**                      | **Description**                                                                                      |
|---------------------------------|------------------------------------------------------------------------------------------------------|
| Access and Review Summary       | Start by looking at the Overview tab to check key stats like error-free orders, total costs, extra fees, and the number of active vendors. This gives you a quick view of overall vendor performance and spending.<br><br> *Example: In the Pedals subcategory overview from 2013 to 2014, about 76% of orders were error-free (correct quantity and quality for stocking), with an average extra fee of 8.68%, and a total cost of 13.60M across seven vendors.*|
| Analyze Trends and Rankings     | Use the trend charts to spot patterns or problems, like a drop in reliability or rising costs. Vendor rankings help you see which vendors are performing well and which need attention.<br><br> *Example: The "% Error-Free Orders over Time" chart reveals that reliability dropped to 71% in March 2014, while total costs spiked to 1.57M in July 2014. VendorID 1586 stands out with a 78.72% error-free rate, suggesting they are a reliable vendor compared to others.*|
| Select and Analyze Vendor       | Switch to the Vendor tab to focus on a specific vendor. View detailed metrics like non-error orders, extra fees, and trends, providing a closer look at their performance and cost-effectiveness.<br><br> *Example: VendorID 1506 ranks second in error-free orders at 77.66%, but they are not among the top vendors for low extra fees.*|
| Examine Vendor Details          | Check product-specific data such as pricing, fees, taxes, and freight costs. This gives you a complete view of each vendor’s cost structure and helps with decision-making.<br><br> *Example: Specifically, the detailed dashboard shows that while their average extra fee is 8.68%, products in the Pedals category have a fee of 9.5%, limiting their competitiveness.*|
| Generate Reports and Take Action| Use the insights to create reports, share findings, and make informed decisions, like improving vendor relationships or renegotiating contracts.<br><br> *Example: Given this, VendorID 1586 could be prioritized for future orders due to their strong performance, while negotiations with VendorID 1506 could focus on reducing freight costs to improve overall cost efficiency.*|
