---
name: stakeholder-comms-drafter
description: Sponsor, müşteri, üst yönetim veya ekip için iletişim mesajları (e-posta, Slack/Teams duyurusu, kötü haber bildirimi, kazanım duyurusu, eskalasyon yazısı) hazırlar. Her durum için doğru ton ve yapıyı seçer. Kullanıcı "sponsora mail yaz", "müşteriye gecikme bildirimi", "ekibe duyuru yap", "eskalasyon yazısı", "kötü haber nasıl iletilir" gibi ifadeler kullandığında devreye girer.
---

# Paydaş İletişimi Hazırlayıcı

Proje yöneticisinin günde 4-5 kez yazdığı paydaş mesajlarını hazırlar. Her senaryo için doğru iskelet, ton ve uzunlukta üretir.

## Ne zaman tetiklenir

- "Sponsor'a mail yazıyorum"
- "Müşteriye gecikme bildirimi"
- "Ekibe duyuru / kick-off davet"
- "Eskalasyon yazısı yaz"
- "Kötü haber nasıl yumuşatılır"
- "Slack/Teams duyurusu"

## Girdi

- **Alıcı:** Sponsor / Müşteri / Üst yönetim / Ekip / Tedarikçi
- **Senaryo:**
  - Gecikme bildirimi
  - Kapsam değişikliği bildirimi
  - Kazanım / milestone duyurusu
  - Eskalasyon (sponsor'a sorunu büyütme)
  - Kick-off davet
  - Karar isteme
  - Risk bildirimi
- **Kanal:** E-posta / Slack-Teams / Toplantı sonrası özet
- **Ana mesaj:** Bir cümlede ne demek istiyoruz
- **Beklenen aksiyon:** Alıcıdan ne istiyoruz

## Çıktı yapısı

### E-posta için

```
Konu: [Proje Adı] — <Net konu, eylem fiili ile>

Merhaba <Ad>,

Özet (2 cümle):
<En önemli bilgi en başta — bottom line up front>

Detay:
<Bağlam, neden, nasıl — kısa madde işareti veya 2-3 paragraf>

İstenen aksiyon / sonraki adım:
<Net beklenti + tarih>

<Selamlama>
<İsim>
```

### Slack / Teams için

- Maksimum 4 satır
- İlk satır: emoji + tek cümle özet
- 2-3 satır detay
- Son satır: link veya aksiyon

## Senaryolara göre özel kurallar

**Gecikme bildirimi:**
- Sebep + yeni tarih + alınan aksiyon + güvence
- "Üzgünüm" yerine "Şunu yaptık, şu tarihte teslim edeceğiz" odağı

**Kötü haber:**
- Önce olgu (ne oldu), sonra etki (ne anlama geliyor), sonra plan (ne yapıyoruz)
- Pasif çatı kullanma ("kararlaştırıldı" yerine "sponsor X'e karar verdi")

**Eskalasyon:**
- "Sponsor'a şikayet etme" tonu değil, "karar gerekiyor" tonu
- 3 unsur: durum + denenenler + sponsor'dan beklenen karar
- Maksimum 1 sayfa

**Kazanım duyurusu:**
- Kısa, somut, kimi takdir ettiğini söyle
- "Harika iş" gibi şişirme yok, "Şu modülü hedefin 3 gün öncesinde teslim ettiler" gibi olgu

## Genel kurallar

- **BLUF — Bottom Line Up Front.** İlk cümlede ne istediğin / ne söylediğin belli olsun.
- **Süslü açılış yok.** "Umarım iyisinizdir" gibi kalıplar kısıtlı kullanılır.
- **Pasif çatıdan kaç.** "Yapıldı" yerine "Ekip yaptı".
- **Tarih yazılı olsun.** "Yakında" değil, "26 Mayıs Pazartesi'ye kadar".
- **Beklenen aksiyon mutlaka.** Alıcı ne yapacağını bilmiyorsa mesaj yarım kaldı.

## Örnek

**Girdi:** "Sponsor'a tedarikçi entegrasyon gecikmesini bildireceğim. 2 hafta sürüyor. Yedek plan hazır."

**Çıktı:** E-posta:
- Konu: "CRM Geçişi — Entegrasyon Gecikmesi ve Aksiyon Planı"
- Özet: 2 hafta gecikme + yedek tedarikçi devrede + canlıya geçiş tarihi korunuyor
- Detay: nedeni, riski, alınan aksiyon
- Beklenti: "Bu kararı onayınıza sunuyorum / bilgilendirme amaçlı"
