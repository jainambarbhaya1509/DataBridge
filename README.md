# 📊 Excel to PostgreSQL Migration & Data Mapping Utility
This Node.js script enables seamless data migration and mapping from an Excel file to a PostgreSQL database. It reads data from the Excel file, creates tables in the database based on sheet names, and prompts the user to define column data types. Additionally, it supports mapping data between source and destination tables, allowing users to specify schemas, tables, and column mappings. The script verifies the existence of tables and columns, creates destination tables if necessary, and transfers data accordingly, streamlining the entire data integration workflow.

---

## 🛠 Prerequisites

* Node.js installed on your machine.
* A running PostgreSQL database.
* Excel files (.xlsx) for migration (for migration tool only).

---

## 📦 Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/jainambarbhaya1509/DataBridge.git
   cd DataBridge
   ```

2. Install the dependencies:

   ```bash
   npm install
   ```

---

## 🚀 Usage

### 1. **Excel to PostgreSQL Migration**

**Script**: `migration.js`

This script:

* Reads data from an Excel file.
* Creates PostgreSQL tables based on sheet names.
* Prompts for column data types.
* Inserts the data into the respective tables.

**Steps:**

1. Open `migration.js` and configure your PostgreSQL credentials:

   ```js
   const pool = new Pool({
     user: "your_user",
     host: "localhost",
     database: "your_db",
     password: "your_password",
     port: 5432,
   });
   ```

2. Set your Excel file path:

   ```js
   await readExcel("<path_to_excel_file>");
   ```

3. Run the script:

   ```bash
   node migration.js
   ```

4. Follow the prompts to specify column data types.

---

### 2. **PostgreSQL Table-to-Table Data Mapping**

**Script**: `mapping.js`

This script:

* Maps data from a source table to a destination table.
* Prompts for schema/table/column details.
* Checks existence and creates the destination table if needed.

**Steps:**

1. Open `mapping.js` and update the PostgreSQL credentials.

2. Run the script:

   ```bash
   node mapping.js
   ```

3. Enter details when prompted:

   * Schema
   * Source table and columns
   * Destination table and columns

4. The script performs the mapping automatically.

---

## 🧑‍💻 Contributing

We welcome contributions! Please:

* Describe issues clearly in pull requests.
* Ensure code follows the existing style.
* Test your changes.

Thank you for supporting this project!

---

## ⚠️ Notes

* Migration assumes each Excel sheet represents a table.
* The first row of each sheet should contain column headers.
* All tables are created in the **public** schema by default.
* Default column type is `TEXT`; you can override this via prompts.

---

## 📄 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT).

---

Let me know if you'd like this in a downloadable file or if you want to customize it further (e.g., add badges, images, or command line flags).
