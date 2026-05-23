# GenAI KPI Meeting Assistant

> An AI-powered sales KPI dashboard that ingests raw sales data, computes executive metrics, generates AI summaries using Google Gemini, and emails full PDF reports with charts — built with Python and Streamlit.

---

## Problem Statement

Business teams spend hours before weekly meetings manually pulling sales numbers, building slides, and writing summaries. This tool automates the entire workflow:
- Upload a sales CSV/Excel file
- Instantly get KPI metrics, trend charts, and AI-generated insights
- Email a formatted PDF report to any stakeholder in one click

---

## Key Features

| Feature | Description |
|---|---|
| Smart Column Mapping | Automatically detects column names (e.g. `price`, `item_mrp`, `revenue` all map to Sales) |
| Executive Summary | Computes Total Sales, Total Profit, Total Quantity, Avg Discount |
| Sales Trend Charts | Auto-selects Daily / Weekly / Monthly / Yearly based on data range |
| Region & Category Analysis | Bar charts, pie charts, and profit heatmap (Region vs Category) |
| Top 10 Products | Bar chart of best-selling products |
| Week-over-Week Change | Detects unusual sales fluctuations automatically |
| AI-Generated Summary | Uses Google Gemini (`gemini-pro`) to write a natural language KPI narrative |
| PDF Report | Generates a formatted PDF with all KPIs and insights |
| Email Delivery | Sends PDF + chart images directly to any recipient via Gmail SMTP |
| Filter Panel | Interactive region and month filters for drill-down analysis |

---

## Tech Stack

| Layer | Tools |
|---|---|
| Frontend/UI | Streamlit |
| Data Processing | Pandas, NumPy |
| Visualizations | Plotly Express, Seaborn, Matplotlib |
| AI / GenAI | Google Gemini API (`gemini-pro`), HuggingFace Transformers (`facebook/bart-large-cnn`) |
| PDF Generation | FPDF |
| Email | smtplib, MIME (multipart, text, application, image) |
| Language | Python 3.x |

---

## Architecture & Workflow

```
Upload CSV/Excel
       |
       v
Column Auto-Detection  <-- Maps varied column names to standard KPIs
       |
       v
Executive Summary      <-- Total Sales, Profit, Quantity, Discount
       |
       v
Visual Dashboards      <-- Trend, Region, Category, Heatmap, Top Products
       |
       v
AI Summary             <-- Google Gemini generates natural language narrative
       |
       v
PDF + Email Report     <-- FPDF generates report, Gmail SMTP delivers it
```

---

## Project Files

| File | Purpose |
|---|---|
| `finalkpiproject.py` | Main Streamlit app — full dashboard with charts, PDF, email |
| `kpi_assistant.py` | Extended version with HuggingFace BART summarizer integration |
| `gemini-run.py` | Standalone Gemini API test script |
| `requirements.txt` | Python dependencies |

---

## Setup Instructions

```bash
# Clone the repository
git clone https://github.com/NeheMalviya1243/genai-kpi-meeting-assistant.git
cd genai-kpi-meeting-assistant

# Install dependencies
pip install -r requirements.txt

# Run the app
streamlit run finalkpiproject.py
```

**Required columns in your data (flexible naming):**
- Sales: `sales`, `item_mrp`, `revenue`, `price`
- Region: `region`, `outlet_location_type`, `city`
- Category: `category`, `item_type`, `product_type`
- Date: `date`, `order_date`, `transaction_date`
- Profit: `profit`
- Quantity: `quantity`, `qty`, `quantity_ordered`
- Discount: `discount`

---

## Example Use Case

**Scenario:** A sales manager wants a weekly KPI report before Monday’s meeting.

1. Upload `weekly_sales.csv` to the dashboard
2. Review auto-generated Executive Summary and trend charts
3. Click **Generate AI Summary** — Gemini writes a boardroom-ready narrative
4. Enter recipient email and click **Send KPI Email**
5. Stakeholder receives a PDF with charts and insights in their inbox

---

## Recruiter Highlights

- **GenAI Integration:** Connected Google Gemini API to generate real natural language business summaries
- **End-to-End Automation:** From raw CSV upload to formatted email delivery in one app
- **Flexible Data Ingestion:** Handles messy, inconsistently named real-world datasets automatically
- **Production Patterns:** PDF generation, SMTP email, temp file handling, exception management
- **Business Value:** Replaces 1-2 hours of manual weekly reporting with a single file upload

---

Built by [Nehe Malviya](https://github.com/NeheMalviya1243) | Rider University — Business Data Analytics
