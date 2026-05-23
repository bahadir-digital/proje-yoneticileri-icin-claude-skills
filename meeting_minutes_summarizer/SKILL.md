---
name: meeting-minutes-summarizer
description: Toplantı ses kaydı transkripti, dağınık notlar, chat dökümü veya yöneticinin kafasındaki bilgiyi yapılandırılmış toplantı özetine çevirir. Konular, kararlar, aksiyon maddeleri (sorumlu + tarih), açık kalan sorular, sonraki adım bölümlerini ayırır. Kullanıcı "toplantı notu özetle", "minute yaz", "meeting recap", "transcripti özetle", "aksiyon maddeleri çıkar" gibi ifadeler kullandığında devreye girer.
---

# Toplantı Notu Özetleyici

Dağınık girdiyi (transkript, chat dökümü, el notu) yapılandırılmış toplantı özetine çevirir. Hedef: katılımcının 30 saniyede okuyup kararını ve aksiyonunu hatırlayabileceği belge.

## Ne zaman tetiklenir

- "Toplantı notlarını özetle"
- "Bu transkripti minute formatına çevir"
- "Meeting recap yaz"
- "Aksiyon maddelerini çıkar"
- "Stand-up notu özetle"

## Girdi

- Transkript / notlar / chat dökümü (dosya, paste, yapıştır)
- **Toplantı adı / amacı**
- **Tarih ve süre**
- **Katılımcılar** (isim listesi)
- **Hedef alıcı:** Sadece katılımcılar / tüm ekip / sponsor

## Çıktı yapısı

```
TOPLANTI ÖZETİ
Toplantı: <Ad>
Tarih: <Tarih> | Süre: <X dk>
Katılımcılar: <isim, isim, isim>
Toplantıyı düzenleyen: <isim>

─────────────────────────────────

TEK CÜMLELİK ÖZET
<Bu toplantıda ne karara varıldı / ne konuşuldu>

GÜNDEM MADDELERİ VE KONUŞULANLAR
1. <Konu başlığı>
   - Konuşulan: ...
   - Sonuç: ...

2. <Konu başlığı>
   - Konuşulan: ...
   - Sonuç: ...

KARARLAR
• <Karar> — Karar veren: <isim>
• ...

AKSİYON MADDELERİ
| # | Aksiyon | Sorumlu | Son Tarih | Statü |
|---|---------|---------|-----------|-------|
| 1 | ... | ... | ... | Açık |
| 2 | ... | ... | ... | Açık |

AÇIK KALAN KONULAR (Parking Lot)
• <Karara bağlanmayan, sonraki toplantıya kalan>

SONRAKI ADIM
<Bir sonraki toplantı / milestone / iletişim>
```

## Kurallar

- **Tek cümlelik özet zorunlu.** En üstte, kalın. Yöneticinin tek cümle okuyacağını varsay.
- **Aksiyon tablosu boş geçilmez.** Yoksa "Bu toplantıda aksiyon çıkmadı" yaz.
- **Her aksiyonda sorumlu + tarih şart.** "Ekip" değil, "Ahmet K." Boşsa "Atanmamış — sonraki toplantıda netleşecek".
- **Karar ile aksiyon ayrı şeyler.** Karar = "Şunu yapacağız", Aksiyon = "Kim, ne zaman yapacak".
- **Görüş bildirme.** Kişi A şunu dedi, kişi B şuna itiraz etti formatından kaçın — kararlar ve sonuçlar yazılır.
- **Konuşma şehir efsanesi yok.** Transkriptte olmayan şey özette olmaz.
- **Hassas / kişiselleştirilmiş ifadeleri filtrele.** "X kişisini eleştirdi" gibi notlar resmi minute'a girmez.
- **Tartışmalı konuyu "iki tarafın görüşü"** olarak özetle, hakemlik yapma.

## Toplantı türüne göre vurgu

- **Stand-up:** Yaptıklarım / yapacaklarım / engelim — 3 sütun
- **Statü:** RAG durumu + aksiyon listesi öne çıkar
- **Karar toplantısı:** Kararlar bölümü en üstte, alternatifleri kısaca özet
- **Brainstorm:** Fikirler kategorize edilir, oylama varsa sonuç eklenir
- **Sponsor / yönlendirme komitesi:** Karar maddeleri ve eskalasyon konuları öne

## Örnek

**Girdi:** 40 dakikalık CRM sprint review transkripti, 8 katılımcı, demo + retrospektif konuları karışık.

**Çıktı:**
- Tek cümle özet: "Sprint 12 tamamlandı, 4/5 story kabul edildi, 1 story bug nedeniyle Sprint 13'e devrediliyor."
- Gündem 2 ana başlık (Demo, Retro)
- 6 aksiyon maddesi, hepsi sorumlu + tarihli
- Açık konu: "Yeni reporting modülü için sponsor onayı bekleniyor"
- Sonraki adım: 22 Mayıs Sprint 13 planlama
