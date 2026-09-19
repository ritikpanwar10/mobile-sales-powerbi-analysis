# mobile-sales-powerbi-analysis
Interactive Power BI dashboard analyzing smartphone sales performance, revenue trends, brand market share, and regional metrics using DAX and Power Query.

# Part 1 : Mobile Sales Data Transformation in Power BI (Power Query)
This demonstrates how to import and transform a raw Excel dataset using **Power Query** in **Power BI Desktop**. It walks through cleaning split date attributes, combining them into a unified date format, and standardizing day names.

---

**Key Goals:**
- Import specific worksheet data (`Sheet1`) from an Excel workbook.
- Merge separate `Day`, `Month`, and `Year` values into a proper `Date` column.
- Normalize weekday names so each record uses the full name format (e.g., `Saturday`, `Sunday`).

---

## 🛠️ Step-by-Step Transformation Process

### Step 1: Connect to the Excel Data Source
1. Open Power BI Desktop and select **Get Data** > **Excel workbook**.
2. Browse to your file path (e.g., `Mobile Sales Data.xlsx`) and click **Next**.

<img width="1917" height="973" alt="1" src="https://github.com/user-attachments/assets/22cd2d4a-3ed0-4e25-b83e-6aa085e13729" />

---

### Step 2: Select Sheet and Launch Power Query
1. In the **Choose data** navigator, select **Sheet1**.
2. Review the data preview: notice the split `Day`, `Month`, `Year` values and non-standardized values in `Day Name` (e.g., `Sat`, `Sun`, `Mon` alongside full names).
3. Click **Transform data** to open the Power Query Editor.

<img width="1543" height="862" alt="2" src="https://github.com/user-attachments/assets/b5c35f45-2d33-4626-b04d-c7a4d04b6413" />

---

### Step 3: Combine Date Columns
1. Select the `Day`, `Month`, and `Year` columns and change their data types from whole numbers to **Text (`ABC`)**.
2. Navigate to the **Add Column** tab in the ribbon and click **Custom Column**.
3. Enter the following formula to build a single date string:
   ```powerquery-m
   = [Day] & "-" & [Month] & "-" & [Year]

<img width="1720" height="826" alt="3" src="https://github.com/user-attachments/assets/30b6df52-f014-4045-9ed1-6a73be347262" />



4. Click **OK**.



---

### Step 4: Reorder and Set Date Data Type

1. Drag the newly created custom column to place it where the original `Day`, `Month`, and `Year` columns were positioned.


2. Rename the column header to **`Date`**.


3. Click the data type indicator (`ABC/123`) on the column header and select **Date**.

<img width="1918" height="987" alt="5" src="https://github.com/user-attachments/assets/689a2584-2089-4499-9aaa-cd8876a7c39d" />


---

### Step 5: Clean Columns and Generate Standard Day Names

1. Select and remove the redundant columns: `Day`, `Month`, `Year`, and the original inconsistent `Day Name` column.


2. Select the newly configured **`Date`** column.


3. Go to the **Add Column** tab > click **Date** dropdown > choose **Day** > select **Name of Day**.


4. This adds a clean, fully spelled weekday column (e.g., `Saturday`, `Sunday`, `Monday`).


<img width="1310" height="590" alt="6" src="https://github.com/user-attachments/assets/021bcafd-59fb-4f1c-9b96-29a1e7190615" />


---

### Step 6: Close & Apply

1. Reorder columns as needed to match your desired structure.


2. Go to the **Home** tab and click **Close & Apply** to load the clean dataset into the Power BI data model.

<img width="1915" height="1018" alt="7" src="https://github.com/user-attachments/assets/006d3d8d-ae2e-4980-ac6d-c131802da50b" />

---

## 📂 Output Data Structure

<img width="1913" height="1016" alt="image" src="https://github.com/user-attachments/assets/da0883b6-1e9b-419f-9082-93db9c259bff" />

```

```
