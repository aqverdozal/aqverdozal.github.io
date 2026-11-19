title: "E-Commerce Database Analytics: Evaluating Profitability & Sell-Through in BigQuery"
date: 2026-10-20
categories:
  - Database Management
tags:
  - SQL
  - Google BigQuery
  - Relational Databases
  - E-Commerce
---

## The Problem
Online retailers track orders, products, customers, and warehouse inventory across separate relational tables, making it hard to see which categories actually drive profit versus which ones just move volume. The goal of this database management project was to query a multi-table e-commerce database in SQL and turn the results into an executive-ready business brief.

## Key Results
* Built a modular **BigQuery SQL query suite** joining transactional, product, and warehouse tables to evaluate **category profitability**, **brand concentration**, and **warehouse sell-through rates**.
* Translated raw query outputs into an **analytical business brief** highlighting margin drivers, over-reliance on specific brands, and fulfillment bottlenecks across distribution centers.

## Data
Google BigQuery’s public **TheLook E-Commerce** relational dataset (`bigquery-public-data.thelook_ecommerce`), containing multi-table records for orders, order items, products, inventory items, users, and distribution centers.

## Approach
1. Mapped out primary and foreign key relationships across the relational schema to ensure clean joins without double-counting revenue or inventory.
2. Wrote structured SQL queries using **Common Table Expressions (CTEs)**, **window functions**, and **aggregations** to calculate net margins, brand share, and sell-through rates by warehouse.
3. Validated row counts and edge cases (such as returned or cancelled orders) before summarizing findings into a business brief.

Breaking revenue down by net margin and brand share showed that top-selling categories do not always produce the healthiest returns—and comparing sell-through across distribution centers pinpointed where inventory was sitting idle.

## What I Learned
Good database analytics starts with respecting the schema. Writing readable CTEs and verifying join granularity up front prevents silent aggregation errors and makes SQL queries much easier for a team to audit and reuse.