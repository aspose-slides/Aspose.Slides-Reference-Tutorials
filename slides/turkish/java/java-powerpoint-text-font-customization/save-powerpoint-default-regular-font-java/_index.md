---
title: Java kullanarak PowerPoint'i Varsayılan Normal Yazı Tipiyle Kaydetme
linktitle: Java kullanarak PowerPoint'i Varsayılan Normal Yazı Tipiyle Kaydetme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarını programlı olarak nasıl değiştireceğinizi öğrenin. Adım adım eğitimlerle Java PowerPoint kullanımında ustalaşın.
weight: 12
url: /tr/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java kullanarak PowerPoint'i Varsayılan Normal Yazı Tipiyle Kaydetme

## giriiş
Java geliştirme alanında, PowerPoint sunumlarını programlı olarak oluşturmak ve değiştirmek, üretkenliği ve özelleştirme seçeneklerini büyük ölçüde artırabilir. Aspose.Slides for Java, basit değişikliklerden karmaşık sunumlara kadar kapsamlı bir dizi özellik sunan, geliştiricilerin PowerPoint dosyalarını verimli bir şekilde yönetmesine olanak tanıyan güçlü bir kitaplıktır.
## Önkoşullar
Aspose.Slides for Java'yı kullanmaya başlamadan önce aşağıdaki önkoşulları oluşturduğunuzdan emin olun:
1. Java Geliştirme Kiti (JDK): Aspose.Slides for Java'nın düzgün çalışması için JDK 1.8 veya üstü gerekir.
2. Aspose.Slides for Java JAR: Aspose.Slides for Java'nın en son sürümünü şu adresten indirin:[Burada](https://releases.aspose.com/slides/java/).
3. Entegre Geliştirme Ortamı (IDE): IntelliJ IDEA, Eclipse veya seçtiğiniz başka bir Java IDE'yi kullanın.
4. Temel Java Anlayışı: Java programlama dilinin temellerine aşinalık gereklidir.

## Paketleri İçe Aktar
Aspose.Slides for Java'yı kullanmaya başlamak için gerekli paketleri içe aktarın:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Bu, Aspose.Slides for Java tarafından sağlanan tüm sınıflara ve yöntemlere erişebilmenizi sağlar.
## 1. Adım: Projenizi Kurun
Öncelikle IDE'nizde yeni bir Java projesi oluşturun ve Aspose.Slides for Java JAR dosyasını projenizin derleme yoluna ekleyin.
## Adım 2: Sunum Nesnesini Başlatın
 Bir örnek oluştur`Presentation` Yerel dizininizden mevcut bir PowerPoint dosyasını (.pptx) yükleyerek nesneyi oluşturun.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Sunumu yükle
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Yer değiştirmek`"Your Document Directory"` Ve`"Your Output Directory"` gerçek dosya yollarınızla.
## 3. Adım: Sunumu Varsayılan Normal Yazı Tipleriyle Kaydetme
 Çıkış formatları (HTML ve PDF) için varsayılan normal yazı tipini kullanarak belirtin.`HtmlOptions` Ve`PdfOptions` sırasıyla.
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
 Değiştirildiğinden emin olun`"Arial Black"` Ve`"Lucida Console"` istediğiniz varsayılan normal yazı tipleriyle.

## Çözüm
Bu adımları izleyerek, Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarını etkili bir şekilde nasıl değiştireceğinizi öğrendiniz. Bu özellik, gelişmiş PowerPoint işleme işlevleriyle görevleri otomatikleştirmenize, sunumları özelleştirmenize ve Java uygulamalarınızı geliştirmenize olanak tanır.
## SSS'ler
### Aspose.Slides for Java, JDK'nın eski sürümleriyle çalışabilir mi?
Aspose.Slides for Java, uyumluluk için JDK 1.8 veya üstünü gerektirir.
### Aspose.Slides for Java için nasıl geçici lisans alabilirim?
 adresinden geçici lisans alabilirsiniz.[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for Java ile ilgili daha ayrıntılı belgeleri nerede bulabilirim?
 Kapsamlı belgeleri keşfedin[Burada](https://reference.aspose.com/slides/java/).
### Aspose.Slides for Java için topluluk desteği mevcut mu?
 Evet, topluluk desteği alabilirsiniz[Burada](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for Java'yı ücretsiz deneyebilir miyim?
 Evet, ücretsiz deneme sürümünü indirin[Burada](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
