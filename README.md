# 🛠 Task: Sync SQL Server and SQLite Databases

## 🎯 Objective
Create a C# console application to synchronize data between a SQL Server database and a SQLite database. The data should be **identical** in both databases at all times (i.e., two-way sync).

---

## 📋 Requirements

### ✅ Functional Requirements
1. **Sync two databases:**
   - One is a SQL Server database.
   - The other is a local SQLite database.
2. Ensure **both databases contain the same records** for specified tables.
3. Perform **two-way sync**:
   - New or updated data in SQL Server should be inserted/updated in SQLite.
   - New or updated data in SQLite should be inserted/updated in SQL Server.
4. Handle **deletions**:
   - If a record is deleted in one database, it should be deleted in the other.
5. Perform sync on-demand (when the console app is run).

---

## 🧱 Technical Requirements
- Language: C# (.NET 6 or later)
- Libraries:
  - `System.Data.SqlClient` for SQL Server
  - `Microsoft.Data.Sqlite` or `System.Data.SQLite` for SQLite
- Use ADO.NET or Dapper (no EF Core)
- Include proper error handling and logging to console
- Use a config file (`appsettings.json`) to store connection strings

---

## 📁 Tables to Sync
- `Users` table (example schema):
  ```sql
  CREATE TABLE Users (
    Id INT PRIMARY KEY,
    Name NVARCHAR(100),
    Email NVARCHAR(100),
    UpdatedAt DATETIME
  );
  ```
- You may assume all rows have an `UpdatedAt` column to determine the latest version.

---

## 🚀 Deliverables
- C# console application (with `.csproj` and `.cs` files)
- `appsettings.json` with sample connection strings
- A brief README explaining how to run the sync
- Sample SQL scripts to create the `Users` table in both databases

---

## 📝 Notes
- You can assume both databases have the same schema.
- Use `UpdatedAt` to detect the newer version of a record.
- You may ignore conflicts caused by simultaneous updates in both DBs for now.

---

## 🔍 Bonus (Optional)
- Add CLI arguments to specify which direction to sync (e.g., `--sql-to-sqlite`, `--sqlite-to-sql`, `--both`)
- Add logging to a `.log` file in addition to console output


---

Good luck, and happy coding! 🚀
