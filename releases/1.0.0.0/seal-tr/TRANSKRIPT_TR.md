# 1.0.0.0 — LLM Test Office tanıtımı · Türkçe transkript

Cümle başına bir satır. Sesler: `[VOICE:HOOK]` kanca, `[VOICE:NARRATOR]` anlatıcı, `[VOICE:CLOSER]` kapanış. 152 cümle; Türkçe cümle N = İngilizce cümle N. Okunuş yazımı ses motoru içindir (ör. 'ey ay' = AI, 'i-di-ay' = EDI, 'kü dört' = Q4).

## KANCA

[VOICE:HOOK] [PARAGRAPH:kanca]
Masamızda test konusu olarak faturalar var.
Temiz bir faturada, yapay zekâ modeli kullanmayan, saf yazılım temelli bir uygulama her on faturanın yedisini okuyor.
Sıfırlar büyük O, birler küçük el olunca, tam okumada iki yüz faturanın yalnız altısını çıkarabiliyor.
Aradaki boşluğu küçük bir ey ay modeli doldurabilir mi?

## GİRİŞ

[VOICE:NARRATOR] [PARAGRAPH:amac]
Amacımız, en küçük modellerden başlayarak, yerel ey ay modellerini hangi konularda ve en verimli olacak şekilde kullanabiliriz sorusuna cevap aramak.
Bunun için insanların denemelerini kaale alıp, gerçek hayat verileri yahut gerçek hayat verilerine uygun şekilde üretilmiş, yani içinde hata da barındıran verilerle çalışan motorlarla test ediyoruz.
Testlerimiz klasik benchmarklara hiç benzemiyor.

[PARAGRAPH:itiraf]
İtiraf edeyim, bir modelin içini, teknolojisini en ince detayına kadar bilmiyorum ve bilemem.
Odaklandığım nokta, modelin bize ne verebileceği; bunu da gerçek ölçümlerle yapmayı hedefliyoruz.
Süreç sadece olumlu haberlerden ibaret değil.
Nerede hangi hatayla karşılaştık, hangi modelde hangi düzeltmeyle iyileşme sağladık; hepsi, yaratmaya çalıştığımız dijital arşivin bir parçası.

[PARAGRAPH:cihaz]
Elimizde şu an test cihazı olarak Asus ProArt he ne yetmiş üç sıfır altı model laptop var.
Şahsıma ait bu cihazın yüz yirmi sekiz gigabayt birleşik bellek içeren yapısı, özellikle çoklu model denemeleri için güzel bir ortam sunuyor.
Elimizdeki cihaz bir süper bilgisayar olmadığı gibi, piyasa ortalamasının altında da değil.
Bu sebeple yaptığımız testleri farklı cihazlara da yayıyoruz; sadece si-pi-yu yongalı bir ofis mini bilgisayarı da, harici ekran kartlı bilgisayarlar da test sistemimizin bir parçası.

[PARAGRAPH:gorev_adami]
Ey ay modellerin yetenekleri, basit tabirle, parametre sayısı büyüdükçe büyüyor diyebiliriz.
Bu dediğimden, daha düşük parametreli olup belli konularda daha iyi sonuç veren modeller olmadığı çıkarılmamalıdır.
Parametre sayısı düşük modelleri görev adamı, parametre sayısı yüksek modelleri hem fikir adamı hem görev adamı olarak tanımlamak mümkün.

[PARAGRAPH:kucukler]
Bizler bazen basit bir modeli kullanabilecekken koca koca modelleri basit işlere koşuyor, hem nakit hem vakit açısından zarara uğruyor, çoğu zaman da bunun farkında olmuyoruz.
Claude, GPT ve sair modellerin mükemmel işler yarattığı zaten biliniyor.
Asıl bilinmeyen cepheye ışık tutmayı önceledik ve bu sebeple küçük modellerden başlamayı tercih ettik.
Kanalın kendisini ayrıca anlattığım kısa bir video var; isterseniz bağlantısı ekranın köşesinde duruyor.

