---
title: Java PowerPoint'te Özel Madde İşareti Numarasını Ayarlama
linktitle: Java PowerPoint'te Özel Madde İşareti Numarasını Ayarlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides ile Java PowerPoint'te özel madde işareti numaralarını nasıl ayarlayacağınızı, sunum netliğini ve yapısını programlı olarak nasıl geliştireceğinizi öğrenin.
weight: 15
url: /tr/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint'te Özel Madde İşareti Numarasını Ayarlama

## giriiş
Günümüzün dijital çağında, fikirlerin ve verilerin etkili bir şekilde iletilmesi için dinamik sunumlar oluşturmak çok önemlidir. Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak yönetmek için güçlü bir araç seti sağlayarak sunum oluşturma sürecinizi geliştirecek kapsamlı özellikler sunar. Bu makalede Aspose.Slides kullanılarak Java PowerPoint sunumlarında özel madde işareti numaralarının ayarlanması anlatılmaktadır. İster deneyimli bir geliştirici ister yeni başlayan biri olun, bu eğitim size süreç boyunca adım adım rehberlik edecek ve bu özellikten verimli bir şekilde yararlanabilmenizi sağlayacaktır.
## Önkoşullar
Öğreticiye dalmadan önce, geliştirme ortamınızda aşağıdaki ön koşulların kurulu olduğundan emin olun:
- Java Geliştirme Kiti (JDK) yüklü
- IntelliJ IDEA veya Eclipse gibi Entegre Geliştirme Ortamı (IDE)
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/)
- Java programlama dili ve nesne yönelimli kavramların temel anlayışı

## Paketleri İçe Aktar
Öncelikle gerekli Aspose.Slides sınıflarını ve diğer Java standart kütüphanelerini içe aktarın:
```java
import com.aspose.slides.*;
```
## Adım 1: Sunum Nesnesi Oluşturun
Aspose.Slides'ı kullanarak yeni bir PowerPoint sunumu oluşturarak başlayın.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## 2. Adım: Metinle Otomatik Şekil Ekleme
Slayda bir Otomatik Şekil (Dikdörtgen) ekleyin ve metin çerçevesine erişin.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## 3. Adım: Varsayılan Paragrafı Kaldır
Varsayılan mevcut paragrafı metin çerçevesinden kaldırın.
```java
textFrame.getParagraphs().removeAt(0);
```
## Adım 4: Numaralı Madde İşaretleri Ekleyin
Belirli numaralardan başlayarak özel numaralı madde işaretleri içeren paragraflar ekleyin.
```java
// 2'den başlayan madde işaretli örnek paragraf
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// 3'ten başlayan madde işaretli örnek paragraf
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// 7'den başlayan madde işaretli örnek paragraf
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## Adım 5: Sunuyu Kaydetme
Son olarak değiştirilen sunumu istediğiniz konuma kaydedin.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## Çözüm
Sonuç olarak Aspose.Slides for Java, PowerPoint sunumlarında özel madde işareti numaralarını program aracılığıyla ayarlama işlemini basitleştirir. Bu eğitimde özetlenen adımları izleyerek sunumlarınızın görsel netliğini ve yapısını verimli bir şekilde geliştirebilirsiniz.
## SSS'ler
### Madde işaretlerinin görünümünü daha da özelleştirebilir miyim?
Evet, Aspose.Slides madde işareti türünü, boyutunu, rengini ve daha fazlasını özelleştirmek için kapsamlı seçenekler sunar.
### Aspose.Slides PowerPoint'in tüm sürümleriyle uyumlu mu?
Aspose.Slides, 97-2003 arası PowerPoint formatlarını en son sürümlere kadar destekler.
### Aspose.Slides için nasıl teknik destek alabilirim?
 Ziyaret etmek[Aspose.Slides Forumu](https://forum.aspose.com/c/slides/11) teknik yardım için.
### Satın almadan önce Aspose.Slides'ı deneyebilir miyim?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Slides'ı nereden satın alabilirim?
 Aspose.Slides'ı şu adresten satın alabilirsiniz:[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
