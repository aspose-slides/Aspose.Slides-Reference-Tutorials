---
title: Java Slaytlarına HTML Gömme Görüntülerini Dönüştürme
linktitle: Java Slaytlarına HTML Gömme Görüntülerini Dönüştürme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Gömülü Görüntülerle PowerPoint'i HTML'ye dönüştürün. Aspose.Slides for Java'yı kullanan adım adım kılavuz. Java'da sunum dönüşümlerini zahmetsizce otomatikleştirmeyi öğrenin.
weight: 11
url: /tr/java/presentation-conversion/convert-html-embedding-images-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarına HTML Gömme Görüntülerini Dönüştürme


## Java Slaytlarına HTML Gömme Görüntülerini Dönüştürmeye Giriş

Bu adım adım kılavuzda, Aspose.Slides for Java kullanarak görselleri gömerken bir PowerPoint sunumunu HTML belgesine dönüştürme sürecinde size yol göstereceğiz. Bu eğitimde, geliştirme ortamınızı zaten kurduğunuzu ve Aspose.Slides for Java kütüphanesinin kurulu olduğunu varsayarız.

## Gereksinimler

Başlamadan önce aşağıdakilere sahip olduğunuzdan emin olun:

1.  Aspose.Slides for Java kütüphanesi kuruldu. Şuradan indirebilirsiniz[Burada](https://downloads.aspose.com/slides/java).

2. HTML'ye dönüştürmek istediğiniz bir PowerPoint sunum dosyası (PPTX biçimi).

3. Bir Java geliştirme ortamı kuruldu.

## 1. Adım: Gerekli Kitaplıkları İçe Aktarın

Öncelikle Java projeniz için gerekli kütüphaneleri ve sınıfları içe aktarmanız gerekir.

```java
import com.aspose.slides.Html5Options;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import java.io.File;
```

## Adım 2: PowerPoint Sunumunu Yükleyin

 Daha sonra HTML'ye dönüştürmek istediğiniz PowerPoint sunumunu yükleyeceksiniz. Değiştirdiğinizden emin olun`presentationName` sunum dosyanızın gerçek yolunu belirtin.

```java
String presentationName = "path/to/your/presentation.pptx";
Presentation pres = new Presentation(presentationName);
```

## 3. Adım: HTML Dönüştürme Seçeneklerini Yapılandırın

Şimdi HTML dönüştürme seçeneklerini yapılandıracaksınız. Bu örnekte, görüntüleri HTML belgesine gömeceğiz ve harici görüntüler için çıktı dizinini belirleyeceğiz.

```java
Html5Options options = new Html5Options();
// HTML5 belgesindeki görüntüleri kaydetmemeye zorla
options.setEmbedImages(true); // Görüntüleri gömmek için true olarak ayarlayın
//Harici görüntülerin yolunu ayarlayın (gerekirse)
options.setOutputPath("path/to/output/directory/");
```

## Adım 4: Çıkış Dizinini Oluşturun

HTML belgesini kaydetmeden önce, eğer mevcut değilse çıktı dizinini oluşturun.

```java
File outputDirectory = new File(options.getOutputPath());
if (!outputDirectory.exists()) {
    outputDirectory.mkdirs();
}
```

## Adım 5: Sunuyu HTML olarak kaydedin

Şimdi sunuyu belirtilen seçeneklerle HTML5 formatında kaydedin.

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

## Java Slaytlarına HTML Gömme Görüntülerini Dönüştürmek İçin Tam Kaynak Kodu

```java
// Kaynak sunumuna giden yol
String presentationName = "Your Document Directory";
// HTML belgesinin yolu
String outFilePath = "Your Output Directory" + "HTMLConvertion" + File.separator;
Presentation pres = new Presentation(presentationName);
try {
	Html5Options options = new Html5Options();
	// HTML5 belgesindeki görüntüleri kaydetmemeye zorla
	options.setEmbedImages(false);
	// Harici görüntüler için yolu ayarla
	options.setOutputPath(outFilePath);
	// Çıktı HTML belgesi için dizin oluşturun
	File f = new File(outFilePath);
	if (!f.exists())
		f.mkdir();
	// Sunuyu HTML5 formatında kaydedin.
	pres.save(outFilePath + "pres.html", SaveFormat.Html5, options);
} finally {
	if (pres != null) pres.dispose();
}
```

## Çözüm

Bu kapsamlı kılavuzda, Aspose.Slides for Java kullanarak görselleri gömerken bir PowerPoint sunumunu HTML belgesine nasıl dönüştüreceğimizi öğrendik. Adım adım talimatları izleyerek bu işlevselliği Java uygulamalarınıza sorunsuz bir şekilde entegre edebilir ve belge dönüştürme süreçlerinizi geliştirebilirsiniz.

## SSS'ler

### Çıktı dosya adını nasıl değiştiririm?

 Bağımsız değişkeni değiştirerek çıktı dosya adını değiştirebilirsiniz.`pres.save()` yöntem.

### HTML şablonunu özelleştirebilir miyim?

Evet, Aspose.Slides tarafından oluşturulan HTML ve CSS dosyalarını değiştirerek HTML şablonunu özelleştirebilirsiniz. Bunları çıktı dizininde bulacaksınız.

### Dönüştürme sırasındaki hataları nasıl ele alabilirim?

Dönüştürme işlemi sırasında oluşabilecek istisnaları ele almak için dönüştürme kodunu bir try-catch bloğuna sarabilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
