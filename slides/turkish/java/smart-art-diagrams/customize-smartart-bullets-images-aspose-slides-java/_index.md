---
"date": "2025-04-18"
"description": "Aspose.Slides for Java kullanarak SmartArt madde işaretlerini görsellerle özelleştirerek sunumlarınızı nasıl geliştireceğinizi öğrenin. Profesyonel bir görünüm için bu adım adım kılavuzu izleyin."
"title": "Aspose.Slides for Java Kullanarak SmartArt Madde İşaretlerini Resimlerle Özelleştirme | Adım Adım Kılavuz"
"url": "/tr/java/smart-art-diagrams/customize-smartart-bullets-images-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java Kullanarak SmartArt Madde İşaretlerini Resimlerle Özelleştirme

## giriiş

Görsel olarak çekici sunumlar oluşturmak, izleyicilerinizin dikkatini çekmek ve mesajınızı etkili bir şekilde iletmek için çok önemlidir. Slayt tasarlamada karşılaşılan yaygın zorluklardan biri, özel görseller kullanarak SmartArt grafiklerindeki madde işaretlerini geliştirmektir. Bu eğitim, Aspose.Slides for Java ile SmartArt düğümlerinde madde işareti doldurma biçimi olarak bir resim ayarlamanıza rehberlik edecek ve sunumlarınızı profesyonel bir şekilde geliştirmenizi sağlayacaktır.

**Ne Öğreneceksiniz:**
- Java için Aspose.Slides'ı kurma ve kullanma
- SmartArt grafiklerinde madde işaretlerini görsellerle özelleştirme
- Bu özelleştirmenin pratik uygulamaları
- Yaygın sorunların giderilmesi

Uygulamaya geçmeden önce her şeyin hazır olduğundan emin olun.

## Ön koşullar

Bu eğitimi takip edebilmek için aşağıdaki ön koşulları karşıladığınızdan emin olun:

1. **Kütüphaneler ve Bağımlılıklar**Aspose.Slides for Java kütüphanesinin 25.4 veya üzeri sürümüne ihtiyacınız olacak.
2. **Çevre Kurulumu**:
   - IntelliJ IDEA veya Eclipse gibi uyumlu bir IDE
   - Makinenizde JDK 16 yüklü
3. **Bilgi Önkoşulları**: Java programlama ve temel PowerPoint sunum yapısı konusunda bilgi sahibi olmak.

## Java için Aspose.Slides Kurulumu

Başlamak için, aşağıdaki yöntemlerden birini kullanarak Aspose.Slides kitaplığını projenize ekleyin:

### Usta

Bu bağımlılığı şuna ekleyin: `pom.xml` dosya:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Bunu da ekleyin `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme

Alternatif olarak, kütüphaneyi doğrudan şu adresten indirin: [Java sürümleri için Aspose.Slides](https://releases.aspose.com/slides/java/).

**Lisans Edinme Adımları**: Aspose, özelliklerini test etmek için mükemmel bir ücretsiz deneme lisansı sunar. Değerlendirme sınırlamalarını kaldırmak için geçici bir lisans talep edebilir veya satın alabilirsiniz.

Ortamınızı başlatmak ve kurmak için bir örnek oluşturun `Presentation` Sınıf gösterildiği gibi:

```java
Presentation presentation = new Presentation();
```

## Uygulama Kılavuzu

Bu bölüm, süreci yönetilebilir adımlara bölerek istenilen işlevselliğin nasıl elde edileceğini açıklayacaktır.

### Özel Madde İşareti Dolgusu ile SmartArt Ekleme

#### Genel bakış

Slaydınıza bir SmartArt şekli ekleyerek ve resim dolgusu kullanarak madde işaretlerini özelleştirerek başlayacağız.

#### Adım Adım Talimatlar

**1. Sunum Nesnesini Başlat**

```java
Presentation presentation = new Presentation();
```

*Amaç*: SmartArt grafiklerini ekleyeceğiniz yeni bir sunum örneği başlatır.

**2. SmartArt Şekli Ekle**

```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```

*Açıklama*: Bu satır, ilk slayda (x=10, y=10) konumunda 500x400 piksel boyutlarında yeni bir SmartArt şekli ekler. `VerticalPictureList` düzen dikey hizalama için kullanılır.

**3. Madde İşareti Doldurma'ya Erişim ve Özelleştirme**

```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);

if (node.getBulletFillFormat() != null) {
    IImage img = Images.fromFile("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg");
    IPPImage image = presentation.getImages().addImage(img);
    
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```

*Amaç*: Düğümün bir `BulletFillFormat` özellik. Eğer öyleyse, bir resim yükler ve onu madde işaretlerinin dolgusu olarak ayarlar.
*Parametreler*:
  - `"YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg"`: Resim dosyanızın yolu.
  - `PictureFillMode.Stretch`: Resmin madde işaretli alanı tamamen doldurmasını sağlar.

**4. Sunumunuzu Kaydedin**

```java
presentation.save("YOUR_OUTPUT_DIRECTORY/out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}