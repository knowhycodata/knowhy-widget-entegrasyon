# Knowhy Chatbot (EduAsist) Entegrasyon Kılavuzu

Modern, hızlı ve güvenli şekilde Knowhy yapay zeka tabanlı chatbot (EduAsist) bileşenini web sitenize entegre etmeniz için hazırlanan resmi kılavuz.

---

## İçindekiler

- [Giriş](#giriş)
- [1) Entegrasyona Başlamadan Önce: Aktivasyon](#1-entegrasyona-başlamadan-önce-aktivasyon)
- [2) Entegrasyon Kodu](#2-entegrasyon-kodu)
- [3) Yapılandırma ve Parametreler](#3-yapılandırma-ve-parametreler)
  - [3.1) Başlatma Butonu (Görünüm ve Konum)](#31-başlatma-butonu-görünüm-ve-konum)
  - [3.2) Pencere Davranışları ve Genel Ayarlar](#32-pencere-davranışları-ve-genel-ayarlar)
  - [3.3) Pencere İçeriği ve Mesaj Metinleri](#33-pencere-içeriği-ve-mesaj-metinleri)
  - [3.4) Başlangıç İstekleri (Hazır Sorular) Stili](#34-başlangıç-istekleri-hazır-sorular-stili)
  - [3.5) Mesaj Balonları ve Giriş Alanı](#35-mesaj-balonları-ve-giriş-alanı)
- [4) Tam Entegrasyon Örneği](#4-tam-entegrasyon-örneği)
- [5) Destek](#5-destek)

---

## Giriş
Merhaba,

Knowhy olarak, kurumunuzun dijital varlığını güçlendirmek ve kullanıcılarınıza anlık, akıllı ve etkileşimli bir deneyim sunmak için geliştirdiğimiz yapay zeka tabanlı chatbot hizmetine (EduAsist) hoş geldiniz. Bu kılavuz, web sitenize entegrasyon sürecini net ve adım adım anlatır.

> Önemli: Entegrasyon kodunu eklemeden önce alan adınızın (domain) yetkilendirilmesi gerekir. Aşağıdaki Aktivasyon adımını mutlaka tamamlayın.

---

## 1) Entegrasyona Başlamadan Önce: Aktivasyon

Chatbot'un yalnızca yetkilendirilmiş domain'lerde çalışması için aktivasyon zorunludur.

Aktivasyonu başlatmak için Knowhy ekibine e-posta ile şu bilgileri iletin:

- Alan adı (Domain): Örn. `www.universiteniz.edu.tr`
- Web sitesi altyapısı: Örn. WordPress, özel geliştirilmiş PHP, Drupal, vb.

Ekibimiz aktivasyonu tamamladığında size "Aktivasyon Tamamlandı" onayı gönderilecektir. Bu onay gelmeden teknik entegrasyon adımlarına geçmeyiniz.

---

## 2) Entegrasyon Kodu

Onay alındıktan sonra, sayfanıza Knowhy chatbot script'ini ekleyin. Performans ve yüklenme sırası için aşağıdaki kodu `</body>` etiketinden hemen önce yerleştirmeniz önerilir.

```html
<!-- Knowhy Chatbot (EduAsist) -->
<script src="https://cdn.example.com/knowhy/edu-asist.js" defer></script>
```

Not: Üretim ortamında kullanılacak gerçek script adresi Knowhy ekibi tarafından iletilecektir.

---

## 3) Yapılandırma ve Parametreler

Chatbot bileşeninin görünümü ve davranışını `<knowhy-bot>` etiketi üzerindeki öznitelikler (attributes) ile özelleştirirsiniz.

### 3.1) Başlatma Butonu (Görünüm ve Konum)

| Parametre              | Açıklama                                           | Örnek Değer |
|------------------------|-----------------------------------------------------|-------------|
| `buton_arkaplan_rengi` | Başlatma butonunun arka plan rengi                  | `#b71c1c`   |
| `buton_konum`          | Konum: `sol` veya `sag`                             | `sol`       |
| `buton_sag_bosluk`     | Sağ kenara uzaklık (px)                             | `24`        |
| `buton_alt_bosluk`     | Alta uzaklık (px)                                   | `24`        |
| `buton_boyut`          | Genişlik ve yükseklik (px)                          | `45`        |
| `buton_ikon_rengi`     | İkon rengi                                          | `#ffffff`   |
| `buton_ikon_src`       | Özel ikon görsel URL                                | `https://...` |
| `buton_ikon_boyut`     | Özel ikon kullanılıyorsa ikon boyutu (yüzde)        | `65`        |

### 3.2) Pencere Davranışları ve Genel Ayarlar

| Parametre                      | Açıklama                                                        | Örnek Değer |
|--------------------------------|------------------------------------------------------------------|-------------|
| `pencere_otomatik_ac`          | Sayfa yüklenince otomatik açılış (true/false)                   | `true`      |
| `pencere_otomatik_ac_gecikme`  | Otomatik açılış gecikmesi (sn)                                  | `2`         |
| `pencere_otomatik_ac_mobil`    | Mobilde otomatik açılış (true/false)                            | `true`      |
| `pencere_yukseklik`            | Maksimum yükseklik (px)                                         | `600`       |
| `pencere_genislik`             | Genişlik (px)                                                   | `420`       |
| `pencere_arkaplan`             | Arka plan rengi                                                 | `#f8f8f8`   |
| `pencere_yazi_boyutu`          | Genel metin boyutu (px)                                         | `16`        |
| `yenilede_temizle`             | Yenilemede sohbet geçmişini temizle (true/false)                | `true`      |

### 3.3) Pencere İçeriği ve Mesaj Metinleri

| Parametre                        | Açıklama                                           | Örnek Değer |
|----------------------------------|-----------------------------------------------------|-------------|
| `pencere_baslik_goster`          | Başlık gösterilsin mi? (true/false)                 | `true`      |
| `pencere_baslik`                 | Başlık metni                                        | `Dijital Öğrenci Asistanınız Sevgi` |
| `pencere_baslik_avatar`          | Başlık avatarı URL                                  | `https://...` |
| `pencere_baslik_avatar_boyut`    | Başlık avatar boyutu (px)                           | `32`        |
| `pencere_agent_mesaj_goster`     | Hoş geldin mesajı gösterilsin mi? (true/false)      | `true`      |
| `pencere_hosgeldin`              | Karşılama mesajı                                    | `Merhaba ben...` |
| `pencere_baslangic_istekleri`    | Öneri sorular (JSON dizi)                           | `['Soru 1','Soru 2']` |
| `pencere_hata`                   | Genel hata mesajı                                   | `Bir hata oluştu...` |
| `pencere_bekliyor_mesaji`        | Yanıt hazırlanırken gösterilecek mesaj              | `Cevabım hazırlanıyor...` |
| `pencere_rate_limit_mesaji`      | Çok sık mesaj uyarısı                               | `Lütfen biraz bekleyin...` |
| `pencere_ag_hatasi_mesaji`       | İnternet kesildi mesajı                             | `İnternet bağlantınızı kontrol edin...` |

### 3.4) Başlangıç İstekleri (Hazır Sorular) Stili

| Parametre                        | Açıklama                                           | Örnek Değer |
|----------------------------------|-----------------------------------------------------|-------------|
| `..._wrapper_arkaplan`           | Hazır sorular alanının arka plan rengi             | `#fdecea`   |
| `..._buton_arkaplan`             | Buton arka plan rengi                              | `#ffffff`   |
| `..._buton_yazi_rengi`           | Buton yazı rengi                                   | `#b71c1c`   |
| `..._buton_hover_arkaplan`       | Üzerine gelince arka plan                          | `#b71c1c`   |
| `..._buton_hover_yazi_rengi`     | Üzerine gelince yazı rengi                         | `#ffffff`   |
| `..._buton_kenarlık_rengi`       | Kenarlık rengi                                     | `#f5c6cb`   |
| `..._baslik_rengi`               | Bölüm başlığı rengi                                 | `#b71c1c`   |

Not: `pencere_baslangic_istekleri_` ile başlayan diğer parametreler; buton boşlukları, gölge, kenarlık ve farklı durum renkleri gibi ayrıntıları kontrol eder.

### 3.5) Mesaj Balonları ve Giriş Alanı

| Parametre                   | Açıklama                                      | Örnek Değer |
|-----------------------------|-----------------------------------------------|-------------|
| `bot_mesaj_arkaplan`        | Bot mesaj balonu arka plan                    | `#ffffff`   |
| `bot_mesaj_yazi_rengi`      | Bot mesaj yazı rengi                         | `#1e1e1e`   |
| `bot_mesaj_avatar`          | Bot avatar URL                                | `https://...` |
| `kullanici_mesaj_arkaplan`  | Kullanıcı mesaj balonu arka plan              | `#b71c1c`   |
| `kullanici_mesaj_yazi_rengi`| Kullanıcı mesaj yazı rengi                    | `#ffffff`   |
| `input_placeholder`         | Mesaj yazma alanı yer tutucu metni            | `Sorunuzu buraya yazın...` |
| `input_arkaplan`            | Mesaj yazma alanı arka planı                  | `#ffffff`   |
| `input_gonder_buton_rengi`  | Gönder butonu rengi                           | `#d32f2f`   |
| `input_max_karakter`        | Maksimum karakter sayısı                      | `500`       |
| `feedback_goster`           | Beğen/Beğenme düğmeleri (true/false)          | `true`      |
| `feedback_rengi`            | Geri bildirim ikon rengi                      | `#b71c1c`   |

---

## 4) Tam Entegrasyon Örneği

Aşağıdaki örnek; script çağrısını ve örnek öznitelikleri içeren basit bir entegrasyon iskeletidir. Gerçek değerleri kurumunuza uygun şekilde güncelleyin.

```html
<!doctype html>
<html lang="tr">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Knowhy Chatbot Entegrasyon Örneği</title>
    <!-- Renk paleti: kurum kimliğinize göre güncelleyiniz -->
    <style>
      body { font-family: system-ui, -apple-system, Segoe UI, Roboto, Arial, sans-serif; }
    </style>
  </head>
  <body>
    <!-- Sayfa içeriğiniz -->

    <!-- Knowhy Chatbot Bileşeni -->
    <knowhy-bot
      buton_arkaplan_rengi="#b71c1c"
      buton_konum="sag"
      buton_sag_bosluk="24"
      buton_alt_bosluk="24"
      buton_boyut="45"
      buton_ikon_rengi="#ffffff"
      
      pencere_otomatik_ac="true"
      pencere_otomatik_ac_gecikme="2"
      pencere_otomatik_ac_mobil="true"
      pencere_yukseklik="600"
      pencere_genislik="420"
      pencere_arkaplan="#f8f8f8"
      pencere_yazi_boyutu="16"
      yenilede_temizle="true"
      
      pencere_baslik_goster="true"
      pencere_baslik="Dijital Öğrenci Asistanınız Sevgi"
      pencere_baslik_avatar="https://cdn.example.com/avatar.png"
      pencere_baslik_avatar_boyut="32"
      pencere_agent_mesaj_goster="true"
      pencere_hosgeldin="Merhaba! Size nasıl yardımcı olabilirim?"
      pencere_baslangic_istekleri='["Bölüm koşulları", "Burs başvurusu", "Akademik takvim"]'
      pencere_hata="Bir hata oluştu, lütfen tekrar deneyin."
      pencere_bekliyor_mesaji="Cevabım hazırlanıyor..."
      pencere_rate_limit_mesaji="Lütfen biraz bekleyin..."
      pencere_ag_hatasi_mesaji="İnternet bağlantınızı kontrol edin..."
      
      bot_mesaj_arkaplan="#ffffff"
      bot_mesaj_yazi_rengi="#1e1e1e"
      bot_mesaj_avatar="https://cdn.example.com/bot-avatar.png"
      kullanici_mesaj_arkaplan="#b71c1c"
      kullanici_mesaj_yazi_rengi="#ffffff"
      input_placeholder="Sorunuzu buraya yazın..."
      input_arkaplan="#ffffff"
      input_gonder_buton_rengi="#d32f2f"
      input_max_karakter="500"
      feedback_goster="true"
      feedback_rengi="#b71c1c"
    ></knowhy-bot>

    <!-- Script en sonda, </body> öncesi -->
    <script src="https://cdn.example.com/knowhy/edu-asist.js" defer></script>
  </body>
</html>
```

> Not: Script yolunu ve URL'leri Knowhy ekibinin ilettiği üretim (prod) adresleriyle değiştiriniz.

---

## 5) Destek

Entegrasyon sırasında aklınıza takılan tüm sorular ve özelleştirme talepleri için bize ulaşabilirsiniz:

- E-posta: [data@knowhy.co](mailto:data@knowhy.co)

Size yardımcı olmaktan mutluluk duyarız.

— Knowhy Ekibi
