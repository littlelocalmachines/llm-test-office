# 1.1.1.2 — Fatura ortak testi, 2. grup · Türkçe transkript

Cümle başına bir satır. Sesler: [VOICE:HOOK] kanca, [VOICE:NARRATOR] anlatıcı, [VOICE:CLOSER] kapanış. 118 cümle. Okunuş yazımı ses motoru içindir (ör. 'ey ay' = AI, 'el-ef-em' = LFM, 'kü dört' = Q4).

## KANCA

[VOICE:HOOK] [PARAGRAPH:kanca]
Ortak test motoru arenamızın ikinci günündeyiz ve bu kez arenaya ikinci gruptaki üç modelimiz çıktı.
Bu grupta aynı şirketten, birebir aynı boyutta iki model karşı karşıya geliyor.
Eski sürüm iki yüz faturanın yetmiş yedisini doğru okurken, yeni sürüm yüz altmış birini çıkarıyor.
Bozulmuş faturalarda ise saf yazılım elli beşine tutunabilirken, yeni sürüm yüz üçünü doğru okuyor.
Ortak test süreci maksimum verim almaktan öte hata tespitine yönelik olmasına karşın yine çok çarpıcı sonuçlar elde ettik.
Gelin beraber inceleyelim.
Başlıyoruz!

## GİRİŞ

[VOICE:NARRATOR] [PARAGRAPH:turnusol]
Kanalımıza doğrudan bir test videosundan, belki bir model adını aratarak gelenler için baştan bir şey söyleyelim: ortak test bir turnusol kâğıdı gibi çalışıyor.
Bütün modellere aynı istemi, aynı kuralı ve aynı cevap biçimini veriyoruz; amacımız bir modeli mahkûm etmek değil, hangi modelin nerede takıldığını ve takılmanın sebebinin model mi, yoksa bizim kurduğumuz paket mi olduğunu ayırmak.
Bu yüzden bazı düşük puanlar modelin okuma becerisinden değil, cevabın bizim beklediğimiz biçimde paketlenmemesinden geliyor; bunları gördüğümüz yerde tek tek işaretliyoruz.
Ortak testte takılan modeller, sonraki özel test videolarında, test motorumuz o modele göre ayarlanarak yeniden sınanacak.

[PARAGRAPH:hesap]
Önce bu testin kurallarını koyalım ki sonuçları birlikte okuyabilelim.
El-El-Em Test Office'in Belge Tarama dalında, fatura konusunun ikinci ortak testine üç model girdi.
Üç modele de ilk gruptaki modellerin gördüğü aynı iki yüz faturayı verdik.
Böylece iki model arasında çıkan fark faturadan değil, modelin kendisinden geliyor.
Testi iki kademeye ayırdık.
İlk kademede faturanın beş temel bilgisini sorduk: numara, tarih, satıcı, vergi ve toplam.
İkinci kademede ise kalemleriyle birlikte faturanın tamamını istedik.

[PARAGRAPH:puan]
İki farklı puanlama sistemi kullanıyoruz.
İlki katı sistem.
Doğru cevabı belirli bir şekil şartı ile talep ediyoruz.
Bir modeli baz alan uygulama çalışırken sorun çıkmaması için modellerin bu şekil şartına bağlı kalması gereklidir.
İkincisi ise esnek sistem.
Bu sistemde şekil şartına takılmadan doğru içerik kontrolü yapıyoruz.
Bu iki farklı okuma hem model yetenekleri hem de modele verilmesi gereken yazılım desteği türü ve miktarı hakkında bize kıymetli bilgiler getiriyor.
Karşılaştırmayı bir kademe daha geliştirmek adına saf yazılımı da koşturduk ve iki yüz temiz faturada aldığı yüz kırk iki doğru sonucu genel değerlendirmeye dahil ettik.

[PARAGRAPH:ortam]
Test süreci Asus ProArt HN7306 modeli bilgisayarımızda, cihaz şarjdayken ve güç modu olarak tüm ayarların maksimumda tutulduğu manuel mod seçiliyken yapılmıştır.
Ölçümlere dair sadece sonuç verilerini değil, hız verilerini de paylaşacağız.
Bu grubu ilk gruptan iki gün sonra koşturduğumuz için güç ayarının hızı etkileyip etkilemediğini ayrıca kontrol deneyiyle sınadık ve hiçbir fark olmadığını doğruladık.

## MODELLER

[VOICE:NARRATOR] [PARAGRAPH:modeller]
Bu grupta üç model var; ikisi aynı ailenin eski ve yeni sürümü, üçüncüsü ise grubun en büyüğü.
Üçünü de kü dört nicemlemesiyle, aynı ayarlarla koşturduk.

