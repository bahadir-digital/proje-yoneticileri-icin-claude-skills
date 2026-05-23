---
name: kickoff-agenda-designer
description: Proje kick-off (başlangıç) toplantısı için detaylı gündem, kolaylaştırıcı notları, zaman bloğu, katılımcı listesi, beklenen çıktılar ve hazırlık listesi üretir. İç ekip ve müşteri/sponsor kick-off'larını ayrı formatlarda işler. Kullanıcı "kickoff agenda", "proje başlangıç toplantısı", "kick-off planı", "ilk toplantı akışı" gibi ifadeler kullandığında devreye girer.
---

# Kickoff Toplantı Akışı Tasarımcısı

Proje kick-off'unu "tanışma + slayt geçişi" olmaktan çıkarıp, projenin temel taşlarını ekibe ve sponsor'a yerleştiren yapılandırılmış oturuma çevirir.

## Ne zaman tetiklenir

- "Proje kick-off planı"
- "Başlangıç toplantısı gündemi"
- "Müşteri kick-off'una hazırlık"
- "İlk toplantı akışı nasıl olmalı"

## Girdi

- **Kick-off türü:** İç ekip / Müşteri-sponsor / Hibrit
- **Süre:** 1 saat / 2 saat / yarım gün / tam gün workshop
- **Katılımcı sayısı ve rolleri**
- **Lokasyon:** Yüz yüze / online / hibrit
- **Proje karmaşıklığı:** Düşük / Orta / Yüksek
- **Önceden hazırlanmış belgeler:** Charter, kapsam, takvim taslağı

## Çıktı yapısı

```
PROJE KICK-OFF TOPLANTISI
Proje: <ad>
Tarih: <tarih> | Süre: <X> | Lokasyon: <yer/link>
Düzenleyen: <PM adı>

────────────────────────────────────

AMAÇ
<Toplantı sonunda 3 cümlede ne başarılmış olacak>

KATILIMCILAR
- Zorunlu: <isim, isim>
- Davetli: <isim, isim>
- Bilgilendirme (özet sonra gönderilecek): <isim>

ÖNCEDEN OKUMA
- Project Charter (link)
- Üst düzey kapsam (link)
- (Müşteri kick-off'sa) Sözleşme özeti

────────────────────────────────────

GÜNDEM

00:00 — 00:10 | Açılış ve Tanışma (10 dk)
  Kolaylaştırıcı: PM
  Beklenen çıktı: Herkes adı + rolü + projeyle bağı söyledi

00:10 — 00:25 | Proje Vizyonu ve İş Gerekçesi (15 dk)
  Kolaylaştırıcı: Sponsor
  Beklenen çıktı: Ekip "neden bu projeyi yapıyoruz" sorusunun cevabını biliyor

00:25 — 00:45 | Kapsam, Hedef ve Başarı Kriterleri (20 dk)
  Kolaylaştırıcı: PM
  Beklenen çıktı: Out-of-scope üzerinde mutabakat

00:45 — 01:00 | Üst Düzey Zaman Çizelgesi ve Milestone'lar (15 dk)
  Beklenen çıktı: Anahtar tarihler bilinçte

01:00 — 01:15 | Roller, Sorumluluklar (RACI) (15 dk)
  Beklenen çıktı: Kararı kim alır, kim onaylar netleşti

01:15 — 01:30 | Çalışma Şekli, Araçlar, İletişim Ritmi (15 dk)
  - Toplantı ritmi (stand-up, statü, retro)
  - Araçlar (Jira/Asana/Slack/e-posta)
  - Eskalasyon yolları
  - Belge yerleri

01:30 — 01:45 | Bilinen Riskler ve Açık Konular (15 dk)
  Beklenen çıktı: İlk RAID kayıtları oluştu

01:45 — 02:00 | Sonraki Adımlar ve Kapanış (15 dk)
  - Aksiyon maddeleri (sorumlu + tarih)
  - Sonraki toplantı tarihleri
  - Açık soru var mı

────────────────────────────────────

PM HAZIRLIK LİSTESİ (toplantıdan önce)
- Charter taslağı sponsor onayında
- Toplantı linki + ajanda 3 gün önce gönderildi
- Slayt deck hazır (max 10 slayt)
- Whiteboard / Miro hazır (interaktif kısımlar için)
- RAID log şablonu açık, ekranda paylaşılacak

TOPLANTI SONRASI
- 24 saat içinde minute + aksiyon listesi gönder
- RAID log'a ilk kayıtları gir
- Sonraki toplantıların takvim davetlerini gönder
```

## Kurallar

- **"Tanışma 30 dakika" yok.** En fazla 10 dk, sonra konuya gir.
- **Sponsor 15-20 dakika ayır,** "proje neden var" sorusunu sadece sponsor cevaplayabilir.
- **Out-of-scope mutlaka konuşulsun.** Kick-off'un en kritik 5 dakikası burası.
- **RACI matrisi ekranda gösterilsin,** ezbere "X sorumlu" demek yetmez.
- **Soru-cevap için zaman buffer'ı,** her büyük bölüm sonrası 3-5 dk.
- **Online kick-off için ek kural:** Kamera açık, chat ekstra soru kanalı, kayıt onayı en başta.
- **Müşteri kick-off'unda ton farkı:** Daha resmî, içeri dair şakalar yok, müşteri lisanına geç (müşterinin terimleri kullanılır).

## Süre varyantları

- **1 saat (basit projeler):** Yukarıdakini kısalt — RACI ve risk kısalır, çalışma şekli iç ekip toplantısına bırakılır
- **Yarım gün workshop (karmaşık projeler):** Risk workshop'u ve out-of-scope üzerine 1 saat ekstra, ekip tanışması interaktif egzersizle uzar
- **Tam gün (yeni ekip + yeni müşteri):** Yarım gün workshop + öğleden sonra teknik mimari + sözleşmesel gereklilikler oturumu

## Örnek

**Girdi:** "ERP geçişi projesi başlıyor. 9 ay sürecek. Müşteri ve iç ekip beraber kickoff yapacak, 18 kişi, hibrit (10 yüz yüze, 8 online), 3 saat ayırdık."

**Çıktı:** 3 saatlik akış — 30 dk sponsor vizyonu + müşteri beklentisi, 45 dk kapsam workshop'u (out-of-scope ortak yazımı), 30 dk RACI canlı doldurma, 30 dk çalışma şekli + araçlar, 30 dk risk workshop'u kısa versiyon, 15 dk kapanış. Hazırlık listesinde charter sponsor onayı, RACI ön taslağı, Miro board kurulumu.
