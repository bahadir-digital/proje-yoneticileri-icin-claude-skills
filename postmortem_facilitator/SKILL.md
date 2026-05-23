---
name: postmortem-facilitator
description: Proje kapanışında lessons learned oturumu, sprint sonu retrospektifi veya incident sonrası postmortem kolaylaştırır. "Blameless" (suçlamadan) yaklaşımla kök neden analizi, ne işe yaradı / ne yaramadı / ne öğrendik formatı, aksiyonlu öğrenim listesi üretir. Kullanıcı "retro yapacağız", "lessons learned", "proje kapanışı", "postmortem", "incident review" gibi ifadeler kullandığında devreye girer.
---

# Postmortem / Retrospektif Kolaylaştırıcı

Sprint, faz veya proje sonunda gerçekleşen retro/postmortem oturumunun gündemini, kolaylaştırıcı sorularını ve çıktı formatını üretir. Amaç: suçlama değil, sistematik öğrenme.

## Ne zaman tetiklenir

- "Sprint retro hazırlığı"
- "Proje kapanış toplantısı / lessons learned"
- "Incident postmortem"
- "Ekip retro template"
- "Geriye dönük değerlendirme"

## Girdi

- **Oturum türü:** Sprint retro / Faz sonu / Proje kapanışı / Incident postmortem
- **Kapsanan dönem:** Hangi sprint veya tarih aralığı
- **Katılımcılar:** Sayı ve roller
- **Süre:** 30 dk / 1 saat / 2 saat
- **Önceki retro'dan kalan aksiyonlar:** Varsa
- **Olağandışı bir olay var mı:** Major incident, başarısız release, müşteri eskalasyonu

## Çıktı yapısı

```
RETROSPEKTİF / POSTMORTEM
Tür: <retro türü>
Tarih: <tarih> | Süre: <X> | Katılımcı: <sayı>
Kolaylaştırıcı: <isim>

────────────────────────────────────

AÇILIŞ (5 dk)

  Prime directive:
  "Bildiklerimize, becerilerimize ve elimizdeki koşullara göre,
  o anda elinden gelenin en iyisini yaptığına inanıyoruz."

  Kurallar:
  - Kişi değil, sistem konuş
  - Kimseyi suçlama
  - Tüm fikirler değerlidir
  - Chatham House Rule (söylenen söylenen yerde kalır)

────────────────────────────────────

VERİ TOPLAMA (15 dk)

  Üç sütunda sessiz yazım (sticky / Miro / paylaşımlı doc):

  ✅ NE İŞE YARADI?
    - Devam etmek istediğimiz şeyler

  ⚠️ NE YARAMADI?
    - Tekrarlandığında değiştirmek istediğimiz şeyler

  💡 NE ÖĞRENDİK / DENEMEK İSTEDİĞİMİZ?
    - Yeni hipotezler, deneyler

────────────────────────────────────

GRUPLAMA VE OYLAMA (15 dk)

  Benzer kartları grupla
  Her katılımcı 3 oy hakkıyla en kritik konuları seçer
  Top 3-5 konu derin tartışmaya alınır

────────────────────────────────────

DERİN ANALİZ — Top 3 (20 dk)

  Her seçilen konu için "5 Neden" sor:
  1. Neden bu yaşandı?
  2. Bunun nedeni neden olabilir?
  3. ...
  Kök nedene ulaş.

────────────────────────────────────

AKSIYON ÜRETİMİ (15 dk)

  | # | Aksiyon | Sorumlu | Son Tarih | Ölçüm |
  |---|---------|---------|-----------|-------|
  | 1 | ... | ... | ... | ... |

  Kurallar:
  - Aksiyon spesifik ve ölçülebilir olmalı
  - Maksimum 3-5 aksiyon (daha fazlası unutulur)
  - "Daha iyi iletişim kuralım" gibi muğlak madde yok

────────────────────────────────────

KAPANIŞ (5 dk)

  - Bir kelime: "Nasıl hissediyorsun"
  - Sonraki retro tarihi
  - Aksiyonlar Jira/Asana'ya eklendi mi
```

## Incident Postmortem için özel format

Major incident sonrası:

1. **Zaman çizelgesi (timeline)** — Olayın saat saat kronolojisi
2. **Etki analizi** — Kim etkilendi, ne kadar süre, finansal-itibar etkisi
3. **Kök neden analizi** — 5 Neden / Ishikawa / Fault Tree
4. **Ne iyi gitti** — Tespit, müdahale, ekip koordinasyonu
5. **Ne kötü gitti** — Tespit gecikmesi, eskalasyon eksikliği, vb.
6. **Aksiyon planı** — Önleyici (tekrarı önlemek) + tespit edici (erken yakalamak)

## "Blameless" yaklaşım kuralları

- **"X kişisi hata yaptı" yerine "Süreç X kişisinin hata yapmasına izin verdi"**
- **"Neden uyarmadı" yerine "Uyarı mekanizması neden eksikti"**
- **Bireysel performans konuşması retro içinde yapılmaz** — birebir yöneticiyle yapılır
- **Tarihsel verileri korumak için belge anonim yazılır** veya katılımcı listesi belgede yer alır ama suçlama olmaz

## Kurallar

- **Prime directive her oturumda okunur,** özellikle yeni ekipte.
- **3-5 aksiyon yeter.** Listenin uzunluğu retro'nun başarısı değil.
- **Bir önceki retro'nun aksiyonlarını başta kontrol et** — yapılmamışsa "neden" sor.
- **Olumsuz vurgu varsa, olumluyu da kaz.** Sadece "yaramayanı" tartışan retro toksik olur.
- **Sessiz katılımcılar var mı diye gözlemle,** kolaylaştırıcı olarak söz hakkını dağıt.
- **Online retro için interaktif araç şart** — Miro, FunRetro, Parabol.

## Örnek

**Girdi:** "Sprint 14 retro'su, 7 kişi, 1 saat, online. Bu sprint'te kritik bug production'a gitti, hotfix yapıldı. Ekipte gerginlik var."

**Çıktı:** Açılışta prime directive özellikle vurgulu, veri toplamada bug konusu için ayrı sütun, 5 Neden bug için derinleştiriliyor, aksiyon listesinde "code review zorunluluğu" ve "deploy öncesi smoke test otomatik" gibi sistemsel öneriler — kişiye yönelik aksiyon yok.
