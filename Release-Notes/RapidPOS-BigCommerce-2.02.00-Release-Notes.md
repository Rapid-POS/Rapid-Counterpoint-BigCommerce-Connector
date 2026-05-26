# Rapid POS BigCommerce Connector v2.02.00 Release Notes

_Release Date: March 27, 2026_

---

## New Functionality

### Added BigCommerce Purchasability Option in Counterpoint (for pre-orders)

- Added support for all BigCommerce purchasability options within Counterpoint under the **`BigCommerce Purchasability`** field.  
- Previously, the option for taking pre-orders was not available in Counterpoint.  
- The following BigCommerce purchasability settings are now supported:
  - **Available:** This product can be purchased in my online store
  - **Preorder:** This product is coming soon but I want to take pre-orders
  - **Disabled:** This product cannot be purchased in my online store

### Added Configuration Setting for Updating Prices

- Added a new configuration setting: **`Update Price`** (**Y/N**).  
  - Default value is **Yes/Enabled** and is strongly recommended.
  - When set to **No/Disabled**, clients can manage ecommerce pricing directly within BigCommerce.

- When set to **Yes/Enabled**:
  - Price changes in Counterpoint will always overwrite pricing in BigCommerce.

- When set to **No/Disabled**:
  - Pricing will only be sent when a new product is created.
  - Future price changes in Counterpoint will **not** overwrite pricing changes made directly in BigCommerce.

---

## Bug Fixes and Performance Enhancements

### Updated Install Script to Automatically Configure GL Account Numbers

- Updated the BigCommerce SQL install script to automatically configure GL account numbers using library variables during installation.  
- Eliminates manual GL account setup after install while preserving any existing custom account numbers during upgrades.
