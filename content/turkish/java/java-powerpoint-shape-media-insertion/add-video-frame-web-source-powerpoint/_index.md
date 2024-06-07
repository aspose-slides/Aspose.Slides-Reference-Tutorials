---
title: PowerPoint'te Web Kaynağından Video Çerçevesi Ekleme
linktitle: PowerPoint'te Web Kaynağından Video Çerçevesi Ekleme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak web kaynaklarından video kareleri ekleyerek PowerPoint sunumlarınızı nasıl geliştireceğinizi öğrenin.
type: docs
weight: 18
url: /tr/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---
## giriiş
Bu eğitimde Aspose.Slides for Java kullanarak YouTube gibi bir web kaynağından PowerPoint sunumuna nasıl video karesi ekleneceğini öğreneceğiz. Bu adım adım talimatları izleyerek, ilgi çekici multimedya öğelerini dahil ederek sunumlarınızı geliştirebileceksiniz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Java programlamanın temel bilgisi.
- JDK (Java Development Kit) sisteminizde kuruludur.
-  Aspose.Slides for Java kütüphanesi indirildi ve Java projenize eklendi. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/java/).
- Web kaynağına (örn. YouTube) erişim için aktif bir internet bağlantısı.

## Paketleri İçe Aktar
Öncelikle gerekli paketleri Java projenize aktarın:
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;
import com.aspose.slides.examples.RunExamples;
import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## Adım 1: PowerPoint Sunum Nesnesi Oluşturun
PowerPoint sunumunu temsil eden bir Sunum nesnesini başlatın:
```java
Presentation pres = new Presentation();
```
## 2. Adım: Video Çerçevesi Ekleme
Şimdi sunuma bir video karesi ekleyelim. Bu çerçeve web kaynağındaki videoyu içerecektir. addVideoFrame yöntemini kullanacağız:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
"VIDEO_ID" ifadesini, yerleştirmek istediğiniz YouTube videosunun kimliğiyle değiştirin.
## 3. Adım: Video Oynatma Modunu Ayarlayın
Video çerçevesi için oynatma modunu ayarlayın. Bu örnekte bunu Otomatik olarak ayarlayacağız:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## 4. Adım: Küçük Resmi Yükleyin
Görsel çekiciliği artırmak için videonun küçük resmini yükleyeceğiz. Bu adım, küçük resim görüntüsünün web kaynağından getirilmesini içerir:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## Adım 5: Sunuyu Kaydetme
Son olarak değiştirilen sunumu kaydedin:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
"YOUR_DIRECTORY" ifadesini sunuyu kaydetmek istediğiniz dizinle değiştirin.

## Çözüm
Tebrikler! Aspose.Slides for Java'yı kullanarak PowerPoint'te bir web kaynağından nasıl video karesi ekleyeceğinizi başarıyla öğrendiniz. Videolar gibi multimedya öğelerini dahil etmek sunumlarınızın etkisini ve etkileşimini önemli ölçüde artırabilir.
## SSS'ler
### YouTube dışındaki kaynaklardan video ekleyebilir miyim?
Evet, yerleştirilebilir bir bağlantı sağladıkları sürece çeşitli web kaynaklarından videolar ekleyebilirsiniz.
### Gömülü videoyu oynatmak için internet bağlantısına ihtiyacım var mı?
Evet, videoyu web kaynağından yayınlamak için aktif bir internet bağlantısı gereklidir.
### Video çerçevesinin görünümünü özelleştirebilir miyim?
Kesinlikle! Aspose.Slides, video karelerinin görünümünü ve davranışını özelleştirmek için kapsamlı seçenekler sunar.
### Aspose.Slides PowerPoint'in tüm sürümleriyle uyumlu mu?
Aspose.Slides, çok çeşitli PowerPoint sürümlerini destekleyerek farklı platformlar arasında uyumluluk sağlar.
### Aspose.Slides için daha fazla kaynağı ve desteği nerede bulabilirim?
 Ziyaret edebilirsiniz[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) yardım, dokümantasyon ve topluluk desteği için.