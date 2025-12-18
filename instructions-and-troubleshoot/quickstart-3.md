---
layout:
  width: default
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# Export Data Files

Use these general rules for any platform before you upload files to Next-Cart:

1. **Export all relevant entity types**
   * Products (including variants/options, images)
   * Categories/collections
   * Customers
   * Orders / invoices / sales history
   * Any extra files required by the platform (XML, additional images, special tables).
2. **Prefer structured formats**
   * Use **CSV**, **XLSX**, or **XML** where the platform supports it.
   * Do **not** manually edit column headers or delete columns unless explicitly documented.
3. **Export in complete ranges**
   * Always use “all records” or the **full date range** where possible.
   * If the platform limits export size (e.g. max 3,000 orders), export in **batches** and keep all files.
4. **Keep files clearly organized**
   * Use a clean folder structure like:
     * `/source-exports/products/`
     * `/source-exports/orders/`
     * `/source-exports/customers/`
   * Avoid renaming files in ways that remove their original meaning.

#### Export Data Instructions

<details>

<summary><strong>AbleCommerce</strong></summary>

**Data types to export**

* Products (including variants/options)
* Orders
* Customers (Users)

**Intrusctions**

1. **Export products (and variants/options)**

* Sign in to **AbleCommerce admin**.
* Go to **Data → Export → Products**.
* Choose **Export All Products** (or filter if you only need a subset).
* Select the correct **Export Type**:
  * Standard Product Export
  * Product Variants Export
  * Product Options Export
* Select all required fields and run the export.
* Download the generated **.zip** containing your product CSV file(s).

2. **Export orders**

* Go to **Data → Export → Orders**.
* Filter by date range or status as needed.
* Select the required fields.
* Run the export and download the orders CSV.

3. **Export customers (users)**

* Go to **Data → Export → Users**.
* Run the export to generate the customers CSV.
* Download the file from the export list.

</details>

<details>

<summary><strong>Adobe Business Catalyst</strong></summary>

If you are looking to migrate your store from Adobe Business Catalyst, there is a critical piece of information you must know: Adobe Business Catalyst is a discontinued platform.

Adobe officially shut down the service, and all servers were taken offline on March 26, 2021. After this date, all sites and all store data were permanently deleted by Adobe.

Before the shutdown, Adobe encouraged users to export their data. This process typically involved:

1. Using the **"Export Site"** tool in the admin panel.
2. Downloading a **.zip** file containing your site's content.
3. Manually exporting your CRM data (Customers) and E-commerce data (Products, Orders) as **.csv** files.

You must have these **.zip** or **.csv** files in your possession. **If you do not have a data backup file from before the 2021 shutdown, your data is unfortunately not recoverable.**

If you _**do**_ have your old Adobe Business Catalyst backup files, a migration is absolutely possible.

</details>

<details>

<summary><strong>Amazon Store (Amazon Seller Central)</strong></summary>

**Data types to export**

* Inventory / product listings
* Orders / sales history

**Instructions**

1. **Export products (Inventory Report)**

* Log in to **Amazon Seller Central**.
* Go to **Reports → Inventory Reports**.
* Choose **Inventory Report** or **Active Listings Report**.
* Click **Request Report**.
* Wait until the status is **Ready**, then click **Download**.
* Save the resulting **.txt** file (tab-delimited).

2. **Export orders (Order Reports)**

* Go to **Orders → Order Reports**.
* For a full history, create a **Date Range Report**.
* Select the required date range.
* Click **Request Report** and wait for it to be generated.
* Download the resulting **.txt** file.

**Limitations**

* Amazon does **not** provide a full standalone customer list; customer data is only included in order reports.

</details>

<details>

<summary><strong>Big Cartel</strong></summary>

**Data types to export**

* Orders (CSV)

> Product data is typically accessed via direct connection; no native full product CSV export is required for a standard migration.

**Instructions**

1. Log in to **Big Cartel** admin.
2. Go to the **Orders** tab.
3. Choose the **Unshipped** or **Shipped** tab, depending on the orders you need.
4. Optionally use the search / filter to narrow results.
5. Open the **action menu (… )** and select **Download CSV**.
6. Save the generated orders CSV file.

</details>

<details>

<summary><strong>EKM (formerly ekmPowershop)</strong></summary>

**Data types to export**

* Products
* Categories
* Orders
* Customers

**Steps**

1. **Enable the Import/Export System**

* Log in to **EKM admin**.
* Go to **Features → Feature Library**.
* Find **Import/Export System** and click it.
* Click **Install Feature**.

2. **Open the export tool**

* Go to **Features → Import/Export System**.
* Click **Export Data**.

3. **Export products**

