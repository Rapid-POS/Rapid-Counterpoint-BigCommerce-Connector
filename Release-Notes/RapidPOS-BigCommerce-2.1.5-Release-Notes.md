# Rapid POS BigCommerce Connector v2.1.5 Release Notes

_Release Date: July 10, 2025_

---

## New Functionality

### Moved the connector to the CI/CD pipeline

- CI/CD stands for Continuous Integration/Continuous Deployment. Previously, when a new feature was developed or a bug was fixed, we would have to manually perform a re-install of that connector at every client. CI/CD means the fixes and new features are automatically deployed, sometimes fixing a bug before you ever experience it.

---

## Bug Fixes and Performance Enhancements

### Stop Setting the Ecommerce Customer Flag on Customers Created by the BigCommerce Connector

- When an order is imported into Counterpoint and no matching customer record can be found, a new customer record is created. Previously, the connector set the Ecommerce Customer flag to checked (**`IS_ECOMM_CUST` = Y**).  
- Because Counterpoint disallows merging a customer flagged as an ecommerce customer with a non-ecommerce customer, this caused issues for some clients.  
  - There is no functional benefit to flagging customers as ecommerce customers.  
- The connector has been updated to set the Ecommerce Customer flag to unchecked (**`IS_ECOMM_CUST` = N**) when creating customers. 
