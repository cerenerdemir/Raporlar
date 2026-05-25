## 1.Projeyi Başlatma
* `git init`  
  İçinde bulunduğum klasörü Git projesi haline getirir. Sıfırdan bir şeye başlarken ilk iş bu.
* `git clone <url>`  
  GitHub'dan veya başka bir yerden hazır bir projeyi bilgisayarıma çekmek, kopyalamak için.

## 2.Kodları Kaydetme
* `git status`  
  Şu an ne durumdayım? Hangi dosyaları değiştirdim, hangilerini eklemeyi unuttum, her şeyi gösteren cankurtaran.
* `git add .`  
  Değişiklik yaptığım her şeyi "bunu kaydetmeye hazırla" diyerek torbaya atar. (Tek dosya için: `git add dosya_adi`)
* `git commit -m "açıklama"`  
  Torbadaki değişiklikleri kalıcı olarak yerel bilgisayarıma kaydeder. Yazdığım mesaj net ve kısa olmalı ki sonra ne yaptığımı bileyim.

## 3. Geçmişe Bakış
* `git log`  
  Şimdiye kadar attığım tüm commit'lerin (kayıtların) geçmişini listeler.
* `git log --oneline`  
  O uzun geçmiş listesini tek satır halinde, gözü yormayacak şekilde sadeleştirir.

## 4. Branch (Dal) İşleri 
* `git branch`  
  Projedeki mevcut dalları listeler, şu an hangisindeyim yıldızla gösterir.
* `git switch -c <yeni-dal-adi>`  
  Ana kodu bozmamak için hemen yeni bir deneme/özellik dalı açar ve beni direkt o dala geçirir. (Eski adı: `git checkout -b`)
* `git switch <dal-adi>`  
  Açtığım diğer dallar arasında geçiş yapmamı sağlar.
* `git merge <dal-adi>`  
  Başka bir dalda işimi bitirip test ettiysem, o daldaki kodları üzerinde bulunduğum ana dala getirip birleştirir.
* `git branch -d <dal-adi>`  
  İşimin bittiği ve ana dalla birleştirdiğim dalı temizlemek için siler.

## 5. Bulutla (GitHub vb.) Bağlantı Kurma
* `git remote add origin <url>`  
  Bilgisayarımdaki bu yerel projeyi, internetteki (GitHub'daki) uzak depoya ilk kez bağlamak için kullanılır.
* `git push -u origin <dal-adi>`  
  İlk yüklemede kodları buluta fırlatır ve yerel dalla uzak dalı birbirine eşitler. Sonraki yüklemelerde sadece `git push` yazmak yeter.
* `git pull`  
  Uzak depoda (bulutta) benden habersiz bir değişiklik yapıldıysa veya başkası kod eklediyse, o güncel kodları bilgisayarıma çeker ve benimkiyle birleştirir.

## 6. Geri Alma
* `git restore <dosya-adi>`  
  Dosyada bir şeyler denedim ama mahvettim, henüz `git add` yapmadıysam dosyayı son kaydettiğim temiz haline geri döndürür.
* `git reset HEAD <dosya-adi>`  
  Yanlışlıkla `git add` ile torbaya attığım dosyayı torbadan geri çıkarır, silmez sadece beklemeye alır.