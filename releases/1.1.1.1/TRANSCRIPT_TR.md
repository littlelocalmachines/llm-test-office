# 1.1.1.1 — Fatura ortak testi, 1. grup · Türkçe transkript

Cümle başına bir satır. Sesler: `[VOICE:HOOK]` kanca, `[VOICE:NARRATOR]` anlatıcı, `[VOICE:CLOSER]` kapanış. 112 cümle. Okunuş yazımı ses motoru içindir (ör. 'ey ay' = AI, 'el-ef-em' = LFM, 'kü dört' = Q4).

## KANCA

[VOICE:HOOK] [PARAGRAPH:kanca]
Tanıtım videolarımızda bahsettiğimiz ortak test motoru arenamız oldu ve bu arenaya en küçük dört modelimiz çıktı.
Ortak test süreci maksimum verim almaktan öte hata tespitine yönelik olmasına karşın çok güzel sonuçlar elde ettik.
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
El-El-Em Test Office'in Belge Tarama dalında, fatura konusunun ilk ortak testine en küçük dört model girdi.
Dört modele de aynı iki yüz faturayı verdik.
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
Karşılaştırmayı bir kademe daha geliştirmek adına saf yazılımı da koşturduk ve sonuçları genel değerlendirmeye dahil ettik.

[PARAGRAPH:ortam]
Test süreci Asus ProArt HN7306 modeli bilgisayarımızda, cihaz şarjdayken ve güç modu olarak tüm ayarların maksimumda tutulduğu manuel mod seçiliyken yapılmıştır.
Ölçümlere dair sadece sonuç verilerini değil, hız verilerini de paylaşacağız.

## MODELLER

[VOICE:NARRATOR] [PARAGRAPH:modeller]
Bu grupta dört model var ve hepsi iki milyar parametrenin altında.
Dört model dört ayrı yayıncıdan geliyor.
Dördünü de kü dört nicemlemesiyle, aynı ayarlarla koşturduk.

[PARAGRAPH:minicpm5]
İlk model OpenBMB'nin bir milyar parametrelik modeli MiniCPM beş oldu.
Temel bilgileri istediğimiz kolay testimizde model, iki yüz faturadan yüz kırk yedi adedini doğru okudu.
Her faturayı yarım saniye altında okuyan bu model, bir belgedeki tüm bilgileri dahil ettiğimiz zor testte ise hiç doğru cevap veremedi; hatta zor test cevaplarında bazı cevaplar okunabilir de değildi.

[PARAGRAPH:gemma3]
İkinci modelimiz Google'a ait Gemma üç modeli.
Model bir milyar parametre içeriyor.
Model kolay testimizde iki yüz belgeden yüz kırkını doğru okudu.
Bu yüzde yetmişlik skor katı okumada da, zor testte de yerini sıfıra bırakıyor.
Sebebi okuma değil; model doğru cevabı kod işaretlerinin arasına koyuyor, yani bu bir paketleme hatası.

[PARAGRAPH:llama32]
Üçüncü yarışmacımız Meta üretimi Llama üç nokta iki modeli.
İlk iki yarışmacımız gibi bir milyar parametreye sahip olan model, kolay test esnek değerlendirmede iki yüz faturadan üç adet doğru okuyabildi.
Tahmin edeceğiniz üzere zor testte ilk iki rakibi gibi, katı değerlendirmede de Gemma gibi başarılı okuma yapamadı.
Modelin diğer iki modelden düşük performans göstermesindeki en büyük hata, modelin çıktılarda rakamları tırnak içine alıp metin olarak yazmasıydı.

[PARAGRAPH:smollm2]
Dördüncü modelimiz grubun en büyüğü: Hugging Face ailesinden SmolLM iki.
Bir nokta yedi milyar parametreye sahip son modelimiz, kolay testte katı ve esnek okumada aynı sonucu vererek iki yüz faturadan yüz yirmi yedi adedini doğru okudu.
Hız konusundaki farkı açık şekilde görüyoruz.
Bu model bir okumayı MiniCPM'den üç kat daha yavaş yapıyor.
Saf yazılımın (yüzde yetmiş bir başarı) ve ilk iki modelin gerisinde kalmasına karşın zor testte sıfır çekmeyen ilk modelimiz oldu ve iki yüz faturanın tam boy okuması görevinde dört başarılı sonuç verdi.

