# ideasoft-case


## Functional Test cases

### Test case 1: Adres ekleme butonunun görünür olması

**Açıklama:** "Yeni Adres Ekle" butonunun Adres Defteri ekranında görünüp görünmediğini doğrulama.

**Ön koşullar:** Kullanıcı, hesabına başarıyla giriş yapmış ve Hesabım -> Adres Defteri ekranına gitmiş olmalıdır.

**Adımlar:**

- Hesabım ekranına git.
- Açılan menüden Adres Defteri ekranına git.
- "Yeni Adres Ekle" butonu ekranda görünmeli ve tıklanabilir olmalıdır.

**Beklenen Sonuç:** "Yeni Adres Ekle" butonu görünmeli ve tıklanabilir olmalıdır.

**Geçme Kriterleri:** Buton görülür ve tıklanabilir.

### Test case 2: Adres ekleme formunun alanlarının doğrulanması

**Açıklama:** Adres eklerken tüm gerekli alanların formda bulunduğunu ve doğru giriş aldığını doğrulama.

**Ön koşullar:** Kullanıcı, hesabına başarıyla giriş yapmış ve Hesabım -> Adres Defteri ekranından adres ekleme formuna girmiş olmalıdır.

**Adımlar:**

- Hesabım ekranına git.
- Açılan menüden Adres Defteri ekranına git.
- "Yeni Adres Ekle" butonuna tıkla.
- Formda aşağıdaki alanlar belirtilen veri ve giriş tipine uygun şekilde, zorunlu olup olmadıkları belirtilecek şekilde bulunmalıdır:
  - Adres İsmi: String - TextBox - Zorunlu
  - Adı: String - TextBox - Zorunlu
  - Soyadı: String - TextBox - Zorunlu
  - Ülke: String - Select - Zorunlu
  - Şehir: String - Select - Zorunlu
  - İlçe: String - Select - Zorunlu
  - Telefon: String - TextBox.Phone - Opsiyonel
  - Cep Telefonu: String - TextBox.Phone - Zorunlu
  - T.C Kimlik No: String - NumberInput - Zorunlu
  - Adres: String - TextArea - Zorunlu

**Beklenen Sonuç:** İlgili alanlar belirtilen veri yapısı ve giriş tipinde formda bulunmalı, zorunlu olanlar uygun şekilde belirtilmeli. İptal ve Kaydet butonları da mevcut olmalı ve tıklanabilir olmalı. Zorunlu

**Geçme Kriterleri:** Buton görülür ve tıklanabilir.

### Test case 3: Zorunlu alanlar boşken adres kaydetme denemesi

**Açıklama:** Zorunlu alanları doldurmadan "Kaydet" butonuna basılması durumunda, formun uygun hata mesajlarını verip vermediğini doğrulama. Not: Zorunlu alanları doldurmadan "Kaydet" butonunun aktif hale gelmemesi durumu ilgili birimlerle konuşup implement edilebilir.

**Ön koşullar:** Kullanıcı, hesabına başarıyla giriş yapmış ve Adres Defteri ekranında “Yeni Adres Ekle” formunu açmış olmalıdır.

**Adımlar:**

- “Yeni Adres Ekle” formunu aç.
- Hiçbir alana veri girişi yapma (tüm zorunlu alanlar boş).
- "Kaydet" butonuna tıkla.

**Beklenen Sonuç:** Form, eksik ya da hatalı alanlara dair hata mesajları göstermeli. Kullanıcı, uyarı gösterilen zorunlu alanları doldurduğunda form uygun hale gelmeli, yani gerekli input'ların hepsinde uygun hata mesajları gösterilmeli.

**Geçme Kriterleri:** Her bir zorunlu alan için kullanıcıya uyarı verilmesi ve adres ekleme işleminin başarısız olması.


### Test case 4: Özel formatı olan alanlara hatalı veri girişi

**Açıklama:** T.C. kimlik no ve telefon numarası alanlarının özel formatları vardır. Bu alanlara bu formatın dışında veriler girerek bu yanlış girişlerin kabul edilmediği, uygun hata mesajlarının gösterildiği kontrol edilir.

**Ön koşullar:** Kullanıcı, hesabına giriş yapmış ve Yeni Adres Ekle formunu açmış olmalıdır.

**Adımlar:**

- “Yeni Adres Ekle” formunu aç.
- T.C Kimlik No alanına karakter sayısı 11’den az bir rakam girişi yap.
- Cep Telefonu alanına geçersiz bir giriş (örneğin eksik rakam) yap.
- "Kaydet" butonuna tıkla.

**Beklenen Sonuç:** T.C. kimlik no için 11 haneden kısa giriş veya geçersiz karakter içeren girişler kabul edilmemeli, cep telefonu alanı için geçerli format (örn. (5XX) XXX XX XX) beklediğini belirtmeli. Adres kaydı tamamlanamamalı.

**Geçme Kriterleri:** Geçersiz formatlı veriler için adres kaydı yapılamaz; kullanıcıya hata bilgisi gösterilir.

### Test case 5: İptal butonunun işlevi

**Açıklama:** Form açıkken İptal butonuna tıklandığında formun kapanıp kapanmadığını doğrulama. Eğer formda veri girilmiş haldeyse, kullanıcıya "Emin misiniz?" tarzı bir prompt çıkarılabilir.

**Ön koşullar:** Kullanıcı, hesabına giriş yapmış ve Adres Defteri -> "Yeni Adres Ekle" formunu açmış olmalıdır.

**Adımlar:**

- Formda en az bir alan doldurulur.
- "İptal" butonuna tıklanır.
- "Emin misiniz" prompt'u çıkarılır, kullanıcı "Evet" dediği durumda form kapanır.
- "Kaydet" butonuna tıkla.

