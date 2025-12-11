# 🤖 Synthetic LEGO Generator (DCGAN)

> Project Deep Learning untuk membangkitkan gambar LEGO baru menggunakan *Deep Convolutional Generative Adversarial Networks*.

## 👤 Project Info
* **Nama:** Yusuf Ahmad Rabbani
* **NIM:** 41236818
* **Kelas:** TI-KIP-P4
* **Topik:** Computer Vision / Generative AI

---

## 📝 Overview
Repositori ini berisi implementasi model **DCGAN** (Deep Convolutional GAN) yang dibangun menggunakan framework **TensorFlow/Keras**. Tujuan utama dari proyek ini adalah melatih model AI agar mampu mempelajari distribusi data dari gambar LEGO asli dan menghasilkan (generate) gambar LEGO sintetis yang baru dari *latent space* (random noise).

Model ini dilatih selama **500 Epoch** untuk mencapai hasil visual yang stabil pada resolusi **64x64 pixel**.

## 🔧 Technical Details

### Dataset
Data yang digunakan bersumber dari Kaggle: **[LEGO Brick Images](https://www.kaggle.com/datasets/joosthazelzet/lego-brick-images)**.
* **Preprocessing:** Resize ke 64x64, Normalisasi pixel ke range `[-1, 1]`.
* **Batch Size:** 64

### Model Architecture
Arsitektur jaringan terdiri dari dua model yang saling berkompetisi (*Minimax Game*):

1.  **Generator ($G$):**
    * Input: Random noise (Latent dimension: 128).
    * Layer: Menggunakan `Conv2DTranspose` untuk *upsampling*.
    * Activation: `LeakyReLU` pada hidden layers dan `Tanh` pada output layer (untuk menghasilkan warna RGB).

2.  **Discriminator ($D$):**
    * Input: Citra (64x64x3).
    * Layer: Menggunakan `Conv2D` dengan stride untuk *downsampling* (ekstraksi fitur).
    * Activation: `LeakyReLU` dan `Dropout` (0.3) untuk regularisasi.
    * Output: Binary Classification (Real vs Fake).

## 🚀 How to Run
1.  **Clone Repository**
    ```bash
    git clone [https://github.com/username-anda/lego-dcgan-project.git](https://github.com/username-anda/lego-dcgan-project.git)
    ```
2.  **Setup Environment**
    Pastikan library berikut terinstall:
    * `tensorflow`
    * `matplotlib`
    * `numpy`
    * `kaggle` (Opsional, untuk auto-download dataset)
3.  **Run Notebook**
    Buka file `Model_DCGAN.ipynb` di Google Colab atau Jupyter Notebook lokal dan jalankan semua cell ("Run All").

## 📊 Results
Training dilakukan menggunakan GPU T4. Pada epoch ke-500, model Generator mampu membentuk struktur bata LEGO yang jelas dengan variasi warna yang beragam.

---
*Dikembangkan sebagai tugas mata kuliah Deep Learning.*
