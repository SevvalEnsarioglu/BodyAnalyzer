# BodyAnalyzer - Spor Becerisi Sınıflandırma Uygulaması
BodyAnalyzer, kişilerin vücut ölçüleri ve sporla ilgili bazı fiziksel verilerini kullanarak onların spor yapma becerilerini tahmin eden bir makine öğrenmesi projesidir. Bu tahminler, "A", "B", "C" ve "D" gibi kategorilere ayrılarak yapılır. Amaç bireyin fiziksel verilerine göre spor yapma becerilerini sınıflandırmak ve bu sayede ona uygun spor önerilerinde bulunmaktır.

📚 Kullanılan Kütüphaneler Hakkında
BodyAnalyzer projesinde verilerle çalışmak ve analiz yapmak için birçok farklı kütüphane kullanıldı. Pandas ve NumPy; verileri tablo gibi düzenli bir şekilde okumamıza, işlemler yapmamıza ve analiz etmemize yardımcı oldu. Görselleştirme işlemlerinde Matplotlib ve Seaborn sayesinde verilerin grafiklerini çizerek hangi alanda nasıl bir dağılım olduğunu kolayca görebildik. Keşifsel veri analizi, veri ön işleme ve modelleme sürecinde ise scikit-learn (sklearn) kütüphanesi büyük rol oynadı; bu kütüphane ile hem verileri eğitim için hazırladık hem de birçok farklı yöntemle modeller oluşturduk. Özellikle karar ağaçları ve toplu modelleme yöntemleri için RandomForestClassifier, model başarılarını artırmak için VotingClassifier, parametre aramaları için RandomizedSearchCV kullandık. Ayrıca gelişmiş ve hızlı çalışan bir modelleme aracı olan LightGBM sayesinde daha yüksek doğruluk oranları elde ettik. Bazı durumlarda daha sade bir başlangıç modeli oluşturmak için LogisticRegression yöntemini de kullandık. Tüm bu araçlar veriden doğru ve anlamlı sonuçlar çıkarabilmemizi sağladı.

📊 Neler Yapıldı?
1. Keşifsel Veri Analizi
İlk adımda elimizdeki verileri tanıdık. Boy, kilo, kuvvet gibi ölçülerin nasıl dağıldığını inceledik. Bazı veriler normal şekilde dağılırken bazıları belli taraflara kaymıştı veya birden fazla grubun birleşimi gibiydi. İlaveten hangi verilerin birbirini ne şekilde etkilediği, ne kadar anlam ifade ettiği gibi analiz ve incelemelerde bulunduk. Bu analiz bize veriyi daha iyi tanımamızı sağladı.

2. Veri Temizleme ve Hazırlık
Verilerde eksikler, uç değerler ve mantıksız bilgiler vardı. Bunları belirledik ve uygun şekilde düzelttik ya da çıkardık. Bu adımda amaç modeli yanıltacak hataları ortadan kaldırmaktı.

3. Ön Modelleme (Hazırlık)
Veri setimizi eğitime hazırlarken bazı ön denemeler yaptık. Bu sayede hangi tür yöntemlerin daha başarılı olabileceğini öngörmeye çalıştık.

4. Model Denemeleri
Birçok farklı yöntem denedik:

Lojistik Regresyon: Basit ama etkili bir yaklaşım. Doğruluk oranı yaklaşık %61.

Rastgele Orman (Random Forest): Karar ağaçlarını birleştirerek çalışan bir sistem. Güçlü sonuçlar verdi. Doğruluk oranı yaklaşık %72.

LightGBM: Daha hafif ve hızlı çalışan bir yöntem. Doğruluk oranı: %75.6

Oy Çokluğu (Voting Classifier): Tüm modellerin ortak kararına göre sonuç veren bir sistem. Böylece daha dengeli ve güvenilir sonuçlar elde ettik. Doğruluk oranı yaklaşık %74.

Model Ayarı (RandomizedSearchCV): En iyi sonuçları almak için modellerin ayarlarını otomatik olarak taradık. Doğruluk oranı yaklaşık %75.

✅ Sonuç
BodyAnalyzer sayesinde elimizdeki verileri kullanarak kişilerin spor yapma potansiyellerini sınıflandırabiliyoruz. Bu uygulamamız hem bireylere hem de spor eğitmenlerine rehberlik edebilecek nitelikte bir yardımcı araç olabilir.
