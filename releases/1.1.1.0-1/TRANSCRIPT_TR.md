# 1.1.1.0-1 — LFM3 1.7B ara video · Türkçe transkript

Satır = cümle; 74 cümle, 17 paragraf. Türkçe cümle N = İngilizce cümle N. Harf ve sürümler seslendirme için okunuşuyla yazılmıştır (ör. 'el ef em üç'). Türkçe önizleme videosunda seslendirilen metin budur.

[PARAGRAPH:1]
Masadaki iki yüz faturanın üstünde aynı ailenin üç sürümü yazılı.
İlk sürüm iki yüz faturanın yetmiş yedisini doğru okumuştu.
Ortanca sürüm ise yüz altmış bire sıçradı.
Peki ailenin yeni modeli, hiçbir yazılım desteği almadan belge okuma işimize aday olabiliyor mu?

[PARAGRAPH:2]
Ailenin yeni üyesi artık masamızda duruyor.
Liquid ey ay, yirmi üç Ekim iki bin yirmi altıda yeni modelini yayımladı.
Adı el ef em üç; bir nokta yedi milyar parametreye sahip.
Tek sürümde doğru sayısını iki katından fazla büyüten bu ailenin yeni adımda ne yaptığını görmek istedik.

[PARAGRAPH:3]
Hedefimiz yarıştırmak değil; modelin El El Em Test Ofisinin belge okuma işine aday olup olamayacağını görmektir.
Bunun için el ef em üçü, bütün modellere aynı istemi ve aynı kuralı verdiğimiz ortak testten geçirdik.
Ortak testte model hiçbir destek almadan tek başına okur.
Ardından özel testlerde sırayla yazılım, karakter tanıma ve görsel model desteği eklenir.
Sürecin sonunda her adayın işi hangi destekle tamamladığını ve bunun için ne kadar bellek gerektiğini kaydediyoruz.
Yeni adayı şimdiye kadar sonuçlarını yayımladığımız yedi modelle aynı masada karşılaştırıyoruz.

[PARAGRAPH:4]
Modelin kimliği kartındaki satırlarda kayıtlı.
İtiraf edeyim, iç mimarisini ayrıntısıyla bilmiyorum; yapı bilgisini doğrudan model kartından aktarıyoruz.
Kartta kısa evrişim ve dikkat katmanlarını birlikte kullanan yirmi dört katmanlı bir yapı ve belli bir gelir sınırının altında ticari kullanıma izin veren bir lisans yer alır.
Biz ölçümde kü dört ka em nicemlemeli dosyayı kullandık ve indirdiğimiz dosyanın Hugging Face'te yayımlanan özetle birebir aynı olduğunu doğruladık.
Testlerimizi önceki modellerde olduğu gibi İngilizce faturalarla yaptık.

[PARAGRAPH:5]
Ölçüm düzenimiz önceki testlerle aynı.
Karşılaştırma adil olsun diye önceki modellerin okuduğu aynı iki yüz sentetik İngilizce faturayı masaya koyduk; böylece iki model arasında çıkan fark faturadan değil, modelin kendisinden geliyor.

[PARAGRAPH:6]
Testi iki kademeye ayırdık.
Kolay testte faturanın beş temel bilgisini soruyoruz: numara, tarih, satıcı, vergi ve toplam.
Tarihi de yıl, ay ve gün sırasıyla belirli bir biçime çevirmesini istiyoruz.
Zor testte ise kalemleriyle birlikte faturanın tamamını istiyoruz; vade, ara toplam, indirim ve kargo gibi bilgilerin yanında her satırın açıklaması, adedi ve tutarı da buna dahil.

[PARAGRAPH:7]
İki farklı puanlama sistemi kullanıyoruz.
İlki katı sistem: doğru cevabı belirli bir şekil şartıyla istiyoruz ve istenen bilgilerden tek biri bile yanlışsa fatura düşüyor.
Modeli kullanan bir uygulamanın sorunsuz çalışması için bu şart gerekli.
İkincisi esnek sistem: şekil şartına takılmadan yalnız içeriğin doğru olup olmadığına bakıyoruz.
İki sistem arasındaki fark, modele ne kadar yazılım desteği gerektiğini gösteriyor.

[PARAGRAPH:8]
Ayrıca yapay zekâ kullanmayan, kurallarla yazılmış bir modelsiz programı da taban olarak koşturduk.
İki modeli karşılaştırırken aynı faturalardaki sonuçlarını yan yana koyan bir istatistik sınaması kullanıyoruz.
Bu sınama, aradaki farkın şansla açıklanma ihtimalini veriyor; bu ihtimal yüzde beşin altında değilse hiçbir modele daha iyi ya da daha kötü demiyoruz.

