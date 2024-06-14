---
title: Aspose.Slides for Java'yı kullanarak Metin Çerçevesine Sütunlar Ekleme
linktitle: Aspose.Slides for Java'yı kullanarak Metin Çerçevesine Sütunlar Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: PowerPoint sunumlarınızı geliştirmek için Aspose.Slides for Java'yı kullanarak metin çerçevelerine nasıl sütun ekleyeceğinizi öğrenin. Adım adım kılavuzumuz süreci basitleştirir.
type: docs
weight: 11
url: /tr/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/
---
## giriiş
Bu eğitimde Aspose.Slides for Java kullanarak sütun eklemek için metin çerçevelerini nasıl değiştireceğimizi inceleyeceğiz. Aspose.Slides, Java geliştiricilerinin PowerPoint sunumlarını programlı olarak oluşturmasına, değiştirmesine ve dönüştürmesine olanak tanıyan güçlü bir kitaplıktır. Metin çerçevelerine sütun eklemek, slaytlardaki metnin görsel çekiciliğini ve organizasyonunu geliştirerek sunumları daha ilgi çekici ve okunması kolay hale getirir.
## Önkoşullar
Bu eğitime dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
- Makinenizde Java Geliştirme Kiti (JDK) yüklü.
-  Aspose.Slides for Java kütüphanesi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).
- Java programlamanın temel anlayışı.
- Eclipse veya IntelliJ IDEA gibi Entegre Geliştirme Ortamı (IDE).
- Maven veya Gradle gibi araçları kullanarak proje bağımlılıklarını yönetme konusunda bilgi sahibi olmak.

## Paketleri İçe Aktar
Öncelikle sunumlar ve metin çerçeveleriyle çalışmak için gerekli paketleri Aspose.Slides'tan içe aktarın:
```java
import com.aspose.slides.*;
```
## Adım 1: Sunumu Başlatın
Yeni bir PowerPoint sunum nesnesi oluşturarak başlayın:
```java
String dataDir = "Your Document Directory";
String outPptxFileName = dataDir + "ColumnsTest.pptx";
// Yeni bir sunum nesnesi oluşturun
Presentation pres = new Presentation();
```
## 2. Adım: Metin Çerçevesi ile Otomatik Şekil Ekleme
İlk slayda bir Otomatik Şekil (ör. dikdörtgen) ekleyin ve metin çerçevesine erişin:
```java
// İlk slayda Otomatik Şekil ekleme
IAutoShape shape1 = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
// Otomatik Şekil'in metin çerçevesine erişme
TextFrameFormat format = (TextFrameFormat) shape1.getTextFrame().getTextFrameFormat();
```
## 3. Adım: Sütun Sayısını ve Metni Ayarlayın
Metin çerçevesi içindeki sütun sayısını ve metin içeriğini ayarlayın:
```java
// Sütun sayısını ayarlayın
format.setColumnCount(2);
// Metin içeriğini ayarlayın
shape1.getTextFrame().setText("All these columns are limited to be within a single text container -- " +
    "you can add or delete text and the new or remaining text automatically adjusts " +
    "itself to flow within the container. You cannot have text flow from one container " +
    "to other though -- we told you PowerPoint's column options for text are limited!");
```
## 4. Adım: Sunuyu Kaydetme
Değişiklik yaptıktan sonra sunuyu kaydedin:
```java
// Sunuyu kaydet
pres.save(outPptxFileName, SaveFormat.Pptx);
```
## Adım 5: Sütun Aralığını Ayarlayın (İsteğe Bağlı)
Gerekirse sütunlar arasındaki boşluğu ayarlayın:
```java
// Sütun aralığını ayarlayın
format.setColumnSpacing(20);
// Sunuyu güncellenmiş sütun aralığıyla kaydedin
pres.save(outPptxFileName, SaveFormat.Pptx);
// Gerekirse sütun sayısını ve aralığını tekrar değiştirebilirsiniz
format.setColumnCount(3);
format.setColumnSpacing(15);
pres.save(outPptxFileName, SaveFormat.Pptx);
```

## Çözüm
Bu eğitimde, PowerPoint sunumlarındaki metin çerçevelerine programlı olarak sütun eklemek için Aspose.Slides for Java'nın nasıl kullanılacağını gösterdik. Bu özellik, metin içeriğinin görsel sunumunu geliştirerek slaytlardaki okunabilirliği ve yapıyı geliştirir.
## SSS'ler
### Bir metin çerçevesine üçten fazla sütun ekleyebilir miyim?
 Evet, ayarlayabilirsiniz`setColumnCount` Gerektiğinde daha fazla sütun ekleme yöntemini kullanın.
### Aspose.Slides sütun genişliğinin ayrı ayrı ayarlanmasını destekliyor mu?
Hayır, Aspose.Slides bir metin çerçevesindeki sütunlar için eşit genişliği otomatik olarak ayarlar.
### Aspose.Slides for Java'nın deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Slides for Java hakkında daha fazla belgeyi nerede bulabilirim?
 Detaylı dokümantasyon mevcut[Burada](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java için nasıl teknik destek alabilirim?
 Topluluktan destek isteyebilirsiniz[Burada](https://forum.aspose.com/c/slides/11).