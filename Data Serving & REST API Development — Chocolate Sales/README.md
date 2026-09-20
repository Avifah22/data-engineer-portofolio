# 🍫 Data Serving & REST API Development — Chocolate Sales

Proyek ini berfokus pada tahap **Data Serving** dalam *Data Engineering Lifecycle*. Proyek ini mengimplementasikan *pipeline* pemrosesan data penjualan cokelat, validasi skema data, serta deployment *serving layer* menggunakan **FastAPI** untuk menyajikan hasil analisis/klasterisasi data secara *real-time*.

---

## 🚀 Fitur Utama (Data Engineering Perspective)

* **Data Ingestion & Preprocessing:** Memproses dan membersihkan raw data penjualan (`amount` dan `boxes_shipped`) menggunakan **Pandas**.
* **Data Schema Validation:** Menggunakan **Pydantic** untuk memastikan *payload* input dari pengguna sesuai dengan tipe data yang dibutuhkan sebelum masuk ke pipeline pemrosesan.
* **Low-Latency Data Serving:** Membangun REST API berbasis **FastAPI** & **Uvicorn** dengan endpoint `POST /predict` untuk *serving* data klaster secara *real-time*.
* **Model Artifact Integration:** Mengintegrasikan model terkompresi (`.pkl`) ke dalam alur eksekusi API tanpa perlu melakukan pelatihan ulang (re-training) saat *runtime*.

---

## 🛠️ Cara Menjalankan API (Lokal)

1. **Install dependencies:**
   ```bash
   pip install fastapi uvicorn scikit-learn pandas joblib pydantic
2. **Jalankan server API:**
   ```bash
   uvicorn main:app --reload
3. **Akses Dokumentasi Interactive API (Swagger UI):**
   Buka browser dan masuk ke: http://127.0.0.1:8000/docs

## 📸 Bukti Eksekusi & Uji Coba API (menggunakan Google Collaboratory)
1. <img width="404" height="272" alt="11" src="https://github.com/user-attachments/assets/71a143ae-715a-4eec-9ed1-9db58517e8d6" />
> *Gambar Dataset.Disclaimer: Dataset ini bersifat publik dan diambil dari https://www.kaggle.com/datasets/saidaminsaidaxmadov/chocolate-sales*
2. <img width="364" height="305" alt="12" src="https://github.com/user-attachments/assets/6f51b081-5e1d-43da-bc3c-8c9f059ba07a" />
> *Analisis eksplorasi dan transformasi fitur data penjualan menggunakan teknikUnsupervised Learning ($K=3$) untuk membentuk lookup logic atau klasterisasi.*
3. <img width="283" height="365" alt="13" src="https://github.com/user-attachments/assets/2ed8dd34-7292-4ff8-8a4f-ef584bc9bc59" />
> *Pengujian endpoint POST /predict secara lokal. API berhasil menerima JSON payload data penjualan (amount dan boxes_shipped), melakukan skema validasi, dan mengembalikan hasil serving data klaster secara real-time.*

## 📂 Struktur Folder
```text
├── 01-chocolate-sales-clustering-api/
│   ├── main.py                 # Script utama FastAPI
│   ├── kmeans_chocolate.pkl    # Model Machine Learning yang sudah di-train
│   ├── Chocolate Sales (2).csv # Dataset penjualan cokelat
│   └── README.md               # Dokumentasi proyek


---
Dibuat sebagai bagian dari Portofolio Data Engineer.



