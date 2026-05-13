#Bilgisasyar Mimarisi

**CPU(Merkezi İşlem Birimi)**
CPU bilgisayarın beynidir, bilgisayarda yapılan her işlem CPU tarafından işlenir ve denetlenir.
Temel çalışma mantığı:
1.RAM'den ilgili komutu alır.
2.Veriyi işler.
3.Sonucu tekrar belleğe kaydeder.


**CPU İç Yapısı((ALU, kontrol birimi))**

##CU(Kontrol Birimi)
Kontrol birimi CPU'nun yöneticisi gibidir, diğer donanımlara talimatları yerine getirmeleri için komut verir.
Temel çalışma mantığı:
1.Bellekten gelen komutları alır.
2.Komutları işler.(decode)
3.ALU, RAM ve giriş-çıkış aygıtlarını harekete geçirecek sinyalleri gönderir.

##ALU(Aritmetik Mantık Birimi)
İşlemcinin beynidir, her işlemcide bulunur.
Aritmetik hesaplamaların, mantıksal işlemlerinin yapıldığı birimdir.(toplama-çıkarma,and,or,nor,not,xor)
Binary sistemde çalışır.
Temel çalışma mantığı:
1.Sayılar registers kısmından ALU girişine gelir.
2.Kontrol birimi ne yapılacğını söyler.(opcode gönderir)
3.Gelen işlem koduna göre belirli mantık gurubu kapısı aktifleşir.
4.sonuç ve flags üretilir.

**Cache katmanları (L1–L2–L3), neden kritik?**
Cache(Önbellek): CPU ile RAM arasında bulunan, RAM'den çok daha hızlı ama kapasitesi çok daha düşük olan bir geçici depolama birimidir.Bilgisayarın genel hızını belirler.

CPU çok hızlıdır, fakat RAM daha yavaştır.
Eğer CPU her veriyi RAM’den almak zorunda kalsaydı büyük zaman kaybı olurdu.Bu yüzden araya cache katmanları eklenir.

L1 Cache(Birinci Seviye Önbellek):İşlemci çekirdeğinin içindeki en hızlı bellektir.Kapasitesi çok küçüktür.Görevi CPU'nun sık kullandığı veri ve komutları hızlıca saklamak.

L2 Cache(İkinci Seviye Önbellek):L1'den daha büyük ama daha yavaştır.Genellikle her çekirdeğin kendine özel L2 belleği bulunur.Görevi L1'de bulunmayan verileri tutmaktır.

L3 Cache(Üçüncü Seviye Önbellek):En büyük kapasiteye sahiptir ama daha yavaştır.İşlemcinin tüm çekirdekleri tarafından ortak kullanılır. RAM'den veri çekmeden önceki son duraktır. Çok çekirdekli işlemcilerde önemlidir.Görevi çekirdek arası veri paylaşımı ve ram erişimini azaltmaktır.

Önbellek neden kritiktir?
İşlemcinin zaman ve hız kaybetmeden işlem yapmasını sağlar.
Gecikmeleri en aza indirir ve performansı arttırır.
Bilgisayarın güç tüketimini azaltmaya yardımcı olur, enerji tasarrufu sağlar.
Sürekli kullanılan verileri tutarak erişim hızını arttırır.
Seviyeli önbellek yapısı sayesinde performansı arttırır.


**RAM nasıl çalışır?**
Rastgele erişimli bellek, kısa süreli/geçici hafıza birimidir.Bir program açıldığında SSD/HDD kısmından veriyi alır hızlıca kullanılabilmesi için RAM'e yükler. CPU veriyi RAM'den alır.(RAM, depolama birimlerinden çok daha hızlıdır.)

RAM, hücre denilen milyonlarca küçük bölmeden oluşur. Her hücre bir bitlik veriyi 0 veya 1'i temsil eder.
İşlemci veri talebinde bulunduğunda RAM bu isteği koordine ederek ilgili adreslemeyi yapar.
Veri kaybı olmaması için DRAM yapılarında hücreleri sürekli tazeleyen yenileyici devreler bulunur.
İşlemci yazma sinyali göndererek veriyi adrese kaydeder bu adres saklanır.
RAM'e giden elektrik kesildiği anda (bilgisayar kapandığında) bilgiler tamamen silinir.

Kısaca:Bir program açıldığında, sabit diskten (HDD/SSD) alınan veriler RAM'e kopyalanır. CPU, ihtiyacı olan veriyi RAM'den (daha doğrusu RAM'den önbelleğe alarak) okur.