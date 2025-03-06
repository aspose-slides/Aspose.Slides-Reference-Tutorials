---
title: PowerPoint'te Biçimlendirilmiş Elips Oluşturun
linktitle: PowerPoint'te Biçimlendirilmiş Elips Oluşturun
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Ayrıntılı adım adım kılavuzumuzla Aspose.Slides for Java'yı kullanarak PowerPoint'te biçimlendirilmiş bir elips oluşturmayı öğrenin.
weight: 17
url: /tr/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Aspose.Slides for Java kullanarak PowerPoint'te biçimlendirilmiş bir elips oluşturmaya ilişkin bu kapsamlı eğitime hoş geldiniz. Aspose.Slides, geliştiricilerin PowerPoint dosyalarını programlı olarak değiştirmesine olanak tanıyan güçlü bir kitaplıktır. İster slayt oluşturmayı otomatikleştiriyor olun ister özel şekillerle sunumları geliştiriyor olun, bu kılavuz size her adımda yol gösterecek ve slaytlarınıza kolaylıkla mükemmel biçimlendirilmiş bir elips ekleyebilmenizi sağlayacaktır. Gelin derinlemesine inceleyelim ve bunu nasıl başarabileceğimizi görelim!
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): JDK 1.6 veya üstünün kurulu olduğundan emin olun.
2.  Java için Aspose.Slides: En son sürümü şu adresten indirin:[Aspose.Slides for Java](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA veya Eclipse gibi bir IDE kullanın.
4. Temel Java Bilgisi: Java programlamaya aşinalık gereklidir.
## Paketleri İçe Aktar
Aspose.Slides'ı kullanmaya başlamak için gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## 1. Adım: Proje Dizininizi Kurun
Öncelikle PowerPoint dosyalarınızı saklayacak bir dizine ihtiyacınız var.
### Dizin Oluştur
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Henüz mevcut değilse dizin oluşturun.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 Değiştirdiğinizden emin olun`"Your Document Directory"` dosyalarınızı depolamak istediğiniz gerçek yolla.
## Adım 2: Sunumu Başlatın
Şimdi PowerPoint dosyasını temsil eden Sunum sınıfını başlatın.
```java
// PPTX'i temsil eden Örnek Sunum sınıfı
Presentation pres = new Presentation();
```
## 3. Adım: İlk Slaydı Alın
Daha sonra sunumdan elipsi ekleyeceğiniz ilk slaydı alın.
```java
// İlk slaydı alın
ISlide sld = pres.getSlides().get_Item(0);
```
## Adım 4: Elips Şekli Ekleyin
Slayda elips türünde otomatik bir şekil ekleyin.
```java
// Elips tipinin otomatik şeklini ekleyin
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 Burada,`50, 150, 150, 50` elipsin koordinatları ve boyutudur (x konumu, y konumu, genişlik, yükseklik).
## Adım 5: Elips'e Biçimlendirme Uygulayın
Şimdi elipse biraz biçimlendirme uygulayın. Düz bir dolgu rengi ve çizgi rengi ayarlayacağız.
### Dolgu Rengini Ayarla
```java
// Elips şekline biraz biçimlendirme uygulayın
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Çizgi Rengini ve Genişliğini Ayarla
```java
// Elips çizgisine biraz biçimlendirme uygulayın
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Adım 6: Sunuyu Kaydetme
Son olarak sunuyu belirttiğiniz dizine kaydedin.
```java
// PPTX dosyasını diske yazın
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Adım 7: Sunum Nesnesini Atın
Kaynakları boşaltmak için sunum nesnesini atın.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Çözüm
Tebrikler! Aspose.Slides for Java'yı kullanarak PowerPoint sunumunda başarıyla biçimlendirilmiş bir elips oluşturdunuz. Bu eğitim, projenizi oluşturma, elips ekleme, biçimlendirme uygulama ve sununuzu kaydetme konusunda size yol gösterdi. Bu becerilerle artık PowerPoint slaytlarınızı programlı olarak geliştirebilir, sunumlarınızı daha dinamik ve görsel olarak çekici hale getirebilirsiniz.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, geliştiricilerin PowerPoint sunumlarını programlı olarak oluşturmasına, değiştirmesine ve yönetmesine olanak tanıyan güçlü bir kitaplıktır.
### Aspose.Slides for Java'yı herhangi bir IDE ile kullanabilir miyim?
Evet, Aspose.Slides for Java'yı IntelliJ IDEA, Eclipse veya NetBeans gibi herhangi bir Java IDE ile kullanabilirsiniz.
### Aspose.Slides için lisansa ihtiyacım var mı?
Evet, Aspose.Slides ticari bir üründür ve tam işlevsellik için lisansa ihtiyacınız vardır. Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java ile ilgili daha fazla belgeyi nerede bulabilirim?
 Aspose.Slides for Java'da ayrıntılı belgeler bulabilirsiniz[dokümantasyon sayfası](https://reference.aspose.com/slides/java/).
### Aspose.Slides için destek mevcut mu?
 Evet, Aspose kendi aracılığıyla destek sunuyor[forum](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
