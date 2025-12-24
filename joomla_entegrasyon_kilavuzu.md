# Knowhy asistan - Joomla Entegrasyon Kılavuzu

[![Joomla](https://img.shields.io/badge/Joomla-3.x%20|%204.x%20|%205.x-blue?logo=joomla)](https://www.joomla.org/)
[![License](https://img.shields.io/badge/License-Proprietary-red)](https://knowhy.co)
[![Support](https://img.shields.io/badge/Support-data%40knowhy.co-green)](mailto:data@knowhy.co)

Modern, hızlı ve güvenli **Knowhy** yapay zeka tabanlı asistan  bileşenini **Joomla** altyapılı web sitenize entegre etmeniz için hazırlanan resmi kılavuzdur.

Kılavız video Linki: https://youtu.be/8cPizlGfjy0

---

## İçindekiler

- [Giriş](#giriş)
- [1. Ön Hazırlık: Aktivasyon](#1-ön-hazırlık-aktivasyon)
- [2. Joomla Güvenlik ve Editör Ayarları](#2-joomla-güvenlik-ve-editör-ayarları)
- [3. Modül Kurulumu ve Kod Entegrasyonu](#3-modül-kurulumu-ve-kod-entegrasyonu)
  - [3.1 Modülü Oluşturma](#31-modülü-oluşturma)
  - [3.2 Ayarlar ve Kodun Eklenmesi](#32-ayarlar-ve-kodun-eklenmesi)
  - [3.3 Yayınlama](#33-yayınlama)
- [4. Yapılandırma ve Parametreler](#4-yapılandırma-ve-parametreler)
  - [4.1 Başlatma Butonu](#41-başlatma-butonu-görünüm-ve-konum)
  - [4.2 Pencere Davranışları](#42-pencere-davranışları)
  - [4.3 Pencere İçeriği](#43-pencere-içeriği)
  - [4.4 Renkler ve Stil](#44-renkler-ve-stil)
- [5. Sık Sorulan Sorular (SSS)](#5-sık-sorulan-sorular-sss)
- [6. Destek](#6-destek)

---

## Giriş

Knowhy olarak, kurumunuzun dijital varlığını güçlendirmek ve kullanıcılarınıza anlık, akıllı ve etkileşimli bir deneyim sunmak için geliştirdiğimiz knowhy asistanı hizmetine hoş geldiniz.

Bu kılavuz, **Joomla 3, 4 ve 5** sürümleriyle uyumlu entegrasyon sürecini adım adım anlatır. Joomla'nın modül yapısı kullanılarak kodun tüm sayfalara veya belirli sayfalara nasıl ekleneceği aşağıda detaylandırılmıştır.

---

## 1. Ön Hazırlık: Aktivasyon

> **⚠️ Önemli:** Entegrasyon kodunu eklemeden önce alan adınızın (domain) yetkilendirilmesi gerekir. asistan yalnızca izin verilen domainlerde çalışır.

Aktivasyonu başlatmak için Knowhy ekibine e-posta ile şu bilgileri iletin:

| Bilgi | Açıklama |
|-------|----------|
| **Alan adı (Domain)** | Örn: `www.universiteniz.edu.tr` |
| **Web sitesi altyapısı** | Joomla (Sürüm belirtmeniz faydalı olur, örn: Joomla 5) |

📧 **E-posta:** [data@knowhy.co](mailto:data@knowhy.co)

Ekibimiz aktivasyonu tamamladığında size **"Aktivasyon Tamamlandı"** onayı gönderilecektir. 

> ❌ Bu onay gelmeden teknik entegrasyon adımlarına geçmeyiniz.

---

## 2. Joomla Güvenlik ve Editör Ayarları

Joomla, varsayılan metin editörleri (TinyMCE vb.) aracılığıyla eklenen `<script>` ve `<knowhy-bot>` gibi özel etiketleri güvenlik önlemi sebebiyle otomatik olarak temizleyebilir. 

**Kodun bozulmaması için** entegrasyon sırasında editörü geçici olarak devre dışı bırakmanızı öneririz:

1. Joomla **Yönetici Paneline** giriş yapın
2. **Sistem (System)** → **Genel Yapılandırma (Global Configuration)** menüsüne gidin
3. **Site** sekmesinde **Varsayılan Düzenleyici (Default Editor)** seçeneğini bulun
4. Aşağıdaki seçeneklerden birini seçin:
   - `Editor - None`
5. **Kaydet** butonuna basın

> 💡 **Not:** Entegrasyon tamamlandıktan sonra bu ayarı eski haline getirebilirsiniz.

---

## 3. Modül Kurulumu ve Kod Entegrasyonu

asistan kodunu sitenize eklemek için **Özel Modül (Custom Module)** kullanacağız.

### 3.1 Modülü Oluşturma

1. **İçerik (Content)** → **Site Modülleri (Site Modules)** sayfasına gidin
2. Sol üstteki **+ Yeni (+ New)** butonuna tıklayın
3. Açılan listeden **"Özel" (Custom)** modülünü seçin

### 3.2 Ayarlar ve Kodun Eklenmesi

Modül düzenleme ekranında aşağıdaki ayarları yapın:

| Ayar | Değer |
|------|-------|
| **Başlık** | `Knowhy asistan` *(veya istediğiniz bir isim)* |
| **Başlığı Göster (Show Title)** | `Gizle (Hide)` |
| **Konum (Position)** | Temanızın footer bölümüne denk gelen pozisyon |

#### Tema Pozisyon Önerileri

| Tema | Önerilen Pozisyon |
|------|-------------------|
| **Cassiopeia** (Joomla 4/5) | `footer` veya `debug` |
| **Protostar** (Joomla 3) | `debug` veya `footer` |
| **Özel Tema** | Temanızın en alt pozisyonu |

#### Entegrasyon Kodu

Aşağıdaki kodu **Modül İçeriği** alanına yapıştırın:

> ⚠️ Parametreleri kurumunuza göre [Bölüm 4](#4-yapılandırma-ve-parametreler)'teki tabloya bakarak düzenleyiniz. Varsayılan kod Knowhy ekibi tarafından size verilecektir. Size verilen kodu Kopyala/Yapıştır yapmanız da yeterlidir.

```html
<script src="https://cdn.knowhy.co//bot.js"></script>

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
    pencere_baslik="Dijital Öğrenci Asistanı"
    pencere_baslik_avatar="https://cdn.example.com/logo.png"
    pencere_baslik_avatar_boyut="32"
    pencere_agent_mesaj_goster="true"
    pencere_hosgeldin="Merhaba! Size nasıl yardımcı olabilirim?"
    
    bot_mesaj_arkaplan="#ffffff"
    bot_mesaj_yazi_rengi="#1e1e1e"
    kullanici_mesaj_arkaplan="#b71c1c"
    kullanici_mesaj_yazi_rengi="#ffffff"
    
    input_placeholder="Sorunuzu buraya yazın..."
    input_arkaplan="#ffffff"
    input_gonder_buton_rengi="#d32f2f"
    feedback_goster="true"
    feedback_rengi="#b71c1c"
></knowhy-bot>
```

### 3.3 Yayınlama

1. **Menü Ataması (Menu Assignment)** sekmesine geçin
2. **Modül Ataması** bölümünde **"Tüm sayfalarda" (On all pages)** seçeneğini işaretleyin
3. **Kaydet ve Kapat** butonuna tıklayarak işlemi tamamlayın

✅ asistan artık sitenizin tüm sayfalarında görünecektir.

---

## 4. Yapılandırma ve Parametreler

Bileşenin görünümünü `<knowhy-bot>` etiketi içindeki değerleri değiştirerek özelleştirebilirsiniz.

### 4.1 Başlatma Butonu (Görünüm ve Konum)

| Parametre | Açıklama | Örnek Değer |
|-----------|----------|-------------|
| `buton_arkaplan_rengi` | Başlatma butonunun arka plan rengi | `#b71c1c` |
| `buton_konum` | Konum: `sol` veya `sag` | `sag` |
| `buton_sag_bosluk` | Sağ kenara uzaklık (px) | `24` |
| `buton_alt_bosluk` | Alt kenara uzaklık (px) | `24` |
| `buton_boyut` | Genişlik ve yükseklik (px) | `45` |
| `buton_ikon_rengi` | İkon rengi | `#ffffff` |
| `buton_ikon_src` | Özel ikon görsel URL | `https://...` |

### 4.2 Pencere Davranışları

| Parametre | Açıklama | Örnek Değer |
|-----------|----------|-------------|
| `pencere_otomatik_ac` | Sayfa yüklenince otomatik açılış | `true` / `false` |
| `pencere_otomatik_ac_gecikme` | Otomatik açılış gecikmesi (saniye) | `2` |
| `pencere_otomatik_ac_mobil` | Mobilde otomatik açılış | `true` / `false` |
| `pencere_yukseklik` | Maksimum yükseklik (px) | `600` |
| `pencere_genislik` | Genişlik (px) | `420` |
| `yenilede_temizle` | Sayfa yenilenince sohbet geçmişini temizle | `true` / `false` |

### 4.3 Pencere İçeriği

| Parametre | Açıklama | Örnek Değer |
|-----------|----------|-------------|
| `pencere_baslik_goster` | Başlık gösterilsin mi? | `true` / `false` |
| `pencere_baslik` | Başlık metni | `Öğrenci İşleri Asistanı` |
| `pencere_baslik_avatar` | Başlık avatarı URL | `https://...` |
| `pencere_baslik_avatar_boyut` | Avatar boyutu (px) | `32` |
| `pencere_hosgeldin` | Karşılama mesajı | `Merhaba ben Sevgi...` |
| `pencere_baslangic_istekleri` | Öneri sorular (JSON dizi) | `['Kayıt Tarihleri','Burslar']` |

### 4.4 Renkler ve Stil

| Parametre | Açıklama | Örnek Değer |
|-----------|----------|-------------|
| `pencere_arkaplan` | Pencere arka plan rengi | `#f8f8f8` |
| `pencere_yazi_boyutu` | Yazı boyutu (px) | `16` |
| `bot_mesaj_arkaplan` | Bot mesaj balonu arka planı | `#ffffff` |
| `bot_mesaj_yazi_rengi` | Bot mesaj yazı rengi | `#1e1e1e` |
| `kullanici_mesaj_arkaplan` | Kullanıcı mesaj balonu arka planı | `#b71c1c` |
| `kullanici_mesaj_yazi_rengi` | Kullanıcı mesaj yazı rengi | `#ffffff` |
| `input_arkaplan` | Giriş alanı arka planı | `#ffffff` |
| `input_placeholder` | Giriş alanı placeholder metni | `Sorunuzu yazın...` |
| `input_gonder_buton_rengi` | Gönder butonu rengi | `#d32f2f` |
| `feedback_goster` | Geri bildirim butonları göster | `true` / `false` |
| `feedback_rengi` | Geri bildirim (Like/Dislike) rengi | `#b71c1c` |

---

## 5. Sık Sorulan Sorular (SSS)

<details>
<summary><strong>❓ Kodları ekledim ama sitenin altında kodlar yazı olarak görünüyor</strong></summary>

**Çözüm:** Joomla editöründe kodu "Metin" modunda yapıştırmışsınız. 

1. Modül içine girip kodu silin
2. Editörü **"Kaynak Kodu" (Code)** moduna alın
3. Veya Genel Ayarlar'dan editörü `None` yapın
4. Kodu tekrar yapıştırın

</details>

<details>
<summary><strong>❓ Modülü kaydettim ama &lt;script&gt; etiketi siliniyor</strong></summary>

**Çözüm:** Joomla'nın metin filtreleri çalışıyor demektir.

Lütfen [Bölüm 2](#2-joomla-güvenlik-ve-editör-ayarları)'deki Editör Ayarları adımını uyguladığınızdan emin olun.

</details>

<details>
<summary><strong>❓ Buton görünüyor ama tıklayınca açılmıyor</strong></summary>

**Olası Sebepler:**
1. Domain yetkilendirmesi yapılmamış olabilir
2. Tarayıcı konsolunda (F12) bir hata mesajı görünüyor olabilir
3. Script dosyası yüklenememiş olabilir

**Çözüm:** Destek ekibimizle iletişime geçin.

</details>

<details>
<summary><strong>❓ asistan sadece belirli sayfalarda görünsün istiyorum</strong></summary>

**Çözüm:** Modül ayarlarında:

1. **Menü Ataması (Menu Assignment)** sekmesine gidin
2. **"Sadece seçili sayfalarda"** seçeneğini işaretleyin
3. asistan'un görünmesini istediğiniz sayfaları seçin
4. Kaydedin

</details>

<details>
<summary><strong>❓ Mobilde asistan çok büyük/küçük görünüyor</strong></summary>

**Çözüm:** Pencere boyutlarını ayarlayın:

```html
pencere_yukseklik="500"
pencere_genislik="350"
```

Mobil cihazlarda otomatik uyum sağlanır, ancak bu değerler maksimum boyutları belirler.

</details>

---

## 6. Destek

Entegrasyon sırasında aklınıza takılan tüm sorular, özelleştirme talepleri veya kurulum desteği için bize ulaşabilirsiniz:

| İletişim | Bilgi |
|----------|-------|
| 📧 **E-posta** | [data@knowhy.co](mailto:data@knowhy.co) |
| 🌐 **Web** | [knowhy.co](https://knowhy.co) |

---

<div align="center">

**Size yardımcı olmaktan mutluluk duyarız.**

Made with ❤️ by **Knowhy Ekibi**

</div>
