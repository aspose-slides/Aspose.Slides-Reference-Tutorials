---
title: Java ile PowerPoint'te Porsiyon Dikdörtgenini Alın
linktitle: Java ile PowerPoint'te Porsiyon Dikdörtgenini Alın
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Bu ayrıntılı, adım adım eğitimle Aspose.Slides for Java kullanarak PowerPoint'te porsiyon dikdörtgenini nasıl alacağınızı öğrenin. Java geliştiricileri için mükemmel.
weight: 12
url: /tr/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
Aspose.Slides for Java ile Java'da dinamik sunumlar oluşturmak çok kolay. Bu derste Aspose.Slides'ı kullanarak PowerPoint'te porsiyon dikdörtgeni almanın en ince ayrıntısına kadar inceleyeceğiz. Ortamınızın kurulumundan kodun adım adım çözülmesine kadar her şeyi ele alacağız. Öyleyse başlayalım!
## Önkoşullar
Koda geçmeden önce, sorunsuz bir şekilde takip etmeniz gereken her şeye sahip olduğunuzdan emin olalım:
1. Java Geliştirme Kiti (JDK): Makinenizde JDK 8 veya üstünün kurulu olduğundan emin olun.
2.  Aspose.Slides for Java: En son sürümü şu adresten indirin:[Burada](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Eclipse, IntelliJ IDEA veya seçtiğiniz herhangi bir Java IDE.
4. Temel Java Bilgisi: Java programlamayı anlamak çok önemlidir.
## Paketleri İçe Aktar
Öncelikle gerekli paketleri import edelim. Bu, Aspose.Slides'ı ve görevimizi verimli bir şekilde yerine getirmemizi sağlayacak birkaç uygulamayı daha içerecek.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Adım 1: Sunumu Ayarlama
İlk adım yeni bir sunum oluşturmaktır. Bu bizim üzerinde çalışacağımız tuvalimiz olacak.
```java
Presentation pres = new Presentation();
```
## Adım 2: Tablo Oluşturma
Şimdi sunumumuzun ilk slaytına bir tablo ekleyelim. Bu tablo metnimizi ekleyeceğimiz hücreleri içerecektir.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Adım 3: Hücrelere Paragraf Ekleme
Daha sonra paragraflar oluşturup bunları tablodaki belirli bir hücreye ekleyeceğiz. Bu, mevcut metnin silinmesini ve ardından yeni paragrafların eklenmesini içerir.
```java
// Paragraflar oluştur
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Tablo hücresine metin ekleme
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Adım 4: Otomatik Şekil'e Metin Çerçevesi Ekleme
Sunumumuzu daha dinamik hale getirmek için Otomatik Şekil'e bir metin çerçevesi ekleyeceğiz ve hizalamasını ayarlayacağız.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Adım 5: Koordinatların Hesaplanması
Tablo hücresinin sol üst köşesinin koordinatlarını almamız gerekiyor. Bu, şekilleri doğru şekilde yerleştirmemize yardımcı olacaktır.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Adım 6: Paragraflara ve Bölümlere Çerçeve Ekleme
 Kullanmak`IParagraph.getRect()` Ve`IPortion.getRect()`yöntemleri kullanarak paragraflarımıza ve bölümlerimize çerçeveler ekleyebiliriz. Bu, paragraflar ve bölümler arasında yineleme yapmayı, bunların etrafında şekiller oluşturmayı ve görünümlerini özelleştirmeyi içerir.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Adım 7: Otomatik Şekil Paragraflarına Çerçeve Ekleme
Benzer şekilde, Otomatik Şekil'deki paragraflara çerçeveler ekleyerek sunumun görsel çekiciliğini artıracağız.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Adım 8: Sunumu Kaydetme
Son olarak sunumuzu belirtilen yola kaydedeceğiz.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Adım 9: Temizleme
Kaynakları serbest bırakmak için sunum nesnesini elden çıkarmak iyi bir uygulamadır.
```java
if (pres != null) pres.dispose();
```
## Çözüm
Tebrikler! Aspose.Slides for Java kullanarak PowerPoint'te porsiyon dikdörtgeninin nasıl elde edileceğini başarıyla öğrendiniz. Bu güçlü kütüphane, programlı olarak dinamik ve görsel olarak çekici sunumlar oluşturmak için bir olasılıklar dünyasının kapılarını açar. Aspose.Slides'ı daha derinlemesine inceleyin ve sunumlarınızı daha da geliştirmek için daha fazla özelliği keşfedin.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, geliştiricilerin PowerPoint sunumlarını programlı olarak oluşturmasına, değiştirmesine ve işlemesine olanak tanıyan güçlü bir kitaplıktır.
### Aspose.Slides for Java'yı ticari projelerde kullanabilir miyim?
 Evet, Aspose.Slides for Java ticari projelerde kullanılabilir. adresinden lisans satın alabilirsiniz.[Burada](https://purchase.aspose.com/buy).
### Aspose.Slides for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Slides for Java belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java için nasıl destek alabilirim?
 Aspose forumundan destek alabilirsiniz[Burada](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
