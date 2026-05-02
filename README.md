# 🚀 Qode: AI-Powered Coding Quiz

Qode, yazılım geliştiricilerin kodlama becerilerini test etmeleri ve mülakat pratikleri yapmaları için tasarlanmış, **Google Gemini AI** destekli dinamik bir quiz uygulamasıdır.

## 🌟 Temel Özellikler

* **Yapay Zeka Destekli İçerik:** Google Gemini (`gemini-2.5-flash`) API'sini kullanarak gerçek zamanlı, konuya özel ve zorluk derecesi ayarlanabilir kodlama soruları üretir.
* **Çoklu Dil Desteği:** Python, Dart, C, C++, JavaScript, Java ve C# dilleri için özelleştirilmiş soru setleri oluşturulabilir.
* **Oyunlaştırma (Gamification):** Kullanıcılar, soruları doğru yanıtladıkça deneyim puanı (XP) kazanır. Bu puanlar oturum boyunca `UserSession` sınıfı ile yönetilir ve AppBar üzerinden takip edilir.
* **Görsel Geri Bildirim:** Kullanıcı etkileşimlerinde anlık yeşil (doğru) ve kırmızı (yanlış) renk kodları ve ikonlarla zenginleştirilmiş UI deneyimi.

## 🏗 Teknik Mimari

* **UI/UX:** Flutter framework ile geliştirilmiştir. Modern ve koyu (Dark Theme) yapısı, `Material3` standartları ile optimize edilmiştir.
* **Veri Akışı:** `LanguageSelectionScreen` (Seçim) → `TopicSelectionScreen` (Konu) → `GameScreenAI` (Oyun).
* **State Management:** Uygulama içi durumlar (skor, soru döngüsü) `setState` ve `UserSession` ile yönetilir.

## 🛡 Hata Yönetimi ve Dayanıklılık

Uygulamanın kararlılığını sağlamak için aşağıdaki mekanizmalar entegre edilmiştir:

* **Bağlantı Hatası Yönetimi:** `AIService` içerisindeki `try-catch` blokları, API bağlantı sorunlarını ve boş yanıtları yakalayarak uygulamanın kilitlenmesini engeller.
* **Mounted Kontrolü:** `GameScreenAI` içerisindeki asenkron işlemlerin ardından widget ağacının hayatta olup olmadığı `if (mounted)` ifadesiyle denetlenir. Bu, arka plan işlemlerinden kaynaklı çökme risklerini ortadan kaldırır.
* **Güvenli Sıfırlama:** "Set Tamamlandı" diyalog kutusu, `setState` çağrısı ile `score` ve `questions` listesini güvenli bir şekilde sıfırlayarak oyun döngüsünün hatasız devam etmesini sağlar.


## 📸 Ekran Görüntüleri

<img width="339" height="599" alt="image" src="https://github.com/user-attachments/assets/e0832cc1-9852-4035-9ed8-b76f19ee8401" />
<img width="337" height="599" alt="image" src="https://github.com/user-attachments/assets/52c3985d-0265-44f6-b660-dbe5ac153df7" />
<img width="337" height="597" alt="image" src="https://github.com/user-attachments/assets/76bf3687-0fea-4c78-b003-328c59452c9b" />
<img width="340" height="598" alt="image" src="https://github.com/user-attachments/assets/d690d3d2-d87c-49a5-91f3-a669bcd38cc7" />
<img width="337" height="597" alt="image" src="https://github.com/user-attachments/assets/b56ad348-57ec-405c-a085-156ad5197dcf" />
<img width="338" height="599" alt="image" src="https://github.com/user-attachments/assets/95e988b9-f9fb-446b-afba-e07928583296" />

---
*Geliştirici: [Elif Nur](https://github.com/ElifNur06)*
