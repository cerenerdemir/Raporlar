*İŞLETİM SİSTEMİ TEMELLERİ (OS BASİCS)*
İşletim sisyemleri, tüm donanım parçalarıyla (RAM, CPU, Harddisk) yazımlımların birlikte verimli çalışmasını sağlayan ve kolaylaştıran sistemdir.Kullanıcı ve bilgisayar arasında bir köprü görevi görür.
Kaynak Yönetimi (Resource Management), programların kaynakları paylşamalarını sağlar.
Programların girdi\çıktı cihazları ile etkileşimini mümkün hale getirir ve oluşacak problemlerden bizi soyutlar(Abstraction).
Bir programın çöküp diğer programların verilerine zarar vermesini ya da doğrudan bilgisayarın can damarı olan donanımları bozmasını engeller.
bir bilgisayar açıldığı anda, henüz hiçbir uygulama açılmamışken, işletim sistemi arka planda ne yapar?
1-Donanım kontrolü: Anakart üzerinden RAM'E, işlemciye,ekran kartına sinyal gönderir.
2-Donanım sağlamsa Kernel diskten RAM'e yüklenir.
3-Çekirdek RAM'e yerleşince kendine özel ve korumalı alan yaratır(kernel space), kullanılacak uygulamlar için de ayrı alan ayırır(user spcae).
4-Arka planda temel hizmetler (internet bağlantıları,klavye-fare algılayıcıları,ses sürücüleri) başlatılır.

*##Kernel nedir?*
Çekirdek (kernel), bir işletim sisteminin kalbi ve en temel yapı taşıdır. Donanım ile yazılım arasında köprü görevi görerek sistemin can damarı olan bellek ve süreç yönetimini, cihaz kontrolünü, dosya sistemlerini, ağ iletişimini ve süreçler arası bağı organize eder. Kısacası, işletim sisteminin diğer tüm bileşenlerine zemin hazırlayan ana yönetim merkezidir.
Görevleri:
1-Kullanıcı ve uygulama arayüzü etkileşimini sağlar.
2-Uygulamaların başlatılması, yürütülmesi ve sonlandırılmasını koordine eder.
3-Donanım kontrolü sağlar.

*##Süreç-iş parçacığı(thread) farkı nedir ?*
1-Bellek: Süreçlerin belleği birbirine tamamen kapalıdır (izoledir). Thread'ler ise bağlı oldukları sürecin belleğini ortak kullanırlar.
2-Maliyet: Yeni bir fabrika (süreç) kurmak çok masraflıdır ve zaman alır. Ama var olan fabrikanın içine yeni bir işçi (thread) almak çok daha hızlı ve az maliyetlidir.
3-Güvenlik/Risk:bir thread çökerse, bağlı olduğu tüm süreci çökertebilir.

*##bellek yönetimi nasıl yapılır?*
Bellek yönetimi, işletim sisteminin bilgisayardaki kısıtlı RAM alanını çalışan programlar arasında adil, güvenli ve verimli bir şekilde paylaştırma sürecidir. Eğer işletim sistemi bu yönetimi yapmasaydı, programlar birbirinin verilerini silebilir ya da RAM yetersizliğinden dolayı sistem anında kilitlenebilirdi.

Sanal Bellek 
Bilgisayarda bazen açtığımız programlar veya oyunlar, elimizdeki fiziksel RAM kapasitesinden daha fazla alana ihtiyaç duyar. İşletim sistemi bu tıkanıklığı aşmak için diskten (SSD/HDD) geçici bir yer ödünç alır ve burayı RAM'miş gibi kullanır. Buna Sanal Bellek denir. Programlar kendilerini devasa bir bellekte sanırlar ama aslında arka planda disk ile RAM arasında sürekli bir veri trafiği döner.

Sanal Bellek (Virtual Memory): Fiziksel RAM yetersiz kaldığında, sabit diskin (SSD/HDD) bir kısmının RAM gibi davranmasını sağlayan sanal bir alan illüzyonudur.
Sayfalama (Paging): Programların mantıksal hafızasını Sayfa" (Page), RAM'i ise Çerçeve (Frame) adı verilen eşit küçük parçalara bölme yöntemidir. Parçaların RAM'de yan yana durma zorunluluğunu ortadan kaldırır. Hangi parçanın nerede olduğunu Sayfa Tablosu (Page Table) takip eder.
MMU (Bellek Yönetim Birimi): İşlemcinin ürettiği sanal adresleri, donanımsal olarak anlık olarak RAM'deki gerçek fiziksel adreslere dönüştüren ve bellek güvenliğini sağlayan birimdir.

*##CPU zamanlayıcıları nedir?*
CPU aynı anda sadece tek bir iş yapabilir. CPU Zamanlayıcısı, hazırda bekleyen süreçlerden hangisinin sırayla işlemciye çıkacağını ve orada ne kadar kalacağını belirler

Temel Zamanlama Algoritmaları
İlk Gelen İlk Alır (FCFS): Uzun işlemler arkadaki kısa işlemleri çok bekletebilir (Konvoy Etkisi).
En Kısa İş Öncelikli (SJF): İş süresi en kısa olana öncelik verilir. Ortalama bekleme süresi için en iyisidir ama iş sürelerini önceden tahmin etmek zordur.
Round Robin (RR): Her sürece eşit bir zaman dilimi (Time Quantum) verilir. Süresi biten arkaya geçer. Modern sistemlerin zaman paylaşımı için kullandığı en adil algoritmadır.
Öncelik Zamanlaması (Priority Scheduling): Süreçlere önem derecesine göre öncelik verilir. Arkada kalan düşük öncelikli işlerin aç kalmaması için bekledikçe öncelikleri artırılır.