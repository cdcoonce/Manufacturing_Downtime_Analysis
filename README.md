# Manufacturing Downtime Analysis

## Table of Contents

- [Manufacturing Downtime Analysis](#manufacturing-downtime-analysis)
  - [Table of Contents](#table-of-contents)
  - [Project Overview](#project-overview)
  - [Objectives](#objectives)
  - [Data \& Tools](#data--tools)
  - [Analysis Steps](#analysis-steps)
    - [Objective 1: Calculate Line Efficiency](#objective-1-calculate-line-efficiency)
    - [Objective 2: Identify Main Downtime Factors](#objective-2-identify-main-downtime-factors)
    - [Objective 3: Downtime by Operator and Factor](#objective-3-downtime-by-operator-and-factor)
  - [Key Findings](#key-findings)
  - [Recommendations](#recommendations)
  - [Acknowledgments](#acknowledgments)

---

## Project Overview

You work as a Production Manager for **Wolf Cola**, a soft drink company that manages bottling operations in Philadelphia. The former manager collected productivity and downtime data in an Excel file. Your task was to:

- Analyze productivity data to calculate **line efficiency**.  
- Investigate downtime logs to identify **main downtime factors**.  
- Examine downtime by operator to determine **operator-specific** improvement areas.

---

## Objectives

1. **Calculate Line Efficiency**  
   - Determine how efficiently the production line is operating by comparing actual production times to standard or minimum batch times.

2. **Identify Main Downtime Factors**  
   - Use a Pareto analysis to highlight the factors that account for the majority of production downtime.

3. **Calculate Downtime by Operator and Factor**  
   - Create a matrix to reveal which operators are most impacted by each downtime factor and prioritize improvement efforts.

---

## Data & Tools

- **Data Source**: An Excel workbook containing:  
  - A **Line Productivity** tab with batch start/end times, operators, and products  
  - A **Products** tab with standard or minimum batch times  
  - A **Line Downtime** tab with downtime logs for each batch  
  - A **Downtime Factors** tab listing categories of downtime
- **Software**: Microsoft Excel (for calculations, lookups, charts, and conditional formatting)

---

## Analysis Steps

### Objective 1: Calculate Line Efficiency

1. **Add a “Batch time” column** in the **Line Productivity** tab:  
   - Formula calculates the number of minutes between each batch’s `Start time` and `End time`.

2. **Add a “Min batch time” column**:  
   - Use a lookup (e.g., `VLOOKUP`) from the **Products** tab to retrieve the standard or minimum time for each product.

3. **Calculate “Efficiency”**:  
   - For each operator, divide the sum of `Min batch time` by the sum of `Batch time`.  
   - Efficiency formula:  
     \[
     \text{Efficiency} = \frac{\sum(\text{Min batch time})}{\sum(\text{Batch time})} \times 100\%
     \]

4. **Create a bar chart**:  
   - Plot operators on the X-axis and their respective efficiency on the Y-axis.

5. **Format the chart and add a title**:  
   - Use labels, clear axes, and an insightful title.  
   - Provide a brief recommendation based on the results (e.g., highlight any operators with below-average efficiency).

---

### Objective 2: Identify Main Downtime Factors

1. **Add a “Downtime” column** in the **Downtime Factors** tab:  
   - Sum the downtime for each factor from the **Line Downtime** tab.

2. **Sort the factors in descending order**:  
   - Focus on the factors with the highest downtime first.

3. **Create a “Pareto” column**:  
   - Calculate the running total of downtime as a percentage of the grand total.  
   - Formula:  
     \[
     \text{Cumulative \%} = \frac{\text{Cumulative Downtime}}{\text{Total Downtime}} \times 100\%
     \]

4. **Build a Pareto chart**:  
   - Combine a bar chart (for downtime) and a line chart (for cumulative %).

5. **Use chart title and formatting**:  
   - Identify the top factors that make up ~80% of downtime.  
   - Provide a short recommendation on how to address them.

---

### Objective 3: Downtime by Operator and Factor

1. **Create a matrix**:  
   - Rows = Operators  
   - Columns = Main downtime factors

2. **Add an “Operator” column** to the **Line Downtime** tab:  
   - Use a lookup to match each downtime entry to the correct operator from the **Line Productivity** tab.

3. **Calculate total downtime for each operator by factor**:  
   - Use a pivot table or `SUMIFS` in Excel.

4. **Apply conditional formatting**:  
   - Highlight cells with higher downtime to quickly spot trouble areas.

5. **Chart title and formatting**:  
   - Present a heat map or similar visual to illustrate which operators are most affected by each factor.  
   - Make a recommendation for targeted improvements.

---

## Key Findings

- **Overall Line Efficiency**: ~64%.  
- **Lowest Efficiency Operator**: Mac at 61% (opportunity for targeted training or process improvement).  
- **Main Downtime Factors**: The top 5 account for ~80% of total downtime (Pareto principle).  
- **Operator Error**: 3 of the top 5 factors were directly related to operator errors, suggesting a need for focused training.

---

## Recommendations

1. **Machine Adjustment Training**  
   - Provide standardized training for all operators to reduce time lost on machine setup/adjustments.

2. **Batch Change Training**  
   - Offer specific training for Mac to improve performance during product or batch changes.

3. **Preventative Maintenance & Inventory Checks**  
   - Schedule regular maintenance to avoid unexpected machine breakdowns.  
   - Double-check inventory labels/stock levels to reduce downtime related to inventory shortages or labeling errors.

---

## Acknowledgments

This project was completed as part of a guided learning experience with **Maven Analytics**. Special thanks to Maven Analytics for providing structured guidance and high-quality datasets to enhance analytical skills.