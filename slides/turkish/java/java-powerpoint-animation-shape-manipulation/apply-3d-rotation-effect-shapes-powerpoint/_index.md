---
"description": "Bu kapsamlı, adım adım eğitimle Aspose.Slides for Java'yı kullanarak PowerPoint'teki şekillere 3B döndürme efektlerinin nasıl uygulanacağını öğrenin."
"linktitle": "PowerPoint'te Şekillere 3B Döndürme Efekti Uygula"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "PowerPoint'te Şekillere 3B Döndürme Efekti Uygula"
"url": "/tr/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint'te Şekillere 3B Döndürme Efekti Uygula

## giriiş
PowerPoint sunumlarınızı bir üst seviyeye taşımaya hazır mısınız? 3D döndürme efektleri eklemek slaytlarınızı daha dinamik ve ilgi çekici hale getirebilir. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu adım adım eğitim size Aspose.Slides for Java kullanarak PowerPoint'teki şekillere 3D döndürme efektlerini nasıl uygulayacağınızı gösterecek. Hemen başlayalım!
## Ön koşullar
Başlamadan önce aşağıdakilerin mevcut olduğundan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın yüklü olduğundan emin olun. Bunu şu adresten indirebilirsiniz: [Oracle web sitesi](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Java için Aspose.Slides: Java için Aspose.Slides'ın en son sürümünü şu adresten indirin: [indirme bağlantısı](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Kodlama için IntelliJ IDEA veya Eclipse gibi bir IDE kullanın.
4. Geçerli bir lisans: Lisansınız yoksa, bir lisans alabilirsiniz. [geçici lisans](https://purchase.aspose.com/temporary-license/) Özellikleri denemek için.
## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java projenize aktaralım. Bu içe aktarımlar Aspose.Slides ile sunumları ve şekilleri işlemenize yardımcı olacaktır.
```java
import com.aspose.slides.*;

```
## Adım 1: Projenizi Kurun
Koda dalmadan önce proje ortamınızı kurun. Projenizin bağımlılıklarına Aspose.Slides for Java'yı eklediğinizden emin olun.
Aspose.Slides'ı Projenize Ekleyin:
1. Aspose.Slides JAR dosyalarını şu adresten indirin: [indirme sayfası](https://releases.aspose.com/slides/java/).
2. Bu JAR dosyalarını projenizin derleme yoluna ekleyin.
## Adım 2: Yeni bir PowerPoint Sunumu Oluşturun
Bu adımda yeni bir PowerPoint sunumu oluşturacağız.
```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Presentation sınıfı örneği oluşturun
Presentation pres = new Presentation();
```
Bu kod parçacığı şekillerimizi ekleyeceğimiz yeni bir sunum nesnesini başlatır.
## Adım 3: Dikdörtgen Şekli Ekleyin
Şimdi ilk slayda dikdörtgen şekli ekleyelim.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Bu kod, ilk slaytta belirtilen konum ve boyutta bir dikdörtgen şekli ekler.
## Adım 4: Dikdörtgene 3B Döndürme Uygulayın
Şimdi dikdörtgen şekline 3 boyutlu döndürme efekti uygulayalım.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Burada dikdörtgenimize 3 boyutlu bir görünüm kazandırmak için derinliği, kamera dönüş açılarını, kamera türünü ve ışıklandırma türünü ayarlıyoruz.
## Adım 5: Bir Çizgi Şekli Ekleyin
Slayda bir şekil daha ekleyelim, bu sefer bir çizgi.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Bu kod slayda bir çizgi şekli yerleştirir.
## Adım 6: Çizgiye 3B Döndürme Uygulayın
Son olarak çizgi şekline 3 boyutlu döndürme efekti uygulayacağız.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Dikdörtgene benzer şekilde çizgi şeklinin 3B özelliklerini ayarlıyoruz.
## Adım 7: Sunumu Kaydedin
Şekillerinizi ekleyip yapılandırdıktan sonra sunumunuzu kaydedin.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Bu kod sunumunuzu belirtilen dosya adıyla istediğiniz formatta kaydeder.
## Çözüm
Tebrikler! Aspose.Slides for Java kullanarak bir PowerPoint sunumundaki şekillere 3B döndürme efektlerini başarıyla uyguladınız. Bu adımları izleyerek görsel olarak çekici ve dinamik sunumlar oluşturabilirsiniz. Daha fazla özelleştirme ve daha gelişmiş özellikler için şuraya bakın: [Aspose.Slides belgeleri](https://reference.aspose.com/slides/java/).
## SSS
### Java için Aspose.Slides nedir?
Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak oluşturmak, değiştirmek ve düzenlemek için güçlü bir API'dir.
### Aspose.Slides for Java'yı ücretsiz deneyebilir miyim?
Evet, alabilirsiniz [ücretsiz deneme](https://releases.aspose.com/) veya bir [geçici lisans](https://purchase.aspose.com/temporary-license/) Özellikleri test etmek için.
### Aspose.Slides'ta hangi şekil türlerine 3D efektler ekleyebilirim?
Dikdörtgenler, çizgiler, elipsler ve özel şekiller gibi çeşitli şekillere 3B efektler ekleyebilirsiniz.
### Java için Aspose.Slides desteğini nasıl alabilirim?
Ziyaret edebilirsiniz [destek forumu](https://forum.aspose.com/c/slides/11) yardım ve herhangi bir konuyu görüşmek için.
### Aspose.Slides for Java'yı ticari projelerde kullanabilir miyim?
Evet, ancak bir lisans satın almanız gerekir. Bir tane satın alabilirsiniz [satın alma sayfası](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}