[PARAGRAPH:taban_esleme]
Burada durup bir şeye daha baktık: model ile saf yazılım aynı faturalarda mı takılıyor?
MiniCPM'in doğru okuyup saf yazılımın kaçırdığı kırk bir fatura vardı.
Saf yazılımın doğru okuyup MiniCPM'in kaçırdığı fatura sayısı ise otuz altıdır.
İkisi aşağı yukarı aynı sayıda faturayı okuyor, ama aynı faturaları değil.
İstatistik sınamamız da aradaki farkı anlamlı bulmadı.
Temiz bir faturada bu boydaki bir model, kurallarla çalışan bir yazılımdan belirgin biçimde iyi değil; ondan farklıdır.

## GÜRÜLTÜ

[VOICE:NARRATOR] [PARAGRAPH:gurultu_neden]
Tam olarak ey ay modellerinin yıldızlaştığı noktadayız.
Çünkü temiz metinle yapılan testlerde saf yazılımın aldığı yüzde yetmiş bir oranındaki değer, gürültülü metin söz konusu olduğunda, yani gerçek hayat senaryoları masamıza geldiğinde, kabul edilemeyecek seviyelere geriliyordu.
Testlerimizdeki asıl zorlu kısımda modellerin ne yapacağını birazdan göreceğiz.

[PARAGRAPH:gurultu_kural]
Faturayı bozarken bir kural koyduk.
Yalnız birbirine benzeyen karakterleri birbiriyle değiştirdik: sıfır ile büyük O, bir ile küçük el ya da büyük ı, beş ile es harfi.
Bir rakamı başka bir rakama ise hiçbir zaman çevirmedik.
Öyle yapsaydık faturadaki bilgi yok olurdu ve doğru cevabı ne model ne de bir insan bulabilirdi.
Bilgiyi silmedik, yalnız gizledik; her faturanın doğru cevabı değişmeden duruyor.
Sonra aynı iki yüz faturanın bozulmuş hâllerini birinci kademede dört modele ve saf yazılıma okuttuk.

[PARAGRAPH:gurultu_taban]
Saf yazılımı tekrardan ele alalım.
Temiz iki yüz belgenin yüz kırk ikisini okurken metin gürültülü olduğunda bu sayı elli beşe geriledi.
Kurallarla çalışan bir sistemde bu kayıp büyük olarak nitelendirilir.
Ayrıca yazılımı kusursuz yapmak için çok uzun, çok çeşitli bir gelişim süreci güdülse bile o tepe noktaya belki hiçbir zaman erişilemeyecek.
İlk modellerde olmayan ama sonradan devreye alacağımız görsel okuma özellikli modellerle bu maliyete katlanmak gerekmeyecek ve o tepe noktaya model yardımıyla çıkılabilecek.
İşte tam bu sebeple, bunu tespit etmek için buradayız.

[PARAGRAPH:gurultu_minicpm]
Modelleri gürültülü teste tabi tuttuk ve ilk modelimiz MiniCPM beş, iki yüz faturada doksan birlik bir skor aldı.
Yazılımın yaşadığı kadar olmayan bir kayıp söz konusuydu.
Hız tarafında da sarsılma yok; model gürültülü faturayı da yarım saniyenin altında okudu.
Burada sayısal bir hız karşılaştırması vermiyoruz; temiz ve gürültülü metnin girdi verisi farklı olduğundan böyle bir kıyas yanlış anlaşılabilir.
Teste giren belgeleri teker teker kontrol ettiğimizde saf yazılımın okuyamadığı ama modelin okuduğu elli altı belge varken, tam tersi durumda yirmi belge var.
Temiz belgedeki bu farka anlam yüklemek zor olsa da, gürültü devreye girdiğinde değişen skorlar bizi ilk sorumuza götürüyor.
Ey ay modelleri yazılımla tam doğruluk arasındaki farkı kapatabilir mi, demiştik; daha ortak testlerde bile kısmen evet cevabını alıyor gibiyiz.

[PARAGRAPH:gurultu_digerleri]
SmolLM iki de aynı skoru verdi MiniCPM ile ve iki yüz gürültülü belgeden doksan birini doğru okudu; iki ayrı yayıncının modeli aynı skorda buluştu.
Gemma, temiz belge okurken yaptığı çıktı hatasını aynen tekrarladı; ama doğru sonuç üzerinden değerlendirdiğimizde iki yüz belgeden yüz üç başarılı okuma yaptı ve bu açıdan değerlendirildiğinde gecenin en başarılı gürültülü metin okuyucusu oldu.
Llama ise ilk otuz faturada hiç başarılı okuyamadığından teste devam edilmedi.

[PARAGRAPH:gurultu_ii]
Testimizin en zor kısmı olan gürültülü ve tüm içerik okumasında ise modeller ilk otuz evrakta hiç doğru okuma yapamadıklarından teste devam edilmedi.
Saf yazılım ise bu zorlu testte iki yüzde altılık bir skor elde etti.

