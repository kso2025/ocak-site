# DOCS PATCH — 2026-08-23

**Kaynak sohbet:** Advaita site yorumları turu (PDF ~95 kalem) · ADIM 1 (A grubu) + ADIM 2 (B2 doz/kayıt doktrini)
**Uygulayan:** `ocak-arsivci`
**Kapsam:** yalnız `docs/` — kod dosyalarına dokunma.

---

## ADIM 0 — SALT OKU, ÖLÇ, RAPORLA, DUR

Yazmadan önce şunları ölç ve raporla. **Bu patch bilerek numara içermiyor.**

```bash
cd ~/Desktop/hlaorpz/ocak
git log --oneline -3
awk -F'\t' 'NR>1{print $1}' docs/01-kararlar.tsv | sort -n | tail -1   # en yüksek KARAR no
grep -c "^## B" docs/02-borclar.md                                      # borç sayısı
grep -n "506" docs/01-kararlar.tsv                                      # 506 satırı duruyor mu, durumu ne
grep -n "299" docs/01-kararlar.tsv                                      # 299 KALICI mı
wc -l docs/00-durum.md                                                  # 200 satır kapağı
```

**UYARI:** Bu sohbet paralel yürüyen başka bir sohbetle aynı gün çalıştı. Karar numaraları ilerlemiş olabilir. Aşağıdaki kararlara **sen sıradaki numaraları ver**, bu dosyadaki K-A/K-B/K-C/K-D etiketlerini kullanma. Çapraz referanslar (`←`, `→`, `↔`) numaraları verdikten sonra doldurulacak.

`ocak-docs` MCP'nin döndürdüğü commit damgası HEAD'in gerisinde olabilir — ölçümü **çalışma kopyasından** yap, MCP'den değil.

Ölçümü raporla ve **dur**. Onay gelmeden yazma.

---

## 1 — YENİ KARARLAR (numaralar CC tarafından verilecek)

### K-A · Kayıt sınırı

| alan | değer |
|---|---|
| tarih | 2026-08-23 |
| başlık | Kayıt sınırı formatın değil bloğun cinsine göre — anlatım ve uygulama kaydedilir, kadın kadına paylaşım kaydedilmez; kayıt varlığı etkinlik başına DB alanında tutulur |
| durum | KALICI |
| ilişki | `↔57` |
| kaynak | kronoloji çapası (önce kronoloji yazılacak) |

