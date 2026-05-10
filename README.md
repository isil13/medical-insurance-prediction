# Sağlık Sigortası Maliyet Tahmini (Medical Insurance Cost Prediction)

## 📌 Genel Bakış
Bu proje, hastaların demografik ve sağlık verilerine dayanarak sağlık sigortası maliyetlerini tahmin etmektedir. Farklı makine öğrenmesi algoritmalarını karşılaştırarak; yaş, vücut kitle indeksi (VKİ) ve sigara içme alışkanlıkları gibi özelliklere göre sigorta masraflarını en doğru şekilde tahmin eden modeli belirlemeyi amaçlamaktadır.

## 📊 Veri Seti
Projede `insurance.csv` veri seti kullanılmıştır. Veri seti aşağıdaki özellikleri içermektedir:
* **Sayısal Özellikler:** `age` (yaş), `bmi` (VKİ), `children` (çocuk sayısı)
* **Kategorik Özellikler:** `sex` (cinsiyet), `smoker` (sigara kullanımı), `region` (bölge)
* **Hedef Değişken:** `charges` (Sağlık sigortası tarafından fatura edilen bireysel tıbbi maliyetler)

## 🛠️ Teknolojiler ve Kütüphaneler
* **Python**
* **Pandas** (Veri manipülasyonu)
* **Scikit-Learn** (Makine öğrenmesi, veri ön işleme, değerlendirme)
* **Matplotlib & Seaborn** (Veri görselleştirme)

## 🚀 Proje İş Akışı
1. **Keşifçi Veri Analizi (EDA):** Veri dağılımı incelendi ve Seaborn kullanılarak yaş, masraflar ve cinsiyet arasındaki ilişki görselleştirildi. Yinelenen (duplicate) veriler tespit edilip temizlendi.
2. **Veri Ön İşleme (Data Preprocessing):** * Kategorik değişkenlere `OneHotEncoder` uygulandı.
   * Sayısal değişkenlere `ColumnTransformer` kullanılarak `StandardScaler` uygulandı.
3. **Model Eğitimi ve Hiperparametre Optimizasyonu:** Birden fazla regresyon modeli eğitildi ve `GridSearchCV` kullanılarak optimize edildi.
4. **Değerlendirme:** Model performansları Ortalama Mutlak Hata (MAE), Ortalama Kare Hata (MSE) ve R² Skoru kullanılarak ölçüldü.

## 🤖 Kullanılan Modeller
* **Karar Ağacı Regresyonu (Decision Tree Regressor):** Hiperparametreler (criterion, splitter, max_depth, max_features) GridSearchCV kullanılarak ayarlandı. Çıktılar arasında en iyi karar ağacının görselleştirilmiş bir grafiği de bulunmaktadır.
* **Doğrusal Regresyon (Linear Regression):** Temel (baseline) model olarak kullanılıp diğerleriyle kıyaslandı.
* **Destek Vektör Regresyonu (SVR):** Optimum karar sınırını bulmak için hiperparametreler (kernel, gamma, C) GridSearchCV ile detaylı bir şekilde test edildi.

## 📈 Sonuçlar
Kodun son bölümü; üç modelin "En İyi Skorunu", "Hiperparametre Optimizasyonu" durumunu ve "En İyi Parametrelerini" karşılaştıran bir Pandas DataFrame (tablo) oluşturur. Bu tablo, veri seti üzerinde en yüksek performansı gösteren algoritmayı kolayca belirleyebilmek için en yüksek skordan en düşüğe doğru dinamik olarak sıralanır.

## 💻 Nasıl Çalıştırılır
1. Bu repoyu bilgisayarına klonla:
   ```bash
   git clone [https://github.com/isil13/medical-insurance-prediction.git](https://github.com/isil13/medical-insurance-prediction.git)
