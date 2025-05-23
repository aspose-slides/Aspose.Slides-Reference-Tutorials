---
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarını programatik olarak nasıl düzenleyeceğinizi öğrenin. Adım adım eğitimlerle Java PowerPoint kullanımında ustalaşın."
"linktitle": "Java kullanarak PowerPoint'i Varsayılan Normal Yazı Tipiyle Kaydet"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java kullanarak PowerPoint'i Varsayılan Normal Yazı Tipiyle Kaydet"
"url": "/tr/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak PowerPoint'i Varsayılan Normal Yazı Tipiyle Kaydet

## giriiş
Java geliştirme alanında, PowerPoint sunumlarını programatik olarak oluşturmak ve düzenlemek üretkenliği ve özelleştirme seçeneklerini büyük ölçüde artırabilir. Aspose.Slides for Java, geliştiricilerin PowerPoint dosyalarını verimli bir şekilde yönetmesini sağlayan, basit değişikliklerden karmaşık sunumlara kadar kapsamlı bir özellik seti sunan sağlam bir kütüphanedir.
## Ön koşullar
Java için Aspose.Slides'ı kullanmaya başlamadan önce, aşağıdaki ön koşulların sağlandığından emin olun:
1. Java Geliştirme Kiti (JDK): Aspose.Slides for Java'nın düzgün çalışması için JDK 1.8 veya üzeri gereklidir.
2. Aspose.Slides for Java JAR: Aspose.Slides for Java'nın en son sürümünü şu adresten indirin: [Burada](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA, Eclipse veya tercih ettiğiniz başka bir Java IDE'sini kullanın.
4. Java'nın Temel Anlayışı: Java programlama dilinin temellerine aşinalık gereklidir.

## Paketleri İçe Aktar
Java için Aspose.Slides'ı kullanmaya başlamak için gerekli paketleri içe aktarın:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Bu, Aspose.Slides for Java tarafından sağlanan tüm sınıflara ve yöntemlere erişebilmenizi sağlar.
## Adım 1: Projenizi Kurun
Öncelikle IDE'nizde yeni bir Java projesi oluşturun ve Aspose.Slides for Java JAR dosyasını projenizin derleme yoluna ekleyin.
## Adım 2: Sunum Nesnesini Başlat
Bir örnek oluştur `Presentation` Yerel dizininizden mevcut bir PowerPoint dosyasını (.pptx) yükleyerek nesneyi açın.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Yükleme sunumu
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
Yer değiştirmek `"Your Document Directory"` Ve `"Your Output Directory"` gerçek dosya yollarınızla.
## Adım 3: Sunumu Varsayılan Normal Yazı Tipleriyle Kaydedin
Çıktı biçimleri (HTML ve PDF) için varsayılan düzenli yazı tipini belirtin `HtmlOptions` Ve `PdfOptions` sırasıyla.
```java
try {
    // HTML kaydetme seçenekleri
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // PDF kaydetme seçenekleri
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
Değiştirdiğinizden emin olun `"Arial Black"` Ve `"Lucida Console"` İstediğiniz varsayılan düzenli yazı tipleriyle.

## Çözüm
Bu adımları izleyerek, Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarını nasıl etkili bir şekilde yöneteceğinizi öğrendiniz. Bu yetenek, görevleri otomatikleştirmenize, sunumları özelleştirmenize ve Java uygulamalarınızı gelişmiş PowerPoint işleme işlevleriyle geliştirmenize olanak tanır.
## SSS
### Aspose.Slides for Java, JDK'nın eski sürümleriyle çalışabilir mi?
Java için Aspose.Slides uyumluluğu için JDK 1.8 veya üzeri gereklidir.
### Aspose.Slides for Java için geçici lisanslamayı nasıl alabilirim?
Geçici lisansı şuradan alabilirsiniz: [Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java hakkında daha detaylı dokümanları nerede bulabilirim?
Kapsamlı belgeleri keşfedin [Burada](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java için topluluk desteği mevcut mu?
Evet, topluluk desteği alabilirsiniz [Burada](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java'yı ücretsiz deneyebilir miyim?
Evet, ücretsiz deneme sürümünü indirin [Burada](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}