**Beklenen Sonuç:** Form kapanmalı ve Adres Defteri ekranına geri dönülmeli. Formda girilmiş veriler varsa bunlar kaydedilmemeli.

**Geçme Kriterleri:** Forma girilmiş menü varsa "Emin misiniz?" prompt'u çıkar ve kullanıcı "Evet" derse form sorunsuzca kapanır ve kullanıcı Adres Defteri ana ekranına geri döner. Eğer girilmiş veri yoksa İptal butonuna basıldığında form kapanır ve kullanıcı Adres Defteri ana ekranına geri döner.

### Test case 6: Maksimum ve minimum karakter sınırlarının kontrolü

**Açıklama:** Bazı alanlarda minimum veya maksimum karakter sınırı koyulabilir. Bu alanlarda bu sınırların dışında kalındığında sistemin nasıl davrandığı kontrol edilir.

**Ön koşullar:** Kullanıcı, hesabına giriş yapmış ve Adres Defteri -> "Yeni Adres Ekle" formunu açmış olmalıdır.

**Adımlar:**

- Aşağıdaki adımlar ad ve soyad alanlarında minimum 2, maksimum 50 karakter giriş sınırı olduğu düşünülerek hazırlanmıştır, sistem spesifikasyonlarına göre doğru sayılarla güncellenebilir:
- Ad ve Soyad alanlarına tek bir karakter girilir, formun kalanı uygun şekilde doldurulur. İkinci adımda ise 51 karakter girilir ve formun kalanı uygun şekilde doldurulur.
- "Kaydet" butonuna tıklanır.

**Beklenen Sonuç:** Minimum ve maksimum karakter sınırları ilgili alanlarda belirtilmelidir. Alternatif olarak maksimum karakter sınırına ulaşıldığında daha fazla karakter girişine izin verilmeyebilir.

**Geçme Kriterleri:** Belirlenen karakter sınırını aşan veya bu sınıra ulaşamayan bir giriş varsa kullanıcı engellenir veya uyarılır. Adres kaydı gerçekleşmez.

### Test case 8: Geçerli veri girildiğinde adresin başarıyla kaydedilmesi

**Açıklama:** Tüm zorunlu alanların doğru şekilde doldurulması durumunda “Kaydet” butonuna basılınca adresin sorunsuz şekilde eklenip eklenmediği doğrulanır. Kullanıcıya gerekli feedback verilir.

**Ön koşullar:** Kullanıcı, hesabına giriş yapmış ve Adres Defteri -> "Yeni Adres Ekle" formunu açmış olmalıdır.

**Adımlar:**

- Formdaki bütün zorunlu alanlar eksiksiz şekilde doldurulur.
- Zorunlu olmayan alanlar boş bırakılır.
- "Kaydet" butonuna tıklanır.
- Adres Defteri listesinde eklenen adresin göründüğü kontrol edilir.

**Beklenen Sonuç:** Kullanıcı, formu doğru bilgilerle doldurup kaydettiğinde adres başarıyla kaydedilir. Ekranda başarılı kaydedildiğine dair mesaj gösterilir.

**Geçme Kriterleri:** Adres kaydının başarılı şekilde ekrana yansımış olması ve girilen verilerin hatasız kaydedilmesi.

### Test case 9: Kayıtlı adresleri düzenleme

**Açıklama:** Kullanıcı, önceden kaydedilmiş bir adresin bilgilerini güncelleyip yeni bilgilerle kaydedebilmeli.

**Ön koşullar:** Kullanıcının en az bir kaydedilmiş adresi bulunmalıdır ve Adres Defteri sayfasında bunu görüyor olmalıdır.

**Adımlar:**

- Adres Defteri sayfasında bir adres altında yer alan Düzenle butonuna tıkla.
- Açılan düzenleme formunda adresin bazı alanlarını (“Adres İsmi” veya “Adres”) değiştir.
- "Kaydet" butonuna bas.
- Değişiklik yaptığın adresin yeni bilgilerle listede görüntülenip görüntülenmediğini kontrol et.

**Beklenen Sonuç:** Kaydedilen değişiklikler, Adres Defteri sayfasındaki ilgili adres kutusu üzerinde anında görüntülenmelidir. Sistem bir başarı mesajı veya görsel uyarı ile kaydın başarıyla güncellendiğini belirtebilir.

**Geçme Kriterleri:** Değiştirilen bilgiler, listeye doğru şekilde yansıması. Veri girişi uygun şekilde yapıldıysa verilerin doğru şekilde güncellenmesi.

### Test case 10: Kayıtlı adresin silinmesi

**Açıklama:** Kullanıcı, adresi silme butonuna tıkladıktan sonra onay verirse adresin listeden gerçekten kaldırılıp kaldırılmadığını doğrular.

**Ön koşullar:** Kullanıcının en az bir kaydedilmiş adresi bulunmalıdır ve Adres Defteri sayfasında bunu görüyor olmalıdır.

**Adımlar:**

- Adres Defteri sayfasında bir adres altında yer alan Sil butonuna tıkla.
- Çıkacak onay penceresinden işlemi onayla.
- Adres listesinde silinen adresin olmadığını onayla.

**Beklenen Sonuç:** Eğer silinmek istenen adres türünden (teslimat veya fatura) birden fazla varsa silme işlemi başarılı olmalıdır. Eğer bir tane varsa da gerekli uyarı kullanıcıya gösterilmeli ve adres silinmemelidir.

**Geçme Kriterleri:** Adres türüne ait tek kayıt varsa adresin silinmemesi, birden çok kayıt varsa adresin silinmesi.