## TEST OFİSİ

[VOICE:NARRATOR] [PARAGRAPH:derlem]
Önce boyutu seçtik ve aralığı bir ila iki buçuk milyar parametre olarak belirledik.
Sonra insanlara kulak verdik.
İki bin yirmi dört yazından bu yana GitHub, Hugging Face ve Hacker News'te bu boyuttaki modellerle neler yapıldığını taradık ve kim ne başarmış, kim ne sormuş, kim ne denemiş ve yarı yolda bırakmış sorularına yanıt aradık.

[PARAGRAPH:kirk_alti]
Ortaya birbirinden farklı kırk altı iş çıktı.
Hem daha ileri testlerimizde bize hem de izleyenlerimizden belli meslek grubunda olanlara yol göstermesi adına bu kırk altı işi, birbiriyle ilintili olanlar bir arada olacak şekilde gruplandırdık.
En kalabalık grup ofis işlerini ilgilendiriyordu.
Her test konusu bir idari asistanın yahut ön muhasebecinin gün içinde sıklıkla yaptığı işlerdendi.
Biz de testlerimize bu büyük konu kümesi ile başladık.

[PARAGRAPH:test_office]
El-El-Em Test Office on iki ayrı işi kapsıyor.
İleride testlerimizde teker teker inceleyeceğimiz işler sırasıyla şunlardır.
Bir: e-postadan tarih ve gönderen bilgisini çıkarmak.
İki: bir metinden sayı ve ölçü çıkarmak.
Üç: fatura gibi bir belgenin görüntüsünden düzenli veri çıkarmak.
Dört: taranmış bir belgedeki yazıyı okumak.
Beş: iş yerine dair soruları cevaplamak.
Altı: bilgisayardaki dosyalar arasında arama yapmak.
Yedi: uzun bir metni özetlemek.
Sekiz: e-posta taslağı yazmak ve gelen e-postayı özetlemek.
Dokuz: sert bir mesajı kibar bir tona çevirmek.
On: bir cümleyi yeniden yazmak.
On bir: dil bilgisi hatalarını düzeltmek.
On iki: bir mesaja cevap önerisi sunmak.

[PARAGRAPH:neden_fatura]
İşe belge okumayla başladık ve belge olarak faturayı seçtik.
Fatura her ofisin masasına gelir, internette gerçek örnekleri bulunur ve okurken yapılan küçük bir hata doğrudan mali zarar doğurabilir.

[PARAGRAPH:amerika]
Kanal adresi Amerika olduğundan test parametreleri de buna göre belirlendi: para birimi dolar, tarih biçimi Amerika tarih biçimi ve dil İngilizce.
Test sürecinde bizi şaşırtan bir bilgiyle karşılaştık: Amerika'da devletin belirlediği tek tip fatura zorunluluğu yok.
Her muhasebe programı kendi geleneğini kurduğundan birbirinden farklı fatura tipleriyle karşılaştık.

[PARAGRAPH:iki_dunya]
Aslında farklı stillerdeki faturalardan da önce şunu fark ettik.
Amerika'da iki farklı fatura dünyası vardı.
Biri insanlar için kâğıda basılabilen tür, diğeri ise sadece makineler arasında ortak bir dili kullanan farklı bir türdü.
Biri insanın gözü için yazılmış; kutuları, başlıkları ve kalın bir toplamı vardır.
Öbürü ise makinenin makineye yazdığı, satır satır işaretli düz bir metin olan i-di-ay'dır.

## MOTOR

[VOICE:NARRATOR] [PARAGRAPH:kural_mahremiyet]
Ortak test motorunu kurarken kendimize üç kural koyduk.
Birincisi: gerçek veri kullanmadık, gerçeğe benzer veri üretici bir mini motor yazdık.
Satıcı adları ve telefonları her seferinde değiştirdik.
Alıcı adını ise Test Office olarak sabit tuttuk.