[PARAGRAPH:9]
Kolay testte sonuçlar ailenin önceki sürümüne yakın çıktı.
Yeni model iki yüz faturanın yüz elli altısını doğru okuyor.
Karşıda ailenin önceki sürümü el ef em iki nokta beş var.
O sürüm aynı testte yüz altmış bir doğru çıkarmıştı.
Aradaki fark şansla açıklanabilecek kadar küçük; istatistik sınamada anlamlı çıkmadı.
Bu yüzden yeni sürüme ne daha iyi ne daha kötü diyoruz.

[PARAGRAPH:10]
Modelsiz program aynı destede yüz kırk iki doğruya ulaştı.
Yeni model istatistik sınamada bu programdan da anlamlı biçimde ayrışmıyor.
Sonuçlarını yayımladığımız yedi modelle birlikte sıralamada ikinci görünse de yakın sayılar arasında anlamlı fark çıkmadığından bu sıra üstünlük hükmü sayılmaz.
Esnek sistemde de sonuç değişmedi ve yüz elli altıda kaldı.
Aynı koşum içinde faturaları farklı biçimlerde gönderdiğimizde de sonuç yüz elli altı ile yüz elli yedi arasında kaldı.

[PARAGRAPH:11]
Faturanın tamamını istediğimiz zor testte ise sonuçlar çok farklı.
Yeni model iki yüz faturanın seksen beşini eksiksiz okudu; esnek sistemde de sonuç aynı.
Önceki sürüm el ef em iki nokta beş, kolay testte en yüksek sayıyı almıştı; ama zor testte çok geride kalıyor.
O sürüm on iki faturayı eksiksiz okuyabildi; ilk sürüm ise hiçbir faturayı eksiksiz okuyamamıştı.
Sonuçlarını yayımladığımız yedi modelin hiçbiri bu testte on ikiyi aşamamıştı.

[PARAGRAPH:12]
Bu farkı da aynı istatistik sınamayla denedik; fark şansla açıklanamayacak kadar büyük.
Yalnız bu sınamayı sonuçları gördükten sonra eklediğimizi not edelim.
Bu yüzden onu kesin bir hüküm değil, dikkat çeken bir bulgu olarak sunuyoruz.

[PARAGRAPH:13]
Kolay testteki kayıplardan ilginç bir kalıp çıktı.
Kaçan kırk dört faturanın otuz altısında, cevabın içinde istemediğimiz fazladan bir alan bulunuyor.
Bu sınıfı ilk sürümde de görmüştük.
O model yirmi beş faturada istemediğimiz fazladan bilgi yazmıştı.
Ortanca sürümde ise bu durum hiç yoktu; onun kaybettiği otuz dokuz faturanın tamamı yanlış değer hatasıdır.

[PARAGRAPH:14]
Bu kütük tek bir okumayı değil, aynı faturaların farklı düzenlerde tekrar tekrar okunduğu cevapları tutuyor.
Bu ek alanların ne olduğuna bakmak için sunucu kütüğünde kalan dört yüz yirmi dokuz başlık cevabını inceledik.
Kayıtların yetmiş dokuzunda aynı davranış tekrarlanıyor.
Model tarih alanına belgedeki ham tarihi bırakmış; istenen yıl, ay ve gün biçimini ise kendi adını koyduğu ikinci bir alana yazmıştır.
Bu yetmiş dokuz cevabın yetmiş dokuzunda da ikinci alandaki çeviri doğru çıktı.
Yani model tarihi doğru okuyor ama çevirme talimatını yeni alan adına dönüştürüyor.
Esnek sistem de bu faturaları kurtarmıyor, çünkü istenen alandaki tarih istenen biçimde değil.
Kütük döndüğü ve ana koşumdaki kayıplarla birebir eşlenmediği için bu sayım yalnız eldeki kayıtları yansıtır.

[PARAGRAPH:15]
Hüküm kurmadan önce sınırları masanın kenarına not edelim.
Denemeyi tek koşumda yaptık; bilgisayarın güç planı önceki ölçümlerden farklı kaldığı için hız karşılaştırmasına girmiyoruz.
Zor testteki sınamanın sonradan eklendiğini ve kütük sayımının kısmî kaldığını unutmamak gerekir.
Modelsiz programı, faturaları üreten yazılımı bilen kişi yazdığından tabanımız iyimserdir; gerçek belgelerdeki sonucu ise bu test ölçmüyor.

[PARAGRAPH:16]
El ef em üç için ortak test süreci tamamlanmıştır.
Tarihi doğru çevirdiği hâlde kendi açtığı ikinci alana yazan bir modelle karşılaşsanız ilk adımı nereden atardınız: istemi mi değiştirirdiniz, yoksa o alanı küçük bir yazılımla temizler miydiniz?

[PARAGRAPH:17]
Ortak test sürecinde şimdilik son yarışmacılarımız MiniCPM beş, Qwen üç nokta beş ve Qwen üç nokta sekiz distill modelleri.
Süreç içinde yeni yayımlanan modeller için ara videolar çekmeye devam edeceğiz.
Sıradaki video on iki Kasım perşembe, New York saatiyle akşam beşte yayında.
