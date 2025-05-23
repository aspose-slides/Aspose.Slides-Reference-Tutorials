---
"description": "Bu ayrıntılı, adım adım eğitimle Aspose.Slides for Java kullanarak PowerPoint'te bölüm dikdörtgeninin nasıl elde edileceğini öğrenin. Java geliştiricileri için mükemmel."
"linktitle": "Java ile PowerPoint'te Bölüm Dikdörtgeni Alın"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java ile PowerPoint'te Bölüm Dikdörtgeni Alın"
"url": "/tr/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java ile PowerPoint'te Bölüm Dikdörtgeni Alın

## giriiş
Java'da dinamik sunumlar oluşturmak Aspose.Slides for Java ile çocuk oyuncağı. Bu eğitimde, Aspose.Slides kullanarak PowerPoint'te bölüm dikdörtgeni elde etmenin inceliklerine dalacağız. Ortamınızı kurmaktan kodu adım adım parçalamaya kadar her şeyi ele alacağız. Hadi başlayalım!
## Ön koşullar
Koda geçmeden önce, sorunsuz bir şekilde takip edebilmeniz için ihtiyacınız olan her şeye sahip olduğunuzdan emin olalım:
1. Java Geliştirme Kiti (JDK): Makinenizde JDK 8 veya üzeri sürümün yüklü olduğundan emin olun.
2. Java için Aspose.Slides: En son sürümü şu adresten indirin: [Burada](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Eclipse, IntelliJ IDEA veya tercih ettiğiniz herhangi bir Java IDE.
4. Temel Java Bilgisi: Java programlamayı anlamak esastır.
## Paketleri İçe Aktar
İlk önce gerekli paketleri içe aktaralım. Bunlara Aspose.Slides ve görevimizi verimli bir şekilde halletmek için birkaç tane daha dahil olacak.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Adım 1: Sunumu Ayarlama
İlk adım yeni bir sunum oluşturmaktır. Bu, üzerinde çalışacağımız tuvalimiz olacaktır.
```java
Presentation pres = new Presentation();
```
## Adım 2: Bir Tablo Oluşturma
Şimdi sunumumuzun ilk slaydına bir tablo ekleyelim. Bu tablo metnimizi ekleyeceğimiz hücreleri içerecek.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Adım 3: Hücrelere Paragraf Ekleme
Sonra, paragraflar oluşturacağız ve bunları tablodaki belirli bir hücreye ekleyeceğiz. Bu, mevcut metni temizlemeyi ve ardından yeni paragraflar eklemeyi içerir.
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
// Tablo hücresine metin ekleyin
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Adım 4: Otomatik Şekle Metin Çerçevesi Ekleme
Sunumumuzu daha dinamik hale getirmek için bir Otomatik Şekle metin çerçevesi ekleyeceğiz ve hizalamasını ayarlayacağız.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Adım 5: Koordinatların Hesaplanması
Tablo hücresinin sol üst köşesinin koordinatlarını almamız gerekiyor. Bu, şekilleri doğru bir şekilde yerleştirmemize yardımcı olacaktır.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Adım 6: Paragraflara ve Bölümlere Çerçeve Ekleme
Kullanımı `IParagraph.getRect()` Ve `IPortion.getRect()` yöntemleriyle, paragraflarımıza ve bölümlerimize çerçeveler ekleyebiliriz. Bu, paragraflar ve bölümler arasında yineleme yapmayı, etraflarında şekiller oluşturmayı ve görünümlerini özelleştirmeyi içerir.
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
Benzer şekilde, AutoShape'imizdeki paragraflara çerçeveler ekleyerek sunumun görsel çekiciliğini artıracağız.
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
Son olarak sunumuzu belirtilen bir yola kaydedeceğiz.
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
Tebrikler! Aspose.Slides for Java kullanarak PowerPoint'te bölüm dikdörtgenini nasıl elde edeceğinizi başarıyla öğrendiniz. Bu güçlü kütüphane, dinamik ve görsel olarak çekici sunumları programatik olarak oluşturmak için bir olasılıklar dünyasının kapılarını açar. Aspose.Slides'a daha derinlemesine dalın ve sunumlarınızı daha da geliştirmek için daha fazla özelliği keşfedin.
## SSS
### Java için Aspose.Slides nedir?
Aspose.Slides for Java, geliştiricilerin PowerPoint sunumlarını programlı bir şekilde oluşturmalarına, değiştirmelerine ve düzenlemelerine olanak tanıyan güçlü bir kütüphanedir.
### Aspose.Slides for Java'yı ticari projelerde kullanabilir miyim?
Evet, Aspose.Slides for Java ticari projelerde kullanılabilir. Lisansı şuradan satın alabilirsiniz: [Burada](https://purchase.aspose.com/buy).
### Aspose.Slides for Java için ücretsiz deneme sürümü mevcut mu?
Evet, ücretsiz deneme sürümünü şu adresten indirebilirsiniz: [Burada](https://releases.aspose.com/).
### Aspose.Slides for Java'nın belgelerini nerede bulabilirim?
Belgeler mevcuttur [Burada](https://reference.aspose.com/slides/java/).
### Java için Aspose.Slides desteğini nasıl alabilirim?
Aspose forumundan destek alabilirsiniz [Burada](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}