# Cut The Corners — 12 Haftalık Plan

> **Faz 2:** Asıl portföy oyunu.
> **Süre:** 12 hafta (2026-09-28 → 2026-12-20). Tempo: haftada 3-5 saat, 2 seans.
> **Kapsam:** `MoSCoW.md`. Tasarım: `GDD.md`.
> **Kural:** Bir hafta bitmezse sıkıştırılmaz, takvim kayar. Haftanın işleri Must'a dokunmuyorsa bir sonraki haftaya atılabilir.
> **Devlog:** Her haftanın son maddesi. Kısa olabilir; önemli olan ritim.

---

## Blok 1 — Öğrenme ve His (Hafta 1-3)

Amaç: "Ağır, sakar gövde + keskin silah" hissinin tutup tutmadığını görmek. Çirkin kareler, art yok.

### Hafta 1 (2026-09-28 → 10-04): Fizikle hareket
- [ ] Commit'lenmemiş 3 ayar dosyasına bak ve commit'le
- [ ] Çöp sahne: zemin + birkaç platform (düz kareler)
- [ ] Hap karakter: Rigidbody2D + CapsuleCollider2D
- [ ] `transform.Translate` yerine kuvvetle koşma (`AddForce` / `velocity`)
- [ ] Zıplama + yere basma kontrolü (ground check)
- [ ] Mass, drag ve gravity scale ile oyna, neyin ne hissettirdiğini not al
- [ ] Devlog #1: "İkinci oyun başlıyor" (konsept + pillar'lar)

### Hafta 2 (10-05 → 10-11): Sakarlık ve ilk silah
- [ ] Karakterin yürürken sallanması (torque / hafif rotasyon ya da joint deneyi)
- [ ] Kılıcı karaktere bağla (child obje veya HingeJoint2D, ikisini dene)
- [ ] Kılıç mouse imlecine doğru dönüyor
- [ ] Sol tık: hızlı savurma
- [ ] Devlog #2

### Hafta 3 (10-12 → 10-18): Vuruş ve karar
- [ ] Hedef kukla (hareketsiz bir dikdörtgen), 3 HP
- [ ] Kılıç vurunca kuklanın HP'si düşüyor, 0'da ölüyor
- [ ] Physics layer'ları ve collision matrix'i kur (Faz 1'deki dersi baştan uygula)
- [ ] **His testi:** kontrast tutuyor mu? Tutmuyorsa pillar 2'yi yeniden yaz
- [ ] **MoSCoW'u gözden geçir ve DONDUR (2026-10-18)**
- [ ] Devlog #3

---

## Blok 2 — Çekirdek (Hafta 4-8)

Amaç: Baştan sona oynanabilir, çirkin bir maç.

### Hafta 4 (10-19 → 10-25): Silah sistemi
- [ ] Silah alma / bırakma
- [ ] Ortak dayanıklılık: 3 kullanımda kırılma
- [ ] Sağ tık: parry (kılıç)
- [ ] Devlog #4

### Hafta 5 (10-26 → 11-01): Mızrak
- [ ] Mızrak: dürtme (sol tık)
- [ ] Mızrak: fırlatma (sağ tık), tek vuruşta öldürme
- [ ] Hızlı obje için continuous collision detection
- [ ] Mızrak duvara saplanıyor, üstüne basılabiliyor, geri alınabiliyor
- [ ] Devlog #5

### Hafta 6 (11-02 → 11-08): Spawn ve maç akışı
- [ ] Silahlar rastgele noktalarda doğuyor
- [ ] Maç başlangıcı: herkes elleri boş
- [ ] Kazanma / kaybetme koşulları
- [ ] Devlog #6

### Hafta 7 (11-09 → 11-15): AI (1)
- [ ] AI state machine iskeleti: Silah ara → Silaha git → Oyuncuya git → Saldır
- [ ] Tek düşmanla çalışan ilk versiyon
- [ ] Devlog #7

### Hafta 8 (11-16 → 11-22): AI (2) + arena
- [ ] 3+ düşman aynı anda
- [ ] AI'nın silahı kırılınca yeniden silah araması
- [ ] Arena v1: farklı yüksekliklerde platformlar
- [ ] **İlk tam maç baştan sona oynanabilir**
- [ ] Devlog #8

---

## Blok 3 — Playtest (Hafta 9-10)

### Hafta 9 (11-23 → 11-29): Playtest 1
- [ ] En az 3 kişiye oynat (`playtest-koordinatoru` ile plan)
- [ ] Geri bildirimleri topla, GDD'ye işle
- [ ] En kritik 3 sorunu seç
- [ ] Devlog #9

### Hafta 10 (11-30 → 12-06): Düzeltme + Should'lar
- [ ] Playtest'ten çıkan 3 sorun
- [ ] Zaman kalırsa: kalkan / dash / game feel (hit-stop, shake), Should listesinden en değerlisi
- [ ] Devlog #10

---

## Blok 4 — Yayın (Hafta 11-12)

### Hafta 11 (12-07 → 12-13): Cila ve UI
- [ ] Sprite pack'i yerleştir (siyah-beyaz dünya + renkli karakterler)
- [ ] Ana menü, HUD (HP), Win / Lose ekranları + Replay
- [ ] Temel ses efektleri
- [ ] İlk WebGL build'i al ve test et (`webGLExceptionSupport` dersini unutma)
- [ ] Devlog #11

### Hafta 12 (12-14 → 12-20): Yayın
- [ ] Must Have listesinin tamamı işaretli mi?
- [ ] itch.io sayfası + tanıtım GIF'i
- [ ] **Yayın**
- [ ] LinkedIn duyurusu
- [ ] Devlog #12: kapanış yazısı

---

## Yayın Sonrası (plan dışı)

- Mobil lite versiyon (Could Have)
- Should / Could listesinde kalanlar
