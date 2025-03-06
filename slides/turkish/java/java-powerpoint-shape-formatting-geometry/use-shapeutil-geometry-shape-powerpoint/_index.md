---
title: PowerPoint'te Geometri Şekli için ShapeUtil'i kullanın
linktitle: PowerPoint'te Geometri Şekli için ShapeUtil'i kullanın
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile PowerPoint'te özel şekiller oluşturun. Sunumlarınızı geliştirmek için bu adım adım kılavuzu izleyin.
weight: 23
url: /tr/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Geometri Şekli için ShapeUtil'i kullanın

## giriiş
Görsel olarak çekici PowerPoint sunumları oluşturmak genellikle standart şekilleri ve metni kullanmaktan daha fazlasını gerektirir. Sununuzun görsel etkisini artıracak şekilde doğrudan slaytlarınıza özelleştirilmiş şekiller ve metin yolları ekleyebileceğinizi hayal edin. Aspose.Slides for Java'yı kullanarak bunu kolaylıkla başarabilirsiniz. Bu eğitim, kullanım sürecinde size rehberlik edecektir.`ShapeUtil` PowerPoint sunumlarında geometri şekilleri oluşturmak için sınıf. İster tecrübeli bir geliştirici olun ister yeni başlıyor olun, bu adım adım kılavuz Aspose.Slides for Java'nın gücünden yararlanarak çarpıcı, özel şekilli içerikler oluşturmanıza yardımcı olacaktır.
## Önkoşullar
Eğiticiye dalmadan önce ihtiyacınız olacak birkaç şey var:
1. Java Geliştirme Kiti (JDK): Makinenizde JDK 8 veya üstünün kurulu olduğundan emin olun.
2.  Aspose.Slides for Java: En son sürümü şuradan indirin:[indirme sayfası](https://releases.aspose.com/slides/java/).
3. Geliştirme Ortamı: IntelliJ IDEA, Eclipse veya NetBeans gibi herhangi bir Java IDE'yi kullanın.
4.  Geçici Lisans: Şu adresten ücretsiz bir geçici lisans edinin:[Aspose'un geçici lisans sayfası](https://purchase.aspose.com/temporary-license/) Aspose.Slides for Java'nın tüm işlevlerinin kilidini açmak için.
## Paketleri İçe Aktar
Başlamak için Aspose.Slides ve Java AWT (Soyut Pencere Araç Seti) ile çalışmak için gerekli paketleri içe aktarmanız gerekir:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.awt.Shape;
import java.awt.font.GlyphVector;
import java.awt.image.BufferedImage;
```
## 1. Adım: Projenizi Kurma
Öncelikle Java projenizi kurun ve Aspose.Slides for Java'yı projenizin bağımlılıklarına ekleyin. Bunu, JAR dosyalarını doğrudan ekleyerek veya Maven veya Gradle gibi bir derleme aracı kullanarak yapabilirsiniz.
## Adım 2: Yeni Bir Sunu Oluşturun
Yeni bir PowerPoint sunum nesnesi oluşturarak başlayın. Bu nesne, özel şekillerinizi ekleyeceğiniz tuval olacaktır.
```java
Presentation pres = new Presentation();
```
## Adım 3: Dikdörtgen Şekli Ekleme
Daha sonra sunumun ilk slaydına temel bir dikdörtgen şekli ekleyin. Bu şekil daha sonra özel bir geometri yolu içerecek şekilde değiştirilecektir.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## Adım 4: Geometri Yolunu Alın ve Değiştirin
 Dikdörtgen şeklinin geometri yolunu alın ve dolgu modunu şu şekilde değiştirin:`None`. Bu adım, bu yolu başka bir özel geometri yoluyla birleştirmenize olanak tanıdığı için çok önemlidir.
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## Adım 5: Metinden Özel Bir Geometri Yolu Oluşturun
Şimdi metne dayalı özel bir geometri yolu oluşturun. Bu, bir metin dizesini grafiksel bir yola dönüştürmeyi ve ardından bu yolu bir geometri yoluna dönüştürmeyi içerir.
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## Adım 6: Geometri Yollarını Birleştirin
Orijinal geometri yolunu yeni metin tabanlı geometri yolu ile birleştirin ve bu birleşimi şekle ayarlayın.
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## Adım 7: Sunuyu Kaydet
Son olarak değiştirilen sunumu bir dosyaya kaydedin. Bu, özel şekillerinizi içeren bir PowerPoint dosyasının çıktısını alacaktır.
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## Çözüm
Tebrikler! Aspose.Slides for Java'yı kullanarak bir PowerPoint sunumunda özel bir geometri şekli oluşturdunuz. Bu eğitim, projenizi ayarlamaktan geometri yollarını oluşturmaya ve birleştirmeye kadar her adımda size yol gösterdi. Bu tekniklere hakim olarak sunumlarınıza benzersiz ve göz alıcı öğeler ekleyerek onları öne çıkarabilirsiniz.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, Java'da PowerPoint dosyalarıyla çalışmak için güçlü bir API'dir. Sunumları programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanır.
### Aspose.Slides for Java'yı nasıl yüklerim?
 En son sürümü adresinden indirebilirsiniz.[indirme sayfası](https://releases.aspose.com/slides/java/) ve JAR dosyalarını projenize ekleyin.
### Aspose.Slides'ı ücretsiz kullanabilir miyim?
Aspose.Slides, şu adresten indirebileceğiniz ücretsiz bir deneme sürümü sunuyor:[Burada](https://releases.aspose.com/)Tam işlevsellik için bir lisans satın almanız gerekir.
### ShapeUtil sınıfının kullanımı nedir?
`ShapeUtil` Aspose.Slides'taki sınıf, şekillerle çalışmak için grafiksel yolları geometri yollarına dönüştürmek gibi yardımcı yöntemler sağlar.
### Aspose.Slides için nereden destek alabilirim?
 adresinden destek alabilirsiniz.[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
