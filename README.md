# Batik Nitik Generative AI: Multimodal RAG & Image Synthesis

[![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/Framework-PyTorch-ee4c2c.svg)](https://pytorch.org/)
[![Model](https://img.shields.io/badge/Model-Stable--Diffusion-lightgrey.svg)](https://huggingface.co/runwayml/stable-diffusion-v1-5)

Proyek ini mengimplementasikan sistem **Multimodal Retrieval-Augmented Generation (RAG)** untuk melestarikan dan mengembangkan motif Batik Nitik. Sistem ini menggabungkan pencarian kemiripan visual, pemahaman konteks filosofis melalui captioning, dan sintesis gambar berbasis difusi.

---

## 🚀 Arsitektur Sistem

Sistem ini terdiri dari tiga komponen utama yang bekerja secara hibrida:



1.  **Retrieval (CLIP + FAISS):** Mengambil motif batik yang relevan dari dataset berdasarkan query gambar atau teks.
2.  **Cognition & Captioning (BLIP-2 + QLoRA):** Model BLIP-2 yang telah di-*fine-tuned* untuk memberikan deskripsi visual detail dan mengekstrak filosofi motif dari metadata.
3.  **Generation (Stable Diffusion v1.5):** Menghasilkan motif batik baru menggunakan teknik *Img2Img* dengan *Fusion Prompt* yang diperkaya oleh konteks RAG.

---

## 📊 Dataset
Dataset yang digunakan berasal dari **Mendeley Data**:
* **Judul:** Batik Nitik 960
* **Link:** [data.mendeley.com/datasets/sgh484jxzy/3](https://data.mendeley.com/datasets/sgh484jxzy/3)
* **Konten:** 960 gambar motif Batik Nitik dengan metadata deskripsi dan filosofi dalam Bahasa Indonesia & Inggris.

---

## 🛠️ Instalasi & Penggunaan

1. **Clone Repository:**
   ```bash
   git clone [https://github.com/username/batik-nitik-generative-ai.git](https://github.com/username/batik-nitik-generative-ai.git)
   ```
2. **Install Dependencies:**
   ```bash
   pip install torch transformers diffusers accelerate peft faiss-gpu bitsandbytes
   ```
3. **Pipeline Utama:**
- Jalankan notebook/script untuk preprocessing CLIP embeddings.
- Lakukan fine-tuning BLIP-2 menggunakan script LoRA yang tersedia.

## 📈 Evaluasi Model
Proyek ini dievaluasi menggunakan berbagai metrik standar industri:

|Komponen|	Metrik|	Tujuan|
---------------------------------
|Retrieval|	Top-K Accuracy, mAP|	Mengukur ketepatan pencarian motif.|
|Captioning|	BLEU, ROUGE|	Mengukur kualitas deskripsi teks model BLIP-2.|
|Generative|	CLIP Score, FID|	Mengukur kesesuaian gambar dengan prompt dan realisme motif.|
