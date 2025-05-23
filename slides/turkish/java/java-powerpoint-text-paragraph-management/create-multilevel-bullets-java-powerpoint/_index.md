---
"description": "Aspose.Slides for Java kullanarak PowerPoint'te çok seviyeli madde işaretlerinin nasıl oluşturulacağını öğrenin. Kod örnekleri ve SSS içeren adım adım kılavuz."
"linktitle": "Java PowerPoint'te Çok Düzeyli Madde İşaretleri Oluşturma"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java PowerPoint'te Çok Düzeyli Madde İşaretleri Oluşturma"
"url": "/tr/java/java-powerpoint-text-paragraph-management/create-multilevel-bullets-java-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java PowerPoint'te Çok Düzeyli Madde İşaretleri Oluşturma

## giriiş
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarında çok seviyeli madde işaretlerinin nasıl oluşturulacağını inceleyeceğiz. Madde işaretleri eklemek, sunumlarda düzenli ve görsel olarak çekici içerik oluşturmak için yaygın bir gerekliliktir. Süreci adım adım ele alacağız ve bu kılavuzun sonunda sunumlarınızı birden fazla seviyede yapılandırılmış madde işaretleriyle zenginleştirebileceğinizden emin olacağız.
## Ön koşullar
Başlamadan önce aşağıdaki ayarların yapıldığından emin olun:
- Java Geliştirme Ortamı: Sisteminizde Java Geliştirme Kiti'nin (JDK) yüklü olduğundan emin olun.
- Aspose.Slides for Java Kütüphanesi: Aspose.Slides for Java'yı indirin ve yükleyin [Burada](https://releases.aspose.com/slides/java/).
- IDE: IntelliJ IDEA, Eclipse veya diğerleri gibi tercih ettiğiniz Java Entegre Geliştirme Ortamını (IDE) kullanın.
- Temel Bilgi: Java programlama ve temel PowerPoint kavramlarına aşinalık faydalı olacaktır.

## Paketleri İçe Aktar
Eğitime başlamadan önce, eğitim boyunca kullanacağımız Aspose.Slides for Java'dan gerekli paketleri içe aktaralım.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Adım 1: Projenizi Kurun
Öncelikle IDE'nizde yeni bir Java projesi oluşturun ve Aspose.Slides for Java'yı projenizin bağımlılıklarına ekleyin. Gerekli Aspose.Slides JAR dosyasının projenizin yapı yoluna dahil edildiğinden emin olun.
```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
```
## Adım 2: Sunum Nesnesini Başlat
Yeni bir sunum örneği oluşturarak başlayın. Bu, slaytlar ve içerik ekleyeceğiniz PowerPoint belgeniz olarak hizmet edecektir.
```java
Presentation pres = new Presentation();
```
## Adım 3: Slayda Erişim
Sonra, çok seviyeli madde işaretlerini eklemek istediğiniz slayda erişin. Bu örnek için, ilk slaytla çalışacağız (`Slide(0)`).
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Adım 4: Metin Çerçevesi ile Otomatik Şekil Ekleme
Metninizi çok seviyeli madde işaretleriyle yerleştireceğiniz slayda bir Otomatik Şekil ekleyin.
```java
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Adım 5: Metin Çerçevesine Erişim
Otomatik Şekil içindeki, madde işaretli paragraflar ekleyeceğiniz metin çerçevesine erişin.
```java
ITextFrame text = aShp.addTextFrame("");
text.getParagraphs().clear(); // Varsayılan paragrafları temizle
```
## Adım 6: Madde İşaretli Paragraflar Ekleyin
Farklı seviyelerde madde işaretlerine sahip paragraflar ekleyin. Çok seviyeli madde işaretlerini şu şekilde ekleyebilirsiniz:
```java
// Birinci Seviye
IParagraph para1 = new Paragraph();
para1.setText("Content");
para1.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para1.getParagraphFormat().getBullet().setChar((char) 8226);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para1.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para1.getParagraphFormat().setDepth((short) 0);
text.getParagraphs().add(para1);
// İkinci Seviye
IParagraph para2 = new Paragraph();
para2.setText("Second Level");
para2.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para2.getParagraphFormat().getBullet().setChar('-');
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().setFillType(FillType.Solid);
para2.getParagraphFormat().getDefaultPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
para2.getParagraphFormat().setDepth((short) 1);
text.getParagraphs().add(para2);
// Üçüncü Seviye
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
## Adım 7: Sunumu Kaydedin
Son olarak sunumu istediğiniz dizine PPTX dosyası olarak kaydedin.
```java
pres.save(dataDir + "MultilevelBullet.pptx", SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarında çok seviyeli madde işaretlerinin nasıl oluşturulacağını ele aldık. Bu adımları izleyerek, farklı seviyelerde düzenlenmiş madde işaretleriyle içeriğinizi etkili bir şekilde yapılandırabilir, sunumlarınızın netliğini ve görsel çekiciliğini artırabilirsiniz.
## SSS
### Madde işaretlerini daha fazla özelleştirebilir miyim?
Evet, Unicode karakterlerini ayarlayarak veya farklı şekiller kullanarak madde işaretlerini özelleştirebilirsiniz.
### Aspose.Slides diğer madde işaretli tiplerini destekliyor mu?
Evet, Aspose.Slides semboller, sayılar ve özel resimler de dahil olmak üzere çeşitli madde işareti türlerini destekler.
### Aspose.Slides PowerPoint'in tüm sürümleriyle uyumlu mudur?
Aspose.Slides, Microsoft PowerPoint 2007 ve üzeri sürümlerle uyumlu sunular oluşturur.
### Aspose.Slides kullanarak slaytların oluşturulmasını otomatikleştirebilir miyim?
Evet, Aspose.Slides, PowerPoint sunumlarının oluşturulmasını, değiştirilmesini ve düzenlenmesini otomatikleştirmek için API'ler sağlar.
### Aspose.Slides for Java için desteği nereden alabilirim?
Aspose.Slides topluluğundan ve uzmanlarından destek alabilirsiniz [Aspose.Slides Forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}