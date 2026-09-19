# mobile-sales-powerbi-analysis
Interactive Power BI dashboard analyzing smartphone sales performance, revenue trends, brand market share, and regional metrics using DAX and Power Query.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Part 1: Data Transformation (Power Query)](#part-1-data-transformation-power-query)
  - [Key Goals](#key-goals)
  - [Step-by-Step Guide](#%EF%B8%8F-step-by-step-transformation-process)
- [Part 2: Dashboard UI Design](#part-2-dashboard-ui-design)
  - [Key Goals](#key-goals-1)
  - [Step-by-Step Guide](#step-by-step-implementation)
## Prerequisites

- **Power BI Desktop** installed
- **Dataset:** Mobile Sales Data.xlsx
- **Assets:** Brand logo file (e.g., vivo-logo.png)
- **Tools:** Microsoft PowerPoint (for color picking)


# Part 1: Data Transformation (Power Query)
Clean split date attributes, combine them into a unified date column, and standardize day names 

---
### Key Goals
- Import Sheet1 from the raw Excel workbook.
- Merge separated Day, Month, and Year values into a single Date column.
- Normalize weekday names into full spelling (e.g., Saturday, Sunday)

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

---

# Part 2: Dashboard UI Design
Set up brand styling by extracting brand colors, setting the canvas background, and creating card containers. 

--- 
### Key Goals

* Logo se exact brand color sample karke uska HEX code extract karna.
* Custom brand color ko Power BI canvas background par apply karna (0% transparency ke sath).
* Visual appeal badhane ke liye logo ke peeche ek clean rounded white card container layer karna.

---

## Step-by-Step Implementation

### Step 1: Insert Logo / Image into Power BI

1. Open your Power BI report and go to the **Insert** tab in the top ribbon.
2. In the **Elements** group, select **Image**.
3. In the right-side **Format image** pane:
   - Expand the **Style** section.
   - Set **Image source** to `Upload Image`.
   - Under the **Image** field, click **Browse...**.
4. Select your file (e.g., `vivo-logo.png`) and click **Open**.
5. Position and resize the image on your canvas as desired.

<img width="1916" height="976" alt="8" src="https://github.com/user-attachments/assets/0dc619e3-6929-40f7-b59a-56661c341a60" />

---

### Step 2: Extract Brand Hex Code using PowerPoint

To match the dashboard's background color precisely with the logo, extract the exact HEX code:

1. Open **Microsoft PowerPoint**.
2. Go to **Insert** > **Pictures** and insert the same image/logo.
3. Go to **Insert** > **Shapes** and add any shape (such as a rectangle or rounded rectangle).
4. Select the shape:
   - Click the **Shape Format** tab in the top ribbon (or the floating toolbar).
   - Click **Shape Fill** > select **Eyedropper**.
   - Hover and click on the desired color within the logo.
5. With the shape now filled with the sampled color:
   - Go back to **Shape Fill** > select **More Fill Colors...**.
   - Go to the **Custom** tab.
   - Locate the **Hex** code input field and copy the code (e.g., `#2424ED`).

<img width="1916" height="980" alt="9 1" src="https://github.com/user-attachments/assets/20acacc4-c6be-471d-a0fb-ebbdd0c02059" />
<img width="1906" height="976" alt="9" src="https://github.com/user-attachments/assets/a56bc990-f5fd-46b2-8c5b-7eb30c225570" />
<img width="1917" height="1013" alt="11" src="https://github.com/user-attachments/assets/fe01bb66-9adb-4576-9866-052da0c1c7df" />
<img width="1218" height="667" alt="12" src="https://github.com/user-attachments/assets/d3aeebe6-c21e-4170-9497-9cdbc77bd320" />

---

### Step 3: Apply the Brand Color to Power BI Canvas

1. Return to **Power BI Desktop**.
2. Deselect all visuals by clicking an empty area on the canvas.
3. Open the **Visualizations** pane and select the **Format page** icon (paint roller/sheet icon).
4. Expand the **Canvas background** section:
   - Click the **Color** swatch dropdown.
   - Click **More colors...**.
   - Paste your copied Hex code (e.g., `#2424ED`) into the **Hex** input box.
   - Set **Transparency** to `0%` to make the color fully visible.

<img width="1918" height="986" alt="13" src="https://github.com/user-attachments/assets/89429617-453e-424e-a6fe-3657a48d0657" />
<img width="1696" height="662" alt="15" src="https://github.com/user-attachments/assets/4cdd11dc-9b69-4682-aeb7-709f4197e5ab" />


---

### Step 4: Add a Rounded Card Container Behind the Logo

1. Go to the **Insert** tab > **Shapes** > choose **Rounded Rectangle**.
2. Configure the shape styling in the **Format shape** pane:
   - **Shape**: Set **Rounded Corners** / **Corner radius** to `18%`.
   - **Style**: Enable fill and set **Fill Color** to `White` (`#FFFFFF`).
   - Remove or adjust the border outline according to your preference.
3. Resize and position the rounded white rectangle directly over the logo.
4. With the rectangle selected:
   - Go to the top **Format** tab.
   - Click **Send backward** (or select **Send to back**).
5. The white rounded card will now sit neatly behind the logo, creating a clean container effect.

<img width="1907" height="990" alt="16 1" src="https://github.com/user-attachments/assets/690b0349-b444-489a-883b-4636836575d6" />

---