* Choose **Export Products**.
* Keep **All Products** selected or filter as needed.
* Continue to **Choose Fields** and leave required fields checked.
* Continue to **Choose Download Type** and select **XML File**.
* Download the products XML.

4. **Export categories, orders, customers**

* Repeat the export for:
  * **Categories** → Download as **CSV**
  * **Orders** → Download as **CSV**
  * **Customers** → Download as **CSV**

</details>

<details>

<summary><strong>GoDaddy</strong></summary>

**Data types to export**

* Products
* Orders
* Customers

**Instructions**

1. **Export products**
   * In GoDaddy admin, go to **Commerce → Products**.
   * Open the **Import/Export** dropdown and select **Export**.
   * Set any filters you need.
   * Click **Export**.
   * Download the products CSV from the link sent to your email.
2. **Export orders**
   * Go to **Commerce → Orders**.
   * Click **Download**.
   * Choose the appropriate **date range** in “Include orders from”.
   * Under **Export details**, select **Orders with line item details**.
   * Confirm and download the orders CSV via the email link.
3. **Export customers**
   * Go to **Customers → All**.
   * Select the accounts to export (or select all).
   * Click the **…** menu and choose **Export**.
   * Download the customers CSV via the email link.

</details>

<details>

<summary><strong>nopCommerce</strong></summary>

**Data types to export**

* Products (XML + XLSX)
* Manufacturers
* Categories
* Customers
* Orders

**Instructions**

1. **Export products (two files)**
   * In **nopCommerce admin**, go to **Catalog → Products**.
   * Click **Export → Export to XML (all found)** and download the products XML.
   * Click **Export** again → **Export to Excel (all found)** and download the products XLSX.
2. **Export manufacturers**
   * **Catalog → Manufacturers → Export → Export to XML**
3. **Export categories**
   * **Catalog → Categories → Export → Export to XML**
4. **Export customers**
   * **Customers → Customers → Export → Export to XML (all found)**
5. **Export orders**
   * **Sales → Orders → Export → Export to Excel (all found)**

</details>

<details>

<summary><strong>QuickBooks</strong></summary>

**Data types to export**

* Products / Items
* Customers
* Orders / Sales (reports)

**QuickBooks Online (QBO)**

1. **Export products & services**
   * Log in to **QuickBooks Online**.
   * Click the **gear icon (⚙)** → **Products and services**.
   * Use **More / report / export** option to run a report.
   * Use the **Export** icon and choose **Export to Excel** (.xlsx).
2. **Export customers**
   * Go to **Business overview → Reports**.
   * Select **Customer Contact List**.
   * Optionally customize columns.
   * Export to **Excel**.
3. **Export orders / sales**
   * Go to **Reports**.
   * Search for and open **Invoice list** (or relevant sales report).
   * Set the full date range for migration.
   * Run the report and export to **Excel**.

**QuickBooks Desktop / POS**

4. **Export item list (products)**
   * Open the company file as **Admin**.
   * Go to **Lists → Item List**.
   * Click the **Excel** dropdown → **Export all Items**.
   * Choose **Create a comma separated values (.csv) file** and export.
5. **Export customers**
   * Go to **Customers → Customer Center**.
   * Click the **Excel** dropdown → **Export Customer List**.
   * Choose **.csv** and export.
6. **Export orders / sales**
   * Go to **Reports → Customers & Receivables**.
   * Run the appropriate sales report.
   * Click **Excel → Create New Worksheet** and choose **.csv** export.

</details>

<details>

<summary><strong>Rain POS</strong></summary>

**Data types to export**

* Products & categories
* Customers
* Orders

**Instructions**

1. **Export products & categories**
   * In **Rain POS** admin, go to **Inventory → Bulk**.
   * Download these four spreadsheets (with appropriate date filters):
     * _Edit Existing Products Long_
     * _Edit Existing Inventory_
     * _Categories_
     * _Product Images_
2. **Export customers**
   * Go to **Customers → Customers**.
   * Click **Export** to download the customer CSV.
3. **Export orders**
   * Go to **Orders** in the left menu.
   * Click **Download CSV** and save the orders file.

</details>

<details>

<summary><strong>Squarespace</strong></summary>

**Data types to export**

* Products
* Customers
* Orders
* Blog content (XML)

**Instructions**

1. **Export products**
   * In the **Home Menu**, go to **Commerce → Inventory** (or **Selling → Products**).
   * Click **Export all**.
   * Save the resulting **products.csv** file.
2. **Export customers**
   * Go to **Commerce → Customers** (or **Contacts → Customers**).
   * Select the group to export (Customers / Subscribers / Donors / All).
   * Open the **…** menu and choose **Export All Profiles / Export All Contacts**.
   * Confirm and download the **customers.csv**.
