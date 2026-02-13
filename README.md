# European-Pharmacy-Sales-Analysis

**Description:** 
```
Power BI dashboard analyzing 120 European pharmacies to identify performance drivers and growth opportunities.
€975K revenue opportunity identified through strategic execution improvements.
```
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

# European Pharmacy Performance Analysis 🏥

**Power BI Dashboard | Retail Analytics | Onyx Data DNA Challenge**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/johanna-ezedinma/)

---

## 📊 Project Overview

Interactive Power BI dashboard analyzing **120 European pharmacies** across **8 countries** to identify performance drivers and quantify growth opportunities.

**Key Metrics:**
- Revenue: €4.41M (+4.4% YOY)
- Profit: €1.24M (+4.9% YOY)
- Profit Margin: 28.11%
- Total Volume: 228K units

---

## 🎯 Business Questions Answered

1. **What drives pharmacy profitability?**
   - Location influences (Urban 4.5x more profitable than Rural)
   - Execution matters more than geography (81% variance within same location type)

2. **Where are the growth opportunities?**
   - €8.13K average gap per underperforming pharmacy
   - €975K total network opportunity
   - Poland shows largest country-level gap (€847/pharmacy)

3. **Which products drive revenue vs. margin?**
   - Prescription leads revenue, Wellness drives margin
   - FreshLine tops brand profitability (36% margin)
   - OTC dominates volume but delivers lower profitability

4. **What differentiates top vs. underperformers?**
   - Sales velocity (2x more units across all categories)
   - Promotional effectiveness (17% vs 11% promo revenue)
   - Strategic category management

---

## 📸 Dashboard Preview

