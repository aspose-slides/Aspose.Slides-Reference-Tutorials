---
title: PowerPoint'te Bağlayıcıları kullanarak Şekilleri Bağlama
linktitle: PowerPoint'te Bağlayıcıları kullanarak Şekilleri Bağlama
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java ile PowerPoint sunumlarında bağlayıcıları kullanarak şekilleri nasıl bağlayacağınızı öğrenin. Yeni başlayanlar için adım adım eğitim.
type: docs
weight: 18
url: /tr/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---
## giriiş
Bu eğitimde Aspose.Slides for Java'nın yardımıyla PowerPoint sunumlarında bağlayıcılar kullanarak şekilleri nasıl bağlayacağımızı keşfedeceğiz. Şekilleri verimli bir şekilde birleştirmek ve görsel olarak çekici slaytlar oluşturmak için bu adım adım talimatları izleyin.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Java programlama dili hakkında temel bilgiler.
- Sisteminize Java Development Kit (JDK) yüklendi.
-  Aspose.Slides for Java'yı indirip kurduk. Henüz yüklemediyseniz adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/java/).
- Eclipse veya IntelliJ IDEA gibi bir kod düzenleyici.

## Paketleri İçe Aktar
Öncelikle Aspose.Slides ile çalışmak için gerekli paketleri Java projenize aktarın.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## Adım 1: Sunum Sınıfını Başlatın
 Örnekleyin`Presentation`üzerinde çalıştığınız PPTX dosyasını temsil eden sınıf.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Adım 2: Şekiller Koleksiyonuna Erişim
Şekil ve bağlayıcı eklemek istediğiniz seçili slaydın şekil koleksiyonuna erişin.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## 3. Adım: Şekiller Ekleyin
Gerekli şekilleri slayta ekleyin. Bu örnekte bir elips ve bir dikdörtgen ekleyeceğiz.
```java
// Otomatik şekil Elips ekle
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Otomatik şekil Dikdörtgeni ekle
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Adım: Bağlayıcı Ekle
Slayt şekli koleksiyonuna bir bağlayıcı şekli ekleyin.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Adım 5: Şekilleri Bağlayıcılara Birleştirin
Şekilleri bağlayıcıya bağlayın.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Adım 6: Bağlayıcıyı Yeniden Yönlendirin
Şekiller arasındaki otomatik en kısa yolu ayarlamak için yeniden yönlendirmeyi çağırın.
```java
connector.reroute();
```
## Adım 7: Sunumu Kaydet
Bağlayıcıları kullanarak şekilleri bağladıktan sonra sunuyu kaydedin.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Son olarak Sunum nesnesini atmayı unutmayın.
```java
if (input != null) input.dispose();
```
Artık Aspose.Slides for Java'yı kullanarak PowerPoint'teki bağlayıcıları kullanarak şekilleri başarıyla bağladınız.

## Çözüm
Bu eğitimde Aspose.Slides for Java ile PowerPoint sunumlarında bağlayıcılar kullanarak şekilleri nasıl bağlayacağımızı öğrendik. Bu basit adımları izleyerek sunumlarınızı görsel olarak çekici diyagramlar ve akış şemalarıyla geliştirebilirsiniz.
## SSS'ler
### Aspose.Slides for Java'da bağlayıcıların görünümünü özelleştirebilir miyim?
Evet, sunum ihtiyaçlarınıza uyacak şekilde bağlayıcıların renk, çizgi stili ve kalınlık gibi çeşitli özelliklerini özelleştirebilirsiniz.
### Aspose.Slides for Java, PowerPoint'in tüm sürümleriyle uyumlu mu?
Aspose.Slides for Java, PPTX, PPT ve ODP dahil olmak üzere çeşitli PowerPoint formatlarını destekler.
### Tek bir bağlayıcıyla ikiden fazla şekli bağlayabilir miyim?
Evet, Aspose.Slides for Java tarafından sağlanan karmaşık bağlayıcıları kullanarak birden fazla şekli bağlayabilirsiniz.
### Aspose.Slides for Java, şekillere metin ekleme desteği sunuyor mu?
Kesinlikle, Aspose.Slides for Java'yı kullanarak şekillere ve bağlayıcılara programlı bir şekilde kolayca metin ekleyebilirsiniz.
### Aspose.Slides for Java kullanıcıları için bir topluluk forumu veya destek kanalı var mı?
 Evet, Aspose.Slides forumunda yararlı kaynaklar bulabilir, sorular sorabilir ve diğer kullanıcılarla iletişim kurabilirsiniz.[Burada](https://forum.aspose.com/c/slides/11).