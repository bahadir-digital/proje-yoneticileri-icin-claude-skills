---
name: project-charter-builder
description: Yeni bir projenin Project Charter (Proje Kartı) belgesini hazırlar. Hedef, kapsam, başarı kriterleri, paydaşlar, üst düzey zaman çizelgesi, varsayımlar ve kısıtları yapılandırılmış format hâlinde üretir. Kullanıcı "yeni proje başlattım", "charter yaz", "proje kartı hazırla", "sponsor toplantısına gidiyorum", "proje başlangıç dokümanı" gibi ifadeler kullandığında devreye girer.
---

# Proje Kartı (Charter) Oluşturucu

Yeni bir proje başlatılırken sponsor onayı için hazırlanan resmi başlangıç dokümanını üretir. Hem PMI/PMBOK hem de hafif Agile başlangıç formatlarını destekler.

## Ne zaman tetiklenir

- "Yeni bir proje başlattım, charter hazırlamam lazım"
- "Proje kartı yaz / proje başlangıç dokümanı"
- "Sponsor onayı için tek sayfa özet"
- "Project initiation document hazırla"

## Girdi

Aşağıdakileri sorarak topla (eksikse varsayım yap ve "doğrulayın" notuyla işaretle):

- Proje adı ve kısa açıklama
- İş gerekçesi / hangi sorunu çözüyor
- Hedef sonuç ve başarı kriterleri (ölçülebilir)
- Sponsor adı, proje yöneticisi adı, anahtar paydaşlar
- Tahmini süre ve bütçe aralığı
- Kapsam dahili / kapsam dışı maddeler
- Önemli varsayımlar ve kısıtlar
- Risk başlıkları (henüz detaylanmamış)

## Çıktı yapısı

Tek sayfa Charter formatı:

1. **Proje Bilgileri** — Ad, kod, sponsor, PM, başlangıç-bitiş tarihleri
2. **İş Gerekçesi** — 2-3 cümle, neden bu proje
3. **Hedefler ve Başarı Kriterleri** — SMART formatında, 3-5 madde
4. **Kapsam**
   - **Dahil olanlar** (in-scope)
   - **Dahil olmayanlar** (out-of-scope) — netlik için zorunlu
5. **Üst Düzey Teslimat Listesi** — 3-7 ana çıktı
6. **Kilometre Taşları** — Tablo: Milestone | Tarih | Sorumlu
7. **Bütçe Özeti** — Toplam tahmini bütçe + aralık
8. **Paydaş Haritası** — Sponsor / Yönlendirme Komitesi / Ekip / Etkilenenler
9. **Varsayımlar ve Kısıtlar** — Madde madde
10. **Üst Düzey Riskler** — En kritik 3-5 risk, kısa
11. **Onaylar** — Sponsor imza alanı

## Kurallar

- **SMART ilkesi:** Hedefler ölçülebilir olsun. "Müşteri memnuniyetini artır" yerine "NPS'i 12 puandan 25 puana çıkar".
- **Out-of-scope mutlaka var olsun.** Boş bırakılırsa "doğrulayın" notu ekle.
- **Bütçe verilmediyse** "Sponsor onayı bekleniyor" yaz, uydurma rakam koyma.
- **Risk dili "olasılık-etki" çiftiyle:** "Tedarikçi gecikmesi (O:Yüksek / E:Yüksek)".
- **Charter 2 sayfayı geçmesin.** Detay başka belgeye (PMP, Scope Statement) bırakılır.
- **Imza alanını her seferinde ekle** — sponsor onayı charter'ın varlık sebebi.

## Örnek

**Girdi:** "Yeni CRM geçişi başlıyor. 6 ay sürecek, 12 kişi çalışacak, sponsor satış direktörü."

**Çıktı:** Tek sayfa Charter — yukarıdaki 11 başlıkla, doldurulabilir alanlar ve örnek SMART hedeflerle (örn. "Q3 sonuna kadar tüm satış ekibinin yeni CRM'e geçişi tamamlanmış, eski sistemden çıkış oranı ≥%95 olacak.").
