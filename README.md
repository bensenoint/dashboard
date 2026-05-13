# Benseno Tasarım Panosu

> Ekibin canlı iş takip dashboard'u. Her 30 dakikada otomatik güncellenir (Brief Sync v7.4).

**🌐 Canlı:** [https://bensenoint.github.io/dashboard/](https://bensenoint.github.io/dashboard/)

---

## 📊 Bu Nedir?

Benseno tasarım ekibinin günlük iş yükünü, aktif brief'leri, kalite skorlarını, anomalileri canlı olarak gösteren web dashboard'u. 19 ekip üyesinin ortak görüntüsü.

**Veri kaynağı:** Slack Canvas (`F0B1B6XUD44`) — Brief Sync scheduled task'ı her `:15` ve `:45` dakikalarda Canvas'ı okuyup bu HTML'i günceller.

**Erişim:** Public, URL'i bilen herkes açabilir. Mobile + desktop.

---

## 🎯 Özellikler

- 📋 **Aktif İşler:** Filtrelenebilir, sıralanabilir tablo (önceliğe/atanana/markaya göre)
- 📅 **Plan + Gantt:** 2 haftalık görsel zaman çizelgesi
- 🆚 **Departman Karşılaştırma:** Tasarım vs Editör vs AI
- 🎯 **Yönetici Sekmesi:** Anomali listesi, KPI editor, force-close yetki
- 👥 **Ekip Matrisi:** 16 kişi × marka detay
- 🤝 **Multi-Assignee:** Lead/Contributor/Reviewer rolleri
- 💎 **Kalite Skorları:** 3 departman için 0-100 skor
- 💬 **Thread Özetleri:** Haiku ile 3-madde otomatik özet
- 🌓 **Dark mode** · 📱 **Mobile-responsive** · ⌘K **arama**

---

## 🔄 Nasıl Güncellenir?

Bu repo `index.html` Brief Sync scheduled task'ı tarafından otomatik commit'lenir:

```
Slack Canvas (F0B1B6XUD44) → değişiklik
        ↓
Brief Sync (her :15 ve :45)
        ↓
EMBEDDED_DATA güncelle + index.html commit
        ↓
GitHub Pages auto-deploy (~1 dk)
        ↓
Ekip refresh ile yeni veriyi görür
```

**Manuel update gerekmez** — sistem kendiliğinden işler.

---

## 📅 Geçmiş Versiyon Erişimi

Git history her commit'i tutar. Önceki dashboard'u görmek için:
- GitHub UI'da `index.html` dosyasını aç → `History` butonu
- Veya direkt: `https://github.com/bensenoint/dashboard/commits/main/index.html`

---

## ⚙️ Teknik Detaylar

- **Framework:** Vanilla JS + Chart.js + Grid.js (CDN)
- **Boyut:** ~250 KB tek dosya (self-contained)
- **Browser desteği:** Modern tarayıcılar (Chrome 90+, Safari 14+, Firefox 88+)
- **Veri:** `window.EMBEDDED_DATA` JSON (inline, runtime'da Cowork değil)
- **Auto-deploy:** GitHub Pages, main branch, root klasör

---

## 🐛 Sorun mu var?

- Dashboard güncellenmiyor → 30 dk bekle, son commit zamanını kontrol et
- 404 → Pages aktif mi? Settings → Pages
- Boş görünüyor → Browser console aç, `EMBEDDED_DATA` var mı kontrol et

Diğer sorular için: **@Görkem** (Slack)

---

*Sistem versiyonu: v7.4 · Brief Sync :15/:45*
*GitHub Pages otomatik deploy · Last manual update: 13 Mayıs 2026*
