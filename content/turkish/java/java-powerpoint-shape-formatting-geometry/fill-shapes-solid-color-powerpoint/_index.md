---
title: PowerPoint'te Şekilleri Düz Renkle Doldurun
linktitle: PowerPoint'te Şekilleri Düz Renkle Doldurun
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint'te şekilleri düz renklerle nasıl dolduracağınızı öğrenin. Geliştiriciler için adım adım kılavuz.
type: docs
weight: 13
url: /tr/java/java-powerpoint-shape-formatting-geometry/fill-shapes-solid-color-powerpoint/
---
## giriiş
Daha önce PowerPoint sunumlarıyla çalıştıysanız, şekiller eklemenin ve renklerini özelleştirmenin, slaytlarınızı görsel olarak çekici ve bilgilendirici hale getirmenin çok önemli bir yönü olabileceğini biliyorsunuzdur. Aspose.Slides for Java ile bu süreç çocuk oyuncağı haline geliyor. İster PowerPoint sunumlarının oluşturulmasını otomatikleştirmek isteyen bir geliştirici olun, ister slaytlarınıza biraz renk katmak isteyen biri olun, bu eğitim Aspose.Slides for Java'yı kullanarak şekilleri düz renklerle doldurma sürecinde size rehberlik edecektir.
## Önkoşullar
Kodun ayrıntılarına girmeden önce yerine getirmeniz gereken birkaç önkoşul vardır:
1.  Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Oracle web sitesi](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java kütüphanesini şu adresten indirin:[Web sitesi](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA veya Eclipse gibi bir IDE, geliştirme sürecinizi daha sorunsuz hale getirecektir.
4. Temel Java Bilgisi: Java programlamaya aşinalık, kodu etkili bir şekilde anlamanıza ve uygulamanıza yardımcı olacaktır.

## Paketleri İçe Aktar
Aspose.Slides for Java'yı kullanmaya başlamak için gerekli paketleri içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
```
## 1. Adım: Projenizi Kurun
 Öncelikle Java projenizi kurmanız ve Aspose.Slides for Java'yı proje bağımlılıklarınıza dahil etmeniz gerekir. Maven kullanıyorsanız aşağıdaki bağımlılığı ekleyin:`pom.xml` dosya:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>XX.X</version> <!-- Replace XX.X with the latest version -->
</dependency>
```
 Maven kullanmıyorsanız JAR dosyasını şuradan indirin:[Web sitesi](https://releases.aspose.com/slides/java/) ve bunu projenizin derleme yoluna ekleyin.
## Adım 2: Sunumu Başlatın
 Bir örneğini oluşturun`Presentation` sınıf. Bu sınıf üzerinde çalışacağınız PowerPoint sunumunu temsil eder.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
Presentation presentation = new Presentation();
```
## 3. Adım: İlk Slayta Erişin
Daha sonra, şekillerinizi ekleyeceğiniz sunumun ilk slaydını almanız gerekiyor.
```java
// İlk slaydı alın
ISlide slide = presentation.getSlides().get_Item(0);
```
## Adım 4: Slayda Şekil Ekleme
Şimdi slayta dikdörtgen şekli ekleyelim. Parametreleri ayarlayarak şeklin konumunu ve boyutunu özelleştirebilirsiniz.
```java
// Dikdörtgen tipinin otomatik şeklini ekle
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
## Adım 5: Doldurma Türünü Katı Olarak Ayarlayın
 Şekli düz bir renkle doldurmak için dolgu türünü şu şekilde ayarlayın:`Solid`.
```java
//Doldurma türünü Katı olarak ayarlayın
shape.getFillFormat().setFillType(FillType.Solid);
```
## Adım 6: Rengi Seçin ve Uygulayın
Şekil için bir renk seçin. Burada sarı kullanıyoruz ama siz istediğiniz rengi seçebilirsiniz.
```java
// Dikdörtgenin rengini ayarlayın
shape.getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
```
## Adım 7: Sunuyu Kaydet
Son olarak değiştirilen sunumu bir dosyaya kaydedin.
```java
// PPTX dosyasını diske yazın
presentation.save(dataDir + "RectShpSolid_out.pptx", SaveFormat.Pptx);
```

## Çözüm
İşte buyur! Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki bir şekli düz renkle başarıyla doldurdunuz. Bu kitaplık, sunumlarınızı kolaylıkla otomatikleştirmenize ve özelleştirmenize yardımcı olabilecek güçlü özellikler sunar. İster rapor oluşturuyor olun, ister eğitim materyalleri oluşturuyor olun, ister iş slaytları tasarlıyor olun, Aspose.Slides for Java çok değerli bir araç olabilir.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, Java'da PowerPoint sunumlarıyla çalışmak için güçlü bir kütüphanedir. Sunumları programlı olarak oluşturmanıza, değiştirmenize ve dönüştürmenize olanak tanır.
### Aspose.Slides for Java'yı nasıl yüklerim?
 adresinden indirebilirsiniz.[Web sitesi](https://releases.aspose.com/slides/java/) JAR dosyasını projenize ekleyin veya eklemek için Maven gibi bir bağımlılık yöneticisi kullanın.
### Aspose.Slides for Java'yı mevcut sunumları düzenlemek için kullanabilir miyim?
Evet, Aspose.Slides for Java, mevcut PowerPoint sunumlarını açmanıza, düzenlemenize ve kaydetmenize olanak tanır.
### Aspose.Slides for Java'nın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Web sitesi](https://releases.aspose.com/).
### Daha fazla belge ve desteği nerede bulabilirim?
 Ayrıntılı belgeler şu adreste mevcuttur:[Web sitesi](https://reference.aspose.com/slides/java/) ve şu adresten destek arayabilirsiniz:[forumlar](https://forum.aspose.com/c/slides/11).