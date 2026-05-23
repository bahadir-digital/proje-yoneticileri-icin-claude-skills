---
name: status-report-writer
description: Haftalık veya aylık proje statü raporu hazırlar. Trafik ışığı (kırmızı/sarı/yeşil) formatında özet, ilerleme, sapma, sonraki hafta planı ve risk güncellemesi içerir. Kullanıcı "haftalık rapor yaz", "statü raporu hazırla", "sponsora gönderecek rapor", "weekly update", "RAG raporu" gibi ifadeler kullandığında devreye girer.
---

# Statü Raporu Yazıcı

Sponsor ve yönlendirme komitesine giden periyodik statü raporunu üretir. Kısa, eylem odaklı, "yöneticinin 2 dakikada okuyup karar vereceği" formatta.

## Ne zaman tetiklenir

- "Bu haftaki statü raporunu yaz"
- "Sponsor toplantısı için tek sayfa özet"
- "Aylık project review hazırlığı"
- "RAG raporu / traffic light update"
- "Weekly status / weekly update"

## Girdi

Aşağıdakileri topla:

- **Rapor dönemi:** (örn. 19-25 Mayıs 2026)
- **Proje adı**
- **Genel statü:** Yeşil / Sarı / Kırmızı (PM değerlendirmesi)
- **Bu dönem yapılanlar:** 3-5 madde
- **Sonraki dönem planı:** 3-5 madde
- **Açık riskler ve issue'lar:** RAID log'tan en kritik 2-3 tanesi
- **Karar bekleyen konular:** Sponsor'dan beklenen aksiyon var mı
- **Bütçe ve takvim sapması:** % cinsinden veya gün cinsinden
- **Ekip morali / kapasite notu:** (isteğe bağlı)

## Çıktı yapısı

```
PROJE STATÜ RAPORU
Proje: <ad> | Dönem: <tarih aralığı> | PM: <ad>

────────────────────────────────────────
GENEL STATÜ: 🟢 YEŞİL / 🟡 SARI / 🔴 KIRMIZI
────────────────────────────────────────

ÖZET (3 cümle max)
<projenin bu hafta nerede olduğu, kritik mesaj>

TAKVIM    🟢/🟡/🔴   Sapma: <X> gün
BÜTÇE     🟢/🟡/🔴   Sapma: %<X>
KAPSAM    🟢/🟡/🔴
KALİTE    🟢/🟡/🔴

BU DÖNEM TAMAMLANANLAR
• ...
• ...
• ...

SONRAKİ DÖNEM PLANI
• ...
• ...
• ...

KRİTİK RİSKLER / İSSUE'LAR
• [R-007] ... (Owner: ..., Skor: ...)
• [I-012] ...

KARAR BEKLEYENLER
• <Sponsor'dan beklenen 1-2 aksiyon — yoksa "Yok">

EK NOTLAR
<isteğe bağlı: ekip, kapasite, dış faktör>
```

## Kurallar

- **Yeşil/Sarı/Kırmızı kriterleri net olsun:**
  - Yeşil: Plan dahilinde, müdahale gerekmiyor
  - Sarı: Sapma var ama PM tarafından yönetilebilir
  - Kırmızı: Sponsor müdahalesi veya kapsam/bütçe/takvim değişikliği gerekiyor
- **"Yeşil" rapor da risksiz değil.** Açık riskler her durumda yazılır.
- **Bütçe ve takvim sapmasını sayıyla ver,** "biraz geride" yazma.
- **"Kapsam yeşil ama %20 değişiklik yapıldı" çelişkisi olmasın** — değişiklikler Sarı'ya çeker.
- **Cümleler kısa olsun.** Sponsor 2 dakikada okur.
- **"Çalışılıyor", "incelendi" gibi muğlak fiiller yok.** "Tamamlandı / başlatıldı / onaya gönderildi" gibi net fiiller.
- **Karar bekleyen yoksa boş bırakma**, "Yok" yaz — sponsor'a netlik.

## Örnek

**Girdi:** "CRM Geçişi projesi. Bu hafta UAT başladı, 12 kullanıcı eğitildi. Tedarikçi entegrasyonunda 1 hafta gecikme var, kapsam değişmedi. Bütçe planda. Sonraki hafta 2. dalga eğitim."

**Çıktı:** 1 sayfa rapor — Sarı statü (entegrasyon gecikmesi nedeniyle), takvim sapması "+7 gün", net aksiyon listesi, sponsor'dan karar beklenen konu yoksa "Yok" yazılır.
