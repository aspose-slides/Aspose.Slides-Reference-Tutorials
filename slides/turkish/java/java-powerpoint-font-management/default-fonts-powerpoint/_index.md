---
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarında varsayılan yazı tiplerini nasıl ayarlayacağınızı öğrenin. Tutarlılığı sağlayın ve görsel çekiciliği zahmetsizce artırın."
"linktitle": "Aspose.Slides for Java ile PowerPoint'te Varsayılan Yazı Tipleri"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Aspose.Slides for Java ile PowerPoint'te Varsayılan Yazı Tipleri"
"url": "/tr/java/java-powerpoint-font-management/default-fonts-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for Java ile PowerPoint'te Varsayılan Yazı Tipleri

## giriiş
Özel yazı tipleriyle PowerPoint sunumları oluşturmak birçok projede yaygın bir gerekliliktir. Aspose.Slides for Java, farklı ortamlarda tutarlılığı garanti ederek varsayılan yazı tiplerini yönetmek için kusursuz bir çözüm sunar. Bu eğitimde, Aspose.Slides for Java kullanarak PowerPoint sunumlarında varsayılan yazı tiplerini ayarlama sürecinde size rehberlik edeceğiz.
## Ön koşullar
Başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Sisteminizde JDK'nın yüklü olduğundan emin olun.
2. Java için Aspose.Slides: Java için Aspose.Slides'ı indirin ve yükleyin [indirme sayfası](https://releases.aspose.com/slides/java/).
3. Temel Java Bilgisi: Java programlama dilinin temellerine aşinalık.

## Paketleri İçe Aktar
Öncelikle Java projenize gerekli paketleri import ederek başlayalım:
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
## Adım 1: Varsayılan Yazı Tiplerini Ayarlayın
Belge dizininize giden yolu tanımlayın ve varsayılan normal ve Asya yazı tiplerini belirtmek için yükleme seçenekleri oluşturun:
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## Adım 2: Sunumu Yükleyin
PowerPoint sunumunu tanımlanan yükleme seçeneklerini kullanarak yükleyin:
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## Adım 3: Çıktıları Oluşturun
Slayt küçük resimleri, PDF ve XPS dosyaları gibi çeşitli çıktılar oluşturun:
```java
try {
    // Slayt küçük resmini oluştur
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // PDF oluştur
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // XPS Oluştur
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## Çözüm
Aspose.Slides for Java kullanarak PowerPoint sunumlarında varsayılan yazı tiplerini ayarlamak basit ve etkilidir. Bu eğitimde özetlenen adımları izleyerek, farklı platformlar ve ortamlarda yazı tipi stillerinde tutarlılık sağlayabilir ve sunumlarınızın görsel çekiciliğini artırabilirsiniz.
## SSS
### Aspose.Slides for Java ile özel yazı tipleri kullanabilir miyim?
Evet, Aspose.Slides for Java'yı kullanarak sunularınızda özel yazı tipleri belirleyebilirsiniz.
### Aspose.Slides for Java, PowerPoint'in tüm sürümleriyle uyumlu mudur?
Java için Aspose.Slides, farklı ortamlarda uyumluluğu garanti altına alarak çok çeşitli PowerPoint sürümlerini destekler.
### Java için Aspose.Slides desteğini nasıl alabilirim?
Java için Aspose.Slides desteğini şuradan alabilirsiniz: [Aspose forumları](https://forum.aspose.com/c/slides/11).
### Satın almadan önce Aspose.Slides for Java'yı deneyebilir miyim?
Evet, Java için Aspose.Slides'ı ücretsiz deneme sürümüyle keşfedebilirsiniz. [sürümler.aspose.com](https://releases.aspose.com/).
### Aspose.Slides for Java için geçici lisansı nereden alabilirim?
Aspose.Slides for Java için geçici bir lisansı şuradan edinebilirsiniz: [satın alma sayfası](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}