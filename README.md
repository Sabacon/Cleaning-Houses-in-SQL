# Data Cleaning in SQL

In this project I used `Microsoft SQL Server` to clean the Nashville Housing dataset.

## Problems fixed
* Used the **CONVERT** function to change the `SaleDate` column from datetime to date. Saved the result in a new column `SaleDate1`.


* Populated the null values in the `PropertyAddress` column. Used the `PropertyAddress` values of the rows that had identical `ParcelID`.
    - **Self joined** the table on `ParcelID` and `UniqueID` where the `PropertyAddress` of the first table was null.


* Split the `PropertyAddress` column into `Address1` and `City1` columns using **SUBSTRING**, **CHARINDEX** and **LEN** functions.


* Split the `OwnerAddress` into 3: `Address2`, `City2`, `State2` using the **PARSENAME** function.
    * **PARSENAME** only works with periods(.). I used the **REPLACE** function to change the commas separating the values in the column to periods before applying **PARSENAME**.


* Updated the `SoldAsVacant` column. The distinct values were Y, N, YES, NO. 
    * Used the **CASE** statement to change Y and N to YES and NO respectively.


* Got rid of duplicates using **CTE** and **ROWNUMBER**.


* Removed unnecessary columns.
