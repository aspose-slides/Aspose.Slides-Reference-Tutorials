---
"description": "Bu kapsamlı adım adım eğitimle Aspose.Slides for Java'yı kullanarak PowerPoint'te Özet Yakınlaştırma'nın nasıl oluşturulacağını öğrenin."
"linktitle": "Özet Oluştur PowerPoint'te Yakınlaştır"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Özet Oluştur PowerPoint'te Yakınlaştır"
"url": "/tr/java/java-powerpoint-shape-thumbnail-creation/create-summary-zoom-powerpoint/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Özet Oluştur PowerPoint'te Yakınlaştır

## giriiş
Aspose.Slides for Java kullanarak PowerPoint'te Özet Yakınlaştırma oluşturmaya ilişkin kapsamlı eğitimimize hoş geldiniz. Sunumlarınıza dinamik ve etkileşimli bir öğe eklemek istiyorsanız, Özet Yakınlaştırma harika bir özelliktir. Sunumunuzun farklı bölümlerine yakınlaştırılabilen tek bir slayt oluşturmanıza olanak tanır ve izleyicileriniz için daha ilgi çekici ve gezilebilir bir deneyim sunar.
Bu adım adım kılavuzda, geliştirme ortamınızı kurmaktan Özet Yakınlaştırma çerçevesi oluşturmaya ve özelleştirmeye kadar tüm süreçte size yol göstereceğiz. İster deneyimli bir Java geliştiricisi olun, ister yeni başlıyor olun, bu kılavuzu takip etmenin kolay olduğunu ve değerli içgörülerle dolu olduğunu göreceksiniz.
## Ön koşullar
Koda dalmadan önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:
1. Java Geliştirme Kiti (JDK): Makinenizde JDK'nın yüklü olduğundan emin olun. Bunu şu adresten indirebilirsiniz: [Oracle web sitesi](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Java için Aspose.Slides: Kütüphaneyi şu adresten indirin: [Aspose sürüm sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Daha sorunsuz bir geliştirme deneyimi için IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE kullanın.
4. Temel Java Bilgisi: Java programlama kavramlarına aşinalık, bu kılavuzdaki adımları anlamanıza ve uygulamanıza yardımcı olacaktır.
## Paketleri İçe Aktar
Başlamadan önce gerekli paketleri içe aktarmanız gerekir. Proje bağımlılıklarınıza Aspose.Slides for Java'yı eklediğinizden emin olun.
```java
import com.aspose.slides.*;

import java.awt.*;
```
## Adım 1: Projenizi Kurun
Öncelikle geliştirme ortamınızın doğru şekilde ayarlandığından emin olun. Projenizi yapılandırmak için şu adımları izleyin:
### Yeni Bir Proje Oluştur
1. IDE’nizi açın.
2. Yeni bir Java projesi oluşturun.
3. Projenizin derleme yoluna Aspose.Slides for Java kütüphanesini ekleyin. JAR dosyasını şuradan indirebilirsiniz: [Aspose sürüm sayfası](https://releases.aspose.com/slides/java/) ve bunu projenize dahil edin.
### Sunumu Başlat
Daha sonra slaytlarınızı ve bölümlerinizi ekleyeceğiniz yeni bir sunum nesnesi başlatın.
```java
Presentation pres = new Presentation();
```
## Adım 2: Slaytlar ve Bölümler Ekleyin
Bu adımda sunuma slaytlar ekleyeceğiz ve bunları bölümlere ayıracağız. Bu düzenleme, Özet Yakınlaştırma oluşturmak için çok önemlidir.
### Yeni Slayt ve Bölüm Ekle
1. Boş Slayt Ekle: Sunuma yeni bir slayt ekleyin.
2. Slayt Arka Planını Özelleştirin: Slayt arka planı için düz bir dolgu rengi ayarlayın.
3. Bölüm Ekle: Slaydı bir bölüm halinde gruplandırın.
Bunu başarmak için gereken kod şu şekilde:
```java
// İlk slaydı ekle
ISlide slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
slide.getBackground().setType(BackgroundType.OwnBackground);
// İlk bölümü ekle
pres.getSections().addSection("Section 1", slide);
```
### Ek Bölümler için Tekrarlayın
Daha fazla slayt ve bölüm eklemek için işlemi tekrarlayın:
```java
// İkinci slaydı ve bölümü ekleyin
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.CYAN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 2", slide);
// Üçüncü slaytı ve bölümü ekleyin
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.MAGENTA);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 3", slide);
// Dördüncü slaytı ve bölümü ekleyin
slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
slide.getBackground().setType(BackgroundType.OwnBackground);
pres.getSections().addSection("Section 4", slide);
```
## Adım 3: Özet Yakınlaştırma Çerçevesini Oluşturun
Şimdi, ilk slaytta bir Özet Yakınlaştırma çerçevesi oluşturacağız. Bu çerçeve, kullanıcıların farklı bölümlere yakınlaştırma yapmasına olanak tanıyan etkileşimli öğe görevi görecektir.

1. İlk Slaydı Bul: Özet Yakınlaştırma çerçevesini ekleyeceğiniz ilk slaydı alın.
2. Özet Yakınlaştırma Çerçevesini ekleyin: `addSummaryZoomFrame` çerçeve ekleme yöntemi.
```java
ISummaryZoomFrame summaryZoomFrame = pres.getSlides().get_Item(0).getShapes().addSummaryZoomFrame(150, 50, 300, 200);
```
## Adım 4: Sunumu Kaydedin
Son olarak, sunumu istediğiniz yere kaydedin. Bu adım, tüm değişikliklerinizin bir dosyaya yazılmasını sağlar.
### Dosyayı Kaydet
1. Çıktı Yolunu Tanımlayın: Sunumun kaydedileceği yolu belirtin.
2. Sunuyu Kaydedin: Şunu kullanın: `save` Dosyayı PPTX formatında kaydetme yöntemi.
```java
String resultPath = "Your Output Directory" + "SummaryZoomPresentation.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
### Sunum Nesnesini Atın
Kullandığı kaynakları serbest bırakmak için sunum nesnesini elden çıkarın:
```java
if (pres != null) pres.dispose();
```
## Çözüm
Tebrikler! Aspose.Slides for Java kullanarak PowerPoint'te Özet Yakınlaştırma'yı başarıyla oluşturdunuz. Bu özellik, sunumlarınızı daha etkileşimli ve ilgi çekici hale getirerek geliştirir. Bu kılavuzu izleyerek, artık bu özelliği kendi projelerinizde uygulama becerisine sahipsiniz. [Java belgeleri için Aspose.Slides](https://reference.aspose.com/slides/java/) Daha gelişmiş özellikler ve özelleştirme seçenekleri için.
## SSS
### Java için Aspose.Slides nedir?
Aspose.Slides for Java, geliştiricilerin Java kullanarak PowerPoint sunumlarını programlı bir şekilde oluşturmalarına, değiştirmelerine ve düzenlemelerine olanak tanıyan güçlü bir kütüphanedir.
### PowerPoint'te diğer içerik türlerini oluşturmak için Aspose.Slides for Java'yı kullanabilir miyim?
Evet, Aspose.Slides for Java, slayt oluşturma, şekil, grafik, tablo ekleme ve daha birçok özelliği içeren geniş bir yelpazede özelliği destekler.
### Aspose.Slides for Java için ücretsiz deneme sürümü mevcut mu?
Evet, Aspose.Slides for Java'nın ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [web sitesi](https://releases.aspose.com/).
### Aspose.Slides for Java için geçici lisansı nasıl alabilirim?
Geçici bir lisansı şuradan alabilirsiniz: [Aspose satın alma sayfası](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java için daha fazla örnek ve desteği nerede bulabilirim?
Daha fazla örnek bulabilir ve destek alabilirsiniz. [Aspose.Slides destek forumu](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}