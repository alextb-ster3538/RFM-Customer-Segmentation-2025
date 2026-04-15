---


<img width="3047" height="500" alt="rfm_banner" src="https://github.com/user-attachments/assets/27d6ed22-33cf-4650-88bb-9ec6d6962c90" />


---

# 📊 RFM Customer Segmentation Analysis  
**SQL (BigQuery) • Power BI • Data Modeling • Customer Insights**

A complete end‑to‑end analytics project demonstrating data engineering, segmentation modeling, and business insight generation for a fictional retail brand, **LoneStar Retail**.

---

## 🚀 Project Overview
This project performs a full **RFM (Recency, Frequency, Monetary)** customer segmentation analysis using **SQL in Google BigQuery** and **Power BI**.

It demonstrates the complete analytics workflow:
- Data unification  
- Feature engineering  
- Scoring and segmentation  
- BI‑ready dataset creation  
- Dashboard storytelling  

The final output identifies high‑value customers, at‑risk groups, and revenue‑driving segments — enabling data‑driven marketing and retention strategies.

---

## 📦 Dataset Context
This project uses a fictional retail dataset representing **12 months of sales transactions for 2025**.  
Each row represents an order with:
- Customer ID  
- Order date  
- Product type  
- Order value  

The goal is to understand customer behavior and value using RFM segmentation.

---

## 🧱 Project Architecture
1. **Unified Sales Table (`all_sales2025`)**  
   Combines 12 monthly sales tables into one standardized dataset.

2. **RFM Metrics (`rfm_metrics`)**  
   Calculates recency, frequency, and monetary values per customer.

3. **RFM Scores (`rfm_scores`)**  
   Applies NTILE deciles to assign R, F, and M scores (1–10).

4. **Total RFM Score (`rfm_total_scores`)**  
   Sums R, F, and M scores into a composite score.

5. **Final Segments (`rfm_segments_final`)**  
   Maps customers into business‑friendly segments (Champions, VIP, At Risk, etc.).

6. **Power BI Dashboard**  
   Visualizes segment distribution, revenue contribution, and customer‑level details.

---

## 🔧 Tools & Technologies
- **Google BigQuery** — SQL processing & data modeling  
- **SQL Window Functions** — NTILE, aggregations  
- **Power BI** — dashboard & visualization  
- **Data Engineering** — views, tables, pipeline design  
- **Customer Analytics** — segmentation, scoring, insights  

---

## 🗂️ Data Dictionary

### `all_sales2025`
| Field | Description |
|-------|-------------|
| OrderID | Unique order identifier |
| CustomerID | Unique customer identifier |
| OrderDate | Date of purchase |
| ProductType | Product category |
| OrderValue | Revenue per order |
| string_field_5–7 | Additional attributes (NULL for most months) |

### `rfm_metrics`
| Field | Description |
|-------|-------------|
| CustomerID | Unique customer identifier |
| last_order_date | Most recent purchase date |
| recency | Days since last purchase |
| frequency | Number of orders |
| monetary | Total spend |

### `rfm_scores`
| Field | Description |
|-------|-------------|
| r_score | Recency decile score |
| f_score | Frequency decile score |
| m_score | Monetary decile score |

### `rfm_total_scores`
| Field | Description |
|-------|-------------|
| rfm_total_score | Combined RFM score (R+F+M) |

### `rfm_segments_final`
| Field | Description |
|-------|-------------|
| rfm_segment | Assigned customer segment |

---

## 📈 Key Insights from the Power BI Dashboard
1. **High‑value customers form a strong revenue core**  
   Champions, VIP, and Potentially VIP customers make up ~37% of the customer base yet contribute a disproportionately large share of total revenue.

2. **VIP customers generate the most revenue**  
   VIP customers outperform Champions in total revenue, indicating higher purchase frequency or higher‑value orders.

3. **Mid‑tier segments offer major growth potential**  
   Engaged (61), Promising (45), and Potentially VIP (41) customers represent the best upgrade opportunities.

4. **“At Risk” and “Requires Attention” segments need intervention**  
   A combined 70 customers show declining engagement — ideal targets for win‑back campaigns.

5. **Lost/Inactive segment is small**  
   Low churn indicates strong customer retention and healthy lifecycle performance.

6. **Customer‑level RFM scores validate segmentation accuracy**  
   Champions consistently score 9–10 across R/F/M, while VIPs show slightly lower recency but strong frequency and monetary values.

---

## 📊 Power BI Dashboard Features
- Treemap: Customer distribution by segment  
- Bar Chart: Revenue contribution by segment  
- KPI Cards: Total customers, revenue, average recency, frequency, monetary  
- Detail Table: Customer‑level RFM scores and segments  

---

## 🔄 How to Reproduce
1. Load the monthly sales tables into BigQuery.  
2. Run the SQL scripts in the `/sql` folder in order.  
3. Export `rfm_segments_final` as a BI‑ready table.  
4. Load into Power BI using the `.pbix` file.  

---

## 💼 Business Impact
This analysis enables LoneStar Retail to:
- Identify high‑value customers for loyalty programs  
- Target at‑risk customers with win‑back campaigns  
- Prioritize marketing spend based on segment value  
- Improve retention and lifetime value  

---

## 🔮 Next Steps (Recommended Enhancements)
1. Customer Lifetime Value (CLV) modeling  
2. Automated scheduled queries  
3. Churn prediction model  
4. Marketing strategy mapping  
5. Integration with CRM or marketing automation  

---

## 🧭 Pipeline Diagram (Mermaid)
```
flowchart TD

A[Monthly Sales Tables<br/>2025_01 ... 2025_12] 
    --> B[Unified Sales View<br/>all_sales2025]

B --> C[RFM Metrics<br/>recency, frequency, monetary]

C --> D[RFM Scores<br/>NTILE deciles for R/F/M]

D --> E[Total RFM Score<br/>r_score + f_score + m_score]

E --> F[Final Segments<br/>Champions, VIP, At Risk, etc.]

F --> G[Power BI Dashboard<br/>Insights & Visualizations]
```

---

## 📝 Credits & Inspiration
This project was inspired by a YouTube tutorial created by **Mo Chen**, whose walkthrough helped shape the RFM scoring logic and project structure.

**Original Tutorial:**  
(https://www.youtube.com/watch?v=YOUR_LINK_HERE)](https://www.youtube.com/watch?v=Da960TW5tf4&t=82s)
