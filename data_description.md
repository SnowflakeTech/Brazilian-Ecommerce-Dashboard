# 📄 Data Description – Brazilian E-Commerce (Olist Dataset)

This document provides an overview of the dataset used in this project, originally sourced from [Kaggle - Olist Brazilian E-Commerce](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce).

The dataset consists of multiple relational tables that describe e-commerce transactions in Brazil between 2016 and 2018.

---

## 🗃️ Table Overview

### 1. `Fact_Sales`
Main fact table containing transactional data.
| Field | Description |
|-------|-------------|
| order_id | Unique identifier for each order |
| product_id | Product being sold |
| customer_id | Customer who made the order |
| seller_id | Seller who fulfilled the order |
| payment_type | Payment method used |
| price | Product price |
| freight_value | Delivery cost |
| order_purchase_timestamp | Date of purchase |

---

### 2. `Dim_Customer`
Customer dimension table.
| Field | Description |
|-------|-------------|
| customer_id | Unique ID per customer |
| customer_city | City of customer |
| customer_state | State of customer |
| customer_zip_code_prefix | Zip code prefix |

---

### 3. `Dim_Product`
Product-related information.
| Field | Description |
|-------|-------------|
| product_id | Unique product ID |
| product_category_name_english | Translated category |
| product_name_length | Length of product name |
| product_description_length | Length of description |
| product_weight_g | Product weight |
| product_length_cm, width_cm, height_cm | Dimensions |

---

### 4. `Dim_Seller`
Seller dimension table.
| Field | Description |
|-------|-------------|
| seller_id | Unique ID per seller |
| seller_city | Seller’s location |
| seller_state | Seller’s state |
| seller_zip_code_prefix | Zip code prefix |

---

### 5. `Dim_Payment`
Payment method and installments.
| Field | Description |
|-------|-------------|
| order_id | Associated order |
| payment_type | e.g. credit_card, boleto, voucher |
| payment_installments | Number of installments |

---

### 6. `Dim_Review`
Customer reviews of delivered orders.
| Field | Description |
|-------|-------------|
| review_id | Unique review ID |
| order_id | Associated order |
| review_score | 1 to 5 rating |
| review_comment_title | Optional title |
| review_comment_message | Optional text feedback |

---

### 7. `Dim_Order`
Order-level metadata.
| Field | Description |
|-------|-------------|
| order_id | Unique ID |
| order_status | e.g. delivered, canceled |
| order_approved_at | Timestamp of approval |
| order_delivered_carrier_date | When it was shipped |
| order_delivered_customer_date | When it was delivered |
| order_estimated_delivery_date | Expected delivery date |

---

### 8. `Dim_Geolocation`
Geo mapping for cities and states.
| Field | Description |
|-------|-------------|
| geolocation_zip_code_prefix | Shared with customer/seller |
| geolocation_lat, long | Latitude and longitude |
| geolocation_city | City name |
| geolocation_state | State abbreviation |

---

### 9. `DimDate`
Date dimension used for time intelligence.
| Field | Description |
|-------|-------------|
| Date | Full date (YYYY-MM-DD) |
| Year, Month, Week, Day | Time breakdown fields |

---

## 📌 Notes:
- All tables are linked through keys like `order_id`, `customer_id`, `product_id`.
- The model is structured in a **Star Schema**, optimized for Power BI analysis.
- Missing values and nulls have been handled appropriately in Power Query (if applicable).

---

**Author**: [Your Name]  
**Project**: `olist-ecommerce-dashboard`  
**Date**: May 2025
