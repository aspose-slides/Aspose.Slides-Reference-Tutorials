---
title: Java PowerPoint'te Çok Düzeyli Madde İşaretleri Oluşturma
linktitle: Java PowerPoint'te Çok Düzeyli Madde İşaretleri Oluşturma
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint'te çok düzeyli madde işaretleri oluşturmayı öğrenin. Kod örnekleri ve SSS içeren adım adım kılavuz.
weight: 14
url: /tr/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint sunumlarında çok düzeyli madde işaretlerinin nasıl oluşturulacağını keşfedeceğiz. Sunumlarda düzenli ve görsel olarak çekici içerik oluşturmak için madde işaretleri eklemek yaygın bir gereksinimdir. Süreci adım adım inceleyeceğiz ve bu kılavuzun sonunda sunumlarınızı birden çok düzeyde yapılandırılmış maddelerle zenginleştirecek donanıma sahip olmanızı sağlayacağız.
## Önkoşullar
Başlamadan önce aşağıdaki kurulumlara sahip olduğunuzdan emin olun:
- Java Geliştirme Ortamı: Sisteminizde Java Geliştirme Kitinin (JDK) kurulu olduğundan emin olun.
-  Aspose.Slides for Java Kütüphanesi: Aspose.Slides for Java'yı şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/slides/java/).
- IDE: IntelliJ IDEA, Eclipse veya diğerleri gibi tercih ettiğiniz Java Entegre Geliştirme Ortamını (IDE) kullanın.
- Temel Bilgi: Java programlamaya ve temel PowerPoint kavramlarına aşina olmak faydalı olacaktır.

## Paketleri İçe Aktar
Derse dalmadan önce ders boyunca kullanacağımız gerekli paketleri Aspose.Slides for Java'dan içe aktaralım.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## 1. Adım: Projenizi Kurun
Öncelikle IDE'nizde yeni bir Java projesi oluşturun ve Aspose.Slides for Java'yı projenizin bağımlılıklarına ekleyin. Gerekli Aspose.Slides JAR dosyasının projenizin derleme yoluna dahil edildiğinden emin olun.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
```
## Adım 2: Sunum Nesnesini Başlatın
Yeni bir sunum örneği oluşturarak başlayın. Bu, slaytlar ve içerik ekleyeceğiniz PowerPoint belgeniz olarak hizmet verecektir.
```java
Presentation pres = new Presentation();
```
## 3. Adım: Slayta Erişin
Ardından, çok düzeyli madde işaretlerini eklemek istediğiniz slayda erişin. Bu örnek için ilk slaytla çalışacağız (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 4. Adım: Metin Çerçevesi ile Otomatik Şekil Ekleme
Metninizi çok düzeyli madde işaretleri ile yerleştireceğiniz slayda bir Otomatik Şekil ekleyin.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Adım 5: Metin Çerçevesine Erişim
Otomatik Şekil'de madde işaretleri içeren paragraflar ekleyeceğiniz metin çerçevesine erişin.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); //Varsayılan paragrafları temizle
```
## Adım 6: Madde İşaretli Paragraflar Ekleme
Farklı düzeylerde madde işaretleri içeren paragraflar ekleyin. Çok düzeyli madde işaretlerini şu şekilde ekleyebilirsiniz:
```java
// İlk seviye
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// İkinci seviye
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// Üçüncü seviye
IParagraph para3 = new Paragraph();
para3.setText("Third Level");
para3.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para3.getParagraphFormat().getBullet().setChar((char) 8226);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para3.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para3.getParagraphFormat().setDepth((short) 2);
text.getParagraphs().add(para3);
// Dördüncü Seviye
IParagraph para4 = new Paragraph();
para4.setText("Fourth Level");
para4.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para4.getParagraphFormat().getBullet().setChar('-');
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para4.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para4.getParagraphFormat().setDepth((short) 3);
text.getParagraphs().add(para4);
```
## Adım 7: Sunuyu Kaydet
Son olarak sunuyu istediğiniz dizine PPTX dosyası olarak kaydedin.
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde Aspose.Slides for Java kullanarak PowerPoint sunumlarında çok düzeyli madde işaretlerinin nasıl oluşturulacağını ele aldık. Bu adımları izleyerek içeriğinizi farklı düzeylerdeki düzenli madde işaretleri ile etkili bir şekilde yapılandırabilir, sunumlarınızın netliğini ve görsel çekiciliğini artırabilirsiniz.
## SSS'ler
### Madde işareti simgelerini daha da özelleştirebilir miyim?
Evet, Unicode karakterleri ayarlayarak veya farklı şekiller kullanarak madde işareti simgelerini özelleştirebilirsiniz.
### Aspose.Slides diğer madde işareti türlerini destekliyor mu?
Evet, Aspose.Slides semboller, sayılar ve özel görseller de dahil olmak üzere çeşitli madde işareti türlerini destekler.
### Aspose.Slides PowerPoint'in tüm sürümleriyle uyumlu mu?
Aspose.Slides, Microsoft PowerPoint 2007 ve üzeri sürümlerle uyumlu sunumlar oluşturur.
### Aspose.Slides'ı kullanarak slayt oluşturmayı otomatikleştirebilir miyim?
Evet, Aspose.Slides, PowerPoint sunumlarının oluşturulmasını, değiştirilmesini ve işlenmesini otomatikleştirmek için API'ler sağlar.
### Aspose.Slides for Java için nereden destek alabilirim?
 Aspose.Slides topluluğundan ve uzmanlardan destek alabilirsiniz:[Aspose.Slides Forumu](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
