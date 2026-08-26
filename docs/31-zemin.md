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
| z02 | `ocak-z02-kul-ustten-kor-alt-2026-08-23.png` | `258d47c0-5057-4f4a-abd3-b5933de551b6` | `0_1` | Gün 0 kazanan promptu | C01 | 1968×2464 · %93.1 · 17.9° · 13.5 |
| z03 | `ocak-z03-kor-gozenekli-2026-08-23.png` | `52756090-be1f-4984-8c7c-8d394070fe1d` | `0_1` | V01 · Vary Subtle · HD | C02 | 1968×2464 · %94.9 · 9.2° · 26.1 |
| z04 | `ocak-z04-kivilcim-yagmuru-2026-08-23.png` | `a48f928d-3a6e-4f27-bd14-10adfa9e9fa4` | `0_0` | V01 · Vary Subtle · HD | C05 | 1968×2464 · %99.1 · 13.0° · 17.7 |
| z05 | `ocak-z05-kivilcim-seyrek-2026-08-23.png` | `9f35df3b-eca9-48d3-8f52-8a4a9da0395c` | `0_0` | V01 · Vary Subtle · HD | C10 | 1968×2464 · %99.8 · 13.4° · 18.9 |
| z06 | `ocak-z06-kul-mat-sag-kenar-2026-08-23.png` | `a1db07ec-81bf-4fa4-813f-8e76df7cce1f` | `0_2` | V01 · Vary Subtle · HD | C13 | 1968×2464 · %97.7 · 13.6° · 20.3 |
| z07 | `ocak-z07-kul-glow-sol-alt-2026-08-23.png` | `13bea9da-ed98-4ce0-b638-04f00645616f` | `0_0` | V01 · Vary Subtle · HD | C22 | 1968×2464 · %97.2 · 11.1° · 25.8 |
| z08 | `ocak-z08-kapi-camur-sivali-dar-2026-08-24.png` | `8060e356-c6b9-4c5f-96c6-203d24fb47b5` | `0_1` | V03 · Vary Subtle · HD | C03 | 1968×2464 · %99.2 · 12.3° · 22.0 |
| z09 | `ocak-z09-kapi-moloz-tas-dar-2026-08-24.png` | `4faa20f6-5411-455c-9a57-fa89468bbd3e` | `0_2` | V03 · Vary Subtle · HD | C07 | 1968×2464 · %98.2 · 15.6° · 20.4 |
| z10 | `ocak-z10-kapi-koyu-tas-orta-2026-08-24.png` | `ef6c2df0-93da-4b8f-8cb7-1de052c35d7f` | `0_0` | V03 · Vary Subtle · HD | C12 | 1968×2464 · %96.4 · 11.5° · 25.5 |
| z11 | `ocak-z11-kapi-kesme-tas-genis-2026-08-24.png` | `5dd54e0d-79c6-4cd9-86b5-f4b9652c7442` | `0_3` | V03 · Vary Subtle · HD | C17 | 1968×2464 · %93.0 · 12.8° · 21.4 |

**z11 notu.** Kapının ardındaki **kor yığını görünür** — diğer üç kapı zemininde ışık var,
kaynağı yok. C17 *"ilk dokunuş"* kartında bu **bilinçli tutuldu**: portre serisi
uyku → merak → dokunuş yayında ilerlerken kaynağın görünür olması **dokunuş anına denk
gelir.** Yani z11'in "kusuru" karta bağlıdır; başka bir karta verilirse kusur olur.

**Ölçüm sütunu sırası:** boyut · üstKaranlık · ton · ortalama luma.

**Tanımlar.** üstKaranlık = karenin üst yarısında luma<40 piksel oranı (kömür `#1A1210`'un
luma'sı 20). ton = doygunluğu 0.20 üstü ve luma>60 piksellerin medyan hue'su
(köz `#C44B2F` = 11.3°). luma = kare ortalaması. Ölçümler Claude.ai'de tam çözünürlüklü
kaynak dosya üzerinden alındı, ekran görüntüsünden değil.

⚠ **Eşikler ölçek-bağımsız tanımlanır (KARAR 572).** Yukarıdaki üç ölçüt oran ya da medyandır,
bu yüzden kare boyutundan bağımsızdır. **Piksel *sayısı* döndüren ölçütler değildir:**
`isikKaynagi` (parlak bağlı bileşen sayısı) küçük ızgara tile'ında kalibre edilmişti, aynı
kare dört kat büyük önizlemede **1–6 yerine 13–42** döndürdü. Kare değişmedi, **ölçek
değişti.** Piksel-sayısı eşiği kare boyutuna oranlanmadan kullanılmaz; ölçüm yazılırken
eşiğin yanına **hangi ölçekte kalibre edildiği** de yazılır (KARAR 470'in uzantısı).

**URL şeması:** `https://cdn.midjourney.com/{iş-kimliği}/{ek}.png`

**z01 mühürlüdür.** Dokuz V promptunun `--sref` çapasıdır (KARAR 542). Vary uygulanmaz,
yeniden üretilmez; değişirse tüm seri kayar.

**z02 mühürlüdür.** C01 zemini olarak 23 Ağustos'ta kapandı (KARAR 546). Yeni atama yapılmaz.

⚠ **On bir zeminin hepsi** yalnız MJ CDN'inde + Kaan'ın diskinde yaşıyor (**B141** · **B170**).
24 Ağustos'ta dört zemin daha eklendi; yedeklenmemiş varlık **7 → 11** oldu.
