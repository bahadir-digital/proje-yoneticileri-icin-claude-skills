# Proje Yöneticileri İçin Claude Skills

Proje yöneticileri için Claude Skill ve Project şablonları. Charter'dan postmortem'e, statü raporundan paydaş iletişimine — proje yönetiminin tüm aşamalarında haftalık saatleri geri kazandıracak hazır kurulum.

## İçerik

### Project Instructions
- [`PROJECT_INSTRUCTIONS.md`](./PROJECT_INSTRUCTIONS.md) — Claude.ai Project'e yapıştırılacak talimat şablonu

### 10 Skill

| # | Skill | Klasör | Ne işe yarar |
|---|-------|--------|--------------|
| 1 | Proje Kartı (Charter) Oluşturucu | [`project_charter_builder`](./project_charter_builder) | Sponsor onayı için tek sayfa charter |
| 2 | RAID Log Yöneticisi | [`raid_log_manager`](./raid_log_manager) | Risks, Assumptions, Issues, Decisions |
| 3 | Statü Raporu Yazıcı | [`status_report_writer`](./status_report_writer) | Haftalık/aylık trafik ışığı raporu |
| 4 | Paydaş İletişimi Hazırlayıcı | [`stakeholder_comms_drafter`](./stakeholder_comms_drafter) | Sponsor, müşteri, ekip mesajları |
| 5 | Risk Değerlendirme Kolaylaştırıcı | [`risk_assessment_facilitator`](./risk_assessment_facilitator) | Risk taraması ve matris |
| 6 | Sprint / İterasyon Planlayıcı | [`sprint_planner`](./sprint_planner) | Sprint goal, kapasite, commit |
| 7 | Toplantı Notu Özetleyici | [`meeting_minutes_summarizer`](./meeting_minutes_summarizer) | Transkripti minute'a çevirir |
| 8 | Kapsam Değişikliği Değerlendirici | [`scope_change_evaluator`](./scope_change_evaluator) | CR etki analizi + alternatifler |
| 9 | Kickoff Toplantı Akışı Tasarımcısı | [`kickoff_agenda_designer`](./kickoff_agenda_designer) | Başlangıç toplantısı gündemi |
| 10 | Postmortem / Retrospektif Kolaylaştırıcı | [`postmortem_facilitator`](./postmortem_facilitator) | Blameless retro ve lessons learned |

## Kurulum

1. **Claude.ai → Projects → Create project**
2. **Name:** Projelerim (veya istediğin)
3. **Custom instructions** alanına [`PROJECT_INSTRUCTIONS.md`](./PROJECT_INSTRUCTIONS.md) içeriğini yapıştır, kendi profilinle doldur
4. **Knowledge** alanına 10 SKILL.md dosyasının her birini ekle
5. Project'te yeni sohbet aç — Claude artık ilgili Skill'i otomatik tanıyor

## Kullanım örnekleri

- *"Yeni başlayan ERP projesi için charter yaz"* → Project Charter Builder
- *"Bu haftaki statü raporunu hazırla, takvim yeşil, bütçe sarı"* → Status Report Writer
- *"Müşteri yeni özellik istiyor, etki analizi çıkar"* → Scope Change Evaluator
- *"Sprint retro hazırlığı yap, bu sprint'te major bug oldu"* → Postmortem Facilitator
- *"Sponsor'a tedarikçi gecikmesi maili yaz"* → Stakeholder Comms Drafter

## Lisans

MIT — özgürce kullan, çoğalt, değiştir.

## Seri

Bu, "Türkçe Profesyoneller İçin Claude Skills" serisinin 7. halkasıdır. Diğerleri:

1. [Öğretmenler](https://github.com/bahadir-digital/ogretmenler-icin-claude-skills)
2. Müşteri Hizmetleri *(yakında)*
3. Finans / Bütçe Uzmanları *(yakında)*
4. İK Profesyonelleri *(yakında)*
5. Yöneticiler *(yakında)*
6. Satış Profesyonelleri *(yakında)*
7. **Proje Yöneticileri** *(buradasınız)*
8. Operasyon Yöneticileri *(yakında)*
9. Mali Müşavirler *(yakında)*

## İletişim

- **Blog:** [bahadir.bearblog.dev](https://bahadir.bearblog.dev)
- **LinkedIn:** [linkedin.com/in/bahadireren](https://www.linkedin.com/in/bahadireren)
- **Instagram (AI):** [@ofiste.ai](https://www.instagram.com/ofiste.ai)
- **X:** [x.com/bahadireren_tr](https://x.com/bahadireren_tr)
- **Claude.ai Türkiye WhatsApp:** [Katıl](https://chat.whatsapp.com/I2763pKIpmS9xADAHLaGPE)
- **E-posta:** bahadireren@gmail.com
