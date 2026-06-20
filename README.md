# Anlamsal Arama ve Belge Getirme Sistemi

### BM5204 Doğal Dil İşleme — Final Projesi
**Ahmetcan PEKTAŞ** | Bandırma Onyedi Eylül Üniversitesi

---

## Hakkında

Bu projede, Türkçe belge getirme problemi için klasik bilgi erişim yöntemi **BM25** ile yoğun vektör tabanlı **Sentence-BERT MiniLM**, **multilingual-E5-base** ve **multilingual-E5-large** modelleri karşılaştırılmıştır. Amaç, doğal dilde yazılan bir sorguya en alakalı pasajları getiren bir anlamsal arama sistemi geliştirmek ve farklı yöntemlerin performanslarını incelemektir.

---

### Kullanılan Veri Seti: https://huggingface.co/datasets/parsak/msmarco-tr

---

## Temel Bulgular

- BM25, genel amaçlı MiniLM modelinden daha yüksek başarı göstermiştir.
- Bilgi erişim görevleri için geliştirilen E5 modelleri tüm yöntemleri belirgin şekilde geride bırakmıştır.
- En yüksek performans **multilingual-E5-large** modeli ile elde edilmiştir.

| Model | MRR | Recall@10 |
|---------|------:|------:|
| BM25 | 0.503 | 0.659 |
| MiniLM | 0.479 | 0.643 |
| E5-base | 0.798 | 0.924 |
| E5-large | **0.839** | **0.943** |

---

## Dosyalar

| Dosya | Açıklama |
|---------|---------|
| `Final_Anlamsal_Arama.ipynb` | Tüm deneyler ve kodlar |
| `Rapor.pdf` | Akademik proje raporu |
| `README.md` | Proje açıklaması |

---

## Kullanılan Teknolojiler

- Python
- PyTorch
- Hugging Face Transformers
- Sentence-Transformers
- FAISS
- rank-bm25
- NumPy
- Pandas
- Matplotlib

---

## Modeller

| Model | Görev |
|---------|---------|
| BM25 | Klasik bilgi erişimi |
| MiniLM | Genel amaçlı cümle benzerliği |
| multilingual-E5-base | Bilgi erişim |
| multilingual-E5-large | Bilgi erişim |
| BM25 + E5 | Hibrit (RRF) |

---

## Değerlendirme Metrikleri

- Precision@k
- Recall@k
- Mean Reciprocal Rank (MRR)
- nDCG@k

---

## Çalıştırma

```bash
pip install datasets transformers sentence-transformers rank-bm25 faiss-cpu torch
```

Notebook dosyasını açıp hücreleri sırasıyla çalıştırmanız yeterlidir.

---

## Sonuç

Bu çalışma, belge getirme problemlerinde başarının yalnızca model boyutuna değil, modelin bilgi erişim görevine uygunluğuna da bağlı olduğunu göstermektedir. Genel amaçlı MiniLM modeli BM25'in gerisinde kalırken, bilgi erişim için geliştirilen multilingual-E5 modelleri belirgin biçimde daha yüksek performans sağlamıştır.

---

## Ders Bilgisi

Bu çalışma **BM5204 Doğal Dil İşleme** dersi kapsamında hazırlanmış final projesidir.
