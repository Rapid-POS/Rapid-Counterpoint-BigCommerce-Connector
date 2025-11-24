# Rapid POS BigCommerce Connector v2.1.10 Release Notes  

_Release Date: November 24, 2025_  

---

## Bug Fixes and Performance Enhancements  

### Adjusted Logic for **Update UPC** Configuration Setting  

- This fix applies when the **Update UPC** setting is enabled.  
  - Sends the ITEM barcode when available; otherwise uses the first barcode in the barcode table (**IM_BARCOD**) linked to the item.  
  - A bug caused the connector to select the first value in the barcode table without filtering by item number. The query now correctly filters by **`ITEM_NO`** to ensure the correct barcode value is sent.  
  - The query also now allows for barcode values greater than 12 characters to be sent.  
