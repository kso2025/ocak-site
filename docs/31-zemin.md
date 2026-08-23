# OCAK — ZEMİN ENVANTERİ

Zemin, bir kart görselinin altındaki kaynak görseldir. Zemin kalıcıdır; hangi karta
gittiği karardır ve değişebilir. Bu yüzden dosya adı karta değil zemine bağlanır.

**Zemin dosya adı:** `ocak-zNN-slug-YYYY-AA-GG.png`
NN üretim sırası (asla yeniden kullanılmaz) · slug betimleyici, Türkçe karaktersiz,
tireli · tarih üretim günü.

**Basılan kart dosya adı:** `ocak-cNN-kM-YYYY-AA-GG.png` — karusel değilse `-kM` yok.

| Z | Dosya adı | MJ iş kimliği | Ek | Üreten | Kart | Ölçüm |
|---|---|---|---|---|---|---|
| z01 | `ocak-z01-kul-ustten-kor-noktali-2026-08-23.png` | `b6457637-7065-4c39-b551-268b156c9408` | `0_2` | Gün 0 kazanan promptu | — (`--sref` çapası) | 1968×2464 · %99.6 · 14.1° · 17.3 |
| z02 | `ocak-z02-kul-ustten-kor-alt-2026-08-23.png` | `258d47c0-5057-4f4a-abd3-b5933de551b6` | `0_1` | Gün 0 kazanan promptu | C1 | 1968×2464 · %93.1 · 17.9° · 13.5 |
| z03 | `ocak-z03-kor-gozenekli-2026-08-23.png` | `52756090-be1f-4984-8c7c-8d394070fe1d` | `0_1` | V1 · Vary Subtle · HD | C2 | 1968×2464 · %94.9 · 9.2° · 26.1 |
| z04 | `ocak-z04-kivilcim-yagmuru-2026-08-23.png` | `a48f928d-3a6e-4f27-bd14-10adfa9e9fa4` | `0_0` | V1 · Vary Subtle · HD | C5 | 1968×2464 · %99.1 · 13.0° · 17.7 |
| z05 | `ocak-z05-kivilcim-seyrek-2026-08-23.png` | `9f35df3b-eca9-48d3-8f52-8a4a9da0395c` | `0_0` | V1 · Vary Subtle · HD | C10 | 1968×2464 · %99.8 · 13.4° · 18.9 |
| z06 | `ocak-z06-kul-mat-sag-kenar-2026-08-23.png` | `a1db07ec-81bf-4fa4-813f-8e76df7cce1f` | `0_2` | V1 · Vary Subtle · HD | C13 | 1968×2464 · %97.7 · 13.6° · 20.3 |
| z07 | `ocak-z07-kul-glow-sol-alt-2026-08-23.png` | `13bea9da-ed98-4ce0-b638-04f00645616f` | `0_0` | V1 · Vary Subtle · HD | C22 | 1968×2464 · %97.2 · 11.1° · 25.8 |

**Ölçüm sütunu sırası:** boyut · üstKaranlık · ton · ortalama luma.

**Tanımlar.** üstKaranlık = karenin üst yarısında luma<40 piksel oranı (kömür `#1A1210`'un
luma'sı 20). ton = doygunluğu 0.20 üstü ve luma>60 piksellerin medyan hue'su
(köz `#C44B2F` = 11.3°). luma = kare ortalaması. Ölçümler Claude.ai'de tam çözünürlüklü
kaynak dosya üzerinden alındı, ekran görüntüsünden değil.

**URL şeması:** `https://cdn.midjourney.com/{iş-kimliği}/{ek}.png`

**z01 mühürlüdür.** Dokuz V promptunun `--sref` çapasıdır (KARAR 542). Vary uygulanmaz,
yeniden üretilmez; değişirse tüm seri kayar.

**z02 mühürlüdür.** C1 zemini olarak 23 Ağustos'ta kapandı (KARAR 546). Yeni atama yapılmaz.

⚠ Yedi zemin de yalnız MJ CDN'inde + Kaan'ın diskinde yaşıyor (B141).