[PARAGRAPH:kural_katalog]
İkincisi, faturada kullanılacak malları önceden belirledik.
Üretim motoru otuz dört farklı mal arasından farklı türlerde ve farklı adetlerde seçim yaparak her defasında farklı faturalar üretti.

[PARAGRAPH:kural_kayit]
Üçüncüsü, üretilen her fatura için doğru cevabı önceden belirledik.
Bunu yapmasaydık yazılım, model ve yazılım artı model değerlendirmelerinde sadece okuyucuyu değil, üreticiyi de ayrıca kontrol etmemiz gerekecekti.

[PARAGRAPH:ezber]
Test sürecinde, yazdığımız modelsiz yazılımın test verisini okumadığını ve ezberlediğini fark ettik ve hemen müdahale ettik.
Verilerin yerlerini değiştirdik; fatura numarası, tarih, toplam gibi bilgilerin etiketlerini çeşitlendirdik ve ezberin önüne geçmeyi başardık.
Aynı bilgi artık her faturada başka bir adla, başka bir köşede bekliyor; örnekleri şu an ekrandadır.

[PARAGRAPH:kademe]
Test iki kademeden oluşuyor.
Birincide modelden beş bilgi istiyoruz: fatura numarası, tarih, satıcı, vergi ve toplam.
İkincide ise hepsini istiyoruz: vade, sipariş numarası, indirim, kargo gibi tüm kalemler.
Biri diğerinden farklı zorlukta olan bu iki iş, bize test öncesi şu tahmini veriyor: basit işte hızlı ve düşük parametreli model, zor işte yavaş ama daha büyük parametreli model tercih edilmeli.
Burada test parametre sınırları içinde konuştuğumuz unutulmamalı.
Peki sizce durum tahmin ettiğimiz gibi mi oldu?

[PARAGRAPH:bozma]
Tertemiz veriyle yapılan bir test bize bir şey öğretmezdi.
Bu yüzden faturayı okuyabileceğimiz üç farklı senaryo ürettik: temiz metin, tarama makinesinden geçmiş gibi gürültülü metin ve sayfanın kendi resmi.
Gürültüyü gelişigüzel kurmadık.
Tarama makinesinin gerçekten karıştırdığı, birbirine benzeyen karakterleri değiştirdik: sıfır ile büyük O, bir ile küçük el ya da büyük I.
Bir rakamı hiçbir zaman başka bir rakama çevirmedik.
Bu işlem test verisini zorlaştırıcı değil değiştirici nitelikteydi.
Bu nedenle test kapsamına almadık.

[PARAGRAPH:edi]
Üretici aynı kaydı dört düzende basabiliyor: klasik, kompakt, e-posta ve i-di-ay.
İ-di-ay faturalarını ayrı bir kulvarda tutuyoruz.
Peki makinenin makine için yazdığı bir faturayı okumak için model gerekir miydi?
Bunu da test ettik ve düz bir ayrıştırıcının i-di-ay faturalarını okuma noktasında kusursuz çalıştığını fark ettik.
Model zekâsına ihtiyaç duyulmayan bu fatura türünü test dışı bıraktık.

[PARAGRAPH:kusur_bir]
İlk denemelerde her hatanın önüne bir soru koyduk: yanılan model mi, motorun kendisi mi?
Dört kusur tespit ettik.
Vergi işareti ürün adının sonuna yapışmıştı; modeller onu adın parçası sandı, işareti ayrı bir sütuna aldık.
Fatura içeriğindeki veri sayısı çok daha fazla olduğundan gürültüyü fatura numaralarından uzak tuttuk ve test motorunun ürettiği tüm faturaların değerlendirilmesini ve değerlendirme sonucunun bize gelmesini sağladık.

