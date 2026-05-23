---
name: risk-assessment-facilitator
description: Risk değerlendirme oturumu kolaylaştırır. Verilen proje bağlamına göre olası riskleri kategorize eder, olasılık-etki matrisi üretir, mitigation önerileri sunar, ve risk register'a hazır kayıtlar oluşturur. Kullanıcı "risk workshop", "risk listesi çıkar", "olası riskler neler", "risk register hazırla", "risk matrisi" gibi ifadeler kullandığında devreye girer.
---

# Risk Değerlendirme Kolaylaştırıcı

Yeni proje veya faz başlangıcında, sponsor toplantısı öncesinde veya audit hazırlığında risk taraması yapar. Beyin fırtınasını yapılandırılmış çıktıya çevirir.

## Ne zaman tetiklenir

- "Bu proje için risk listesi çıkar"
- "Risk workshop'a hazırlık"
- "Olası riskler neler olabilir"
- "Risk register güncelle"
- "Risk matrisi / heat map yap"

## Girdi

- **Proje türü:** BT, inşaat, ürün lansmanı, organizasyonel değişim, M&A, vb.
- **Proje aşaması:** Initiation / Planning / Execution / Closing
- **Süre ve bütçe büyüklüğü**
- **Ekip yapısı:** İç / dış / hibrit, lokasyon dağılımı
- **Bilinen kısıtlar:** Regülasyon, tedarikçi, teknoloji, takvim
- **Geçmiş benzer projeler:** Lessons learned var mı

## Çıktı yapısı

### 1. Risk Kategorileri Tablosu

Aşağıdaki 7 kategori için 2-4 örnek risk üret:

| Kategori | Örnek Risk | Olasılık (1-5) | Etki (1-5) | Skor |
|----------|------------|----------------|------------|------|
| Teknik | ... | | | |
| Kapsam | ... | | | |
| Takvim | ... | | | |
| Bütçe | ... | | | |
| Kaynak / İK | ... | | | |
| Tedarikçi / Dış paydaş | ... | | | |
| Regülasyon / Uyum | ... | | | |

### 2. Risk Heat Map (matris görsel açıklaması)

5x5 matris, hangi risk hangi hücrede:
- Kırmızı bölge (15-25): Acil mitigation, sponsor bilgisi şart
- Sarı bölge (8-14): Aktif izleme, mitigation planı
- Yeşil bölge (1-7): Pasif izleme

### 3. Mitigation Önerileri

Her risk için 4 strateji seçeneği sun:
- **Kaçınma (Avoid):** Aktiviteyi yapma
- **Azaltma (Mitigate):** Olasılığı veya etkiyi düşür
- **Transfer:** Sigorta, sözleşme, üçüncü taraf
- **Kabul (Accept):** Bilinçli olarak kabul et, yedek plan kur

### 4. Risk Register Çıktısı (RAID log formatına hazır)

| ID | Risk | Kategori | O | E | Skor | Mitigation | Owner Önerisi |
|----|------|----------|---|---|------|------------|---------------|

## Kurallar

- **Skor = Olasılık × Etki.** 1-25 ölçek.
- **Genel ifade yerine somut risk.** "Ekip motivasyonu düşebilir" değil, "2 anahtar kişinin Q3'te ayrılma riski (exit interview sinyalleri var)".
- **Her riske mutlaka mitigation öner.** Boş bırakma.
- **Skor 15+ riskler için sponsor bilgilendirme** önerisini ekle.
- **Owner öner ama kesinleştirme.** "Önerilen sahip: Tedarikçi Yöneticisi" yaz, kullanıcı atar.
- **Bilinmeyenler için "doğrulama gerek" notu** koy — uydurma rakam yok.
- **Proje aşamasına göre filtrele:** Initiation'da teknik detay az olur, Execution'da çoktur.

## Önerilen workshop akışı (kolaylaştırıcı modu)

Kullanıcı "workshop yapacağız" derse:

1. **Açılış (5 dk):** Bağlam ve kurallar
2. **Beyin fırtınası (20 dk):** Kategori bazlı sessiz yazım
3. **Gruplama (15 dk):** Benzer riskleri birleştir
4. **Skorlama (20 dk):** Olasılık-etki, ekip oylaması
5. **Mitigation atama (20 dk):** Top 5 risk için sahip ve plan
6. **Kapanış (10 dk):** Risk register güncelleme, sonraki review tarihi

## Örnek

**Girdi:** "ERP geçiş projesi başlıyor. 9 ay, 18 kişi, ana tedarikçi SAP. Daha önce 2 başarısız ERP girişimimiz oldu."

**Çıktı:** 7 kategoride 18-25 risk, geçmiş başarısızlık verisi göz önünde — kullanıcı adopsiyonu ve değişim yönetimi kategorileri ağırlıklı, tedarikçi performansı riski yüksek skor, mitigation olarak değişim yönetimi rolü atanması önerisi.
