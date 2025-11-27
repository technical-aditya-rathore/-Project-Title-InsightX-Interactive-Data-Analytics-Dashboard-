# -Project-Title-InsightX-Interactive-Data-Analytics-Dashboard-
Analyze any CSV dataset (sales, student scores, COVID data, etc.) using:
------------------------------------==-------------------------------------------------==-------------------------------------------------------==-------------------
🔐 Project: InsightX – Data Analytics Dashboard  
👑 Owner: Aditya Kumar Jha  
📅 Year: 2025  

This project is the intellectual property of Aditya Kumar Jha.  
All content, code, and design elements are protected under copyright laws.

🚫 Unauthorized use, duplication, or redistribution of this codebase in any form is strictly prohibited.  
Any violation will result in legal action under GitHub's Terms of Service and applicable international laws.

✅ You may use this project for learning purposes only with proper attribution.

© 2025 Aditya Kumar Jha. All rights reserved.


---

## 📊 Project Title: **"InsightX – Interactive Data Analytics Dashboard"**

### 🔍 Objective:

* Summary statistics 📈
* Data visualizations (bar chart, pie chart, line graph) 📊
* Correlation matrix 🔗
* Interactive dashboard using **Streamlit** 🖥️

---

### 🧰 Tech Stack:

* Python 🐍
* Pandas (Data Handling)
* Matplotlib & Seaborn (Visualization)
* Streamlit (Dashboard UI)

---

## 🗂️ Folder Structure:

```
InsightX_Dashboard/
├── app.py
├── dataset.csv
└── README.md
```

---

### 📜 `app.py`

```python
import streamlit as st
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt

st.set_page_config(page_title="InsightX Data Dashboard", layout="wide")

st.title("📊 InsightX – Data Analytics Dashboard")

uploaded_file = st.file_uploader("Upload your CSV dataset", type=["csv"])
if uploaded_file:
    df = pd.read_csv(uploaded_file)
    st.subheader("Dataset Preview")
    st.write(df.head())

    st.subheader("Descriptive Statistics")
    st.write(df.describe())

    st.subheader("Correlation Matrix")
    corr = df.corr(numeric_only=True)
    fig, ax = plt.subplots()
    sns.heatmap(corr, annot=True, cmap="coolwarm", ax=ax)
    st.pyplot(fig)

    st.subheader("Select Column for Distribution Plot")
    col = st.selectbox("Column", df.select_dtypes(include='number').columns)
    fig2, ax2 = plt.subplots()
    sns.histplot(df[col], kde=True, ax=ax2)
    st.pyplot(fig2)

    st.subheader("Line Chart")
    st.line_chart(df.select_dtypes(include='number'))
```

---

### 🧾 `README.md`

```markdown
# InsightX – Data Analytics Dashboard

This is a powerful Python Streamlit app that allows users to:
- Upload a CSV dataset
- View data summary, stats & visual insights
- Plot heatmaps, histograms & line graphs

## How to Run
1. Install dependencies:
   pip install streamlit pandas matplotlib seaborn

2. Run the app:
   streamlit run app.py

## Owner Notice
© 2025 Aditya Kumar Jha  
Unauthorized copying is strictly prohibited. Legal action will be taken under GitHub security policies.
```

---





