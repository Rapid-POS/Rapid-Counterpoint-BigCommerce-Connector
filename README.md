# Rapid POS BigCommerce Connector - Version 2.1.8
Updated 12/11/2025

---

## Overview

The **Rapid POS BigCommerce Connector** seamlessly integrates your Counterpoint POS system with your BigCommerce online store. This connection keeps your items, customers, and orders synchronized automatically — helping you manage your ecommerce operations efficiently without duplicate data entry.

---

## Minimum System Requirements:
- Minimum Counterpoint version: **8.5.6.2**  
- Minimum SQL Server version: **2016**  
- Minimum Windows Server version: **2016**  
- Minimum PowerShell version: **5.1**  

If you would like the BigCommerce connector but your system does not meet these minimum requirements, please consult your Care Team Lead (vCIO) for an upgrade quote.

---

## Section 1: Data Flow Summary

The Rapid POS BigCommerce Connector allows you to:

- Sync **inventory data** between Counterpoint and BigCommerce, keeping pricing and quantity information consistent across systems.  
- Automatically import **online orders** and **customers** from BigCommerce into Counterpoint.

### Items (Products)
- Flow **from Counterpoint → BigCommerce**  
- Includes both standard and gridded items.  
- Can be configured to send alternate units as variants instead of gridded items (for example, selling by unit or by case).  

### Orders & Customers
- Flow **from BigCommerce → Counterpoint**  
- New online orders and customer updates are imported every 15 minutes.  

---

**Note:** Rapid POS does not provide website design or hosting services. We recommend working with a qualified ecommerce professional to build and maintain your BigCommerce storefront.