[PARAGRAPH:kusur_iki]
Biçimi de baştan söylememiştik; tarihi her model başka yazıyor, indirimi kimi eksiyle veriyordu.
Artık tarihi yıl ay gün sırasıyla, indirimi de artı olarak istiyoruz.
Son kusur bir zincirdi: kalemler sırayla eşlendiği için tek bir yanlış, arkasındakilerin de yanlış sayılmasına yol açıyordu.
Şimdi önce açıklamaya, sonra adet ve fiyata bakıyoruz.
Modelden kaynaklanan kusurlara dokunmadık; model bazlı test sürecinde adalet gereği test motorunun yazılım kısmını iyileştirmeye çalıştık ve daha önce dediğimiz gibi model kullanımını gerektirmeyen i-di-ay fatura tipini test sürecine dahil etmedik.

[PARAGRAPH:ders]
Bir de saklamadığımız bir ders var.
Satıcı adını tarif ederken modele "adres, telefon, e-posta yazma" dedik.
Küçük modeller tam da o telefonu satıcı adı diye yazdı.
Talimatı geri aldık ve modele yasak listesi vermeme kararı aldık.

## KANIT

[VOICE:NARRATOR] [PARAGRAPH:dondurma]
Ortak test motorunu belirlediğimiz on farklı modelle koşturduk.
Ortak test motorunun tüm modellere aynı mesafede durmasına özen gösterdik.
Bir model adına yapılan değişiklikler, diğer bir modelin sonucunu etkilemiyordu.
Bu durum, ortak test ve ön inceleme sürecinde modeller hakkında belli hataları görmemizi sağladı ve bir model için doğru olanın diğer model için yanlış olduğu bilgisini bize getirdi.
Tüm bu verileri de ilerleyen süreçte modele özgü özel test sürecinde nasıl ele aldığımızı göreceksiniz.

[PARAGRAPH:taban]
Her testin yanında hiç model kullanmayan saf yazılımı da koşturduk.
Temiz faturada her on faturanın yedisini okuyordu; gürültü girince tam okumada iki yüz faturanın yalnız altısını çıkarabildi.
Burada şunu tespit ettik: temiz belgede saf yazılım çok daha hızlı ve az maliyetlidir.
Tam tersi, gürültülü metinlerde ise model zekâsı, tam olarak aradığımız kurtarıcı rolüne bürünüyor.
Asıl test malzememizi de bu nedenle gürültülü metinler oluşturuyor.

[PARAGRAPH:gercek_hayat]
Ortak teste özel belgeleri, gerçek hayat verisini bilerek sokmadık.
Çünkü hangi model ne açıdan yazılım desteği istiyor, hangi konularda iyi, başlangıçta bilmiyorduk.
Bu verilerin birçoğunu ortak testle elde ettik.
Ortak test anlatımları bitince başlayacağımız özel testler, her model için en iyi yazılım desteğini sunarken kontrol verisini de mümkün olduğunca gürültülü, okuması zor hale getirdi.
Bu özel testlerle suni olumlu sonuçlar almaya değil bir modeli gerçek bir iş ortamında kullanabilir miyiz sorusuna cevap alacak şekilde şartları zorlaştırarak koşturduk.

[PARAGRAPH:modeller]
Teste tabi tuttuğumuz model listesi, parametre sayısına göre artan şekilde şöyledir.
Gemma üç, bir milyar.
MiniCPM beş, bir milyar.
LFM iki ve LFM iki nokta beş.
Llama üç nokta iki.
SmolLM iki.
Qwen üç nokta beş.
Qwen üç nokta sekiz.
Qwen üç.
Son olarak iki buçuk milyar parametreyle MiniCPM beş.

[PARAGRAPH:hukum]
Bir modelden olumsuz sonuç almamız modelin genel yeteneği hakkında bir hüküm teşkil etmeyecek; yalnızca bu test sisteminde, bu verilerle ve bu çalışma şekliyle ondan aldığımız verimi gösterecektir.
Ortak testte her model kü dört kuantizasyon ayarıyla teste girdi.
Modelleri test ederken aynı zamanda en verimli çalıştırma şeklini ve koşullarını da test ediyoruz.
Bir model kü dört versiyonuyla verimli çalışıyorsa kü sekizi tercih edip hız kaybı yaşamaya gerek yok diye düşündük; kü sekiz, hatta bazı modellerde ef on altı versiyon testleri özel testlerde yer alıyor.