## ÇOKLU

[VOICE:NARRATOR] [PARAGRAPH:coklu_kur]
Sonra bir ofisin asıl sorusuna geçtik: aynı anda birden çok fatura gelirse ne oluyor?
Aynı anda işlenen fatura sayısını sekizde tuttuk ve bu yükü üç farklı biçimde dağıttık.
Faturaları ya tek bir isteğin içine koyduk, ya tek bir ajana aynı anda gönderdik, ya da modelin ayrı ajanlarına dağıttık.

[PARAGRAPH:coklu_sonuc]
Sekiz faturayı tek bir isteğin içine koyduğumuzda doğruluk çöktü.
Tek tek verdiğimizde faturaların çoğunu okuyan MiniCPM, bu kez iki yüz faturanın yalnız birini doğru okudu.
Bu da suni bir sonuçtur; model aynı faturaları tek tek verdiğimizde okuyordu.
Tek ajana aynı anda sekiz iş verdiğimizde doğruluk korunuyor, ama hız artmıyor, hatta biraz düşüyor.
Ayrı ajanlarda ise doğruluk yerinde kaldı.
Hız MiniCPM'de iki kata yaklaştı, SmolLM'de iki katın biraz üzerine çıktı.
Sekiz ajandan sekiz kat hız gelmemesinin sebebi, bütün ajanların aynı ekran kartını paylaşmasıdır.

## SONUÇ

[VOICE:NARRATOR] [PARAGRAPH:sonuc]
Birinci grubun sonuçlarını bir arada toplayalım.
Temiz metinde temel bilgileri okuma işinde MiniCPM yüzde yetmişin üstüne çıktı, SmolLM altında kaldı; ikisi de saf yazılımla aynı bölgedeydi.
Gemma'nın sıfırı ve Llama'nın başarısız sonucu paketleme kaynaklıdır ve özel test videolarında yeniden ölçülecek.
Faturayı bozduğumuzda saf yazılım sarsılırken iki model ayakta kalıyor ve aradaki fark istatistik olarak anlamlı hâle geliyor.
Faturanın tamamını okuma işinde en iyi sonuç iki yüz faturada dörttü.
Gürültülü metinde ise modellerin hiçbiri ilk otuz faturada tek doğru veremedi.
Çoklu testte tek istekte birden çok fatura doğruluğu bozdu; ayrı ajanlar ise doğruluğu koruyup hızı yaklaşık iki katına çıkardı.
Bu sonuçlar bu test sisteminde, bu verilerle ve bu çalışma şekliyle bu modellerden aldığımız verimi gösteriyor; modellerin genel yeteneği hakkında bir hüküm değil ve modellerden aldığımız nihai en iyi skorlar bunlar değil.
Her modeli tek tek ele aldığımız ve maksimum seviyede zorladığımız özel testlerde bu modelleri yeniden göreceğiz.

## DEĞERLENDİRME

[VOICE:CLOSER] [PARAGRAPH:degerlendirme]
Açıkçası bu kadar küçük bir modelin bir faturanın temel bilgilerini yarım saniyenin altında okuması beni şaşırttı.
Ama temiz faturada basit kurallarla çalışan bir yazılımın da aynı yerde durduğunu görmezden gelemem.
Asıl cevabı faturayı bozduğumuzda aldık.
Yazılım sarsılırken iki ayrı model ayakta kaldı ve tanıtım videosunda sorduğumuz soruya ilk ölçülmüş cevabı verdi.
Gemma'nın durumu bence bu videonun en öğretici yanı; okuyor ama teslim edemiyor, bozuk faturada bile.
Bunun basit bir ayarla düzelip düzelmediğini özel testte görmek istiyorum.
Tam okuma işi ise bu grubun boyunu aşıyor gibi görünüyor.
Çoklu testten çıkardığım ders de şu: modele işi tek tek vermek, hepsini birden önüne yığmaktan daha doğru sonuç veriyor; en hızlı seçenek de genelde modelin ayrı ajanlarına birer iş vermek oluyor.

## SIRADAKİ VİDEO

[VOICE:NARRATOR] [PARAGRAPH:siradaki]
Bir sonraki videoda ikinci grup ortak teste tabi tutulacak.
Bunlar Liquid AI'ın el-ef-em iki ve el-ef-em iki nokta beş modelleri.
Yanlarında Qwen ailesinden Qwen üç var.
İlk ikisi aynı ailenin eski ve yeni sürümü ve boyları birebir aynı.
O videoda sürüm değişince neyin değiştiğine aynı faturalarla bakacağız.
Sizce aynı boyda yeni bir sürüm ne kadar fark yaratır?
Takipte kalın.
