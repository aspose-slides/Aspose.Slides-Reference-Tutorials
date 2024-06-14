---
title: Aspose.Slides for Java ile PowerPoint'te Varsayılan Yazı Tipleri
linktitle: Aspose.Slides for Java ile PowerPoint'te Varsayılan Yazı Tipleri
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java kullanarak PowerPoint sunumlarında varsayılan yazı tiplerini nasıl ayarlayacağınızı öğrenin. Tutarlılığı sağlayın ve görsel çekiciliği zahmetsizce geliştirin.
type: docs
weight: 11
url: /tr/java/java-powerpoint-font-management/default-fonts-powerpoint/
---
## giriiş
Özel yazı tipleriyle PowerPoint sunumları oluşturmak birçok projede ortak bir gerekliliktir. Aspose.Slides for Java, varsayılan yazı tiplerini yönetmek için kusursuz bir çözüm sunarak farklı ortamlarda tutarlılık sağlar. Bu eğitimde, Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarında varsayılan yazı tiplerini ayarlama sürecinde size rehberlik edeceğiz.
## Önkoşullar
Başlamadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın kurulu olduğundan emin olun.
2.  Aspose.Slides for Java: Aspose.Slides for Java'yı şu adresten indirip yükleyin:[indirme sayfası](https://releases.aspose.com/slides/java/).
3. Temel Java Bilgisi: Java programlama dilinin temellerine aşinalık.

## Paketleri İçe Aktar
Gerekli paketleri Java projenize aktararak başlayın:
```java
import com.aspose.slides.LoadFormat;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1. Adım: Varsayılan Yazı Tiplerini Ayarlayın
Belge dizininizin yolunu tanımlayın ve varsayılan normal ve Asya yazı tiplerini belirlemek için yükleme seçenekleri oluşturun:
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## 2. Adım: Sunuyu Yükleyin
Tanımlanan yükleme seçeneklerini kullanarak PowerPoint sunumunu yükleyin:
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## 3. Adım: Çıktıları Oluşturun
Slayt küçük resimleri, PDF ve XPS dosyaları gibi çeşitli çıktılar oluşturun:
```java
try {
    // Slayt küçük resmi oluştur
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // PDF oluştur
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // XPS oluştur
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## Çözüm
Aspose.Slides for Java kullanarak PowerPoint sunumlarında varsayılan yazı tiplerini ayarlamak basit ve etkilidir. Bu eğitimde özetlenen adımları izleyerek, farklı platformlar ve ortamlardaki yazı tipi stillerinde tutarlılık sağlayarak sunumlarınızın görsel çekiciliğini artırabilirsiniz.
## SSS'ler
### Aspose.Slides for Java ile özel yazı tiplerini kullanabilir miyim?
Evet, Aspose.Slides for Java'yı kullanarak sunumlarınızda özel yazı tipleri belirleyebilirsiniz.
### Aspose.Slides for Java, PowerPoint'in tüm sürümleriyle uyumlu mu?
Aspose.Slides for Java, çok çeşitli PowerPoint sürümlerini destekleyerek farklı ortamlar arasında uyumluluk sağlar.
### Aspose.Slides for Java için nasıl destek alabilirim?
 Aspose.Slides for Java için destek alabilirsiniz.[forumlar](https://forum.aspose.com/c/slides/11).
### Satın almadan önce Aspose.Slides for Java'yı deneyebilir miyim?
 Evet, Aspose.Slides for Java'yı şu adresteki ücretsiz deneme sürümüyle keşfedebilirsiniz:[bültenleri.aspose.com](https://releases.aspose.com/).
### Aspose.Slides for Java için nereden geçici lisans alabilirim?
 Aspose.Slides for Java için geçici bir lisansı şu adresten edinebilirsiniz:[satın alma sayfası](https://purchase.aspose.com/temporary-license/).