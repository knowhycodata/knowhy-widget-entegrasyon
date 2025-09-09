1. Giriş
Merhaba,
Knowhy olarak, kurumunuzun dijital varlığını güçlendirmek ve kullanıcılarınıza anlık, akıllı ve etkileşimli bir deneyim sunmak için geliştirdiğimiz yapay zeka tabanlı chatbot hizmetine (EduAsist) hoş geldiniz.
Bu doküman, chatbot'u web sitenize entegre etme sürecinde size adım adım yol gösterecektir. Lütfen aşağıdaki adımları sırasıyla takip ediniz.

2. Entegrasyona Başlamadan Önce: Gerekli Bilgiler ve Aktivasyon
Bu adım, entegrasyonun en önemli ve ilk adımıdır.
Knowhy chatbot'un web sitenizde sorunsuz bir şekilde çalışabilmesi için, entegrasyon kodunu eklemeden önce atmanız gereken kritik bir adım bulunmaktadır. Güvenlik ve performans nedenleriyle, chatbot'un yalnızca yetkilendirilmiş domain'lerde çalışmasını sağlıyoruz. Bu nedenle, öncelikle chatbot'u kullanacağınız domain adresinin tarafımızca aktive edilmesi gerekmektedir.
Aktivasyon sürecini başlatmak için lütfen aşağıda listelenen bilgileri size gönderilen maile cevap olarak gönderin:
Domain Adresi: Chatbot'un çalışacağı tam web sitesi adresi. (Örn: www.universiteniz.edu.tr)
Web Sitesi Altyapısı: Sitenizin teknik altyapısı hakkında bilgi. (Örn: WordPress, özel geliştirilmiş PHP, Drupal, vb.) Bu bilgi, olası bir teknik sorunda size daha hızlı destek vermemize yardımcı olacaktır.
Ekibimiz, domain aktivasyonunu tamamladıktan sonra size bir onay e-postası ile geri dönüş yapacaktır.
Lütfen Knowhy ekibinden "Aktivasyon Tamamlandı" onayını almadan aşağıdaki teknik adımlara geçmeyiniz.






3. Entegrasyon Kodu
(Önemli: Bu adımı, Knowhy ekibinden domain aktivasyon onayı aldıktan sonra uygulayınız.)
Chatbot'un web sitenizde çalışabilmesi için aşağıda verilen JavaScript dosyasını sayfanıza eklemeniz zorunludur. Bu script, chatbot'un tüm fonksiyonlarını ve kullanıcı arayüzünü yükleyen çekirdek koddur.
Gerekli Script Kodu:
Bu kodu, web sitenizin <body> etiketinin kapanışından (</body>) hemen önce yerleştirmenizi öneririz.
SCRİPT KODU KNOWHY EKİBİ TARAFINDAN VERİLECEKTİR

4. Yapılandırma ve Parametreler
<knowhy-bot> etiketi, chatbot'un tüm görsel ve işlevsel özelliklerini kontrol etmenizi sağlayan parametreleri (attributes) içerir. Her bir parametre, chatbot'un farklı bir özelliğini yönetir.
Aşağıda, bu parametrelerin ne işe yaradığını ve nasıl kullanıldığını gruplandırılmış bir şekilde bulabilirsiniz.
Bu parametreler, web sitenizde görünecek olan chatbot başlatma butonunun stilini ve konumunu belirler.
Parametre
Açıklama
Örnek Değer
buton_arkaplan_rengi
Başlatma butonunun arka plan rengi.
"#b71c1c"
buton_konum
Butonun ekrandaki konumu (sol veya sag).
"sol"
buton_sag_bosluk
Butonun sağ kenara olan uzaklığı (piksel).
"24"
buton_alt_bosluk
Butonun alt kenara olan uzaklığı (piksel).
"24"
buton_boyut
Butonun genişliği ve yüksekliği (piksel).
"45"
buton_ikon_rengi
Buton içindeki ikonun rengi.
"#ffffff"
buton_ikon_src
Buton için özel bir ikon kullanılacaksa, görselin URL adresi.
[URL]
buton_ikon_boyut
buton_ikon_src kullanıldığında, ikonun boyutu (yüzde).
"65"


4.2. Pencere Davranışları ve Genel Ayarlar
Chatbot sohbet penceresinin açılma davranışlarını ve genel özelliklerini yönetir.
Parametre
Açıklama
Örnek Değer
pencere_otomatik_ac
Sayfa yüklendiğinde pencerenin otomatik açılıp açılmayacağı. true/false
"true"
pencere_otomatik_ac_gecikme
Otomatik açılacaksa, kaç saniye sonra açılacağı.
"2"
pencere_otomatik_ac_mobil
Mobil cihazlarda da otomatik açılıp açılmayacağı. true/false
"true"
pencere_yukseklik
Sohbet penceresinin maksimum yüksekliği (piksel).
"600"
pencere_genislik
Sohbet penceresinin genişliği (piksel).
"420"
pencere_arkaplan
Sohbet penceresinin genel arka plan rengi.
"#f8f8f8"
pencere_yazi_boyutu
Pencere içindeki genel metin boyutu (piksel).
"16"
yenilede_temizle
Kullanıcı sayfayı yenilediğinde sohbet geçmişinin temizlenip temizlenmeyeceği. true/false
"true"



