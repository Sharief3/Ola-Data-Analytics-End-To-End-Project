huh# Ola-Data-Analytics-End-To-End-Project
## Project Objective
   
1.  **To analyze and solve crucial business challenges faced by ride-share companies** by utilizing a large dataset of Ola bookings, which encompasses 19 columns and imported nearly 100,000 records.
2.  **To monitor and optimize key operational metrics,** such as improving delivery time, analyzing fare structures, and tracking critical issues like cancellation rates and vehicle breakdowns.
3.  **To execute a full end-to-end data analytics workflow,** beginning with essential data cleaning, employing SQL to answer specific business questions, and concluding with the creation of a comprehensive Power BI dashboard for effective visualization and reporting.

## Data Set Used
<a href="https://app.powerbi.com/links/iNNMN3jznq?ctid=eb322777-d3cb-4cf3-8785-b55cf5ec11ce&pbi_source=linkShare">Data set</a>

# The Setup
 
## SQL Questions
 1. Retrieve all successful bookings
 2. Find the average  ride distance for each vehicle type
 3. Get the total number of cancelled ride by customers
 4. List the top 5 customers who booked the highest number of rides
 5. Get the number bof rides cancelled by driver due to personal and car related issues
 6. Find the maximum and minimum driver ratings for prime sedon bookings
 7. Retrieve  all rides where payment was made using UPL
 8. Find the average customer rating per vehile type 
 9. Calculate the total booking value of rides completed successfully
 10. List all incomplete ride along with the reason

## PowerBI  Questions
 1. Ride volume over time
 2. Booking status breakdown
 3. Top 5 vehicle type by ride distance
 4. Average customer ratings by vehicle type
 5. Cancelled rides reason
 6. Revenue by payment method
 7. Top 5 customers by total booking value
 8. Ride distance distribution
 9. Driver ratings distribution
 10. Customer vs. Driver ratings 

# Detailed Process
To explain the project's detailed process is to chart the entire journey from raw data to actionable insights. The Ola Data Analytics End-to-End Project is a comprehensive workflow designed to solve key business challenges through structured analysis and visualization.

The project follows three major phases: **Data Preparation**, **SQL Analysis**, and **Visualization/Reporting**.

---

### Phase 1: Data Preparation and Acquisition

This phase focuses on ensuring the data is clean, accessible, and properly structured for analysis.

1.  **Data Acquisition and Scope:** The project begins with a large-scale dataset of Ola bookings. This dataset includes **19 columns** and imports a substantial volume of records, specifically **99,956 records** that were successfully imported into the database (derived from a larger set of 100,000+ rows).
2.  **Initial Data Cleaning (Excel):** The data analysis process starts with data cleanings. Initial cleaning is performed in Excel, primarily by removing duplicates. For instance, **857 duplicate rows were found and removed**. Other cleanup actions, such as trimming white spaces, are also mentioned.
3.  **Database Setup (SQL Workbench):** The cleaned data is downloaded as a CSV file [6]. MySQL Workbench is used to create and manage the database.
    *   A database named `ola` is created and selected for use.
    *   The CSV file is imported into this database using the Table Data Import Wizard to create the main table, named `bookings`. Data types for the 19 columns are confirmed during this import process.

---

### Phase 2: SQL Analysis and Business Queries

The core objective of this phase is to use SQL to answer specific, real-world business questions, which often mirror requests managers might make in a daily business environment.

1.  **Question Complexity:** The queries range from easy to hard, covering common operational concerns.
2.  **Query Execution and Grouping:** SQL queries are run to extract key metrics. Examples include:
    *   Retrieving **all successful bookings** (by selecting records where `Booking Status` equals 'Success').
    *   Finding the **average ride distance for each vehicle type** (using the `AVG` function and grouping by `Vehicle Type`).
    *   Calculating the **total number of canceled rides by customers** (using the `COUNT` function) .
    *   Listing the **top five customers who booked the highest number of rides** (using `COUNT(Booking ID)`, `GROUP BY Customer ID`, `ORDER BY Total Rides DESC`, and applying a `LIMIT 5`).
    *   Calculating the **total booking value of successfully completed rides** (using the `SUM` function on `Booking Value` and filtering for successful bookings, resulting in approximately 34 million).
