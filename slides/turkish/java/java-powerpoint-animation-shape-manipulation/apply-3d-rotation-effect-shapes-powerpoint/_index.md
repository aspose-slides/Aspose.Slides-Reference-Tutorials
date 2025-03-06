---
title: PowerPoint'teki Şekillere 3B Döndürme Efekti Uygulayın
linktitle: PowerPoint'teki Şekillere 3B Döndürme Efekti Uygulayın
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Bu kapsamlı, adım adım eğitimle Aspose.Slides for Java kullanarak PowerPoint'teki şekillere 3D döndürme efektlerini nasıl uygulayacağınızı öğrenin.
weight: 12
url: /tr/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
PowerPoint sunumlarınızı bir sonraki seviyeye taşımaya hazır mısınız? 3D döndürme efektleri eklemek slaytlarınızı daha dinamik ve ilgi çekici hale getirebilir. İster deneyimli bir geliştirici olun ister yeni başlıyor olun, bu adım adım eğitim size Aspose.Slides for Java kullanarak PowerPoint'teki şekillere 3D döndürme efektlerini nasıl uygulayacağınızı gösterecek. Haydi hemen dalalım!
## Önkoşullar
Başlamadan önce aşağıdakilerin mevcut olduğundan emin olun:
1.  Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Oracle web sitesi](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Aspose.Slides for Java'nın en son sürümünü şuradan indirin:[İndirme: {link](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): Kodlama için IntelliJ IDEA veya Eclipse gibi bir IDE kullanın.
4.  Geçerli bir lisans: Lisansınız yoksa, bir lisans alabilirsiniz.[geçici lisans](https://purchase.aspose.com/temporary-license/) Özellikleri denemek için.
## Paketleri İçe Aktar
Öncelikle Java projenize gerekli paketleri import edelim. Bu içe aktarmalar Aspose.Slides ile sunumları ve şekilleri yönetmenize yardımcı olacaktır.
```java
import com.aspose.slides.*;

```
## 1. Adım: Projenizi Kurun
Koda dalmadan önce proje ortamınızı ayarlayın. Aspose.Slides for Java'yı projenizin bağımlılıklarına eklediğinizden emin olun.
Aspose.Slides'ı Projenize Ekleyin:
1.  Aspose.Slides JAR dosyalarını şu adresten indirin:[indirme sayfası](https://releases.aspose.com/slides/java/).
2. Bu JAR dosyalarını projenizin derleme yoluna ekleyin.
## Adım 2: Yeni Bir PowerPoint Sunusu Oluşturun
Bu adımda yeni bir PowerPoint sunumu oluşturacağız.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Sunum sınıfının bir örneğini oluşturun
Presentation pres = new Presentation();
```
Bu kod parçacığı, şekillerimizi ekleyeceğimiz yeni bir sunum nesnesini başlatır.
## Adım 3: Dikdörtgen Şekli Ekleme
Daha sonra ilk slayta dikdörtgen şekli ekleyelim.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Bu kod, ilk slaytta belirtilen konuma ve boyuta bir dikdörtgen şekli ekler.
## Adım 4: Dikdörtgene 3B Döndürme Uygulayın
Şimdi dikdörtgen şekline 3 boyutlu döndürme efekti uygulayalım.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Burada dikdörtgenimize 3 boyutlu bir görünüm kazandırmak için derinliği, kamera dönüş açılarını, kamera tipini ve aydınlatma tipini ayarlıyoruz.
## Adım 5: Çizgi Şekli Ekleme
Slayda bu kez bir çizgi olmak üzere başka bir şekil ekleyelim.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Bu kod, slayta bir çizgi şekli yerleştirir.
## Adım 6: Çizgiye 3B Döndürme Uygulayın
Son olarak çizgi şekline 3 boyutlu döndürme efekti uygulayacağız.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Dikdörtgene benzer şekilde çizgi şeklinin 3 boyutlu özelliklerini ayarlıyoruz.
## Adım 7: Sunuyu Kaydet
Şekillerinizi ekleyip yapılandırdıktan sonra sunuyu kaydedin.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Bu kod sununuzu belirtilen dosya adı ile istenilen formatta kaydeder.
## Çözüm
 Tebrikler! Aspose.Slides for Java'yı kullanarak PowerPoint sunumundaki şekillere 3D döndürme efektlerini başarıyla uyguladınız. Bu adımları takip ederek görsel açıdan çekici ve dinamik sunumlar oluşturabilirsiniz. Daha fazla özelleştirme ve daha gelişmiş özellikler için bkz.[Aspose.Slides belgeleri](https://reference.aspose.com/slides/java/).
## SSS'ler
### Aspose.Slides for Java nedir?
Aspose.Slides for Java, PowerPoint sunumlarını programlı olarak oluşturmak, değiştirmek ve yönetmek için kullanılan güçlü bir API'dir.
### Aspose.Slides for Java'yı ücretsiz deneyebilir miyim?
 Evet, alabilirsiniz[ücretsiz deneme](https://releases.aspose.com/) veya bir[geçici lisans](https://purchase.aspose.com/temporary-license/) Özellikleri test etmek için.
### Aspose.Slides'ta ne tür şekillere 3D efektler ekleyebilirim?
Dikdörtgenler, çizgiler, elipsler ve özel şekiller gibi çeşitli şekillere 3B efektler ekleyebilirsiniz.
### Aspose.Slides for Java için nasıl destek alabilirim?
 Ziyaret edebilirsiniz[destek Forumu](https://forum.aspose.com/c/slides/11) Yardım için ve herhangi bir konuyu tartışmak için.
### Aspose.Slides for Java'yı ticari projelerde kullanabilir miyim?
 Evet, ancak bir lisans satın almanız gerekiyor. Şu adresten bir tane satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
