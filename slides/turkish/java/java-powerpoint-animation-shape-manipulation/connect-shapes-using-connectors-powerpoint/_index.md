---
"description": "Aspose.Slides for Java ile PowerPoint sunumlarında bağlayıcılar kullanarak şekilleri nasıl bağlayacağınızı öğrenin. Yeni başlayanlar için adım adım eğitim."
"linktitle": "PowerPoint'te Bağlayıcıları Kullanarak Şekilleri Bağlayın"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te Bağlayıcıları Kullanarak Şekilleri Bağlayın"
"url": "/tr/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Bağlayıcıları Kullanarak Şekilleri Bağlayın

## giriiş
Bu eğitimde, Aspose.Slides for Java yardımıyla PowerPoint sunumlarında bağlayıcılar kullanarak şekilleri nasıl bağlayacağımızı keşfedeceğiz. Şekilleri etkili bir şekilde bağlamak ve görsel olarak çekici slaytlar oluşturmak için bu adım adım talimatları izleyin.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Java programlama dilinin temel bilgisi.
- Sisteminize Java Development Kit'i (JDK) yükleyin.
- Java için Aspose.Slides'ı indirip kurun. Eğer henüz yüklemediyseniz, şuradan indirebilirsiniz: [Burada](https://releases.aspose.com/slides/java/).
- Eclipse veya IntelliJ IDEA gibi bir kod düzenleyici.

## Paketleri İçe Aktar
Öncelikle Aspose.Slides ile çalışmak için gerekli paketleri Java projenize aktarın.
```java
import com.aspose.slides.*;

```
## Adım 1: Sunum Sınıfını Oluşturun
Örneklemi oluştur `Presentation` Üzerinde çalıştığınız PPTX dosyasını temsil eden sınıf.
```java
// Belgeler dizinine giden yol.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Adım 2: Şekiller Koleksiyonuna Erişim
Şekil ve bağlayıcı eklemek istediğiniz seçili slayt için şekil koleksiyonuna erişin.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Adım 3: Şekiller Ekleyin
Slayda gerekli şekilleri ekleyin. Bu örnekte bir elips ve bir dikdörtgen ekleyeceğiz.
```java
// Otomatik şekil Elips ekle
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Otomatik şekil Dikdörtgeni ekle
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Adım 4: Bağlayıcı Ekle
Slayt şekli koleksiyonuna bir bağlayıcı şekil ekleyin.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Adım 5: Şekilleri Bağlayıcılara Birleştirin
Şekilleri konnektöre bağlayın.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Adım 6: Bağlayıcıyı Yeniden Yönlendirin
Şekiller arasındaki en kısa yolu otomatik olarak ayarlamak için yeniden yönlendirme çağrısını kullanın.
```java
connector.reroute();
```
## Adım 7: Sunumu Kaydedin
Şekilleri bağlayıcılar kullanarak bağladıktan sonra sunuyu kaydedin.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Son olarak Presentation nesnesini elden çıkarmayı unutmayın.
```java
if (input != null) input.dispose();
```
Artık Aspose.Slides for Java'yı kullanarak PowerPoint'te bağlayıcıları kullanarak şekilleri başarıyla birbirine bağladınız.

## Çözüm
Bu eğitimde, Aspose.Slides for Java ile PowerPoint sunumlarında bağlayıcılar kullanarak şekilleri nasıl bağlayacağımızı öğrendik. Bu basit adımları izleyerek, sunumlarınızı görsel olarak çekici diyagramlar ve akış şemalarıyla zenginleştirebilirsiniz.
## SSS
### Aspose.Slides for Java'da bağlayıcıların görünümünü özelleştirebilir miyim?
Evet, sunum ihtiyaçlarınıza uyacak şekilde renk, çizgi stili ve kalınlık gibi konektörlerin çeşitli özelliklerini özelleştirebilirsiniz.
### Aspose.Slides for Java, PowerPoint'in tüm sürümleriyle uyumlu mudur?
Java için Aspose.Slides, PPTX, PPT ve ODP dahil olmak üzere çeşitli PowerPoint formatlarını destekler.
### Tek bir bağlayıcıyla ikiden fazla şekli birbirine bağlayabilir miyim?
Evet, Aspose.Slides for Java tarafından sağlanan karmaşık bağlayıcıları kullanarak birden fazla şekli birbirine bağlayabilirsiniz.
### Aspose.Slides for Java şekillere metin ekleme desteği sunuyor mu?
Kesinlikle, Aspose.Slides for Java'yı kullanarak şekillere ve bağlayıcılara programlı olarak kolayca metin ekleyebilirsiniz.
### Aspose.Slides for Java kullanıcıları için bir topluluk forumu veya destek kanalı var mı?
Evet, Aspose.Slides forumunda yararlı kaynaklar bulabilir, sorular sorabilir ve diğer kullanıcılarla etkileşim kurabilirsiniz [Burada](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}