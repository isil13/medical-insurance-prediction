# Sağlık Sigortası Maliyet Tahmini (Medical Insurance Cost Prediction)

##  Genel Bakış
Bu proje, hastaların demografik ve sağlık verilerine dayanarak sağlık sigortası maliyetlerini tahmin etmektedir. Farklı makine öğrenmesi algoritmalarını karşılaştırarak; yaş, vücut kitle indeksi ve sigara içme alışkanlıkları gibi özelliklere göre sigorta masraflarını en doğru şekilde tahmin eden modeli belirlemeyi amaçlamaktadır.

##  Veri Seti
Projede `insurance.csv` veri seti kullanılmıştır. Veri seti aşağıdaki özellikleri içermektedir:
* **Sayısal Özellikler:** `age`, `bmi`, `children` 
* **Kategorik Özellikler:** `sex`, `smoker`, `region`
* **Hedef Değişken:** `charges` (Sağlık sigortası tarafından fatura edilen bireysel tıbbi maliyetler)

##  Teknolojiler ve Kütüphaneler
* **Python**
* **Pandas** 
* **Scikit-Learn** 
* **Matplotlib & Seaborn** 

##  Proje İş Akışı
1. **EDA:** Veri dağılımı incelendi ve Seaborn kullanılarak yaş, masraflar ve cinsiyet arasındaki ilişkiyi görselleştirdim. Duplicate verileri tespit edip temizledim.
2. **Data Preprocessing:** * Kategorik değişkenlere `OneHotEncoder` uyguladım.
   * Sayısal değişkenlere `ColumnTransformer` kullanılarak `StandardScaler` uyguladım.
3. **Model Eğitimi ve Hiperparametre Optimizasyonu:** Birden fazla regresyon modeli eğittim ve `GridSearchCV` kullanılarak optimize ettim.
4. **Değerlendirme:** Model performansları Ortalama Mutlak Hata (MAE), Ortalama Kare Hata (MSE) ve R² Skoru kullanılarak ölçtüm.

##  Kullanılan Modeller
* **Decision Tree Regressor:** Hiperparametreleri (criterion, splitter, max_depth, max_features) GridSearchCV kullanılarak ayarlandım. Çıktılar arasında en iyi karar ağacının görselleştirilmiş bir grafiği de bulunmaktadır.
* **Linear Regression:** baseline model olarak kullanılıp diğerleriyle kıyaslandım.
* **Destek Vektör Regresyonu (SVR):** Optimum karar sınırını bulmak için hiperparametreleri (kernel, gamma, C) GridSearchCV ile detaylı bir şekilde test ettim.

##  Sonuçlar
Kodun son bölümü; üç modelin "En İyi Skorunu", "Hiperparametre Optimizasyonu" durumunu ve "En İyi Parametrelerini" karşılaştıran bir Pandas DataFrame oluşturdum. Bu tablo, veri seti üzerinde en yüksek performansı gösteren algoritmayı kolayca belirleyebilmek için en yüksek skordan en düşüğe doğru dinamik olarak sıralanır.


