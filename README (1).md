# CHCF Donor Intelligence: Analytics & Insights

**A comprehensive donor analytics dashboard for Children's Hospital Colorado Foundation - from publicly available financial data to actionable insights.**

---

## 💡 How This Project Started

While going through the **Children's Hospital Colorado Foundation website**, I noticed they had a link to their **publicly available financial information**. I clicked on it and downloaded their **official IRS Form 990 filing** (the mandatory financial disclosure form all nonprofits must submit to the IRS annually).

The Form 990 filing from **November 2024** (reporting FY 2023 data) showed:
- **$76.4M in total revenue**
- **$95.5M in total assets**  
- **$54M in giving distributed**

This is impressive financial data, but it got me thinking: *"An organization with $76.4M in annual revenue probably has limited visibility into donor-level insights. What if I could show them:*
- *Which donors are their real MVPs?*
- *Which ones are at risk of leaving?*
- *Which campaigns and channels actually drive ROI?*
- *Where the biggest growth opportunities are?"*

That question sparked this entire project. I decided to build a complete **data analytics solution** that transforms publicly available Form 990 data into actionable donor intelligence.

---

## 📊 What This Project Shows

Using the real Form 990 data as my foundation, I created transaction-level synthetic data (calibrated to match the exact $76.4M revenue total) to demonstrate:
- **How to model nonprofit donor data** in a professional BI platform
- **Where hidden insights exist** in fundraising that leadership doesn't see
- **What strategic improvements could deliver** $7.6-$11.4M in additional annual revenue
- **How dashboards drive action** - not just pretty visualizations, but insights that lead to decisions

---

## 💡 Solution Delivered

A **4-dashboard analytics platform** built in Tableau Public featuring:

### **Dashboard 1: Executive Summary**
- KPI cards: $76.4M revenue, 1,500 donors, 3% active rate, 39% churn rate
- Revenue growth trend (2016-2026)
- Top 10 donor analysis
- Revenue distribution by donor type

### **Dashboard 2: RFM Segmentation Analysis**
- Donor count distribution across 6 segments (Champions, High Value, Loyal, At-Risk Winners, Needs Activation, Potential Loyalists)
- Revenue contribution by segment
- Segment performance benchmarks (Frequency, LTV, Donor Count)
- Strategic recommendations for each segment

### **Dashboard 3: Channel & Campaign Performance**
- Revenue by channel (Email, Events, Major Gifts, etc.)
- Top 6 campaigns ranked by performance
- Channel × Campaign heatmap revealing optimal donor/revenue combinations
- ROI insights (Email generates 3.2x better ROI than Direct Mail)

### **Dashboard 4: ⚠️ CRITICAL - Churn Risk & Retention**
- Risk distribution: 378 donors in Critical status, 236 in High Risk
- Overall at-risk breakdown: 614 donors (41% of base)
- Critical donor table with action items
- Reactivation strategy recommendations ($500K-$750K recovery potential)

---

## 📁 What's Included

```
CHCF-Donor-Analytics/
├── README.md                                    # This file
├── DATA/
│   ├── donations_final.xlsx                    # 3,745 donation transactions
│   ├── donors_final.xlsx                       # 1,500 donor profiles
│   ├── rfm_analysis.xlsx                       # RFM segmentation scores
│   └── engagement_final.xlsx                   # 7,126 engagement events
├── DASHBOARDS/
│   ├── CHCF_Donor_Analytics_Book6.twbx        # Tableau Public workbook (all 4 dashboards)
│   └── Dashboard_Screenshots/                  # PNG screenshots of each dashboard
├── ANALYSIS/
│   ├── 00_COMPLETE_ANALYSIS_REPORT.md         # Full analysis findings
│   ├── 02_EXECUTIVE_SUMMARY.md                # 1-page executive summary
│   ├── 03_TALKING_POINTS_CHEAT_SHEET.md       # Key metrics & insights
│   ├── powerbi_sql_queries.sql                # SQL queries for Power BI/databases
│   └── powerbi_dax_measures.txt               # DAX measures for Power BI
└── DOCUMENTATION/
    ├── TABLEAU_ADVANCED_DATA_MODELING.md      # Star schema, joins, design decisions
    ├── HOW_TO_RECREATE_IN_TABLEAU.md          # Step-by-step recreation guide
    ├── DATA_AUTHENTICITY_EXPLAINED.md         # Real vs. synthetic data explanation
    ├── CREATE_ALL_SHEETS_FIRST.md             # Sheet creation checklist
    ├── CORRECTED_TABLEAU_FORMULAS.md          # Working formulas for all calculations
    └── DASHBOARD_FORMATTING_IMPROVEMENTS.md   # Design best practices
```