4.3. Pencere İçerik ve Mesaj Ayarları
Pencere başlığı, hoş geldin mesajı ve diğer metin içeriklerini belirler.
Parametre
Açıklama
Örnek Değer
pencere_baslik_goster
Pencere başlığının gösterilip gösterilmeyeceği. true/false
"true"
pencere_baslik
Pencere başlığında yazacak metin.
"Dijital Öğrenci Asistanınız Sevgi"
pencere_baslik_avatar
Başlıkta görünecek avatarın URL adresi.
[URL]
pencere_baslik_avatar_boyut
Başlıktaki avatarın boyutu (piksel).
"32"
pencere_agent_mesaj_goster
Hoş geldin mesajının gösterilip gösterilmeyeceği. true/false
"true"
pencere_hosgeldin
Chatbot'un kullanıcıyı karşıladığı ilk mesaj.
"Merhaba ben..."
pencere_baslangic_istekleri
Kullanıcıya sunulacak hazır soru önerileri. JSON formatında bir dizi olmalıdır.
'["Soru 1", "Soru 2"]'
pencere_hata
Bir hata oluştuğunda gösterilecek genel hata mesajı.
"Bir hata oluştu..."
pencere_bekliyor_mesaji
Bot cevap verirken gösterilecek bekleme mesajı.
"Cevabım hazırlanıyor..."
pencere_rate_limit_mesaji
Kullanıcı çok sık mesaj gönderdiğinde gösterilecek uyarı.
"Lütfen biraz bekleyin..."
pencere_ag_hatasi_mesaji
İnternet bağlantısı koptuğunda gösterilecek mesaj.
"İnternet bağlantınızı kontrol edin..."



4.4. Başlangıç İstekleri (Hazır Sorular) Stil Ayarları
pencere_baslangic_istekleri ile sunulan hazır soru butonlarının görünümünü özelleştirir.
Parametre
Açıklama
Örnek Değer
..._wrapper_arkaplan
Hazır sorular alanının arka plan rengi.
"#fdecea"
..._buton_arkaplan
Hazır soru butonlarının arka plan rengi.
"#ffffff"
..._buton_yazi_rengi
Hazır soru butonlarının yazı rengi.
"#b71c1c"
..._buton_hover_arkaplan
Fare ile butonun üzerine gelindiğindeki arka plan rengi.
"#b71c1c"
..._buton_hover_yazi_rengi
Fare ile butonun üzerine gelindiğindeki yazı rengi.
"#ffffff"
..._buton_kenarlık_rengi
Butonların kenarlık rengi.
"#f5c6cb"
..._baslik_rengi
"Bunları sorabilirsiniz" gibi başlıkların rengi.
"#b71c1c"

(Not: Diğer pencere_baslangic_istekleri_ parametreleri de benzer şekilde butonların kenarlık, gölge, boşluk gibi detaylı stil özelliklerini ayarlar.)


4.5. Mesaj Balonları ve Giriş Alanı Ayarları
Kullanıcı ve bot mesajlarının görünümünü ve kullanıcının soru yazdığı alanı kontrol eder.
Parametre
Açıklama
Örnek Değer
bot_mesaj_arkaplan
Chatbot'un mesaj balonlarının arka plan rengi.
"#ffffff"
bot_mesaj_yazi_rengi
Chatbot'un mesajlarının yazı rengi.
"#1e1e1e"
bot_mesaj_avatar
Chatbot'un avatar URL'si.
[URL]
kullanici_mesaj_arkaplan
Kullanıcının mesaj balonlarının arka plan rengi.
"#b71c1c"
kullanici_mesaj_yazi_rengi
Kullanıcının mesajlarının yazı rengi.
"#ffffff"
input_placeholder
Mesaj yazma alanında görünen yer tutucu metin.
"Sorunuzu buraya yazın..."
input_arkaplan
Mesaj yazma alanının arka planı.
"#ffffff"
input_gonder_buton_rengi
Gönder butonunun rengi.
"#d32f2f"
input_max_karakter
Kullanıcının bir mesajda gönderebileceği maksimum karakter sayısı.
"500"
feedback_goster
Mesajlar için beğen/beğenme butonlarının gösterilip gösterilmeyeceği. true/false
"true"
feedback_rengi
Beğen/beğenme ikonlarının rengi.
"#b71c1c"









5. Tam Entegrasyon Kodu Örneği
(Önemli: Bu kodu sitenize eklemeden önce domain aktivasyon işleminin tamamlandığından ve onay e-postası aldığınızdan emin olunuz.)
Sizlere ekde bir kod bloğu göndereceğiz, bu kod, yukarıda açıklanan script çağrısını ve tüm özelleştirme parametrelerini içeren tam bir örnektir. Sizler için örnek bir tasarım yapmış bulunmaktayız. Mail ekinde sizlere iletilmiş olması gerekmektedir. Ekde bulunan dosya da ki kodu kopyalayıp doğrudan web sitenizin <body> etiketleri arasına yapıştırarak chatbot'u çalıştırabilirsiniz.
   

6. Destek
Entegrasyon sırasında herhangi bir sorunla karşılaşırsanız, ek bir özelleştirme talebiniz olursa veya aklınıza takılan herhangi bir soru için bizimle iletişime geçmekten çekinmeyin.
Teknik destek ekibimize data@knowhy.co e-posta adresinden ulaşabilirsiniz.
Size yardımcı olmaktan mutluluk duyarız.
Saygılarımızla,
Knowhy Ekibi