### Page 1: Sales & Profitability Overview
![Overview Dashboard](https://github.com/Johanna-Ezedinma/European-Pharmacy-Sales-Analysis/blob/main/Pharmacy%20Sales%20Overview%20Page.jpg?raw=true)

**Key Insights:**
- Revenue grew 4.4% YOY while profit grew 4.9%
- Prescription products lead revenue consistently
- Personal Care and Wellness drive margin (28.11% overall)
- Summer peaks at €1.36M revenue (+37% vs Winter)

---

### Page 2: Pharmacy Performance & Growth Opportunities
![Pharmacy Performance](https://github.com/Johanna-Ezedinma/European-Pharmacy-Sales-Analysis/blob/main/Pharmacy%20performance%20and%20growth%20opportunities.jpg?raw=true)

**Key Insights:**
- Urban pharmacies: €21.2K avg profit vs €4.7K rural
- Top performers earn 81% more than underperformers (same location)
- Total revenue gap opportunity: €8.13K per pharmacy
- Promotional effectiveness gap: 17.26% (top) vs 11.28% (under)

---

### Page 3: Product Performance Analysis
![Product Performance](https://github.com/Johanna-Ezedinma/European-Pharmacy-Sales-Analysis/blob/main/Product%20Performance%20and%20growth%20opportunities.jpg?raw=true)

**Key Insights:**
- FreshLine leads profitability: 36% margin
- Top 5 brands: FreshLine, ZenHealth, NatureFit, SkinGuard, ImmunoPlus
- Top performers stock 17-20pp more high-margin categories
- Scatter plot reveals strategic prioritization opportunities

---

## 🛠️ Technical Implementation

### Data Model
- **Fact Table:** FactSales (transaction-level data)
- **Dimension Tables:** 
  - DimPharmacy (120 pharmacies, 8 countries)
  - DimProduct (220 products, 4 categories)
  - DimDate (calendar table with time intelligence)

### Key DAX Calculations

**Performance Tier Classification:**
```dax
Performance Tier = 
VAR PharmacyRevenue = [Pharmacy Total Revenue]
VAR CountryAverage = [Country Average Revenue]
VAR TopThreshold = CountryAverage * 1.2
VAR BottomThreshold = CountryAverage * 0.8
RETURN
    SWITCH(
        TRUE(),
        PharmacyRevenue >= TopThreshold, "Top Performer",
        PharmacyRevenue >= BottomThreshold, "Average Performer",
        "Underperformer"
    )
```

**YoY Growth:**
```dax
YoY Growth % = 
DIVIDE(
    [Total Revenue] - [Revenue Last Year],
    [Revenue Last Year],
    0
)
```

**Revenue Gap Analysis:**
```dax
Revenue Gap per Pharmacy = 
[Top Country Avg Revenue per Pharmacy] - [Avg Revenue per Pharmacy]
```

### Features Implemented
- ✅ Time intelligence (YOY, YTD, SAMEPERIODLASTYEAR)
- ✅ Performance tier segmentation
- ✅ Geographic clustering & comparison
- ✅ Product portfolio analysis
- ✅ Interactive slicers (Country, Quarter, Performance Tier)
- ✅ Dynamic KPI cards with variance indicators
- ✅ Conditional formatting for data-driven insights

---

## 💡 Key Findings & Recommendations

### Finding 1: Execution Over Location
**Insight:** Even within the same location type, top performers earn 81% more than underperformers.

**Recommendation:** Focus on operational excellence, not just site selection.

---

### Finding 2: Volume Drives Success
**Insight:** Top performers sell 2x more units across ALL categories, not different products.

**Recommendation:** 
- Improve sales velocity through better customer engagement
- Optimize inventory turnover
- Enhance promotional effectiveness

---

### Finding 3: Category Mix Matters
**Insight:** Top performers stock 17-20pp more high-margin categories (Prescription, Wellness).

**Recommendation:**
- Shift inventory toward high-margin categories
- Reduce reliance on low-margin OTC generics
- Strategic brand selection (FreshLine, NatureFit vs generic alternatives)

---

### Finding 4: Promotional Effectiveness Gap
**Insight:** Top performers generate 17% of revenue from promotions vs 11% for underperformers.

**Recommendation:**
- Study top-performer promotional strategies
- Implement targeted campaigns
- Measure promotional ROI more rigorously

---

## 📈 Business Impact

**If all underperforming pharmacies matched top-performer metrics:**

| Metric | Current | Target | Opportunity |
|--------|---------|--------|-------------|
| Avg Revenue per Pharmacy | €1.32K | €2.39K | +€1.07K (+81%) |
| Network-wide Opportunity | - | - | €975K |
| Largest Country Gap (Poland) | - | - | €847/pharmacy |

---

## 🔧 Tools & Technologies

- **Power BI Desktop** - Data visualization & reporting
- **DAX** - Calculated columns, measures, time intelligence
- **Power Query** - Data transformation & modeling
- **Excel** - Source data (Onyx Data challenge dataset)

--- 

## 📂 Repository Structure
```
European-Pharmacy-Analytics/
├── README.md                           # This file
├── images/                             # Dashboard screenshots
│   ├── page1_overview.png
│   ├── page2_pharmacy_performance.png
│   └── page3_product_performance.png
└── data/                               # Sample data
    └── data_dictionary.md
```

---

## 📊 Data Source

**Onyx Data DNA Challenge (Jan-Feb 2026)**
- Dataset: European Pharmacy Sales Data
- 120 pharmacies across 8 countries
- 220 products, 4 categories
- Transaction-level sales, profit, volume data

---

## 🎓 Learning Outcomes

This project demonstrates:
- Advanced DAX calculations (time intelligence, performance segmentation)
- Data modeling best practices (star schema, relationship management)
- Visual design principles (color theory, hierarchy, white space)
- Business storytelling through data
- Insight-driven recommendations

---

## 📝 About This Project

Created as part of the **Onyx Data DNA Challenge** (Jan-Feb 2026).

**Challenge Theme:** Analyze pharmacy performance to identify growth opportunities and performance drivers.

**My Approach:**
1. Built performance tier classification based on country-relative metrics
2. Conducted within-region comparisons to isolate execution factors
3. Quantified revenue gaps and opportunities
4. Delivered actionable recommendations based on data insights

---

## 👤 Author

**Johanna Ezedinna**
- 📧 Email: johannaezedinna@gmail.com
- 💼 LinkedIn: (https://www.linkedin.com/in/johanna-ezedinma/)
- 🐙 GitHub: (https://github.com/Johanna-Ezedinma)

---

## 🏆 Acknowledgments

- **Onyx Data** for the challenge dataset and opportunity
- **Power BI Community** for continuous learning resource

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 📌 Tags

`#PowerBI` `#DataAnalytics` `#RetailAnalytics` `#DAX` `#DataVisualization` `#BusinessIntelligence` `#OnyxData` `#DataDNA` `#PharmacyAnalytics` `#PerformanceAnalysis`

---

**⭐ If you found this project helpful, please star this repository!**
```