---

## 📊 Key Metrics (FY 2023)

| Metric | Value | Insight |
|--------|-------|---------|
| **Total Revenue** | $76,431,633 | From official Form 990 filing (Nov 2024) |
| **Total Donors** | 1,500 | Realistic for org size |
| **Active Rate** | 3% | 47 donors with recent activity (≤365 days) |
| **Churn Rate** | 39% | 614 donors at risk, need intervention |
| **Top Donor** | $3,650K | Single largest annual contribution |
| **Average Donor LTV** | $50,954 | Lifetime value per donor |
| **Critical Risk Donors** | 378 | 2+ years inactive (730+ days) |
| **Email ROI** | 3.2x | Better than Direct Mail |
| **Event Engagement** | 5x | Higher giving than other channels |
| **Recovery Potential** | $7.6-$11.4M | With proper segmentation strategy |

---

## 🔧 Technical Stack

- **BI Platform:** Tableau Public
- **Data Source:** Real Form 990 data + synthetic transaction-level data
- **Data Modeling:** Star schema (Fact: Donations; Dimensions: Donors, RFM, Engagement)
- **Calculations:** Tableau LOD (Level of Detail) expressions, window functions
- **Formulas:** COUNTD, SUM(IF...), {FIXED}, aggregation functions
- **Data Generation:** Python (pandas)
- **Version Control:** Git + GitHub

---

## 📈 Data Architecture

**Star Schema Design:**

```
DONATIONS (Fact Table - 3,745 records)
├─ Donor_ID → DONORS (Dimension - 1,500 records)
├─ Donor_ID → RFM_ANALYSIS (Dimension - 1,500 records)
└─ Donor_ID → ENGAGEMENT (Fact - 7,126 records)

All tables joined via LEFT JOIN on Donor_ID
```

**Why this design:**
- ✅ Normalized structure prevents data redundancy
- ✅ Separate dimensions enable quick filtering
- ✅ Scalable for real Blackbaud CRM data
- ✅ Enables complex donor-level analysis

---

## 🎯 Key Findings

### **1. Extreme Churn Risk**
- 41% of donor base (614 donors) is at immediate risk
- 378 donors haven't given in 2+ years
- Synthetic data shows extreme scenario (96.9% inactive) - requires validation on real data

### **2. High-Value Segment Dominance**
- High Value donors: 35% of base, 79% of revenue ($60.5M)
- Champions: 7% of base, 14% of revenue but 5x higher engagement
- Concentration risk: Top 10 donors = 40% of annual revenue

### **3. Channel Performance Disparity**
- Email: Most effective channel ($35M annually)
- Foundation Grants: Attract highest-value donors
- Events: Drive 5x higher future giving
- Direct Mail: Lowest ROI vs. email (3.2:1 ratio)

### **4. Strategic Opportunities**
- **Retention:** Personal reactivation of top 50 at-risk donors = $500K-$750K recovery
- **Segmentation:** Targeted campaigns by segment could improve response 2-3x
- **Channel Mix:** Shifting budget to email/events could increase revenue 10-15%

---

## 📝 Data Authenticity

**Real Data (From IRS Form 990):**
- Organization: Children's Hospital Colorado Foundation (EIN: 84-0813462)
- Filing Date: November 5, 2024
- Fiscal Year: 2023 (ended December 31, 2023)
- Total Revenue: $76,431,633 ✓
- Total Assets: $95,522,513
- Total Distributed: $54,029,718

**Synthetic Data:**
- Individual donor names, transaction dates, amounts
- Campaign and channel assignments
- Engagement event logs
- All calibrated to match real $76.4M revenue total
- Standard practice for BI interviews/portfolio projects

