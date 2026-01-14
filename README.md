Brazilian E-Commerce Conversion Funnel & Revenue Impact Analysis using OCI
Project Overview

This project analyzes e-commerce conversion performance using real transactional data to identify funnel drop-offs, category-level delivery performance, and revenue loss from failed orders. The analysis focuses on incremental, measurable improvements and reflects a test-and-learn analytics approach commonly used in e-commerce, product, and conversion optimization teams.

All analysis was performed in Oracle Cloud Infrastructure (OCI) using Python and pandas.

Business Objective

The primary goals of this analysis is to:

- Measure end-to-end e-commerce conversion performance

- Identify where orders drop out of the funnel

- Quantify revenue at risk from failed orders

- Compare delivery performance across product categories

- Translate data findings into actionable business insights

Dataset

Brazilian E-Commerce Public Dataset (Olist)

~99,000 orders

Public, real-world transactional dataset

Includes orders, order items, and product metadata

Important scope note:
This dataset does not include page views or add-to-cart events. As a result, the funnel is modeled at the order lifecycle level, which is a standard and accepted approach for transactional and marketplace analytics.

Raw CSV files are intentionally not stored in this repository.

Funnel Definition

Given the available data, the conversion funnel is defined as:

**Order Placed** – All orders in the dataset

**Order Shipped** – Orders with status "shipped" or "delivered"

**Order Delivered** – Orders with status delivered

This structure allows accurate measurement of completion rates and drop-off points without misrepresenting the data.

Key Results
**Overall Conversion Performance**

**Ship rate**: ~98.1%

**Delivery rate (from shipped)**: ~98.9%

**End-to-end delivery rate**: ~97.0%

Insight:
The majority of orders successfully complete the funnel. Drop-offs occur primarily **before shipment**, rather than during last-mile delivery.

Category-Level Delivery Analysis

Delivery performance was analyzed at the order level (not item level) to ensure accurate aggregation.

Small-volume categories often show 100% delivery rates and were treated cautiously.

Higher-volume categories (e.g., audio products) showed consistently high but non-perfect delivery performance (~99%+).

**Insight**:
Category risk varies more by operational complexity and volume than by delivery execution.

Revenue Loss from Failed Orders

Failed orders were defined as those with status:

canceled

unavailable

**Findings**:

~1,200 failed orders overall

~$97,000 in item-level revenue at risk

Canceled orders account for **over 97% of lost revenue**

Average lost revenue per canceled order: ~$207

**Incremental impact framing**:

A **5% reduction in cancellations** could recover ~$4,700–$5,000

A **10% reduction** could recover ~$9,500+

This aligns with common CRO goals focused on **3–5% incremental improvements**.

Key Business Insights

Funnel performance is strong post-shipment

Order cancellations are the primary source of revenue leakage

Inventory validation and order confirmation represent the highest-impact optimization opportunities

Small improvements in cancellation rates can produce measurable revenue gains

Tools & Environment

Oracle Cloud Infrastructure (OCI) – Data Science Notebook

Python (pandas)

JupyterLab

SQL-style aggregations and joins