## ÖLÇÜM

[VOICE:NARRATOR] [PARAGRAPH:dogruluk]
Üç şeyi ölçüyoruz.
Birincisi doğruluktur; bu konuda puanımız katıdır: bir fatura ancak bütün bilgileri doğruysa ve cevap tam istenen biçimdeyse geçer.
Cevap doğru ama kod işaretlerinin arasına konmuşsa katı puan geçirmiyor; kaybetmemek için yanında esnek bir puan tutuyoruz.
İkisi arasındaki aralık, modelin okuyamadığını değil, paketi kuramadığını gösteriyor; o aralığı kapatmak özel testin işidir.

[PARAGRAPH:hiz]
İkincisi hızdır: bir faturanın kaç saniyede okunduğunu ve bir dakikada kaç fatura çıktığını ölçüyoruz.
Üçüncüsü ise bir ofisin asıl sorusudur: aynı anda birden çok iş gelirse ne oluyor?
Önce tekil testi koşuyoruz: bir model, bir istek, bir fatura.
Sonra aynı anda uçan fatura sayısını sekize çıkarıyoruz.
Yükü farklı biçimlerde dağıtıyoruz: modelin ayrı kopyalarına, tek kopyaya gelen sekiz isteğe ya da tek isteğin içindeki sekiz faturaya.
Hangisinin hızlandırdığını ve hangisinin doğruluğu koruduğunu ortak test videolarında gösteriyoruz.

[PARAGRAPH:yol]
Tanıtımını yaptığımız video serisi şu aşamaları kat ederek ilerleyecektir: ortak test süreci, ortak test süreç değerlendirmesi, özel test süreci, özel test süreç değerlendirmesi ve model sıralaması.
Sonrasında, hangi işte hangi modelin verimli çalıştığını tespit ettikten sonra, gerçek hayatta kullanılabilecek bir uygulamanın yazımı, kullanımı ve incelemesi geliyor.

[PARAGRAPH:arsiv]
Her testi, her sonucu ve test günündeki model dosyalarının kendisini saklıyoruz.
Sonuçları zaman damgası ve dijital imzayla mühürlüyoruz; sonradan bir şey değişirse, değiştiren biz olsak bile, bu hemen anlaşılır.
Çünkü modeller sürekli güncelleniyor ve yarın aynı testi yeni bir modelle koştuğumuzda dünle bugün arasındaki farkı tahminle değil, aynı ölçüyle söylemek istiyoruz.
Mühürlerin parmak izleri video açıklamasındadır.

## TOPARLAMA

[VOICE:CLOSER] [PARAGRAPH:toparla]
Başa dönelim.
Masada bir fatura vardı ve bir soru: aradaki boşluğu küçük bir model doldurabilir mi?
Temiz kâğıtta basit bir program işin çoğunu görüyor; kâğıt bozulunca tökezliyor.
Küçük modellerin değeri tam o boşlukta aranır; bunu varsayarak değil, ölçerek gösteriyoruz.
Ortak test motoru kuruldu, kusurları ayıklandı, donduruldu.
Ortak test motoru tamamlandı; şimdi fatura örnekleri masada ve sıra modellerde!

## SIRADAKİ VİDEO

[VOICE:HOOK] [PARAGRAPH:siradaki]
Bir sonraki videomuzda ortak testlere başlıyoruz.
İlk sırada MiniCPM beş ve Gemma üç var.
Ardından Llama üç nokta iki geliyor.
Sonra SmolLM iki.
İki yüz faturalık ortak testin sonucu için takipte kalın.
