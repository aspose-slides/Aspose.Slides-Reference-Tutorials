---
title: PowerPoint'te Şekilleri Desenle Doldurun
linktitle: PowerPoint'te Şekilleri Desenle Doldurun
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint'te şekilleri desenlerle doldurmayı öğrenin. Sunumlarınızı görsel olarak geliştirmek için kolay, adım adım kılavuzumuzu izleyin.
weight: 11
url: /tr/java/java-powerpoint-shape-formatting-geometry/fill-shapes-pattern-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Şekilleri Desenle Doldurun

## giriiş
Hedef kitlenizin ilgisini çekmek için görsel olarak çekici sunumlar oluşturmak çok önemlidir. PowerPoint slaytlarınızı geliştirmenin bir yolu şekilleri desenlerle doldurmaktır. Bu eğitimde Aspose.Slides for Java'yı kullanarak şekilleri desenlerle doldurma adımlarını inceleyeceğiz. Bu kılavuz, Aspose.Slides'ın güçlü özelliklerinden yararlanarak programlı olarak çarpıcı sunumlar oluşturmak isteyen geliştiriciler için özel olarak hazırlanmıştır.
## Önkoşullar
Koda dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
- IntelliJ IDEA veya Eclipse gibi Entegre Geliştirme Ortamı (IDE).
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).
- Java programlamanın temel bilgisi.
## Paketleri İçe Aktar
Öncelikle örneğimiz için gerekli olan paketleri import edelim.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## 1. Adım: Projenizi Kurun
Kodu yazmadan önce projenizin doğru şekilde kurulduğundan emin olun. IDE'nizde yeni bir Java projesi oluşturun ve Aspose.Slides for Java kütüphanesini proje bağımlılıklarınıza ekleyin.
## Adım 2: Belge Dizinini Oluşturun
Dosyalarınızı verimli bir şekilde yönetmek için PowerPoint sunumumuzu kaydedeceğimiz bir dizin oluşturalım.
```java
String dataDir = "Your Document Directory";
// Henüz mevcut değilse dizin oluşturun.
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs();
}
```
Bu kod parçası, dizinin var olup olmadığını kontrol eder ve yoksa onu oluşturur.
## Adım 3: Sunum Sınıfını Başlatın
 Daha sonra, örneğinin bir örneğini oluşturmamız gerekiyor.`Presentation` PowerPoint dosyamızı temsil eden sınıf.
```java
Presentation pres = new Presentation();
```
Bu, slaytlar ve şekiller eklemek için kullanacağımız yeni bir sunum nesnesini başlatır.
## Adım 4: İlk Slayta Erişin
Başlamak için sunumumuzdaki ilk slayda erişmemiz gerekiyor. Şekillerimizi buraya ekleyeceğiz.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Adım 5: Dikdörtgen Şekli Ekleme
Slaytımıza dikdörtgen bir şekil ekleyelim. Bu dikdörtgen bir desenle doldurulacak.
```java
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Bu kod parçacığı, slayda belirtilen konum ve boyutta bir dikdörtgen ekler.
## Adım 6: Doldurma Türünü Desene Ayarlayın
Şimdi dikdörtgenimizin dolgu tipini desen dolgusuna ayarlamamız gerekiyor.
```java
shape.getFillFormat().setFillType(FillType.Pattern);
```
## Adım 7: Bir Desen Stili Seçin
Aspose.Slides çeşitli desen stilleri sunar. Bu örnekte "Trellis" desenini kullanacağız.
```java
shape.getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.Trellis);
```
## Adım 8: Desen Renklerini Ayarlayın
Desenimizin renklerini özelleştirebiliriz. Arka plan rengini açık gri, ön plan rengini ise sarı olarak ayarlayalım.
```java
shape.getFillFormat().getPatternFormat().getBackColor().setColor(Color.LIGHT_GRAY);
shape.getFillFormat().getPatternFormat().getForeColor().setColor(Color.YELLOW);
```
## Adım 9: Sunuyu Kaydetme
Şeklimizi istediğimiz desenle oluşturduktan sonra sunumu bir dosyaya kaydetmemiz gerekiyor.
```java
pres.save(dataDir + "RectShpPatt_out.pptx", SaveFormat.Pptx);
```
Bu, sunumu "RectShpPatt_out.pptx" dosya adıyla belirtilen dizine kaydeder.
## Adım 10: Kaynakları Temizleyin
Kaynakları serbest bırakmak için sunum nesnesini elden çıkarmak iyi bir uygulamadır.
```java
if (pres != null) pres.dispose();
```
## Çözüm
Tebrikler! Aspose.Slides for Java'yı kullanarak PowerPoint slaytındaki bir şekli desenle başarıyla doldurdunuz. Bu güçlü kitaplık, sunumları kolaylıkla oluşturmanıza ve değiştirmenize olanak tanıyarak projelerinize profesyonel bir dokunuş katar.
 Bu adım adım kılavuzu izleyerek sunumlarınızı çeşitli desenlerle geliştirebilir, onları daha ilgi çekici ve görsel olarak çekici hale getirebilirsiniz. Daha gelişmiş özellikler ve özelleştirme seçenekleri için mutlaka şuraya göz atın:[Aspose.Slides for Java belgeleri](https://reference.aspose.com/slides/java/).
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, geliştiricilerin Java uygulamalarında PowerPoint sunumları oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir API'dir.
### Aspose.Slides for Java'yı nasıl edinebilirim?
 Aspose.Slides for Java'yı şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/slides/java/).
### Aspose.Slides for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, şu adresten ücretsiz deneme alabilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Slides for Java'yı mevcut sunumları düzenlemek için kullanabilir miyim?
Evet, Aspose.Slides for Java, mevcut PowerPoint sunumlarını açmanıza, düzenlemenize ve kaydetmenize olanak tanır.
### Aspose.Slides for Java için nereden destek alabilirim?
 adresinden destek alabilirsiniz.[Aspose.Slides destek forumu](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
