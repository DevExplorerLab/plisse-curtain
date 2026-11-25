# Plise Perde — Sipariş & Yönetim Sistemi (Tek Sayfa / Sunucusuz SPA)

Eski çok sayfalı **PHP + MySQL** tabanlı plise perde sipariş otomasyonunun; hiçbir sunucu veya harici veritabanı kurulumu gerektirmeden, **tek bir HTML dosyası** içerisinde çalışan modern, sekmeli (SPA) ve gömülü/kalıcı veritabanı destekli yeni sürümüdür.

---

## Öne Çıkan Özellikler

* **Tek Dosya & Sunucusuz Mimari:** XAMPP, WAMP, Apache, PHP veya MySQL kurulumuna gerek kalmadan doğrudan tarayıcıda (`index.html`) veya GitHub Pages üzerinde çalışır.
* **Sekmeli (Tab) Tek Sayfa Deneyimi:**
  * **Sipariş Oluştur:** Milimetrik en/boy girişi, minimum $1.00\text{ m}^2$ hesaplama kuralı, kasa rengi seçimi, seri/model filtreleme, **Çiftli Sistem** (Model 2 + Ekstra Sistem) desteği ve canlı SVG plise perde önizlemesi.
  * **Ürün Galerisi:** Serilere göre filtreleme, canlı arama ve tam ekran Lightbox görsel inceleme.
  * **Siparişlerim & Hesap:** Müşteri/bayi kayıt ve giriş sistemi, cari bakiye görüntüleme, profil güncelleme ve 4 aşamalı sipariş durum takibi.
  * **Yönetim Paneli (Admin):** Aktif ve teslim edilen sipariş yönetimi, sipariş aşaması güncelleme, yazdırılabilir/PDF üretim fişi, müşteri cari borç tahsilatı, model/sistem/kasa fiyat yönetimi ve Base64 galeri yükleme.
* **Gömülü ve Taşınabilir Veritabanı:**
  * Tüm veriler tarayıcı `localStorage` (`plise_perde_db_v1`) üzerinde kalıcı olarak saklanır.
  * Tek tıkla **JSON yedek** dışa/içe aktarımı ve güncel tüm verilerin içine gömülü olduğu **Taşınabilir Tek Dosya (`.html`)** indirme özelliği bulunur.
* **Web Audio API Bildirim Zili:** Harici `.mp3` dosyasına ihtiyaç duymadan sipariş oluşturulduğunda veya test edildiğinde tarayıcı içinde zil sesi üretir.

---

## Fiyat ve Alan Hesaplama Mantığı

Uygulama, özel ölçü plise perde üretim standartlarına göre hesaplama yapar:

$$\text{Ham Alan } (\text{m}^2) = \frac{\text{En (cm)} \times \text{Boy (cm)}}{10000}$$

$$\text{Hesaplanan Alan } (\text{m}^2) = \max(\text{Ham Alan}, 1.00)$$

$$\text{Satır Tutarı} = \text{Hesaplanan Alan} \times \text{Adet} \times \left(\text{Sistem} + \text{Model 1} + \text{Model 2} + \text{Ekstra Sistem}\right)$$

---

## Kurulum ve Çalıştırma

1. Bu depoyu klonlayın veya ZIP olarak indirin:
   ```bash
   git clone https://github.com/DevExplorerLab/plisse-curtain
   ```
2. Uygulama dosyasının adını `index.html` olarak ayarlayın ve herhangi bir modern tarayıcıda açın.
3. **GitHub Pages** ile yayınlamak için:
   * Depo ayarlarından **Settings → Pages** bölümüne gidin.
   * **Branch** olarak `main` ve klasör olarak `/ (root)` seçip kaydedin.

---

## Demo Giriş Bilgileri

Uygulama içindeki **Siparişlerim & Hesap** sekmesinde tek tıkla doldur/giriş butonları hazırdır:

| Rol | E-posta | Şifre |
| :--- | :--- | :--- |
| **Yönetici (Admin)** | `Admin@gmail.com` | `987654321` |
| **Bayi / Müşteri** | `admin2@gmail.com` | `1234` |
| **Bayi / Müşteri** | `deneme@gmail.com` | `1234` |

---

## Sipariş Durum Kodları

| Kod | Aşama |
| :---: | :--- |
| `1` | Sipariş Alındı |
| `2` | Hazırlanıyor / Üretime Başlandı |
| `3` | Kargoya Verildi |
| `4` | Sipariş Tamamlandı (Teslim Edildi) |

---

## Kullanılan Teknolojiler

* **HTML5 & Vanilla JavaScript (ES6+)**
* **Tailwind CSS (CDN)**
* **LocalStorage & FileReader API (Base64 / JSON / Standalone HTML Export)**
* **Web Audio API (Sipariş Bildirim Zili)**

---

## Geliştirici

**Uğur Akbaş**
