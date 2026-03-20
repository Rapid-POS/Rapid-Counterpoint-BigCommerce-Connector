# Rapid POS BigCommerce Connector v2.01.13 Release Notes

_Release Date: March 23, 2026_

---

## New Functionality

### Added Item Status View

- Introduced a new **Item Status View** to provide visibility into the synchronization status of item records.
  
- The view displays a summary table showing:
  - Each sync status code
    - **`0`** – Synced  
    - **`1`** – Pending Sync  
    - **`2`** – Active Sync  
    - **`9`** – Error Syncing  
  - The total number of item records associated with each status
 
- This tool allows users to quickly identify items that may require attention, such as records in an error state.  

- Notes:
  - Statuses with no associated records will not appear in the table.  
  - The table can be refreshed at any time to display the most up-to-date information.  
  - Best viewed in table view.

---

## Bug Fixes and Performance Enhancements

### Ensure Inventory Updates Trigger During Replication

- Removed the replication check from the **`USER_TR_BIGCOMMERCE_IM_INV_U`** trigger.  
- This ensures inventory updates are properly flagged for sync with BigCommerce, even during replication.

### Improved Error Handling for Item Synchronization

- Enhanced error handling in **`ItemsInterface.cs`**.  
- The connector will now:
  - Automatically resync items when a **"Value cannot be null"** error occurs  
  - Send detailed error notifications to the message center for improved visibility
