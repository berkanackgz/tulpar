# tulpar
### Amaç ve Özellikler
Bu program GUI arayüzü ile kolayca yapay zeka modelleri oluşturabileceğiniz bir programdır. Bu programda:
- Eğitimin "epochs, batch size, aktivasyon fonksiyonu" gibi özelliklerini GUI üzerindeki konsoldan kolayca ayarlayabilirsiniz,
- Sadece klasör ismi ile sınıflandırılmış dosyalarınızı kolayca test-train klasörlerine random olarak çevirebilirsiniz (%33 train %67 test),
- Eğitilen modellerin başarı oranlarını grafik ile görüntüleyebilirsiniz,
- Daha önce eğitilmiş modelleri test edebilirsiniz,
- Modelleri test etme aşamasında webcam ve ya fotoğraf kullanabilirsiniz,
- Output kısmında model eğitimini anlık takip edebilir; modelin verdiği sonucu takip edebilirsiniz.
# 
### Kullanım
Program içerisindeki yönlendirmeler programın kullanımını kolaylaştıracak şekilde tasarlanmıştır. Ancak daha önce yapay zeka modeli oluşturmamış ve kullanmamış kişilerin dikkat etmeleri gereken bazı hususlar aşağıda sıralanmıştır:
##### Model Eğitimi
- Model eğitiminde kullanılacak görseller kategorilerine göre klasörlenmelidir. Örneğin kedi ve köpeği tanıması üzere eğitilecek bir model için kedilerin fotoğrafları "kedi" köpeklerin ise "köpek" isimli bir klasöre konulması makul olacaktır. Program modeli eğitirken bu klasör isimlerini kategori olarak almaktadır. 
- Bu kategorize edilmiş klasörlerin bulunduğu ana klasör "Dosya>Test-Train Oluştur" kısmından seçilir ve model eğitimine hazır bir klasör oluşturulur. Bu işlem ile birlikte %33 train %67 test şeklinde bir klasör yapısı oluşacaktır. 
- Sonrasında test ve train klasörlerini oluşturan klasör "Dosya>Train Klasörü Seç" kısmından seçilir. Bu işlemle birlikte, "Dosyalar" kısmında test ve train klasörleri ve bunların içlerinde kategorize ettiğiniz görseller bulunacaktır. Bu görsellere çift tıklayarak proram üzerinde görüntüleyebilirsiniz. Aynı zamanda "Output" kısmında küme parantezi içinde {test_dosya_sayısı train_dosya_sayısı} şeklinde test ve train içerisindeki görsellerin sayısını kontrol edebilirsiniz.
- "Konsol" kısmına tıklayarak epochs sayısını ayarlayabilirsiniz, değeri kutuya girip enter a basarak bu işlemi yapabilirsiniz. Aynı zamanda sağ üstten epochs sayısının değişimini gözlemleyebilirsiniz. Bu sayı bir bakıma eğitimi tekrarlama sayısı olacaktır. Yüksek epochs değeri ile daha iyi sonuçlar alabileceğiniz gibi; test-train klasörünüzde bulunan görsellerde ve ya diğer konsol değişkenlerinde uyumsuz sayılar girmeniz durumunda epochs ı ne kadar yüksek yapsanız da daha ötü sonuçlar da alabilirsiniz. Bu kısımda matematik bilgisi ve ya en azından deneme yanılma ile ilerleyerek doğru sonuca ulaşmaya çalışabilirsiniz.
- Yine "Kosnol" kısmından "batch size" ayarlanabilir. Ancak bunun ne olduğunu ve ne işe yaradığını iyice araştırmanız önerilir.
- "Konsol" kısmında ayarlayacağınız "Width" ve "Height" değerleri ise çok önemli bir yere sahip. Model eğitiminde bu kısım girdi olarak verilen görseli buraya yazılan değerlere transpoze eder. Ancak daha sonra bu modeli kullanabilmek için de bu verilerin girilmesi gerekir. Aksi taktirde model hata verecektir. 
- En altta bulunan checkbox kısmından aktivasyon fonksiyonu seçilebilir. Bazı işletim sistemlerinde bu checkbox kısmına çift tıklama gerekebilir. Değerin değişip değişmediği sağ üstten kontrol edilebilir.
- Tüm ayarlar tamamlandıktan sonra sağdan "Modeli Eğit" butonuna tıklayıp "Output" tan ilerleme kontrol edilebilir. Model eğitimi tamamlanınca "Eğitim Grafiği" kısmında modelin başarı oranı grafikle çizilmiş olacaktır.
"Konsol"da yapılan değişikler hem sağ üstte yer alacak hem de "Output" kısmında bildirim olarak görüntülenecektir. "Konsol" kısmında chekbox'lar çift tıklama ile seçilirken; sayı girişleri giriş yapıldıktan sonra enter a basılarak onaylanır.
##### Modeli Kullanarak Görsel Çözümleme
- Eğitim yapıldıktan hemen sonra program kapatılmaz ise son eğitilen model varsayılan olarak seçilir. Eğer daha önce eğitilen bir model kullanılmak isteniyor ise bu model "Dosya>Modeli İçe Aktar" kısmından seçilir. Buradan eklenen model "Modeller" sekmesinde "Dışarıdan Alınan" kısmında gösterilir. Ardından "Dışarıdan Alınan" kısmında görünen modele çift tıklanarak bu model seçilir. Bu modeli kullanabilmek için model eğitiminde seçildiği gibi "Train Klasörü Seç" işlemi yapılmalıdır. Burada önemli olan test-train klasörlerinin içindeki kategorize edilerek isimler verilen klasörlerde görüntü bulunması değil; görüntü bulunan bu klasörlerin isimlerinin eğitilmiş modelde verilen isimlerle aynı isimde olmaları ve tüm kategorilerin boş da olsa bir klasörünün olmasıdır. Çünkü program kategori ismi olarak bu klasör isimlerini almaktadır. Aksi taktirde hata verecektir. 
- "Dosyalar" kısmında şayet test-train içinde görsel varsa bu görsellerden seçim yaparak; eğer yoksa "Dosya>Test İçin Fotoğraf Seç" kısmından fotoğraf eklenerek ve istenilen fotoğraf "Dosyalar" kısmından üzerine çift tıklanarak seçilerek "Görsel" sekmesinde görüntülenmesi sağlanır. "Fotoğraf Çöz" tuşuna basılınca fotoğrafı kategorize eder ve modelin eğitiminin başarısına göre doğru sonuç verir. 
- "Dosya>Test İçin Fotoğraf Seç" kısmından fotoğraf eklerken eğer test-train klasörlerinden çok fazla görsel "Dosyalar" kısmına yüklendiyse seçilen fotoğrafınız yüklenmeyebilir. Bu durumda zaten daha öncesinde "Train Klasörü Seç" işlemini yaptınız için tekrardan "Train Klasörü Seç" kısmında içi tamamen boş bir klasör seçilip tekrar fotoğraf eklemesi denenebilir. 
- Aynı zamanda eğer bilgisayarınızın WebCam'i varsa "WebCam" sekmesini seçin ve "WebCam Çöz" tuşuna basın. Açılan pencerede WebCam'inizin görüntüsü gösterilirken WebCam'inizle çözümlemek istediğiniz görüntüyü yakalayınca "q" tuşuna basın. Ardından bu görüntü "WebCam" sekmesinde gösterilecektir. Bu sekmede gösterildiğini gördükten sonra "Fotoğrafı Çöz" tuşuna basarak modelin bunu tahmin etmesini sağlayabilirsiniz. 
#
![Capture3](https://user-images.githubusercontent.com/71699856/193470190-27f5f7da-fb17-48a2-8340-edbc4d2240b3.PNG)

[Berkan Acikgoz](https://github.com/berkanackgz)