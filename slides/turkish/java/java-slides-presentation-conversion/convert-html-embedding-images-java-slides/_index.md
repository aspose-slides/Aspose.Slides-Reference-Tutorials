---
"description": "PowerPoint'i Gömülü Görüntülerle HTML'ye Dönüştürün. Java için Aspose.Slides'ı kullanarak adım adım kılavuz. Java'da sunum dönüşümlerini zahmetsizce otomatikleştirmeyi öğrenin."
"linktitle": "Java Slaytlarında HTML Yerleştirmeli Resimleri Dönüştürme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında HTML Yerleştirmeli Resimleri Dönüştürme"
"url": "/tr/java/presentation-conversion/convert-html-embedding-images-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında HTML Yerleştirmeli Resimleri Dönüştürme


## Java Slaytlarında HTML Gömülü Resimleri Dönüştürmeye Giriş

Bu adım adım kılavuzda, Aspose.Slides for Java kullanarak görüntüleri gömerek bir PowerPoint sunumunu HTML belgesine dönüştürme sürecinde size yol göstereceğiz. Bu eğitim, geliştirme ortamınızı zaten kurduğunuzu ve Aspose.Slides for Java kitaplığının yüklü olduğunu varsayar.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1. Java kütüphanesi için Aspose.Slides yüklendi. Buradan indirebilirsiniz [Burada](https://downloads.aspose.com/slides/java).

2. HTML'ye dönüştürmek istediğiniz bir PowerPoint sunum dosyası (PPTX formatı).

3. Java geliştirme ortamı kuruldu.

## Adım 1: Gerekli Kitaplıkları İçe Aktarın

Öncelikle Java projeniz için gerekli kütüphaneleri ve sınıfları içe aktarmanız gerekiyor.

```java
import com.aspose.slides.Html5Options;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```

## Adım 2: PowerPoint Sunumunu Yükleyin

Ardından, HTML'ye dönüştürmek istediğiniz PowerPoint sunumunu yükleyeceksiniz. Değiştirdiğinizden emin olun `presentationName` sunum dosyanızın gerçek yolunu içerir.

```java
String presentationName = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presentationName);
```

## Adım 3: HTML Dönüştürme Seçeneklerini Yapılandırın

Şimdi, HTML dönüştürme seçeneklerini yapılandıracaksınız. Bu örnekte, HTML belgesine resimler gömeceğiz ve harici resimler için çıktı dizinini belirteceğiz.

```java
Html5Options options = new Html5Options();
// HTML5 belgesinde resimleri kaydetmeyi zorla
options.setEmbedImages(true); // Resimleri yerleştirmek için true olarak ayarlayın
// Harici resimler için yolu ayarlayın (gerekirse)
options.setOutputPath("path/to/output/directory/");
```

## Adım 4: Çıktı Dizinini Oluşturun

HTML belgesini kaydetmeden önce, eğer yoksa çıktı dizinini oluşturun.

```java
File outputDirectory = new File(options.getOutputPath());
if (!outputDirectory.exists()) {
    outputDirectory.mkdirs();
}
```

## Adım 5: Sunumu HTML Olarak Kaydedin

Şimdi sunumu belirtilen seçeneklerle HTML5 formatında kaydedelim.

```java
pres.save(options.getOutputPath() + "output.html", SaveFormat.Html5, options);
```

## Adım 6: Kaynakları Temizleyin

Tahsis edilen kaynakları serbest bırakmak için Sunum nesnesini elden çıkarmayı unutmayın.

```java
if (pres != null) {
    pres.dispose();
}
```

## Java Slaytlarında HTML Yerleştirmeli Resimleri Dönüştürmek İçin Tam Kaynak Kodu

```java
// Kaynak sunumuna giden yol
String presentationName = "Your Document Directory";
// HTML belgesine giden yol
String outFilePath = "Your Output Directory" + "HTMLConvertion" + File.separator;
Presentation pres = new Presentation(presentationName);
try {
	Html5Options options = new Html5Options();
	// HTML5 belgesinde resimleri kaydetmeyi zorla
	options.setEmbedImages(false);
	// Harici resimler için yol ayarla
	options.setOutputPath(outFilePath);
	// Çıktı HTML belgesi için dizin oluştur
	File f = new File(outFilePath);
	if (!f.exists())
		f.mkdir();
	// Sunumu HTML5 formatında kaydedin.
	pres.save(outFilePath + "pres.html", SaveFormat.Html5, options);
} finally {
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu kapsamlı kılavuzda, Aspose.Slides for Java kullanarak görüntüleri yerleştirirken bir PowerPoint sunumunu HTML belgesine nasıl dönüştüreceğinizi öğrendik. Adım adım talimatları izleyerek, bu işlevselliği sorunsuz bir şekilde Java uygulamalarınıza entegre edebilir ve belge dönüştürme süreçlerinizi geliştirebilirsiniz.

## SSS

### Çıktı dosya adını nasıl değiştirebilirim?

Çıktı dosya adını, argümanı değiştirerek değiştirebilirsiniz. `pres.save()` yöntem.

### HTML şablonunu özelleştirebilir miyim?

Evet, Aspose.Slides tarafından oluşturulan HTML ve CSS dosyalarını değiştirerek HTML şablonunu özelleştirebilirsiniz. Bunları çıktı dizininde bulacaksınız.

### Dönüştürme sırasında oluşan hataları nasıl düzeltebilirim?

Dönüştürme işlemi sırasında oluşabilecek istisnaları ele almak için dönüştürme kodunu bir try-catch bloğunun içine sarabilirsiniz.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}