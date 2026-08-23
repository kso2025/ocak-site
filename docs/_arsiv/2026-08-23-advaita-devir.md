# DEVİR — Advaita site yorumları turu

**Bu dosyayı yeni sohbetin ilk mesajına yapıştır.** Proje: OCAK. Kaynak: Advaita'nın ~95 kalemlik yorum listesi — **kalanların tamamı §EK'te birebir yazılı, PDF'e gerek yok.**

---

## NEREDE KALDIK

**Bitti:** 14 etkinlik gövdesinin tamamı (Etkinlikler DB `Detay` property'si). Advaita'nın ~70 kalemi kapandı.
**Kaldı:** Sayfalar DB'de dokuz sayfa (~15 kalem) + sekiz soruluk C listesi + deploy.

**DEPLOY YAPILMADI.** Notion'da 14 gövde yeni, sitede eski. Bilinçli karar — bugün üç hata yakalandı, hiçbiri siteye ulaşmadı çünkü deploy sonda. Her şey bitince tek seferde.

---

## VERİLMİŞ DOKTRİN KARARLARI (yeniden tartışma)

**Kayıt** — bloğun cinsine göre, formatın değil. Anlatım ve uygulama kaydedilir; kadın kadına paylaşım kaydedilmez. Etkinlik başına `Kayıt Var` checkbox'ı otorite.
- Açık Kapı: tema+pratik kaydedilir, soru bölümü kaydedilmez
- Çember: hiç kayıt yok
- Seremoni: tema+seremoni kaydedilir, paylaşım kaydedilmez · `kakao-seremonisi-yuzyuze` istisna, hiç kayıt yok
- Atölye: anlatım+uygulama kaydedilir, paylaşımlar kaydedilmez

**Doz** — akış, hazırlık ve mahrem sorular kamuya açılmaz. Hazırlık gerektiren formatlarda `Yanına Al` işaretçiye iner. Beslenme/ilaç/hamilelik kayıt sonrası kanala.

**cacaoista** — `/advaita` künyesinde **kalıyor** (c ile). KARAR 506 daraltıldı: unvan yasağı sürüyor, betimleme eki serbest.

**Anadolu = kap, kaynak değil.** Bu zaten KARAR 299, KALICI. Yeni karar açılmadı; korpusta uygulanmamış iki yer borç olarak kaydedildi.

**Kapı** — süre verilmiyor: *"çember açıldıktan sonra kapı kapanır."*

---

## ÇALIŞMA PROTOKOLÜ (bugün üç hata bu protokolle yakalandı)

**Sıra sayfaya göre, gruba göre değil.** Bir sayfa açılır, o sayfaya ait tüm kalan yorumlar tek geçişte girer, kapanır. (Grup sırası `elin-neyle-dolu`'yu üç kez açtırdı.)

**Önce ölç.** Advaita'nın listesinin bir kısmı zaten uygulanmış. Her kalem için önce "bu hâlâ orada mı" sorgusu — yoksa düzeltilmiş şeyi ikinci kez bozarız.

**Property yazımı cerrahi değil.** `Detay` bir text property; `update_properties` alanın tamamını değiştirir, `old_str` güvenliği yok. Protokol:
1. Delta'yı `python3 len()` ile hesapla (`awk length` bayt sayar, Türkçe'de yanlış)
2. Karmaşıksa gövdeyi önce kabukta kur, uzunluğu doğrula
3. Yaz
4. Geri oku — ölçülen uzunluk beklenenle **birebir** tutmalı; tutmuyorsa hata var

**Sayfa gövdesi cerrahi.** `update_content` `old_str`/`new_str` alır, eşleşmezse yazmaz. Sayfalar DB için bu kullanılabilir — property riski orada yok.

**Kaçış dizisi kullanma.** Türkçe harfleri doğrudan yaz. `\u0131` yerine `u0131` yazılması bugün bir gövdeyi bozdu.

**Denetim deseni gevşek olmasın.** SQL `LIKE` büyük/küçük harf duyarsız: `%Pas%` "ku**pas**ını" içine düşüp yanlış alarm verdi.

---

## SONRAKİ İŞ — SAYFALAR DB, DOKUZ SAYFA

Data source: `collection://367b61eb-fa87-8170-a158-000b8f440fbe`
Etkinlikler: `collection://365b61eb-fa87-808d-84e2-000be0bcbdd5`

| Sayfa | Advaita'nın kalan yorumu |
|---|---|
| `/sen-neredesin` | "yargı" kelimesi (2. İlk dokunuş) → "yorum, tad ya da tanım" · Çember lideri → **rehber** (8. Taşıyıcı) · aşağı-kaydırma işareti yok |
| `/acik-kapi` | "kadın gelmeyi gerçekten istesin diye" → nesneleştirmiş, "sen" ya da "gelmek isteyen kişi" · **dakikalar silinsin**, bir saatlik buluşma bu kadar detaylı anlatılmasın |
| `/seremoni` | "Niyet tek başına düşünce…" → anlamadım *(C, soru)* · "Kakao ayda en az bir kez" → **bu taahhüdü vermeyelim** · "Kayıt yapılıyor mu" → **kayıt yapılmaz** |
| `/mini-retreat` | "yaban kadın / wild woman mı" *(C, soru)* |
| `/anadolu` | "Tanışma görüşmesi — sınav değil demek bile sınava işaret ediyor" |
| `/biz` | "Advaita tek dile getiren kadın" → tek o dile getiriyor gibi olmuş |
| `/advaita` | SSS son soru: "ulaşılabilir değil" rahatsız etti. **Ölçüm:** ibare artık yok, yeniden yazılmış; ama kalan *"Bu bir mesafe değil, alanın korunması"* hâlâ savunmacı |
| `/ekip` | "Çıraklık — konuşalım" *(C, soru)* |
| `/hikaye` | mum→ateş ✓ zaten yapılmış · Amerikalar ✓ zaten yapılmış · marker `bes-kadim-kaynak` → `dort-yon-bir-ocak` *(kod grep gerekir)* |
| `/bulusmalar` | "en hafifi… en ağırı" → **"en ağırı" olmasın**, "en derini" ya da "en uzunu" |
| `/araclar` | ✓ bitti (yedi→altı raf) |

**Yorum almamış ama taranmalı:** `/adimiz` · `/atolye` · `/cember` · `/felsefe` · `/iletisim` · `/sehir-aksami` · `/takvim` · `/yolculuk`. Özellikle **Çember Lideri → Rehber** ve **batı sıfatı** (wild woman / womb yoga / şamanik) taraması.

**Kod işleri (CC brief'i gerekir, metin değil):**
- Ana sayfa + `/sen-neredesin` aşağı-kaydırma işareti — ortak komponent
- "Hikâyeyi oku"ya tıklayan kullanıcı sayfalar arasında kayboluyor — dönüş yolu

---

## SEKİZ SORULUK C LİSTESİ (Advaita ile birlikte)

Bunlar yeniden yazım gerektiriyor, Advaita'nın kararı olmadan yapılmaz. Kaan bunları **Claude ile tartışarak** hazırlamak istiyor, sonra Advaita'ya gidecek.

1. `elin-neyle-dolu` adı — "sepetin olabilir mi" (sayfa artık sofra metaforuyla kapanıyor)
2. `ekmeden-once` adı — "ekme kelimesi oturmamış"
3. `kokun-nerede-kaldi` — **ad + çerçeve**. Advaita yeni bir bakış veriyor: gurbet kelimesinin ağırlığı, "kökler fiziksel yere bağlı değildir, sağlamsa seninle gelir", köprü/örmek/bağ. Ayrıca Advaita'nın gerçek hikâyesini veriyor: pandemide haftada iki gün İngiltere'deki Türklerle çalışmış, Açık Kapı fikri oradan doğmuş — mevcut metin bunu bilmiyor
4. `hangi-tohumu-ekeceksin` — "Kimin İçin" tamamı (çok eril, çok sert, "buna karışamayız") + büyük başlık "tamamen değişmeli"
5. `dusundugum-hissettigim-yaptigim` — ana başlık "Bu üçü en son ne zaman aynı yöne baktı?"; öneri "hizalı mı / nasıl hizalı olur / neye yarar"
6. `/mini-retreat` yaban kadın → "hatırlayan kadın"? Advaita uzun bir not yazmış: womb yoga/şamanik yoga gibi batı sıfatlarına duruş netleşsin istiyor
7. `/seremoni` "Niyet tek başına düşünce…"
8. `/ekip` çıraklık

⚠ **Slug değişirse** URL + Notion + MailerLite `etkinlik_url` + sosyal plan E-kartları etkilenir. Başlığı slug'a dokunmadan değiştirmek mümkün — ayrı karara bağlanmalı.

---

## AÇIK UÇLAR

- `Kayıt Var` işaretleme doğrulanmalı: işaretli = 6 Açık Kapı + `hasat-ve-sukran` + `kakao-seremonisi-online` + `rituel-tasarimi`
- `/advaita` SSS'in kalan savunmacı tonu
- Gölge satır `Ritüel Tasarımı | Gölge 0210 o#2` — Detay bayat (4.904 vs 4.541), takvim amaçlı, yayında değil, bilerek dokunulmadı
- Advaita'nın PDF'inde **program tasarımına ait** bir bölüm var (Açık Kapı içerik matrisi, Merhaba–Ayni çerçevesi, ritüel tanım metni, "13 ay ay döngüsü???", Ağustos ortası çember başlangıcı). Bunlar site patch'i değil — ayrı sohbet
- `docs-patch-2026-08-23.md` CC'ye verildi mi, uygulandı mı?

---

## SON UZUNLUKLAR (bekçi bantları bunlardan yeniden üretilecek)

```
Açık Kapı   3036–3264   (bir-esikte 3226 · bu-ses 3212 · dusundugum 3049
                         istek-mi 3118 · kokun 3036 · nereye-kadar 3264)
Çember      3480–3771   (ekmeden-once 3505 · elin-neyle-dolu 3771
                         hangi-tohumu 3480 · neyi-bekliyorsun 3720)
Seremoni    3605–3686   (hasat 3672 · kakao-online 3605 · kakao-yuzyuze 3686)
Atölye      4541        (rituel-tasarimi)
```

Eski bantlar (`Çember 3.824–4.113`) **geçersiz** — bekçi yanlış hedef gösteriyor.

---

# EK — ADVAITA'NIN KALAN YORUMLARI (birebir)

Sol sütun onun **Yorum**u, sağ sütun onun **Öneri**si. Yazım hataları dahil olduğu gibi; kendi kelimesi kayıp gitmesin. PDF'te iki sütun ayrı tablolardaydı, eşleşme yer yer kaydırılmıştı — belirsiz olanları işaretledim.

---

## `https://www.ocak.biz/` (ana sayfa)

**Neresi:** Ateşin yanına gel
**Yorum:** Aşağı kaydırma hissi gelmiyor
**Öneri:** Aşağı işaret eden bir 'şey' ok gibi

---

## `/sen-neredesin`

**Neresi:** Bir kadının yolu
**Yorum:** Burada da aşağı indirme hissi eksik
**Öneri:** Aşağı işaret eden bir 'şey' ok gibi (belki böyle sayfalara ortak bir işaret)

**Neresi:** 2. İlk dokunuş — "İlk gelişin sürprizi var, hâlâ bir yargı geliştirmemişsin."
**Yorum:** Yargı kelimesi
**Öneri:** Yorum, tad ya da tanım olabilir

**Neresi:** 8. Taşıyıcı — "Çember lideri eğitimi"
**Yorum:** Lider değil de
**Öneri:** Rehber belki

---

## `/acik-kapi`

**Neresi:** "Kadın gelmeyi gerçekten istesin diye"
**Yorum:** Bunu daha farklı anlatabiliriz. Ve kadın demek biraz nesneleştirmiş.
**Öneri:** Kadın yerine direk sen diyebiliriz. Ya da 3. Tekil şahıs olarak ifade etmek gerekirse gelmeyi isteyen kişi yazılabilir. / Gelmek isteyen kişinin niyetinin netleşmesi için gibi bir cümle daha düzgünü

**Neresi:** "Bir nefes al"
**Yorum:** Dakika dakika verilmiş. Ne gerek var. Bu bilgi benim için iyi ama okuyan için zihinsel yük
**Öneri:** Dakikaları silelim :) / Bir saatlik bir buluşmayı bu detaylı anlatmayalım. Biraz mekanik hissettiriyor

---

## `/seremoni`

**Neresi:** "Niyet tek başına düşünce…"
**Yorum:** Bunu anlamdım *(anlamadım)*
**Öneri:** — *(C listesi #7, konuşulacak)*

**Neresi:** "Kakao ayda en az bir kez"
**Yorum:** Bu taahhütü vermeyelim

**Neresi:** Kayıt yapılıyor mu
**Öneri:** Kayıt yapılmaz

---

## `/mini-retreat`

**Neresi:** Yaban kadın
**Yorum:** Wild woman mı
**Öneri:** Başka isim bana anlatırsan ne demek istediğini bakarız

**Ayrıca uzun notu (birebir):**
> Doğa kadın nasıl olur? Doğanın parçası olduğunu hatırlayan. Toprak anne gibi. Yaban kelimesinin götürdüğü yeri düşününce doğaya, toprağa, özüne dönen, hatırlayan kadın gibi… hatırlayan kadın.
> Doğa-l kadın. Doğal kelimesi değil ama. Doğal bir yere çeker.
> Yoganın başına batı sıfatlar geitiriyor.. womb yoga güzel bir amaca hizmet ediyor ama kullanım hali bira yogasından farksız. Burada bir duruşumuz olmalı.
> Mesela şamanik yoga ismi geldi bana da ama bir yandan doğru da gelmedi. Bunu kullanmıyorum bilinçli olarak.
> Duruşumuz netleşsin diye uzun uzun yazdım. İstersen konuşuruz da…
> Rahim için yoga / Rahim bilgeliği için yoga / Rahim sağlığı için yoga gibi başlıklar olabilir

---

## `/anadolu`

**Neresi:** Tanışma görüşmesi
**Yorum:** Sıva değil demek bile sınava işaret ediyor *(sınav değil)*

---

## `/biz`

**Neresi:** "Advaita tek dile getiren kadın"
**Yorum:** Tek advaita dile geitriyor gibi olmuş
**Öneri:** Bu da tam oturmadı ama daha mı iyi sanki *(eşleşme belirsiz)*

---

## `/advaita`

**Neresi:** SSS'de son soruda
**Yorum:** Ulaşılabilir değil ifadesi şahsi olarak rahatsız etti
**Öneri:** İkinci cümleyi silsen bile yeterli

> **Ölçüm notu:** "ulaşılabilir değil" ibaresi metinde artık yok, yeniden yazılmış. Kalan cümle: *"Bu bir mesafe değil, alanın korunması. Çember bir terapi alanı değildir; ciddi kriz anlarında bir uzmana yönlendirme yapılır."* — hâlâ savunmacı.

---

## `/ekip`

**Neresi:** Çıraklık
**Yorum:** Konuşalım *(C listesi #8)*

---

## `/hikaye`

**Neresi:** Merkez — "Her çemberin mumu" → **zaten yapılmış** ("her çemberin ateşi")
**Neresi:** Batı — "Amerikalar" → **zaten yapılmış** ("Kadim Amerika")

---

## `/bulusmalar`

**Neresi:** "En hafifi… en ağırı…"
**Yorum:** En ağırı olmasın
**Öneri:** En derini olabilir ya en uzunu yazıver

---

## Tarihli notlar (sayfa belirtilmemiş)

**21 Temmuz:** "Çember liderlik eğitimi" → **Çember rehberlik eğitimi**

**29 Temmuz — İlk sayfa:** Hikayeyi oku ya tıklayıp sonra kayboluyorlar sayfalar arasında
**Öneri:** Hikayeyi oku linki sen neredesin linkinin üzerine gelebilir

**19 Ağustos — Buluşmalar / Açık kapı:** *(satır var, yorum metni boş)*

---

## `bu-ses-kimin` — çözülmemiş satır

**Neresi:** "Kendine hala" / "Çember buluşmaları"
**Yorum:** *(yok)*

Metinde karşılığı: *"Kendine 'neden hâlâ yapmadım' diye soran…"*. Ne demek istediği anlaşılmıyor — Advaita'ya sorulacak.

---

# C LİSTESİ — ADVAITA'NIN KENDİ KELİMELERİYLE

Yeniden yazım gerektiren sekiz kalem. Onun ifadesi birebir; parafraz etme.

## 1 · `elin-neyle-dolu` adı

**Yorum:** Elin neyle dolu — bu isim değişebilir.
**Öneri:** Ellerin… belki / Sepetin olabilir mi? / Heyben, cebin olmasın. Bohça farklı bir manada. Sepet gibi bir şey iyi sanki.

Büyük başlık için ayrıca:
> Ellerin dolu… Sepetin belki artık. Ama adını sepetinde ne var desek de burada ellerin olabilir çünkü sofraya koyuyor :)

*(Not: sayfa artık sofra metaforuyla kapanıyor — "sen getirdiğini sofraya koyuyorsun, birlikte görüyoruz" / "Gel, sofraya koy". İsim kararı buna bakarak verilmeli.)*

## 2 · `ekmeden-once` adı

**Yorum:** Adı ekmeden önce — ekme kelimesi oturmamış
**Öneri:** Ekimden önce olsa? Ekme mevsiminden önce, (sen yazmışsın çok güzel) ekme döneminden, vaktinden gibi de olabilir

## 3 · `kokun-nerede-kaldi` — ad + çerçeve

**Advaita'nın verdiği gerçek arka plan:**
> Advaitayı anlatırken pandemi ile birlikte online alanda haftada iki gün ingilterede yaşayan Türklerle birlikte çalışıyor. Onlarla olan yol arkadaşlığı yaşamının özel bir yerinde, bu açık kapı konusu da buradan doğdu.

**Çerçeve itirazı (birebir):**
> Gurbette yaşayan Türkler… gurbet kelimesi bile bir konu; kimi derinden sahiplenir, kimini rahatsız eder bu kelime.
> O insanlar orada e yaşıyor, dertleri ne.
> Onlar köprü, kendi içlerinde de. Kökler fiziksel yere bağlı değildir. Sağlamsa seninle gelir. **Kökün nerede kaldı da doğru bir bakış açısı olmayabilir. Adını da değiştirelim.** Köklerden dallara, bağlarla yeniden örülen ağlara…
> Sadece oranın kültürüne alışmak değil buranın kültürünü de oraya taşımak, bağ oluşturmak, örmek.
> Ve bir kadın olarak gurbette yaşamak, aile kurmak, çocuk yetiştirmek…

**Ayrıca son paragrafa:**
**Yorum:** "kimse sana dönmeni söylemeyecek, kalmanı da…" → Niye böyle bir şey söylensin ki zaten. Dert, konu… o değil

## 4 · `hangi-tohumu-ekeceksin` — "Kimin İçin" + büyük başlık

**Neresi:** "Elinde birden fazla tohum var…" ile başlayan
**Yorum:** Bakacağımız yer o yine değil. Ona biz karışamayız.

**Neresi:** "Her tohum ekilmez" ile başlayan büyük başlık
**Yorum:** Üst satıra dayanarak bu da tamamen değişmeli

**Neresi:** Kimin için — "Aynı anda beş şey isteyen, hiçbirine başlamayan kadın için"
**Yorum:** Çok eril bir cümle olmuş. Davetkar değil, itici

**Neresi:** Kimin için — "İstediğini aldığında bile doymayan"
**Yorum:** Bu da çok sert. Şefkat, davet, anlayış yok

**Neresi:** Kimin için — "Bu kez bir tane seçmeye…"
**Yorum:** Buna da karışamayız ki, kadınlar çoğu zaman birden fazla şeyi seçmek zorunda…

**Öneri:**
> Daha çok şöyle… Ruhun çağrısı ne? Hangi tohumu ekmeye bedenin, kalbin davet ediyor?

**Ve şu notu düştü:**
> Anlamadığın yerleri benle konuşsan keşke, ama önce anlamadığını anlaman gerek tabii :) o yüzden böyle devam, çok teşekkür ederim emeğine

## 5 · `dusundugum-hissettigim-yaptigim` — ana başlık

**Neresi:** Ana başlık — "Bu üçü en son ne zaman aynı yöne baktı?"
**Yorum:** Bu soru ne amaçla yazıyor? En son ne zaman baktığına bakmıyoruz.
**Öneri:** Düşündüğüm, hissettiğim ve yaptığım hizalı mı? Olabilir. Hizalansın, nasıl hizalı olur ya da hizalı olması neye yarar gibi bir cümle olabilir.

## 6 · `/mini-retreat` yaban kadın → yukarıdaki uzun notu

## 7 · `/seremoni` "Niyet tek başına düşünce…" → anlamadı

## 8 · `/ekip` çıraklık → "konuşalım"

---

# PDF'İN SİTE DIŞI BÖLÜMÜ — AYRI SOHBET

Advaita'nın listesinin son üçte biri site metni değil, **program tasarımı.** Site turuyla karıştırılmasın; karıştırılırsa ikisi de yarım kalır. Başlıklar:

- **Açık Kapı içerik matrisi** — üç sütun: "Kadın kapıdan ne ile ayrılsın" / "Açık kapı konusu" / "Çember konusu"
- **Merhaba–Ayni çerçevesi** — "Merhaba: Sana yer açıyorum" · "Ayni: Aramızdaki dengeyi onurlandırıyorum" · içsel ayni ve karşılıklı denge
- **Eşik kadını vurgusu** — "Eşik kadını ne demek? Eşik kadını olduğunu nasıl anlarsın?"
- **Niyeti alt seslerden ayırt etmek** — iki boyut: niyetin kaynağı, ve ilerlemeyi engelleyen iç sesler
- **Çember takvimi** — "Ağustos ortası başlar???" · Ekim ekme dönemi, 21 Eylül ile başlar · toprağı havalandırma metaforu
- **Hasat çemberi çerçevesi** — "Ocak yeni başladı. Seneye birlikte hasadımızı yapacağız. Ancak sen de buraya boş gelmedin."
- **Ritüel tanım metni** — Advaita'nın yazdığı uzun tanım (niyet / sembolik eylem / eşik; tören ile ritüel farkı; İnanna, Kibele, Brigid, Baba Yaga)
- **Kaan'a soru:** "12 ay değil 13 ay ay döngüsü???"
- **Açık kapı malzemeleri:** mum, çakmak, defter, kalem, su
