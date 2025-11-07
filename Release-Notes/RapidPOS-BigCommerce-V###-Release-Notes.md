# Rapid POS Mailchimp Connector v#.#.# Release Notes

_Release Date: November 10, 2025_

---

## Bug Fixes and Performance Enhancements

### Adjust Customer Handling for Clients using Default DOB Configuration Option

- Clients who sell products that require a date of birth (DOB) on the customer record associated with a document have a configuration option for **`IsSupportDefaultDOB`** enabled. When enabled, **`AgeYearsToSubtract`** is populated with a value such as -21 years or -18 years. This allows for a temporary birthdate to be associated with the ecommerce order to prevent missing DOB validation errors in Counterpoint.  
   
- The code has been adjusted so that this temporary birthdate no longer persists in Counterpoint.  
  - If the associated customer record already had a birthdate populated prior to the ecommerce order, that DOB will remain untouched.  
  - If the customer record did not have a birthdate, or if the BigCommerce connector is creating a new customer record because no match exists in Counterpoint, a temporary DOB will be applied based on the **`AgeYearsToSubtract`** value but will be immediately removed so that the customer record retains a null DOB value.

### Stop Setting the Ecommerce Customer Flag on Customers Created by the BigCommerce Connector

- When an order is imported into Counterpoint and no matching customer record can be found, a new customer record is created. Previously, the connector set the Ecommerce Customer flag to checked (**`IS_ECOMM_CUST` = Y**).  
- Because Counterpoint disallows merging a customer flagged as an ecommerce customer with a non-ecommerce customer, this caused issues for some clients.  
  - There is no functional benefit to flagging customers as ecommerce customers.  
- The connector has been updated to set the Ecommerce Customer flag to unchecked (**`IS_ECOMM_CUST` = N**) when creating customers in Counterpoint.
 