**Why synthetic?** Donor-level data is confidential. Synthetic data demonstrates:
- Data modeling capability
- Dashboard design
- Analytics methodology
- Business insight generation

---

## 🚀 How to Use This Project

### **View the Dashboards**
1. Download `CHCF_Donor_Analytics_Book6.twbx` from the Dashboards folder
2. Open in [Tableau Public](https://public.tableau.com/) (free account required)
3. Interact with filters and drill-downs
4. View all 4 dashboards: Summary → Segmentation → Channels → Churn Risk

### **Review the Analysis**
- Start with `00_COMPLETE_ANALYSIS_REPORT.md` for full findings
- Read `02_EXECUTIVE_SUMMARY.md` for quick overview
- Reference `03_TALKING_POINTS_CHEAT_SHEET.md` for key metrics

### **Recreate in Your BI Tool**
- Use `HOW_TO_RECREATE_IN_TABLEAU.md` for step-by-step guide
- Reference `TABLEAU_ADVANCED_DATA_MODELING.md` for data model details
- Use `CORRECTED_TABLEAU_FORMULAS.md` for working calculations
- Adapt `powerbi_sql_queries.sql` for Power BI or SQL Server





## 📚 Learning Resources

### **Tableau**
- [Tableau Official Documentation](https://help.tableau.com/)
- [Tableau Level of Detail (LOD) Expressions](https://help.tableau.com/current/pro/desktop/en-us/calculations_calculatedfields_lod.htm)
- [Star Schema Design](https://www.tableau.com/en-us/learn/articles/data-modeling)

### **Nonprofit Fundraising**
- [RFM Analysis for Donors](https://www.donordrive.com/resources/rfm-analysis/)
- [Donor Segmentation Best Practices](https://www.afpnet.org/toolkits/donor-segmentation)
- [Blackbaud CRM Overview](https://www.blackbaud.com/nonprofit-crm)

### **Data Modeling**
- [Star Schema Tutorial](https://www.sisense.com/blog/star-schema-database/)
- [Fact vs. Dimension Tables](https://www.kimballgroup.com/data-warehouse-business-intelligence-resources/)

---

## 🔍 Key Design Decisions

1. **Why FY 2023?** Official 990 filing date (Nov 2024) provides verified, recent data

2. **Why Synthetic Donor Data?** Protects donor privacy while demonstrating modeling capability

3. **Why Star Schema?** Scalable for real Blackbaud data integration and complex queries

4. **Why 4 Dashboards?** Mirrors typical nonprofit BI structure (Executive → Segments → Channels → Risk)

5. **Why Tableau?** Most common BI tool for nonprofits, excellent for storytelling

---

## 🎓 What You'll Learn From This Project

- How to analyze nonprofit fundraising data
- RFM segmentation theory and implementation
- Dashboard design for different audiences
- Data storytelling and executive communication
- How to quantify business value from data
- Tableau best practices and advanced features
- Interview preparation for data analytics roles

---

## 📧 Questions & Feedback

Have questions about this project? Check these resources:
- **Data source:** See DATA_AUTHENTICITY_EXPLAINED.md
- **Dashboard recreation:** See HOW_TO_RECREATE_IN_TABLEAU.md
- **Formulas:** See CORRECTED_TABLEAU_FORMULAS.md
- **Full analysis:** See 00_COMPLETE_ANALYSIS_REPORT.md

---

## 📄 License

This project is for educational and portfolio purposes. The organization name and form 990 data are publicly available. Synthetic donor data is created for demonstration only.

---

## 🌟 Key Takeaway

**Data without insight is just noise. This project transforms $76.4M in annual revenue data into a clear roadmap for growth: identify at-risk donors, optimize channel spending, and recover $7.6-$11.4M in annual opportunity.**

---

**Created:** April 2026  
**Tools:** Tableau Public, Python, SQL  
**Data Source:** IRS Form 990 Filing (November 5, 2024)  
**Organization:** Children's Hospital Colorado Foundation (EIN: 84-0813462)

---

*Transform public financial data into strategic business intelligence: from discovering $76.4M in annual revenue to uncovering $7.6-$11.4M in growth opportunities.*
