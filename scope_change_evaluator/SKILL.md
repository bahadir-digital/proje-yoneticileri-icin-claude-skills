---
name: scope-change-evaluator
description: Gelen change request'i (kapsam değişikliği talebi) değerlendirir. Etki analizi, kaynak ihtiyacı, takvim ve bütçe etkisi, alternatif seçenekler ve sponsor onay tavsiyesi üretir. CCB (Change Control Board) sunumu için hazır format çıkarır. Kullanıcı "change request geldi", "kapsam değişikliği talebi", "CR değerlendir", "scope creep", "CCB hazırlığı" gibi ifadeler kullandığında devreye girer.
---

# Kapsam Değişikliği Değerlendirici

Müşteri, sponsor veya iç paydaştan gelen kapsam değişikliği taleplerini yapılandırılmış formatta değerlendirir. PM'in "duygusal olarak" değil, veriyle karar vermesini sağlar.

## Ne zaman tetiklenir

- "Müşteri yeni özellik istiyor, etkisi ne"
- "CR geldi, değerlendireceğim"
- "Change request analizi"
- "Sponsor'a sunum için kapsam değişikliği"
- "Bu istek scope creep mi"

## Girdi

- **Talep eden:** Müşteri / sponsor / iç paydaş / kullanıcı
- **Talep:** Ne istiyor — orijinal cümle hâliyle
- **İş gerekçesi:** Neden istiyor (varsa)
- **Mevcut faz:** Initiation / Planning / Execution / UAT / Closing
- **Kalan süre ve bütçe:**
- **Etkilenecek modül / iş paketi**

## Çıktı yapısı

```
CHANGE REQUEST DEĞERLENDİRMESİ
CR-ID: <CR-XXX>
Talep eden: <isim/rol>
Tarih: <bugün>
Değerlendiren PM: <isim>

────────────────────────────────────

1. TALEP ÖZETİ
<Tek paragraf — ne istendiği>

2. İŞ GEREKÇESİ (varsa)
<Talep edenin iş nedeni>

3. ETKİ ANALİZİ

   Kapsam:
   - Yeni teslimat: <evet/hayır>
   - Etkilenen mevcut teslimatlar: <liste>

   Takvim:
   - Tahmini ek süre: <gün>
   - Critical path etkisi: <evet/hayır>
   - Yeni teslim tarihi: <tarih>

   Bütçe:
   - Tahmini ek maliyet: <aralık>
   - İç kaynak / dış kaynak dağılımı: <oran>

   Kaynak:
   - İhtiyaç duyulan ekip / beceri
   - Mevcut ekipten çekilecek kapasite

   Risk:
   - Eklenen yeni riskler
   - Mevcut risklerin değişimi

   Kalite:
   - Test kapsamı değişimi
   - Teknik borç etkisi

4. ALTERNATİFLER

   Seçenek A — Talebi kabul et, kapsam genişlet
     Etki: ...
   Seçenek B — Sonraki faza/release'e ertele
     Etki: ...
   Seçenek C — Reddet, mevcut kapsamla kal
     Etki: ...
   Seçenek D — Kısmen kabul, hibrit çözüm
     Etki: ...

5. PM TAVSİYESİ
<Hangi seçeneği öneriyorsun, neden>

6. SPONSOR'DAN BEKLENEN KARAR
<Net cümle: "Seçenek X için onayınızı rica ederim" veya
"Şu tarihe kadar karar vermenizi rica ederim">

7. ONAYLAR
- Talep eden: __________
- PM: __________
- Sponsor: __________
```

## Kurallar

- **Duygu değil, veri.** "Bu çok zor olur" yerine "Bu +8 gün ve 2 ek geliştirici gerektirir".
- **Maliyet aralık olarak ver.** Tek nokta tahmin yapma, ±%20 aralık koy.
- **En az 3 alternatif sun.** "Ya kabul ya red" sunumu kötü PM işidir.
- **PM tavsiyesi mutlaka.** Sponsor'a "siz karar verin" demek olmaz, profesyonel görüş bildir.
- **"Scope creep" yaftası yapıştırma.** Talep edenin gerekçesi olabilir; analizle göster, terim kullanma.
- **Critical path etkisi** her zaman değerlendirilmeli, kritik aktiviteleri etkiliyorsa Sarı/Kırmızı.
- **Onay süreci faza göre değişir:** Execution'da CCB onayı çoğu kez gerekir, Initiation'da PM kararı yeterli olabilir.

## Talebin "ne kadar büyük" olduğunu netleştirme

Küçük (PM kararıyla kabul):
- < 5 saat efor, takvim etkisi yok, bütçe etkisi <%2

Orta (sponsor bilgisi yeterli):
- < 1 hafta efor, takvim etkisi <3 gün, bütçe etkisi <%5

Büyük (sponsor onayı şart, CCB):
- ≥ 1 hafta efor veya kritik path etkisi veya bütçe >%5

## Örnek

**Girdi:** "Müşteri canlıya geçiş öncesi 'mobil app de olsun' diyor. UAT bitti, 2 hafta sonra go-live."

**Çıktı:** Büyük kategori CR — alternatif olarak A: 6 hafta gecikme + 250-350K ek bütçe, B: faz-2'ye al, C: hibrit (responsive web yeterli mi sorusu). PM tavsiyesi: B (faz-2'ye al) — go-live gecikmenin maliyeti müşteri ilişkisi için yüksek. Sponsor'dan beklenen: 28 Mayıs'a kadar karar.
