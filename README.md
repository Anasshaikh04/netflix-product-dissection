# 🎬 Netflix Product Dissection & Database Analysis

---

## 📌 Overview

A comprehensive product dissection and database analysis of **Netflix**, the world's largest OTT streaming platform with 300M+ subscribers across 190+ countries. This project covers real-world problem solving, relational database schema design, advanced DBMS concepts, business case studies, guesstimates, and revenue growth strategies.

---

## 📂 Project Structure

```
netflix-product-dissection/
│
├── Case_Studies_Guesstimates_for_Netflix.pdf    # Full case study document
├── Netflix_Product_Dissection_Database_Analysis_Final.pptx  # Presentation deck
└── README.md
```

---

## 🔍 Key Sections Covered

### 1. Product Dissection
- Identified 5 real-world problems Netflix solves (Content Discovery, Streaming Quality, Multi-user Profiles, Piracy Prevention, Accessibility)
- Analyzed Netflix's core features: AI Recommendations, Adaptive Bitrate Streaming, DRM, Kids Mode, Offline Viewing

### 2. Database Schema Design
Designed a normalized relational schema with **11+ entities**:

| Entity | Purpose |
|--------|---------|
| Users | Account management & authentication |
| Profiles | Multi-profile support per account |
| SubscriptionPlans | Plan tiers (Basic, Standard, Premium) |
| Content | Movies, shows, documentaries catalog |
| Genres | Content categorization |
| ContentGenres | Many-to-many content-genre mapping |
| ContentArtists | Actor/Director associations |
| Artists | Artist metadata |
| UserContentInteraction | Watch history, ratings, progress |
| Watchlist | Saved content per user |
| Payments | Transaction records |
| AuditLogs | Security & compliance logging |

### 3. DBMS Concepts Applied
- **ACID Compliance** — Atomic episode transitions in Continue Watching, concurrency control for multi-device progress updates
- **Indexing** — Full-text, composite, and standard indexes for actor, genre, and keyword search
- **Partitioning** — Range (date-based) and List (region-based) partitioning for billion-row streaming logs
- **Sharding** — Consistent hashing by User ID and region-based sharding for global scale
- **Normalization vs Denormalization** — Normalized schema for data integrity; denormalized cache for recommendation engine (10–50ms vs 500–2000ms)
- **ETL Pipelines** — Batch aggregation for view counts; ingestion ETL for audit log standardization
- **Data Lake vs Data Warehouse** — Raw clickstream → Data Lake (AWS S3); Transactions → Data Warehouse (MySQL/CockroachDB)
- **SCD Type 2** — TV show metadata versioning for historical analysis

### 4. Real-Time Data Pipeline Architecture
```
Smart TVs / Mobile Apps
        ↓
   Apache Kafka
        ↓
  Spark / Flink (Stream Processing)
        ↓
Apache Cassandra ──→ AWS S3 (Data Lake)
        ↓
  Analytics Dashboard (Grafana / Tableau)
```
- Sub-second latency | Billions of events/day | 300M+ users

### 5. Business Case Studies & Scenario Analysis
- **Cohort Retention Analysis** — Tracked monthly drop-off across 4 user cohorts; identified highest churn in Month 2–3
- **A/B Test Design** — Text-based vs Interactive tutorial comparison measuring Day-7 retention and conversion rate

### 6. Guesstimates
| Question | Projection |
|----------|-----------|
| Netflix subscribers by 2030 | ~476 Million (9% CAGR) |
| Avg. content consumption per week | ~6.5 hours/user |
| Annual content production by 2030 | ~524 titles (15% growth scenario) |
| International revenue by 2030 | ~$47 Billion |
| AR/VR revenue share by 2035 | ~$2.5 Billion |

### 7. Revenue Growth Strategies (25–36% Profit Growth Target)

| Strategy | Projected Growth |
|----------|----------------|
| Ad-Supported Tier Expansion | +9–11% |
| Global Pricing Optimization & Bundles | +4.5–6.5% |
| Merchandise & Licensing | +3–5% |
| AI Personalization & Churn Reduction | +1.75–3.5% |
| Freemium Content Sampling | +3–4.5% |
| Sports & Live Events Streaming | +3.5–6% |
| **Total Potential Growth** | **≈ 25–36.5%** |

---

## 🛠️ Tools & Technologies

`SQL` `MySQL` `CockroachDB` `Apache Cassandra` `Apache Kafka` `Apache Spark` `Apache Flink` `AWS S3` `Apache Airflow` `Redis` `Grafana` `Tableau`

---

## 💡 Key Takeaways

- Denormalized schema for recommendation engine delivers **10–50x faster** query performance vs normalized joins
- Real-time pipeline handles **billions of streaming events daily** with sub-second latency
- Batch ETL using Apache Airflow is **10x cheaper** than streaming for weekly third-party data
- Cohort analysis revealed **Month 2–3 as the critical churn window**, informing targeted retention strategies

---