[PARAGRAPH:lfm2]
İlk model Liquid AI'ın bir nokta iki milyar parametrelik modeli el-ef-em iki oldu.
Temel bilgileri istediğimiz kolay testimizde model, iki yüz faturanın yetmiş yedisini doğru okudu.
Hatalarının çoğu yanlış değerden oluşurken, yirmi beş faturada da bizim istemediğimiz fazladan bilgileri cevaba ekledi; biz beş bilgi sorarken model fazlasını yazdı.
Dakikada kırk altı fatura okuyan bu model, bir belgedeki tüm bilgileri dahil ettiğimiz zor testte ise hiç doğru cevap veremedi; faturaların çoğunda istenen bilgilerin bir kısmını hiç yazmadığı için esnek okumada da sonuç sıfır kaldı.

[PARAGRAPH:lfm25]
İkinci modelimiz aynı ailenin yeni sürümü el-ef-em iki nokta beş modeli.
İlk modelle birebir aynı boyutta, yani bir nokta iki milyar parametre içeriyor.
Model kolay testimizde iki yüz faturanın yüz altmış birini doğru okuyarak yüzde seksene ulaştı ve saf yazılımın üstüne çıktı.
Böylece şu ana kadar ölçtüğümüz yedi model arasında kolay testin en yüksek puanını aldı.
Cevabının biçimi hiçbir faturada bozulmadı, otuz dokuz faturadaki hatanın tamamı değer hatasıydı ve dakikada elli dokuz fatura okudu.
Zor testte ise iki yüz faturanın tam boy okuması görevinde on ikisini eksiksiz çıkardı.
Bu sonuçla ilk gruptaki SmolLM ikinin dört doğrusunu geride bıraktı ve şimdiye kadarki en yüksek zor test sonucunu verdi.

[PARAGRAPH:surum_farki]
İki sürümü yan yana koyduğumuzda doğru okunan fatura sayısı iki kattan fazla arttı.
Daha da öğretici olanı hataların türünün değişmesidir: eski sürümün fazladan bilgi yazdığı yirmi beş fatura yeni sürümde sıfıra indi ve bozuk cevapların hepsi ortadan kalktı.
Yani yeni sürüm yalnız daha çok doğru bulmuyor, kendisine verilen talimatı da daha iyi dinliyor.
Boyut ve mimari birebir aynı kaldığına göre farkın kaynağı sürümdür; eğitimin neresinin değiştiğini ise bu ölçümle ayırt edemiyoruz.

[PARAGRAPH:qwen3]
Üçüncü yarışmacımız grubun en büyüğü: Qwen ailesinden Qwen üç modeli.
Bu modelin adı bir nokta yedi milyar parametreyi işaret ediyor.
Kolay testimizde ise iki yüz faturanın doksan dokuzunu doğru okuyarak yüzde ellinin hemen altında kaldı.
Sekiz faturada doğru cevabı kod işaretlerinin arasına koyduğu için paketleme hatasına takıldı; esnek değerlendirmede ise doğru sayısı yüz yediye çıkıyor.
Motoru sabitlerken yaptığımız koşularda ve gürültülü testte modelin bozuk cevaplarına tek tek baktığımızda, düşünce kipini kapatmış olmamıza rağmen bozuk cevapların yaklaşık yarısında cevabın içine düşünce etiketinin sızdığını gördük.
Bu da modelin okumasından değil, cevabın paketlenmesinden gelen bir sorundur ve özel test videosunda üzerinde duracağımız ilk konulardan biri olacak.
Qwen üç dakikada otuz yedi faturayla grubun en yavaşı oldu.
Zor testte ise iki yüz faturadan beş başarılı sonuç verdi.

[PARAGRAPH:taban_esleme]
Burada durup ilk videoda sorduğumuz soruya tekrar baktık: model ile saf yazılım aynı faturalarda mı takılıyor?
Yeni sürüm el-ef-em iki nokta beşin doğru okuyup saf yazılımın kaçırdığı kırk dört fatura vardı.
Saf yazılımın doğru okuyup modelin kaçırdığı fatura sayısı ise yirmi beştir.
İlk grupta temiz metinde model ile saf yazılım arasında anlamlı bir fark bulamamıştık; burada ise fark modelin lehine çıktı ve istatistik sınamamızdan da geçti.
Böylece temiz bir faturada kurallarla çalışan saf yazılımı istatistik olarak geride bırakan ilk modelimiz el-ef-em iki nokta beş oldu.
Öteki iki modelde ise tablo tersine dönüyor; eski sürüm de Qwen üç de saf yazılımın okuduğu faturaların önemli bir kısmını kaçırdı.

## GÜRÜLTÜ

