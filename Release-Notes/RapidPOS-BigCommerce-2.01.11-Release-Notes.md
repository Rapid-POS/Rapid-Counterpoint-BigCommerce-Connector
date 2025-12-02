# Rapid POS BigCommerce Connector v2.01.11 Release Notes  

_Release Date: December 2, 2025_  

---

## Bug Fixes and Performance Enhancements  
  
### Updated Logic for **Update UPC** Setting to Match BigCommerce Requirements  
  
- This fix applies when the **Update UPC** configuration setting is enabled.  
- The connector will now send the ITEM barcode only when it:  
  - Is numeric  
  - Contains 14 characters or fewer  
- If the ITEM barcode does not meet these requirements, the connector will send the first barcode in **IM_BARCOD** linked to the item that meets the same criteria.  
- If no barcode meets BigCommerce’s restrictions, no UPC value will be sent to BigCommerce.  
