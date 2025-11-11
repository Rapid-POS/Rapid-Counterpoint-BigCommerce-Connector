# Rapid POS BigCommerce Connector v2.1.8 Release Notes  

_Release Date: November 12, 2025_  

---

## Bug Fixes and Performance Enhancements  

### Refactored Default Date of Birth Logic  

- Clients who sell products that require a date of birth (DOB) on the customer record associated with a document have a configuration option for **`IsSupportDefaultDOB`** enabled. When enabled, **`AgeYearsToSubtract`** is populated with a value such as -21 years or -18 years. This allows a temporary birthdate to be associated with the ecommerce order to prevent missing DOB validation errors in Counterpoint.  
- The logic has been refactored to temporarily apply **`AgeYearsToSubtract`** to **`AR_CUST.USER_DOB`** when saving a document that includes a firearm item.  
- After the document is saved, the customer’s previous date of birth value is restored so that no temporary DOB persists in Counterpoint.  
  - If the associated customer record already had a birthdate populated prior to the ecommerce order, that DOB remains untouched.  
  - If the customer record did not have a birthdate, or if the connector creates a new customer record because no match exists in Counterpoint, a temporary DOB is applied based on the **`AgeYearsToSubtract`** value but is immediately removed so that the record retains a null DOB value.  

### Updated Inventory Trigger to Flag Items for Sync When Inventory Changes  

- The inventory trigger has been enhanced to flag items for sync whenever inventory levels change.  
- Previously, items were only marked for sync with BigCommerce when the item record itself was updated, not when inventory quantities changed due to posted transactions or inventory adjustments.  

### Renamed Data Dictionary Columns for Clearer Context  

- Updated data dictionary column names to provide greater clarity in the Counterpoint interface:  
  - **`Purchasability`** → **`BigCommerce Purchasability`**  
  - **`Visible on Storefront`** → **`BigCommerce Visible on Storefront`**  

### Updated SQL Install Script – Adjusted Default Pay Code to `EC_BIGCOMM`  

- The SQL installation script for **`PS_STA_CFG_PS`** has been updated to set default pay code values from **`CASH`** to **`EC_BIGCOMM`**, ensuring better alignment with ecommerce transaction processing.  

### Updated SQL Install Script – Added Pay Codes for Online Gift Cards and Store Credit  

- BigCommerce can return specific pay codes when a customer pays on the website using an online gift card or online store credit.  
- These are **not** Counterpoint gift cards or store credits, but rather payment types specific to BigCommerce. 
- The SQL installation script has been updated to include **`ONLINE_GC`** and **`ONLINE_SC`** pay codes to ensure these codes exist in Counterpoint when used by BigCommerce.  

