---
title: PowerPoint'te Biçimlendirilmiş Dikdörtgen Oluşturma
linktitle: PowerPoint'te Biçimlendirilmiş Dikdörtgen Oluşturma
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Bu adım adım kılavuzla Aspose.Slides for Java'yı kullanarak PowerPoint'te dikdörtgen oluşturmayı ve biçimlendirmeyi öğrenin.
weight: 18
url: /tr/java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Bu eğitimde, Aspose.Slides for Java'yı kullanarak PowerPoint slaytında biçimlendirilmiş bir dikdörtgen oluşturma sürecinde size rehberlik edeceğiz. Her adımı ayrıntılı olarak inceleyerek bunu takip edebilmenizi ve kendi projelerinizde uygulayabilmenizi sağlayacağız.
## Önkoşullar
Koda dalmadan önce önkoşulları ele alalım. Aşağıdakilere ihtiyacınız olacak:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2. Aspose.Slides for Java Kütüphanesi: Aspose.Slides for Java kütüphanesini indirin ve projenize ekleyin.
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA veya Eclipse gibi bir IDE, kodlama deneyiminizi daha sorunsuz hale getirecektir.
4. Temel Java Bilgisi: Java programlamaya aşina olmak bu eğitimi takip etmenize yardımcı olacaktır.
## Paketleri İçe Aktar
Başlamak için gerekli paketleri Aspose.Slides kütüphanesinden içe aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
Bu içe aktarmalar, PowerPoint sununuzdaki şekilleri oluşturmak ve biçimlendirmek için gereken sınıfları getirdikleri için çok önemlidir.
## Adım 1: Proje Dizinini Ayarlama
Öncelikle projeniz için bir dizin oluşturmanız gerekir. Bu dizin PowerPoint dosyalarınızı depolayacaktır.
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Bu kod, dizinin var olup olmadığını kontrol eder ve yoksa onu oluşturur. Proje dosyalarınızı düzenli tutmak iyi bir uygulamadır.
## Adım 2: Sunum Sınıfını Başlatın
 Daha sonra, şunu örnekleyeceksiniz:`Presentation` PowerPoint dosyanızı temsil eden sınıf.
```java
Presentation pres = new Presentation();
```
Bu kod satırı, içerik eklemeye başlayabileceğiniz yeni, boş bir sunum oluşturur.
## 3. Adım: Sunuya Slayt Ekleme
Şimdi sunumunuza bir slayt ekleyelim. Varsayılan olarak yeni bir sunum bir slayt içerir, dolayısıyla onunla çalışacağız.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
Bu kod parçacığı sunumdaki ilk slaydı alır.
## Adım 4: Dikdörtgen Şekli Ekleme
Şimdi slayta bir dikdörtgen ekleyeceğiz.
```java
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Burada, slayta boyutları (genişlik, yükseklik) ve konumu (x, y) belirtilen bir dikdörtgen ekliyoruz.
## Adım 5: Dikdörtgeni Biçimlendirin
Dikdörtgeni görsel olarak çekici hale getirmek için bazı biçimlendirmeler uygulayalım.
```java
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
Bu kod, dolgu türünü katı, dolgu rengini ise çikolata olarak ayarlar.
## Dikdörtgenin Kenarlığını Biçimlendir
Daha sonra dikdörtgenin kenarlığını biçimlendireceğiz.
```java
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
Bu kod, kenarlık rengini siyaha ve kenarlık genişliğini 5'e ayarlar.
## Adım 6: Sunuyu Kaydetme
Son olarak sunumu proje dizininize kaydedelim.
```java
pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
Bu kod satırı, sunuyu belirttiğiniz dizine PPTX dosyası olarak kaydeder.
## Adım 7: Kaynakları Temizleyin
 imha etmek iyi bir uygulamadır.`Presentation` Kaynakların serbest bırakılmasına karşı çıkıyoruz.
```java
if (pres != null) pres.dispose();
```
Bu, tüm kaynakların uygun şekilde serbest bırakılmasını sağlar.
## Çözüm
Aspose.Slides for Java'yı kullanarak bir PowerPoint sunumunda şekiller oluşturmak ve biçimlendirmek basit bir işlemdir. Bu eğitimde özetlenen adımları izleyerek görsel olarak çekici slaytların oluşturulmasını kolaylıkla otomatikleştirebilirsiniz. İster iş raporlaması, eğitim içeriği veya dinamik sunumlar için uygulamalar geliştiriyor olun, Aspose.Slides for Java, başarılı olmanız için ihtiyacınız olan araçları sunar.
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, geliştiricilerin PowerPoint sunumlarını programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan bir kitaplıktır.
### Aspose.Slides for Java'yı herhangi bir IDE ile kullanabilir miyim?
Evet, Aspose.Slides for Java'yı IntelliJ IDEA, Eclipse veya NetBeans gibi Java uyumlu herhangi bir IDE ile kullanabilirsiniz.
### Aspose.Slides for Java'nın ücretsiz deneme sürümünü nasıl edinebilirim?
 Aspose.Slides for Java'nın ücretsiz deneme sürümünü şu adresten indirebilirsiniz:[Burada](https://releases.aspose.com/).
###  elden çıkarmak gerekli mi`Presentation` object?
 Evet, elden çıkarma`Presentation` nesne, kaynakların serbest bırakılmasına ve bellek sızıntılarının önlenmesine yardımcı olur.
### Aspose.Slides for Java belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