3. **Export orders**
   * Go to **Commerce → Orders** (or **Selling → Orders**).
   * Use filters for status or date range if needed.
   * Click **Export / Download CSV** and save the **orders.csv**.
4. **Export blog content (optional)**
   * Go to **Settings → Advanced → Import / Export**.
   * Click **Export**.
   * Choose the **WordPress** option.
   * After processing, click **Download** to save the blog **.xml** file.

</details>

<details>

<summary><strong>Storenvy</strong></summary>

**Data types to export**

* Products
* Orders

**Instructions**

1. **Export products**
   * Log in to **Storenvy** admin.
   * Go to the **Products** tab.
   * Click **Export Products**.
   * Save the generated **products.csv** file.
2. **Export orders**
   * Go to the **Orders** tab.
   * Click **Export these orders**.
   * Choose the desired **date range**.
   * Download the resulting orders CSV file.

</details>

<details>

<summary><strong>Volusion</strong></summary>

**Data types to export**

* Products
* Categories
* Options / Option Categories / Kits
* Customers
* Orders (and related tables)
* Additional product images (via custom query)

**Instructions**

1. Log in to **Volusion** admin.
2. Go to **Inventory → Import/Export → STANDARD EXPORT**.
3. For each table below, repeat these actions:
   * In **Export From**, select the data table (e.g. _Products_).
   * In **Columns**, click **Check All**.
   * In **File Format**, choose **CSV – Comma Delimited Text File**.
   * Click **Export**, then **Download** the CSV.
4. Export the following tables:
   * ExchangeRates
   * Tax
   * Categories
   * Products
   * OptionCategories
   * Options
   * KITS
   * KITLNKS
   * Customers
   * Orders
   * OrderDetails
   * TrackingNumbers
   * Reviews

**Additional product images (custom query)**

5. Go to **Inventory → Import/Export → Saved Exports → Add New Query**.
6. Fill in the fields (QB Table, Title, Query Type, Export File Type) exactly as specified in your internal SQL template.
7. Paste the provided **SQL query** from your internal doc into the query field.
8. Save the query, return to **Saved Exports**, select it and export as **CSV**.

</details>

<details>

<summary><strong>Weebly</strong></summary>

**Data types to export**

* Products & categories
* Orders & customers

**Instructions**

1. **Export products & categories**
   * In **Weebly** admin, go to **Items → Item Library**.
   * Click the **…** icon (top right).
   * Select **Export Items**.
   * Download the CSV file that contains both product and category data.
2. **Export orders & customers**
   * Go to **Orders** (or **Store → Orders**).
   * Click **Export Orders**.
   * Choose:
     * All orders,
     * Since last export, or
     * Specific date range.
   * Confirm export and download the **orders.csv** from the email link.
   * Customer details are included inside the orders CSV.

</details>

<details>

<summary><strong>WIX</strong></summary>

**Data types to export**

* Products
* Customers (contacts)
* Orders

**Instructions**

1. **Export products**
   * In **Wix** admin, go to **Store Products → Products**.
   * Click **More Actions → Export**.
   * Choose **All / Filtered / Selected** products.
   * Confirm and download the product CSV.
2. **Export customers (contacts)**
   * Go to **Contacts → Contacts**.
   * Click the **…** icon.
   * Select **Export contacts**.
   * Choose the subset to export.
   * Set format to **Regular CSV file**.
   * Export and download the CSV.
3. **Export orders**
   * Go to **Orders → Orders**.
   * Select all orders (or specific ones).
   * Click **Export**.
   * In the export popup, tick **Select all columns** in the “Items purchased” area.
   * Export and download the orders CSV.

</details>

<details>

<summary><strong>Yahoo Store</strong></summary>

**Data types to export**

* Orders (Orders.xml)
* Products catalog (Catalog.xml)
* Store info (Objinfo.xml)

**Steps**

1. **Export orders (Orders.xml)**
   * Log in to **Yahoo Store** admin.
   * In the **Process** column, click **Orders**.
   * Enter the order range (e.g. `1-3000`).
   * Set **format = XML**.
   * Click **Export**, then **Download** the **Orders.xml** file.
   * For more than 3,000 orders, repeat with the next ranges (e.g. `3001-6000`).
2. **Export products (Catalog.xml)**
   * Sign in to **Store Manager**.
   * Under **Promote**, click **Search Engines**.
   * Find **Catalog.xml**.
   * Set its status to **Enabled** and click **Done**.
   * Download **Catalog.xml**.
3. **Export store info (Objinfo.xml)**
   * In the same **Search Engines** area, find **Objinfo.xml**.
   * Set it to **Enabled**, click **Done**.
   * Download **Objinfo.xml**.

</details>
