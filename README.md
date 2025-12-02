
# Customer Segmentation Analysis using LRFM & Marketing Campaign Data

Proyek ini bertujuan untuk melakukan **segmentasi pelanggan** pada sebuah supermarket dengan menggabungkan pendekatan:

- **LRFM Analysis**  
- **Demographic Segmentation**  
- **Campaign Response Profiling**  
- **Behavioral Analysis (Channel Usage, Spending Pattern)**  
- **Tableau Dashboard** untuk visualisasi interaktif  

Hasil akhir digunakan untuk mendukung keputusan strategis terkait **marketing**, **customer retention**, dan **loyalty program**.

---

## 1. Dataset

Dataset berisi 2.236 pelanggan dengan variabel:

### **Demografi**
- `ID`
- `Year_Birth`
- `Education`
- `Marital_Status`
- `Income`
- `Kidhome`, `Teenhome`
- `Dt_Customer` (tanggal pertama menjadi pelanggan)

### **Behavioral / RFM**
- `Recency`
- `MntWines`, `MntFruits`, `MntMeatProducts`, dll.
- `NumWebPurchases`, `NumStorePurchases`, `NumDealsPurchases`, dll.
- `NumWebVisitsMonth`

### **Campaign Response**
- `AcceptedCmp1` – `AcceptedCmp5`
- `Response`
- `Complain`

---

## 2. Data Cleaning

Tahapan pembersihan data meliputi:

- Mengisi missing values pada `Income` dengan nilai median
- Menghapus outlier ekstrem pada pendapatan (nilai 666.666)
- Membuat fitur baru:
  - `Year`
  - `Age`

---

## 3. Feature Engineering (LRFM)

Fitur LRFM yang digunakan untuk clustering:

- **Length** – Lama menjadi pelanggan  
- **Recency** – Hari sejak pembelian terakhir  
- **Frequency** – Total frekuensi transaksi  
- **Monetary** – Total belanja (`Total_Spending`)

Data kemudian distandardisasi menggunakan **StandardScaler**.

---

## 4. Clustering

Metode yang digunakan:

- **Elbow Method** → optimal cluster = **5**
- **K-Means Clustering (k=5)**

### **Hasil Segmen**

1. **High Value** — Spending tertinggi, Frequency tertinggi, respons kampanye terbaik  
2. **Active Buyers** — Frequent shoppers dengan respon kampanye tinggi  
3. **New Active** — Baru belanja, Frequency rendah  
4. **Passive Long-Term** — Lama menjadi pelanggan tetapi jarang berbelanja  
5. **Churn-To-Be** — Recency tinggi, spending rendah, hampir tidak merespons kampanye  

---

## 5. Tableau Dashboard

Dashboard berisi:

- KPI (Total Customers, Avg Spending, Avg Income)
- Distribusi Cluster
- Distribusi Spending & Income
- LRFM Profile per Cluster
- Channel Behavior
- Campaign Response Heatmap

Link Tableau Public:  
(**(https://public.tableau.com/app/profile/yoga.brahma/viz/Capstone2_YogaBrahma_SupermarketDataset/Dashboard1?publish=yes)**)

---

## 6. Business Insights

- High Value & Active Buyers adalah **segmen paling profit**
- Churn-To-Be perlu **program reaktivasi**
- Campaign 2 adalah **kampanye paling tidak efektif**
- Mayoritas pelanggan memiliki **pendidikan tinggi**, sehingga promo harus menonjolkan *value driven decision-making*
- Pelanggan rata-rata berasal dari **keluarga kecil**, sehingga promo family bundle kurang relevan

---

## 7. Tools yang Digunakan

- Python (Pandas, NumPy, Seaborn, Matplotlib, Scikit-Learn)
- Jupyter Notebook
- Tableau Public
- GitHub

---

## 📁 8. Struktur Repository