[VOICE:NARRATOR] [PARAGRAPH:gurultu_neden]
Tam olarak ey ay modellerinin yıldızlaştığı noktadayız.
Çünkü temiz metinle yapılan testlerde saf yazılımın aldığı yüzde yetmiş bir oranındaki değer, gürültülü metin söz konusu olduğunda, yani tarama makinesinden geçmiş gerçek hayat senaryoları masamıza geldiğinde, kabul edilemeyecek seviyelere geriliyordu.
Tanıtım videomuzda sorduğumuz "aradaki boşluğu küçük bir model doldurabilir mi?" sorusuna ilk gruptan sonra bu gruptaki modellerin ne cevap vereceğini şimdi göreceğiz.

[PARAGRAPH:gurultu_kural]
Faturayı bozarken aynı kuralı koruduk.
Yalnız birbirine benzeyen karakterleri birbiriyle değiştirdik: sıfır ile büyük O, bir ile küçük el ya da büyük ı, beş ile es harfi.
Bir rakamı başka bir rakama ise hiçbir zaman çevirmedik.
Öyle yapsaydık faturadaki bilgi yok olurdu ve doğru cevabı ne model ne de bir insan bulabilirdi.
Bilgiyi silmedik, yalnız gizledik; her faturanın doğru cevabı değişmeden duruyor.
Sonra aynı iki yüz faturanın bozulmuş hâllerini birinci kademede üç modele ve saf yazılıma okuttuk.

[PARAGRAPH:gurultu_taban]
Saf yazılımı tekrardan ele alalım.
Saf yazılım temiz iki yüz belgenin yüz kırk ikisini okuyordu.
Metin gürültülü olduğunda ise iki yüz faturanın yalnız elli beşine tutunabildi.
Kurallarla çalışan bir yazılım aradığı kalıbı bulamayınca durur; sıfırın yerinde bir O harfi gördüğü anda o faturayı kaçırıyor.

[PARAGRAPH:gurultu_lfm25]
Modelleri gürültülü teste tabi tuttuk.
Yeni sürüm el-ef-em iki nokta beş, iki yüz faturanın yüz üçünü doğru okudu.
Model de gürültüden etkilendi ama saf yazılımın yaşadığı kadar büyük bir kayıp söz konusu değildi.
Burada sayısal bir hız karşılaştırması vermiyoruz; temiz ve gürültülü metnin girdi verisi farklı olduğundan ve ayrı günlerde koşulduğundan böyle bir kıyas yanlış anlaşılabilir.
Teste giren belgeleri teker teker kontrol ettiğimizde saf yazılımın okuyamadığı ama modelin okuduğu altmış bir belge varken, tam tersi durumda yalnız on üç belge var.
Temiz belgede on dokuz olan fark, gürültü devreye girdiğinde kırk sekize çıktı ve istatistik sınamamızdan çok güçlü biçimde geçti.
Böylece bir nokta iki milyarlık bir model, bu gürültü düzeyinde saf yazılımın açığının önemli bir kısmını kapattı.

[PARAGRAPH:gurultu_digerleri]
Öteki iki modelde ise tablo bu kadar net değil.
Eski sürüm el-ef-em iki, iki yüz gürültülü belgeden elli altısını doğru okudu ve saf yazılımla başa baş kaldı.
Qwen üç ise altmış sekiz doğru okumayla saf yazılımın biraz üstüne çıktı, ama aradaki fark istatistik olarak anlamlı değildi.
İlk grubun gürültülü sonuçlarıyla birlikte baktığımızda tablo netleşiyor.
El-ef-em iki nokta beş, yüz üç doğruyla şu ana kadar ölçtüğümüz yedi model arasında en yüksek gürültülü metin skorunu aldı.

[PARAGRAPH:gurultu_ii]
Testimizin en zor kısmı olan gürültülü ve tüm içerik okumasında ise üç model de ilk otuz faturada hiç doğru okuma yapamadıklarından teste devam edilmedi.
Modeller alanların bir kısmını kısmen okuyordu, ama kalemleriyle birlikte tam bir fatura çıkaramadılar.
Saf yazılım ise bu zorlu testte iki yüz faturanın yalnız altısını okuyabildi.

## ÇOKLU

[VOICE:NARRATOR] [PARAGRAPH:coklu_kur]
Sonra bir ofisin asıl sorusuna geçtik: aynı anda birden çok fatura gelirse ne oluyor?
Aynı anda işlenen fatura sayısını sekizde tuttuk ve bu yükü üç farklı biçimde dağıttık.
Faturaları ya tek bir isteğin içine koyduk, ya tek bir ajana aynı anda gönderdik, ya da modelin ayrı ajanlarına dağıttık.

