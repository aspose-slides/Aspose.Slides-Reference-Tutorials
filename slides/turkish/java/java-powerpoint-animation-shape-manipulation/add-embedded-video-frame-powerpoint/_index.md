---
title: PowerPoint'e Gömülü Video Çerçevesi Ekleme
linktitle: PowerPoint'e Gömülü Video Çerçevesi Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Bu adım adım eğitimle Aspose.Slides for Java kullanarak PowerPoint'e video karelerini nasıl yerleştireceğinizi öğrenin. Sunumlarınızı kolayca geliştirin.
weight: 21
url: /tr/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
PowerPoint sunumlarınıza video eklemek onları daha ilgi çekici ve bilgilendirici hale getirebilir. Aspose.Slides for Java'yı kullanarak videoları doğrudan slaytlarınıza kolayca gömebilirsiniz. Bu eğitimde, kodun her bölümünü ve nasıl çalıştığını anlamanızı sağlayacak şekilde süreç boyunca size adım adım yol göstereceğiz. İster deneyimli bir geliştirici olun, ister yeni başlıyor olun, bu kılavuz, yerleşik videolarla sunumlarınızı geliştirmenize yardımcı olacaktır.
## Önkoşullar
Kodun ayrıntılarına girmeden önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1. Java Geliştirme Kiti (JDK): Makinenizde JDK'nın kurulu olduğundan emin olun.
2. Aspose.Slides for Java: Aspose.Slides for Java kütüphanesini indirip yükleyin.
3. Entegre Geliştirme Ortamı (IDE): Daha iyi bir geliştirme deneyimi için IntelliJ IDEA veya Eclipse gibi bir IDE kullanın.
4. Video Dosyası: PowerPoint sunumunuza eklemek istediğiniz bir video dosyanız olsun.
## Paketleri İçe Aktar
Öncelikle Aspose.Slides ile çalışmak için gerekli paketleri içe aktarmanız gerekecek. Bu içe aktarmalar slaytları, videoları ve sunum dosyalarını yönetmenize yardımcı olacaktır.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## 1. Adım: Ortamınızı Kurun
Kodlamaya başlamadan önce ortamınızın doğru şekilde kurulduğundan emin olun. Bu, gerekli dizinlerin oluşturulmasını ve video dosyasının hazırlanmasını içerir.
```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Henüz mevcut değilse dizin oluşturun.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Adım 2: Sunum Sınıfını Başlatın
 Bir örneğini oluşturun`Presentation` sınıf. Bu sınıf PowerPoint dosyanızı temsil eder.
```java
// PPTX'i temsil eden Örnek Sunum sınıfı
Presentation pres = new Presentation();
```
## 3. Adım: İlk Slaydı Alın
Videoyu yerleştireceğiniz sunumdaki ilk slayda erişin.
```java
// İlk slaydı alın
ISlide sld = pres.getSlides().get_Item(0);
```
## 4. Adım: Videoyu Sunuya Ekleme
Video dosyasını sunuma ekleyin. Video yolunun doğru şekilde belirtildiğinden emin olun.
```java
// Sunumun içine video yerleştirme
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Adım 5: Slayta Video Çerçevesi Ekleme
Slaytta bir video çerçevesi oluşturun ve boyutlarını ve konumunu ayarlayın.
```java
// Video Çerçevesi Ekle
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Adım 6: Video Çerçevesi Özelliklerini Yapılandırın
Videoyu video çerçevesine ayarlayın ve oynatma modu ve ses seviyesi gibi oynatma ayarlarını yapılandırın.
```java
// Videoyu Video Çerçevesine ayarla
vf.setEmbeddedVideo(vid);
// Videonun Oynatma Modunu ve Sesini Ayarlayın
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Adım 7: Sunuyu Kaydet
Sunuyu gömülü videoyla birlikte belirttiğiniz dizine kaydedin.
```java
// PPTX dosyasını diske yazın
pres.save(resultPath, SaveFormat.Pptx);
```
## Adım 8: Kaynakları Temizleyin
Son olarak, kaynakları serbest bırakmak için sunum nesnesini atın.
```java
// Sunum nesnesini atın
if (pres != null) pres.dispose();
```
## Çözüm
Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarınıza video eklemek basit bir işlemdir. Bu kılavuzda özetlenen adımları izleyerek sunumlarınızı ilgi çekici video içeriğiyle geliştirebilirsiniz. Unutmayın, pratik yapmak mükemmelleştirir; bu nedenle ihtiyaçlarınıza en uygun olanı görmek için farklı videolar yerleştirmeyi ve özelliklerini ayarlamayı deneyin.
## SSS'ler
### Tek bir slayda birden fazla video yerleştirebilir miyim?
Evet, birden fazla video karesi ekleyerek tek bir slayda birden fazla video gömebilirsiniz.
### Videonun oynatılmasını nasıl kontrol edebilirim?
 Oynatmayı kullanarak kontrol edebilirsiniz.`setPlayMode` Ve`setVolume` yöntemleri`IVideoFrame` sınıf.
### Aspose.Slides hangi video formatlarını destekliyor?
Aspose.Slides MP4, AVI ve WMV dahil olmak üzere çeşitli video formatlarını destekler.
### Aspose.Slides'ı kullanmak için lisansa ihtiyacım var mı?
Evet, Aspose.Slides'ı kullanmak için geçerli bir lisansa ihtiyacınız var. Değerlendirme için geçici bir lisans alabilirsiniz.
### Video çerçevesinin boyutunu ve konumunu özelleştirebilir miyim?
Evet, video karesini eklerken uygun parametreleri ayarlayarak boyutu ve konumu özelleştirebilirsiniz.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
