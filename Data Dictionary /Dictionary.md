# Data Dictionary - Core Data Stores

This directory contains the detailed specifications and metadata definitions for the primary data stores utilized in the Circle K system model. Standardizing these definitions ensures data consistency and prevents structural discrepancies across development teams.

---

## 1. Data Store Description: Customer Master (ID: D1)

* **Alias:** Client Master, Registered User File
* **Description:** Contains a permanent record for each registered CK GO customer, including their profile and account status. It interacts directly with the *Settle Order Transaction* process to update balances and reward points.

### Data Store Characteristics
| Attribute | Specification |
| :--- | :--- |
| **File Type** | ☑️ Computer |
| **File Format** | ☑️ Database |
| **Record Size** | 250 Characters |
| **Number of Records** | Average: 20,000 / Maximum: 50,000 |
| **Percent Growth / Year** | 10% |
| **Data Set Name** | `Customer.MST` |
| **Copy Member** | `Custmast` |
| **Data Structure** | Customer Record |
| **Primary Key** | `Customer Number` |
| **Secondary Keys** | `Customer Name`, `Telephone` |

> **Comments:** Customer Master records are archived to a history file if the customer has not made a purchase within the past two years to optimize database performance.

---

## 2. Data Store Description: Item Master (ID: D2)

* **Alias:** Product Inventory, SKU File
* **Description:** Contains a permanent record of all products available for sale, including pricing, descriptions, and stock levels at Circle K stores.

### Data Store Characteristics
| Attribute | Specification |
| :--- | :--- |
| **File Type** | ☑️ Computer |
| **File Format** | ☑️ Database |
| **Record Size** | 180 Characters |
| **Number of Records** | Average: 5,000 / Maximum: 10,000 |
| **Percent Growth / Year** | 5% |
| **Data Set Name** | `Item.MST` |
| **Copy Member** | `Itemmast` |
| **Data Structure** | Item Record |
| **Primary Key** | `Item Number` |
| **Secondary Keys** | `Item Description`, `Category` |

> **Comments:** This store is integrated with the real-time inventory system to reflect current availability for the CK GO application.

---

## Systems Methodology Note
Following the architectural frameworks outlined by *Kendall & Kendall (2020)*, maintaining this centralized Data Dictionary serves as the project's **"Single Source of Truth."** It systematically mitigates data redundancy, enforces clean data constraints (e.g., standardizing structural codes), and ensures seamless cross-referencing during system scalability phases.
