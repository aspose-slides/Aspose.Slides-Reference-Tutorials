---
title: Özet Oluştur PowerPoint'te Yakınlaştır
linktitle: Özet Oluştur PowerPoint'te Yakınlaştır
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Bu kapsamlı adım adım eğitimle Aspose.Slides for Java'yı kullanarak PowerPoint'te Özet Yakınlaştırma oluşturmayı öğrenin.
weight: 16
url: /tr/java/java-powerpoint-shape-thumbnail-creation/create-summary-zoom-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Özet Oluştur PowerPoint'te Yakınlaştır

## giriiş
Aspose.Slides for Java kullanarak PowerPoint'te Özet Yakınlaştırma oluşturma hakkındaki kapsamlı eğitimimize hoş geldiniz. Sunumlarınıza dinamik ve etkileşimli bir öğe eklemek istiyorsanız Özet Yakınlaştırma harika bir özelliktir. Sunumunuzun farklı bölümlerini yakınlaştırabilen tek bir slayt oluşturmanıza olanak tanıyarak izleyicilerinize daha ilgi çekici ve gezinilebilir bir deneyim sunar.
Bu adım adım kılavuzda, geliştirme ortamınızı ayarlamaktan Özet Yakınlaştırma çerçevesi oluşturup özelleştirmeye kadar tüm süreç boyunca size yol göstereceğiz. İster deneyimli bir Java geliştiricisi olun ister yeni başlıyor olun, bu kılavuzun takip edilmesi kolay ve değerli bilgilerle dolu olduğunu göreceksiniz.
## Önkoşullar
Koda dalmadan önce, başlamak için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:
1.  Java Geliştirme Kiti (JDK): Makinenizde JDK'nın kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Oracle web sitesi](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Kitaplığı şu adresten indirin:[Aspose sürümler sayfası](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Daha kusursuz bir geliştirme deneyimi için IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE kullanın.
4. Temel Java Bilgisi: Java programlama kavramlarına aşina olmak, bu kılavuzdaki adımları anlamanıza ve uygulamanıza yardımcı olacaktır.
## Paketleri İçe Aktar
Başlamadan önce gerekli paketleri içe aktarmanız gerekiyor. Aspose.Slides for Java'yı proje bağımlılıklarınıza dahil ettiğinizden emin olun.
```java
import com.aspose.slides.*;

import java.awt.*;
```
## 1. Adım: Projenizi Kurun
Öncelikle geliştirme ortamınızın doğru şekilde kurulduğundan emin olun. Projenizi yapılandırmak için şu adımları izleyin:
### Yeni Bir Proje Oluştur
1. IDE'nizi açın.
2. Yeni bir Java projesi oluşturun.
3.  Aspose.Slides for Java kütüphanesini projenizin derleme yoluna ekleyin. JAR dosyasını şuradan indirebilirsiniz:[Aspose sürümler sayfası](https://releases.aspose.com/slides/java/) ve bunu projenize dahil edin.
### Sunumu Başlat
Daha sonra slaytlarınızı ve bölümlerinizi ekleyeceğiniz yeni bir sunum nesnesini başlatın.
```java
Presentation pres = new Presentation();
```
## 2. Adım: Slaytlar ve Bölümler Ekleme
Bu adımda sunuma slaytlar ekleyeceğiz ve bunları bölümler halinde düzenleyeceğiz. Bu organizasyon Özet Yakınlaştırma oluşturmak için çok önemlidir.
### Yeni Slayt ve Bölüm Ekle
1. Boş Slayt Ekle: Sunuma yeni bir slayt ekleyin.
2. Slayt Arka Planını Özelleştirin: Slayt arka planı için düz bir dolgu rengi ayarlayın.
3. Bölüm Ekle: Slaydı bir bölüm halinde gruplandırın.
İşte bunu başarmak için kod:
```java
// İlk slaydı ekleyin
ISlide slide = pres.getSlides().addEmptySlide(pres.getSlides().get_Item(0).getLayoutSlide());
slide.getBackground().getFillFormat().setFillType(FillType.Solid);
slide.getBackground().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
slide.getBackground().setType(BackgroundType.OwnBackground);
// İlk bölümü ekleyin
pres.getSections().addSection("Section 1", slide);
```
### Ek Bölümler için Tekrarlayın
Daha fazla slayt ve bölüm eklemek için işlemi tekrarlayın:
```java
// İkinci slaytı ve bölümü ekleyin
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
## 3. Adım: Özet Yakınlaştırma Çerçevesini Oluşturun
Şimdi ilk slaytta bir Özet Yakınlaştırma çerçevesi oluşturacağız. Bu çerçeve, kullanıcıların farklı bölümleri yakınlaştırmasına olanak tanıyan etkileşimli bir öğe görevi görecek.

1. İlk Slaydı Bulun: Özet Yakınlaştırma çerçevesini ekleyeceğiniz ilk slaydı alın.
2.  Özet Yakınlaştırma Çerçevesini ekleyin:`addSummaryZoomFrame` çerçeve ekleme yöntemi.
```java
ISummaryZoomFrame summaryZoomFrame = pres.getSlides().get_Item(0).getShapes().addSummaryZoomFrame(150, 50, 300, 200);
```
## 4. Adım: Sunuyu Kaydetme
Son olarak sunuyu istediğiniz konuma kaydedin. Bu adım, tüm değişikliklerinizin bir dosyaya yazılmasını sağlar.
### Dosya 'yı kaydet
1. Çıkış Yolunu Tanımlayın: Sunumun kaydedileceği yolu belirtin.
2.  Sunuyu Kaydet:`save` dosyayı PPTX formatında kaydetme yöntemi.
```java
String resultPath = "Your Output Directory" + "SummaryZoomPresentation.pptx";
pres.save(resultPath, SaveFormat.Pptx);
```
### Sunum Nesnesini Atın
Kullandığı kaynakları serbest bırakmak için sunum nesnesini atın:
```java
if (pres != null) pres.dispose();
```
## Çözüm
 Tebrikler! Aspose.Slides for Java'yı kullanarak PowerPoint'te başarıyla Özet Yakınlaştırma oluşturdunuz. Bu özellik sunumlarınızı daha etkileşimli ve ilgi çekici hale getirerek geliştirir. Bu kılavuzu takip ederek artık bu özelliği kendi projelerinizde uygulayabilecek becerilere sahipsiniz. Keşfetmeyi unutmayın[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/)daha gelişmiş özellikler ve kişiselleştirme seçenekleri için.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, geliştiricilerin Java kullanarak programlı olarak PowerPoint sunumları oluşturmasına, değiştirmesine ve işlemesine olanak tanıyan güçlü bir kitaplıktır.
### Aspose.Slides for Java'yı PowerPoint'te başka türde içerik oluşturmak için kullanabilir miyim?
Evet, Aspose.Slides for Java; slayt oluşturma, şekil, grafik, tablo ekleme ve çok daha fazlasını içeren çok çeşitli özellikleri destekler.
### Aspose.Slides for Java'nın ücretsiz deneme sürümü mevcut mu?
Evet, Aspose.Slides for Java'nın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[İnternet sitesi](https://releases.aspose.com/).
### Aspose.Slides for Java için nasıl geçici lisans alabilirim?
 Geçici lisansı adresinden alabilirsiniz.[Satın alma sayfasını atayın](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java için daha fazla örneği ve desteği nerede bulabilirim?
 Daha fazla örnek bulabilir ve destek alabilirsiniz.[Aspose.Slides destek forumu](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
