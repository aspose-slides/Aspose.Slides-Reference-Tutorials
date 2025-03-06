---
title: Java ile Programlı Olarak Slayta Metin Kutusu Ekleme
linktitle: Java ile Programlı Olarak Slayta Metin Kutusu Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint slaytlarına programlı olarak nasıl metin kutusu ekleyeceğinizi öğrenin. Bu adım adım kılavuzla üretkenliğinizi artırın.
weight: 24
url: /tr/java/java-powerpoint-text-font-customization/add-text-box-slide-programmatically-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
PowerPoint sunumlarını programlı olarak oluşturmak ve değiştirmek, rapor oluşturmaktan sunumları otomatikleştirmeye kadar birçok iş akışını kolaylaştırabilir. Aspose.Slides for Java, geliştiricilerin bu görevleri verimli bir şekilde gerçekleştirmesine olanak tanıyan güçlü bir API sağlar. Bu eğitimde Aspose.Slides for Java'yı kullanarak bir slayda metin kutusu ekleme konusunda size rehberlik edeceğiz. Bu eğitimin sonunda, bu işlevselliği Java uygulamalarınıza nasıl entegre edeceğiniz konusunda net bir anlayışa sahip olacaksınız.
## Önkoşullar
Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Java Geliştirme Kiti (JDK) yüklü
- IntelliJ IDEA veya Eclipse gibi IDE (Entegre Geliştirme Ortamı)
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/)
- Java programlamayla ilgili temel bilgiler
## Paketleri İçe Aktar
İlk olarak kodlamaya başlamak için Aspose.Slides ve Java çekirdek kütüphanelerinden gerekli paketleri içe aktarın.
```java
import com.aspose.slides.*;
import java.io.File;
```
## 1. Adım: Projenizi Kurun
IDE'nizde yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini projenizin derleme yoluna ekleyin. Henüz indirmediyseniz şu adresten edinin:[Burada](https://releases.aspose.com/slides/java/).
## Adım 2: Sunum Nesnesini Başlatın
 Bir başlat`Presentation` PowerPoint dosyasını temsil eden nesne.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## 3. Adım: Slayta Erişin ve Otomatik Şekil Ekleyin
Sunudaki ilk slaydı alın ve buna bir Otomatik Şekil (Dikdörtgen) ekleyin.
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## 4. Adım: Otomatik Şekil'e Metin Çerçevesi Ekleme
Metni içerecek şekilde Otomatik Şekil'e bir metin çerçevesi ekleyin.
```java
shape.addTextFrame(" ");
ITextFrame textFrame = shape.getTextFrame();
```
## Adım 5: Metin İçeriğini Ayarlayın
Metin çerçevesinin içindeki metin içeriğini ayarlayın.
```java
IParagraph para = textFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## Adım 6: Sunuyu Kaydet
Değiştirilen sunumu bir dosyaya kaydedin.
```java
pres.save(dataDir + "TextBox_out.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde Aspose.Slides for Java kullanarak bir slayta programlı olarak nasıl metin kutusu ekleneceğini araştırdık. Bu özellik, geliştiricilerin PowerPoint sunumlarının oluşturulmasını ve özelleştirilmesini otomatikleştirmesine olanak tanıyarak çeşitli uygulamalarda üretkenliği ve verimliliği artırır.
## SSS'ler
### Aspose.Slides for Java dikdörtgenlerin yanı sıra diğer şekilleri de işleyebilir mi?
Evet, Aspose.Slides daire, çizgi ve daha fazlası gibi çeşitli şekilleri destekler.
### Aspose.Slides for Java büyük ölçekli kurumsal uygulamalara uygun mu?
Kesinlikle karmaşık görevleri verimli bir şekilde yerine getirmek için tasarlandı.
### Aspose.Slides için daha fazla örnek ve belgeyi nerede bulabilirim?
 Ziyaret edin[Aspose.Slides belgeleri](https://reference.aspose.com/slides/java/) Kapsamlı kılavuzlar ve örnekler için.
### Test için nasıl geçici lisans alabilirim?
 Bir[geçici lisans](https://purchase.aspose.com/temporary-license/) Aspose'tan.
### Aspose.Slides sunumların diğer formatlara dönüştürülmesini destekliyor mu?
Evet, PDF ve resimler dahil çeşitli formatları destekler.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