Uygulama karşılığı (Notion'da tamamlandı):
- Açık Kapı → tema ve pratik kaydedilir; soruların okunduğu bölüm kaydedilmez
- Çember → hiç kaydedilmez
- Seremoni → tema ve seremoni kaydedilir, paylaşım turu kaydedilmez; `kakao-seremonisi-yuzyuze` istisna, hiç kaydedilmez
- Atölye → anlatım ve uygulama kaydedilir, paylaşımlar kaydedilmez
- Etkinlikler DB'ye `Kayıt Var` checkbox'ı eklendi (Kaan açtı), otorite alan orada

### K-B · Unvan yasağının daraltılması

| alan | değer |
|---|---|
| tarih | 2026-08-23 |
| başlık | Unvan yasağı betimlemeyi kapsamaz — `cacaoista` Türkçe betimlemenin açıklayıcı eki olarak geçebilir; tek başına unvan olarak kullanılmaz |
| durum | KALICI |
| ilişki | `←506` |

**KARAR 506 satırı da değişecek:** `durum` → `SUPERSEDE`, `ilişki` → `→K-B (kısmi: unvan yasağı korundu, betimleme serbest)`

Yaslandığı canlı cümle (`/advaita`, `tasidigi-bati`): *"Advaita bir kakao taşıyıcısı — cacaoista."* Yazım **c** ile (cacaoista), k ile değil.

### K-C · Kamuya açık etkinlik metninde doz

| alan | değer |
|---|---|
| tarih | 2026-08-23 |
| başlık | Etkinlik sayfası akışı, hazırlığı ve mahrem soruları kamuya açmaz — hazırlık gerektiren formatlarda `Yanına Al` işaretçiye iner, beslenme/ilaç/hamilelik kayıt sonrası kanala taşınır |
| durum | KALICI |

Gerekçe (Advaita): alan korunmuyor · akış kopyalanabiliyor · mahrem konu kamuya açılıyor · ne olacağını zaten bilmiyoruz, taahhüt veremeyiz.

### K-D · Property yazım protokolü

| alan | değer |
|---|---|
| tarih | 2026-08-23 |
| başlık | Notion text property'sine yazım cerrahi değildir — gövde önce kabukta kurulur, `python3 len()` ile ölçülür, yazılır, geri okunan uzunluk beklenenle karşılaştırılır |
| durum | KALICI |

---

## 2 — KARAR NOTU (yeni karar değil, kayıt)

`KARAR 459` (içerik otoritesi: Notion'a giriş elle) **KALICI olarak duruyor.** Bu oturumda Kaan parti kapsamlı bir istisna verdi: Claude diff'i hazırladı, her yazma çağrısı istemci onayından geçti. Kalıcı gevşetme yapılmadı; ileride istenirse ayrı karar gerekir.

Not: istemci her `notion-update-page` çağrısını kullanıcı onayına düşürüyor — yani 459'un koruduğu insan halkası araç seviyesinde de zorunlu.

---

## 3 — BORÇLAR (B numaraları CC tarafından verilecek)

**Ölçüm bantları — acil, bekçi yanlış hedef gösteriyor**
1. Çember karakter bandı yeniden ölçülsün. Eski bant `3.824–4.113` **geçersiz**; yeni gerçek: `3.480–3.771`
2. Açık Kapı bandı yeniden ölçülsün. Yeni gerçek: `3.036–3.264`
3. Seremoni ve Atölye için bant yok — oluşturulsun. Seremoni `3.605–3.686`, Atölye `4.541`

**`ocak-etkinlik` skill'i**
4. SABİT BLOKLAR bölümü güncellensin — dört blokta değişiklik var (aşağıda §5)
5. `ornekler.md` (Açık Kapı bekçisi) ve `ornekler-cember.md` (Çember bekçisi) yeni gövdelerden yeniden üretilsin
6. "Notion rich text tek parçada 2.000 taşır, fazlası sessizce kırpılır" notu **yanlış ya da eksik**. API yazımıyla 5.203 karakter tek parçada gitti, kırpılmadı. Not ya kaldırılsın ya "elle yapıştırma yolu" diye daraltılsın
7. K-D protokolü skill'e yazılsın (kabukta kur → ölç → yaz → karşılaştır)
8. Kaçış artığı taraması skill'e yazılsın: `LIKE '%u0131%' OR '%u015%' OR '%u011%'`. **Uyarı:** desen gevşek yazılırsa yanlış alarm verir — `%Pas%` "ku**pas**ını" içine düşüyor

**Notion DB hijyeni**
9. Sayfalar DB `Son Güncelleme` property'si elle bakılıyor ve yalan söylüyor (`/araclar` üç ay geride, `/advaita` boş). Notion `Last edited time` tipine çevrilsin. **Önce:** `grep -rn "Son Güncelleme\|Son_Guncelleme" src/`
10. `Versiyon` property'si aynı sınıf sorun — elle bakım
11. Gölge satır `Ritüel Tasarımı | Gölge 0210 o#2` Detay'ı bayat (4.904, asıl satır 4.541). Takvim amaçlı, yayında değil, bilerek dokunulmadı — kayda geçsin

**`10-marka.md` (marka çekirdeği — üçü de aynı sınıf: süperselenmiş dil hâlâ duruyor)**
12. "Yoga ve nefes (Rishikesh YTT)" → eğitim Sivananda kökenli, ve Advaita "belirtmeye gerek yok" diyor. Sitede kaldırıldı, korpusta duruyor
13. "**Beşli kültürel sentez:** Güney Amerika + Doğu/Hint + Nordik + Mısır/Akdeniz + Türk/Anadolu" satırı `KARAR 299` ile **süperselendi** (Anadolu kaynak değil kap), satır hâlâ duruyor
14. Dosyanın giriş notu *"'beş kadim kaynak' ifadeleri bu dosyada YOK"* diye iddia ediyor — yanlış. Birebir ifade yok ama aynı fikir madde 13'te duruyor. Not düzeltilsin
15. K4'teki "Wild Woman Project modelinin OCAK versiyonu" referansı — Advaita'nın batı-sıfatı itirazıyla (`yaban kadın` / `womb yoga` / `şamanik yoga`) çelişiyor, gözden geçirilsin

**Kod (CC işi, bu patch'te değil — brief gerekir)**
16. `/hikaye` section marker `bes-kadim-kaynak` → `dort-yon-bir-ocak`. **Önce:** `grep -rn 'bes-kadim-kaynak' src/`
17. Çember Lideri → **Çember Rehberi** rename (Advaita). Yerler: `10-marka.md` K4, `/sen-neredesin` 8. Taşıyıcı, `/ekip`
18. Ana sayfa + `/sen-neredesin`: aşağı-kaydırma işareti yok. Advaita ortak bir komponent öneriyor
19. "Hikâyeyi oku"ya tıklayan kullanıcı sayfalar arasında kayboluyor — dönüş yolu / navigasyon

**Operasyon**
20. **DEPLOY YAPILMADI.** 14 etkinlik gövdesi Notion'da yeni, sitede eski. Bilinçli karar: bugün üç transkripsiyon/sınıflandırma hatası yakalandı, hiçbiri siteye ulaşmadı çünkü deploy sonda. Sayfalar DB de bitince tek seferde
21. `Kayıt Var` işaretleme durumu doğrulansın: işaretli = 6 Açık Kapı + `hasat-ve-sukran` + `kakao-seremonisi-online` + `rituel-tasarimi`; işaretsiz = 4 Çember + `kakao-seremonisi-yuzyuze`

---

## 4 — KRONOLOJİ (`90-kronoloji/2026-08.md`, append-only, KIRPMA YASAĞI)

Bu oturum bir gün içinde 14 etkinlik gövdesinin tamamını yeniden yazdı. Advaita'nın ~95 kalemlik yorum PDF'inin ~70'i kapandı.

**Yöntem değişikliği:** Sıra önce gruba göre kuruldu (A→B→C→D), sonra **sayfaya göre**ye çevrildi. Gerekçe: doktrin kararları verildikten sonra grup sırası aynı gövdeyi üç kez açtırıyordu. `elin-neyle-dolu` bu yüzden üç kez yazıldı.

**Ölçüm — 14 gövde, net −6.554 karakter:**

| Format | gövde | net |
|---|---|---|
| Açık Kapı | 6 | −1.190 |
| Çember | 4 | −1.634 |
| Seremoni | 3 | −3.367 |
| Atölye | 1 | −363 |

Son uzunluklar: `bir-esikte-duruyorsun` 3226 · `bu-ses-kimin` 3212 · `dusundugum-hissettigim-yaptigim` 3049 · `istek-mi-ihtiyac-mi` 3118 · `kokun-nerede-kaldi` 3036 · `nereye-kadar-senin` 3264 · `ekmeden-once` 3505 · `elin-neyle-dolu` 3771 · `hangi-tohumu-ekeceksin` 3480 · `neyi-bekliyorsun` 3720 · `hasat-ve-sukran` 3672 · `kakao-seremonisi-online` 3605 · `kakao-seremonisi-yuzyuze` 3686 · `rituel-tasarimi` 4541

**Üç hata yapıldı, üçü de farklı bir ağa takıldı, hiçbiri siteye ulaşmadı:**

| hata | sınıf | yakalayan |
|---|---|---|
| `uykudan mu0131` (bozuk kaçış dizisi) | transkripsiyon | kaçış artığı taraması |
| `yerleşemmiş` + `yerleşemeyen` | transkripsiyon | uzunluk aritmetiği (−2 sapma) |
| Dört Çember'de iki cümle atlandı | sınıflandırma | denetim sorgusu |

Ders: tek ağ yetmiyor. Kaçış taraması geçerli-ama-yanlış dizeyi görmez; uzunluk aritmetiği eşit uzunluklu hatayı görmez; denetim sorgusu ancak doğru desenle çalışır (`%Pas%` "kupasını" içine düşüp yanlış alarm verdi).

**İkinci ders:** `A grubu` ölçülünce Advaita'nın beş yorumundan dördünün **zaten uygulanmış** olduğu görüldü — ama bir uygulama yarım kalmıştı: psikolojik raf `/araclar`'dan silinmiş, "yedi raf" sayacı güncellenmemişti. Aynı sınıf hata `/hikaye`'de (`bes-kadim-kaynak` marker'ı) ve `10-marka.md`'de ("Beşli sentez") de bulundu. **Etiket içeriği takip etmiyor** — bu oturumda dört kez.

---

## 5 — SABİT BLOK DEĞİŞİKLİKLERİ (skill ve bekçi dosyaları için referans)

```
# Tüm Açık Kapı + Çember
Ne olacağını şimdiden söylemiyoruz — anlatılınca bilgiye dönüşüyor, oysa yaşanacak bir şey.
→ Ne geleceğini önceden bilmiyoruz — akış o akşam kuruluyor.

Ortak olan şu: pratik biterken…   →   Ortak olan şu: Pratik biterken…

# Açık Kapı
Kimse düzeltilmiyor. Kimseye tavsiye verilmiyor. Reçete vermiyoruz, alan tutuyoruz.
→ Kimse düzeltilmiyor. Reçete vermiyoruz, alan tutuyoruz.

- Kayıt alınır, hemen ardından e-postana düşer — gelemezsen sonradan izlersin
→ - Tema ve pratik kaydedilir, hemen ardından e-postana düşer — gelemezsen sonradan izlersin
  - Soruların okunduğu bölüm kaydedilmez; yazdığın o akşamda kalır

Önce tema açılır: eşik ne demek…   →   Önce tema açılır: Eşik ne demek…   (TDK: iki noktadan
sonra bağımsız cümle geliyorsa büyük harf — altı Açık Kapı ve dört Çember'e uygulandı)

# Çember
İstediğin kadar konuşursun ya da "pas" dersin; ikisi de aynı ağırlıkta.        → SİLİNDİ
Bu turun uzun sürmesi normaldir. Çemberin kalbi burasıdır… çemberin parçasıdır. → SİLİNDİ

- Tema bölümü kaydedilebilir, gelemeyen kadınlar erişsin diye
- Paylaşım turu kaydedilmez — söylenen o çemberde kalır
→ - Çember kaydedilmez — söylenen o çemberde kalır

Baştan başlıyoruz; geç kalırsan sessizce katıl, tur bozulmaz
→ Baştan başlıyoruz; çember açıldıktan sonra kapı kapanır

## Yanına Al — son iki madde çıktı, yerine:
Buluşmadan önce gerekli başka bir şey varsa sana yazıyoruz.

# Seremoni
"Pas" demek de konuşmak kadar makbul.                        → SİLİNDİ
Bundan sonrasını şimdiden anlatmıyoruz — anlatılınca…        → Bundan sonrası her seferinde başka.
Katılım kaydı alınır… Ses ya da video kaydı alınmaz…
→ Tema ve seremoni kaydedilir; paylaşım turu kaydedilmez — söylenen o akşamda kalır
Pratik Bilgi: beslenme · aç karnına · ilaç · hamilelik satırları SİLİNDİ
```

---

## 6 — YAZIM SIRASI

1. Kronoloji dilimi (`90-kronoloji/2026-08.md`) — append-only, çapalar burada doğar
2. `01-kararlar.tsv` — K-A/B/C/D'ye numara ver, 506'yı SUPERSEDE'e çevir, çapraz referansları doldur
3. `02-borclar.md` — 21 borç, numaralar sırayla
4. `03-sira.md` — sıradaki iş: Sayfalar DB dokuz sayfa, sonra deploy
5. `00-durum.md` — 200 satır kapağında; yazım için **ayrı onay** al

Satırlar `printf` ile üretilsin; sekme markdown'dan kopyalanmaz.
