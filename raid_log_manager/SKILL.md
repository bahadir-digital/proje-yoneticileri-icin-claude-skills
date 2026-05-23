---
name: raid-log-manager
description: Risks, Assumptions, Issues, Dependencies/Decisions (RAID) log'unu oluşturur ve günceller. Yeni risk/issue/aksiyon ekleme, mevcut kayıtların statüsünü güncelleme, kapanmış olanları arşivleme işlerini yapar. Kullanıcı "RAID güncelle", "yeni risk ekle", "issue açıyorum", "decision kaydet", "RAID log yaz" gibi ifadeler kullandığında devreye girer.
---

# RAID Log Yöneticisi

Proje yöneticisinin en sık güncellediği belge olan RAID log'unu yapılandırılmış tabloda tutar. Risk, Assumption, Issue, Decision (veya Dependency) — dört kategoriyi ayrı sekmelerde yönetir.

## Ne zaman tetiklenir

- "RAID log güncelle / oluştur"
- "Yeni risk ekle: ..."
- "Bu konuyu issue olarak aç"
- "Karar verildi, decision olarak kaydet"
- "Sponsor toplantısı için RAID'i hazırla"

## Girdi

Aşağıdaki bilgileri kayıt başına topla:

- **Tip:** Risk / Assumption / Issue / Decision (veya Dependency)
- **Başlık:** kısa, eylem odaklı
- **Tanım:** 1-2 cümle bağlam
- **Olasılık (Risk için):** 1-5
- **Etki:** 1-5
- **Sorumlu (Owner):**
- **Açılış tarihi:**
- **Hedef kapanış tarihi:**
- **Statü:** Açık / İzleniyor / Hafifletildi / Kapandı
- **Aksiyon planı / Mitigation:**

## Çıktı yapısı

Dört bölüm hâlinde tablo:

### 1. Riskler

| ID | Başlık | O | E | Skor | Owner | Statü | Mitigation | Açılış | Hedef Kapanış |
|----|--------|---|---|------|-------|-------|------------|--------|---------------|
| R-001 | ... | 4 | 5 | 20 | ... | Açık | ... | ... | ... |

### 2. Varsayımlar (Assumptions)

| ID | Varsayım | Doğrulama Yöntemi | Owner | Statü |

### 3. Konular (Issues)

| ID | Başlık | Etki | Owner | Aksiyon | Açılış | Hedef Çözüm |

### 4. Kararlar (Decisions)

| ID | Karar | Karar Veren | Tarih | Gerekçe | Bağlantılı Risk/Issue |

## Kurallar

- **Risk skoru = Olasılık × Etki.** 15+ olanlar kırmızı, 8-14 sarı, 1-7 yeşil.
- **Yüksek skorlu riskler en üstte** (skor azalan sıralama).
- **Kapanmış kayıtları silme** — statüyü "Kapandı" yap, tarihi kaydet. Audit için kalsın.
- **ID kalıbı:** R-001 (Risk), A-001 (Assumption), I-001 (Issue), D-001 (Decision). Sıralı, sıçramasız.
- **Sorumluluk boş bırakılmaz.** Owner yoksa "Atanmamış — sponsor onayı bekleniyor" yaz.
- **Mitigation ifadeleri eylem fiili ile başlasın.** "İzlenecek" değil, "Tedarikçiyle haftalık check-in kurulacak".

## Mevcut log üzerinde çalışma

Kullanıcı mevcut RAID log paylaşırsa:
- Yeni eklenenleri **listenin sonuna** ekle, ID'yi sırala
- Statü güncellemelerini yaparken **değişiklik tarihi** notu bırak
- Kapanan riskler ayrı bir "Archived" tablosuna alınabilir (isteğe bağlı)

## Örnek

**Girdi:** "Yeni risk: tedarikçi onayı 2 hafta gecikebilir, etki orta-yüksek, sorumlu Ayşe."

**Çıktı:**
```
R-007 | Tedarikçi onay gecikmesi | O:3 | E:4 | Skor:12 | Ayşe K. | Açık |
Mitigation: Tedarikçiyle haftalık check-in, paralel olarak yedek tedarikçi araştırılacak |
Açılış: <bugün> | Hedef Kapanış: <+30 gün>
```
