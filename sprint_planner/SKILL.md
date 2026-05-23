---
name: sprint-planner
description: Agile/Scrum projeleri için sprint planlama oturumu çıktısı üretir. Sprint hedefi, kapasite hesabı, story prioritization, definition of done ve commit edilen iş listesi hazırlar. Kanban kullananlar için de iş çekme limitleri ve WIP önerileri sunar. Kullanıcı "sprint planı yap", "sprint goal", "kapasite hesabı", "backlog refinement", "sprint zero" gibi ifadeler kullandığında devreye girer.
---

# Sprint / İterasyon Planlayıcı

Scrum sprint'leri, Kanban iterasyonları veya 2-4 haftalık planlama dilimleri için yapılandırılmış plan çıktısı üretir. Sprint hedefi netliği ve kapasite gerçekçiliği iki ana odak.

## Ne zaman tetiklenir

- "Sonraki sprint için plan yap"
- "Sprint goal yazıyorum"
- "Backlog refinement / grooming"
- "Sprint kapasitesi nasıl hesaplanır"
- "Kanban WIP limitleri nasıl belirlenir"

## Girdi

- **Metodoloji:** Scrum / Kanban / SAFe / hibrit
- **Sprint süresi:** 1, 2, 3 veya 4 hafta
- **Ekip büyüklüğü ve rolleri**
- **Geçmiş velocity:** Son 3 sprint'in ortalama story point veya iş sayısı
- **Tatil, izin, eğitim:** Kapasiteyi etkileyen faktörler
- **Mevcut backlog:** Prioritized item listesi
- **İş hedefi:** Bu sprint sonunda ne çıkacak

## Çıktı yapısı

### 1. Sprint Bilgileri

```
Sprint No: <X> | Süre: <başlangıç-bitiş> | Ekip: <isim>
Sprint Goal: <Tek cümle, eylem fiili ile, müşteri değerine bağlı>
```

### 2. Kapasite Hesabı

| Üye | Toplam Gün | İzin/Eğitim | Sprint Dışı İş % | Net Kapasite (gün) |
|-----|-----------|--------------|--------------------|---------------------|
| ... | 10 | 1 | 20% | 7.2 |

Toplam ekip kapasitesi: <X gün> → <Y story point> (geçmiş velocity üzerinden)

### 3. Commit Edilen İşler

| ID | Story | Sahip | SP | DoD Kriteri |
|----|-------|-------|----|--------------|

### 4. Definition of Done (DoD) Hatırlatması

- Kod review yapıldı
- Test coverage > %X
- Acceptance criteria karşılandı
- Dokümantasyon güncellendi
- Demo'ya hazır

### 5. Sprint Riskleri ve Bağımlılıklar

- ...

### 6. Sprint Sonu Aktiviteleri Takvimi

- Daily standup: ...
- Mid-sprint review: ...
- Sprint review demo: ...
- Retrospektif: ... (Postmortem skill'i ile)

## Kapasite hesap kuralları

- **Tam günlük çalışma yok:** Toplantı, e-posta, taban gürültü için %20 kesintisi varsay
- **Sprint Master / PO** velocity'ye dahil değil (çoğu durumda)
- **Yeni ekip üyesi varsa** ilk sprint kapasitesi %50 say
- **Geçmiş 3 sprint ortalamasını al,** son sprint'i tek başına baz alma

## Kanban kullanıcıları için

- **WIP limitleri:** Her sütun için "ekip büyüklüğü × 1.5" üst sınır
- **Pull yerine push olmasın** — boş yer açılınca yeni iş çekilir
- **Cycle time hedefi:** Geçmiş ortalamanın üstüne çıkarsa erken uyarı

## Kurallar

- **Sprint Goal ölçülebilir olsun.** "X özelliğini geliştir" değil, "X özelliği UAT'a hazır".
- **Yüzde 80 commit, %20 buffer.** %100 commit edilen sprint büyük olasılıkla başarısız.
- **Bağımlılıklar listesi boş bırakılmaz.** Yoksa "Yok — doğrulayın" yaz.
- **Backlog prioritization:** MoSCoW (Must, Should, Could, Won't) veya RICE skoru kullanılabilir.

## Örnek

**Girdi:** "6 kişilik ekip, 2 haftalık sprint, geçmiş velocity 28 SP. Bu hafta 1 kişi 3 gün izinli. Sprint goal: checkout akışı production'a hazır."

**Çıktı:** Net kapasite ~25 SP, %20 buffer ile commit 20 SP, 4 story seçimi, 2 bağımlılık (ödeme tedarikçi onayı, güvenlik review), demo tarihi 14 Haziran.