[PARAGRAPH:coklu_sonuc]
Sekiz faturayı tek bir isteğin içine koyduğumuzda bu grupta da doğruluk çöktü.
Tek tek verdiğimizde yüz altmış bir faturayı doğru okuyan yeni sürüm, bu kez tek bir doğru cevap vermedi.
Bu sıfır da suni bir değerdir; çünkü sekiz faturayı tek pakette vermek bizim seçimimizdi ve model aynı faturaları tek tek verdiğimizde okuyordu.
Modelin sekiz ayrı ajanını yan yana çalıştırdığımızda ise doğruluk yerinde kaldı ve hız iki kat civarına çıktı.
Bu grupta yeni bir şey daha gördük: Qwen üç, tek bir ajanına aynı anda sekiz iş verdiğimizde de doğruluğu koruyarak hızını iki katın üzerine çıkardı; ilk gruptaki MiniCPM'de bu düzen hız kazandırmamıştı.

## SONUÇ

[VOICE:NARRATOR] [PARAGRAPH:sonuc]
İkinci grubun sonuçlarını bir arada toplayalım.
Temiz metinde temel bilgileri okuma işinde el-ef-em iki nokta beş yüzde seksene ulaştı ve saf yazılımın açıkça üstüne çıktı.
Aynı ailenin eski sürümü ve Qwen üç ise saf yazılımın gerisinde kaldı; Qwen üçün kaybının bir kısmı paketleme kaynaklıdır ve özel test videolarında yeniden ölçülecek.
Faturayı bozduğumuzda saf yazılım sarsılırken yeni sürüm model ayakta kaldı ve aradaki fark iki kattan fazla büyüdü.
Faturanın tamamını okuma işinde temiz metinde en iyi sonuç iki yüz faturada on ikiydi.
Gürültülü metinde ise modellerin hiçbiri ilk otuz faturada tek doğru veremedi.
Çoklu testte ilk grubun dersi değişmedi: tek istekte birden çok fatura doğruluğu bozdu; ayrı ajanlar ise doğruluğu koruyup hızı yaklaşık iki katına çıkardı.
Bu sonuçlar bu test sisteminde, bu verilerle ve bu çalışma şekliyle bu modellerden aldığımız verimi gösteriyor; modellerin genel yeteneği hakkında bir hüküm değil ve modellerden aldığımız nihai en iyi skorlar bunlar değil.
Her modeli tek tek ele aldığımız ve maksimum seviyede zorladığımız özel testlerde bu modelleri yeniden göreceğiz.

## DEĞERLENDİRME

[VOICE:CLOSER] [PARAGRAPH:degerlendirme]
Bence bu videonun en güzel tarafı, birebir aynı boyuttaki iki modelin arasındaki farkı aynı faturalarla görebilmemiz oldu.
Bize çoğu zaman büyük modelin daha iyi olduğu söyleniyor; burada ise büyüklük değişmeden yalnız sürüm değişti ve sonuç ikiye katlandı.
Bir de şunu söylemem lazım: kurallarla çalışan saf yazılımımızı temiz faturada bile ilk kez bir model açıkça geride bıraktı ve bunu yalnız daha çok doğru bularak değil, verilen talimata daha iyi uyarak yaptı.
Asıl heyecanlandığım an ise faturayı bozduğumuz andı; yazılımımız orada sarsılırken yeni sürüm model ayakta kaldı ve tanıtım videosunda sorduğumuz soruya şimdiye kadarki en net cevabı verdi.
Qwen üçün durumu da bence çok öğretici; düşünce kipini kapatsak bile o düşüncenin izi cevaba sızabiliyor ve bunu ancak cevapların içine tek tek bakınca görebiliyorsunuz.
Tam okuma işi ise hâlâ bu sınıfın üstünde duruyor; ama temiz metinde şimdiye kadarki en yüksek tam okuma sonucunu gördük ve bu bana bu işin kapısının kapalı olmadığını düşündürüyor.
Çoklu testten çıkardığım ders de ilk videoyla aynı: modele işi tek tek vermek, hepsini birden önüne yığmaktan daha doğru sonuç veriyor; en hızlı seçenek de genelde modelin ayrı ajanlarına birer iş vermek oluyor.

## SIRADAKİ VİDEO

[VOICE:NARRATOR] [PARAGRAPH:siradaki]
Bir sonraki videoda üçüncü ve son grup ortak teste tabi tutulacak.
Bunlar MiniCPM beşin büyük kardeşi, Qwen üç nokta beş ve topluluğun bu modelin üzerine eğittiği Qwen üç nokta sekiz damıtma modeli.
Bu üç model ortak testin en büyükleri.
O videoda boyut büyüdükçe sonucun da büyüyüp büyümediğine aynı faturalarla bakacağız.
Sizce boyut tek başına yeter mi, yoksa sürüm farkı yine öne mi geçer?
Takipte kalın.