3.  **Creating Views for Reporting:** A critical step for the end-to-end workflow is creating a **VIEW** for the result of every query. This is done using the `CREATE VIEW` command. The purpose of the view is to store the query output in a temporary format so that managers can easily retrieve the answers (e.g., `SELECT * FROM Successful Bookings`) without needing to execute or even see the complex underlying SQL query.

---

### Phase 3: Visualization and Reporting (Power BI Dashboard)

The final phase involves transitioning the insights gathered from SQL into visual reports using Power BI for effective decision-making.

1.  **Dashboard Structure and Design:**
    *   The project involves building a multi-page Power BI dashboard. This segmenting prevents confusion and ensures clean display of many metrics.
    *   The five primary segments (pages) created are: **Overall, Vehicle Type, Revenue, Cancellation, and Ratings** .
    *   Navigation: Custom backgrounds/decks are prepared, and interactive **buttons** are implemented across all pages using the **Page Navigation** action to allow users to easily switch between segments.
2.  **Connecting Data and Transformation:**
    *   The data source (the CSV/Excel file) is connected to Power BI.
    *   Initial transformations are performed, such as changing the data type of the `Date and Time` column to strictly `Date` format.
3.  **Creating Key Visualizations (Examples):** The dashboard addresses the remaining Power BI questions using appropriate visualizations:
    *   **Overall Page:** Features a **Line Graph** showing **Ride Volume Over Time**  and a **Pie Chart** for the **Booking Status Breakdown** (Success, Cancel by Customer, etc.) . Key numerical metrics (Total Bookings, Total Booking Value) are displayed using **Card** visualizations, with the Booking Value specifically filtered to show only successful rides.
    *   **Revenue Page:** Uses a **Column Chart** to show **Revenue by Payment Method** (e.g., Cash, UPI, Credit Card). It also features a **Table** listing the **Top Five Customers by Booking Value**.
    *   **Cancellation Page:** Visualizes **Cancellation Rights Reason by Customer** and **Cancellation Rights by Drivers**
. This page also uses **DAX measures** to calculate the **Cancellation Rate** (Percentage of Canceled Bookings / Total Bookings * 100).
    *   **Ratings Page:** Displays the **Average Driver Ratings** and **Average Customer Ratings** segmented by specific vehicle types (like Prime Sedan or Prime SUV).
4.  **Final Steps:** A date slicer is placed on relevant pages to allow users to dynamically filter the visualizations. Once completed, the dashboard can be shared or published.

## Dashboard
![Uploading Screenshot 2025-10-24 064704.png…]


# Project Insights
 When we look at the Ola Data Analytics End-to-End Project, the goal is to transform raw data into clear business intelligence.

Here are the project's key insights, distilled into three simple lines:

1.  **Business Focus and Data Foundation:** The project utilizes a large dataset of nearly **100,000 Ola booking records** (specifically, 99,956 records were imported) to find solutions for crucial business issues, such as **optimizing delivery time, analyzing fares, and reducing cancellation rates**.
2.  **Actionable Metrics via SQL:** The analysis answers specific questions by generating critical numbers, including identifying **top five customers** who book the highest number of rides, calculating the **average ride distance for each vehicle type**, and determining the **total booking value of successfully completed rides**, which totaled approximately **34 million**.
3.  **Visual Reporting for Decisions:** The workflow culminates in a segmented Power BI dashboard (covering sections like Overall, Revenue, and Cancellation) that visually reports key trends, such as **ride volume over time** and the calculated **cancellation rate** (found to be around 28%).

# Final Conclusion
Drawing on the journey from raw data to final visualization, the conclusion of the Ola Data Analytics End-to-End Project can be summarized in these three simple lines:

1.  **Successful Data Transformation:** The project validated an effective process for handling and cleaning a large dataset (nearly **100,000 Ola booking records** across 19 columns)  to find solutions for core business issues like optimizing delivery time and managing cancellation rates.
2.  **Generation of Actionable Intelligence:** Detailed SQL analysis successfully quantified key business metrics, confirming, for example, that the **total booking value of successfully completed rides** amounted to approximately **34 million**, and identifying the **top five customers** based on booking frequency.
3.  **Delivery of a Decision-Making Dashboard:** The entire workflow resulted in the creation of a **five-segmented Power BI dashboard** (Overall, Revenue, Cancellation, Vehicle Type, and Ratings), providing clear visual reports—such as the calculated **28% cancellation rate** —to support efficient management and operational decisions.
