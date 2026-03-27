# 📰 News Category Clustering using TF-IDF and K-Means

โปรเจกต์นี้เป็นการนำเทคนิค **Machine Learning และ Natural Language Processing (NLP)** มาใช้ในการจัดกลุ่มข่าวออนไลน์โดยอัตโนมัติ
โดยใช้ **TF-IDF Vectorization** และ **K-Means Clustering** เพื่อจัดกลุ่มข่าวจากชุดข้อมูล **BBC News Dataset**

โปรเจกต์นี้อยู่ในหัวข้อ

> **New Paradigms of Pattern Recognition: News Category Classification using TF-IDF and K-Means Clustering**

---

# 🎯 Objective

วัตถุประสงค์ของโปรเจกต์นี้คือ

* แปลงข้อความข่าวเป็นเวกเตอร์ด้วย **TF-IDF**
* ใช้ **K-Means Clustering** เพื่อจัดกลุ่มข่าว
* วิเคราะห์ว่ากลุ่มข่าวที่ได้มีความสัมพันธ์กับหมวดข่าวจริงหรือไม่
* แสดงผลด้วย **PCA** และ **t-SNE Visualization**

---

# 📂 Dataset

ใช้ Dataset จาก **Kaggle**

BBC News Summary Dataset

ประกอบด้วยข่าว 5 หมวดหมู่

| Category      | Description   |
| ------------- | ------------- |
| business      | ข่าวเศรษฐกิจ  |
| entertainment | ข่าวบันเทิง   |
| politics      | ข่าวการเมือง  |
| sport         | ข่าวกีฬา      |
| tech          | ข่าวเทคโนโลยี |

Dataset ถูกดาวน์โหลดด้วย Kaggle API

---

# ⚙️ Technologies Used

* Python
* Google Colab
* Pandas
* Scikit-learn
* Matplotlib
* Seaborn
* Kaggle API

---

# 🧠 Machine Learning Methods

## 1️⃣ TF-IDF Vectorization

ใช้ **TF-IDF (Term Frequency – Inverse Document Frequency)**
เพื่อแปลงข้อความข่าวให้เป็นตัวเลข

```python
vectorizer = TfidfVectorizer(stop_words='english', max_df=0.7, min_df=5)
X = vectorizer.fit_transform(df["text"])
```

---

## 2️⃣ K-Means Clustering

ใช้ K-Means เพื่อจัดกลุ่มข่าว

```python
model = KMeans(n_clusters=5, random_state=42)
df["cluster"] = model.fit_predict(X)
```

กำหนดจำนวน cluster = 5 เพื่อให้ตรงกับจำนวนหมวดข่าว

---

# 📊 Data Visualization

## PCA (Principal Component Analysis)

ใช้ PCA เพื่อลดมิติของข้อมูลจากหลายพันมิติให้เหลือ 2 มิติ

เพื่อแสดงผลบนกราฟ

---

## t-SNE Visualization

ใช้ **t-SNE** เพื่อกระจายจุดข้อมูลให้เห็นการแยก cluster ชัดเจนมากขึ้น

```python
tsne = TSNE(n_components=2, random_state=42)
```

---

# 📈 Example Results

ผลลัพธ์จากการ clustering

| Cluster   | Category ส่วนใหญ่   |
| --------- | ------------------- |
| Cluster 0 | Business / Politics |
| Cluster 1 | Sport               |
| Cluster 2 | Technology          |
| Cluster 3 | Entertainment       |
| Cluster 4 | Technology          |

---

# 📊 Cluster Evaluation

ใช้ **Cross Tabulation** เพื่อตรวจสอบความสัมพันธ์ระหว่าง

* Cluster ที่โมเดลจัด
* Category จริงจาก dataset

```python
ct = pd.crosstab(df['cluster'], df['category'])
print(ct)
```

---

# 📉 Visualization Output

โปรเจกต์นี้สร้างกราฟ

* PCA Scatter Plot
* t-SNE Scatter Plot

เพื่อแสดงการกระจายตัวของข่าวในแต่ละ Cluster

---

# 🚀 How to Run

## 1️⃣ Clone Repository

```bash
git clone https://github.com/yourusername/news-clustering-tfidf-kmeans.git
```

---

## 2️⃣ Install Dependencies

```bash
pip install pandas scikit-learn matplotlib seaborn kaggle
```

---

## 3️⃣ Upload Kaggle API

อัปโหลดไฟล์

```
kaggle.json
```

เพื่อใช้ดาวน์โหลด dataset

---

## 4️⃣ Run Notebook

เปิดไฟล์

```
news_clustering.ipynb
```

ใน

* Google Colab
* Jupyter Notebook

---

# 📁 Project Structure

```
news-clustering
│
├── news_clustering.ipynb
├── README.md
└── dataset
```

---

# 📚 Key Concepts

โปรเจกต์นี้ใช้แนวคิดจาก

* Natural Language Processing (NLP)
* Machine Learning Clustering
* Dimensionality Reduction
* Pattern Recognition

---

# 👨‍💻 Author

Student: Computer Engineering
Rajamangala University of Technology Lanna

Project Topic:

**New Paradigms of Pattern Recognition**

News Category Classification using TF-IDF and K-Means Clustering

---

# 📌 Notes

โปรเจกต์นี้จัดทำขึ้นเพื่อการศึกษาในวิชา

* Machine Learning
* Pattern Recognition
* Natural Language Processing
