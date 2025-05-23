---
"description": "Aspose.Slides for Java kullanarak PowerPoint sunumlarını özel boyutlu TIFF görüntülerine nasıl dönüştüreceğinizi öğrenin. Geliştiriciler için kod örnekleri içeren adım adım kılavuz."
"linktitle": "Java Slaytlarında Özel Boyutla Dönüştürme"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Özel Boyutla Dönüştürme"
"url": "/tr/java/presentation-conversion/convert-custom-size-java-slides/"
"weight": 31
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Özel Boyutla Dönüştürme


## Java Slaytlarında Özel Boyutla Dönüştürmeye Giriş

Bu makalede, Aspose.Slides for Java API'sini kullanarak PowerPoint sunumlarını özel boyutlu TIFF görüntülerine nasıl dönüştüreceğinizi inceleyeceğiz. Aspose.Slides for Java, geliştiricilerin PowerPoint dosyalarıyla programatik olarak çalışmasına olanak tanıyan güçlü bir kütüphanedir. Adım adım ilerleyeceğiz ve bu görevi başarmanız için gereken Java kodunu size sağlayacağız.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

- Java Geliştirme Kiti (JDK) yüklendi
- Java kütüphanesi için Aspose.Slides

Aspose.Slides for Java kütüphanesini şu web sitesinden indirebilirsiniz: [Java için Aspose.Slides'ı indirin](https://releases.aspose.com/slides/java/)

## Adım 1: Aspose.Slides Kitaplığını İçe Aktar

Başlamak için Aspose.Slides kütüphanesini Java projenize aktarmanız gerekir. Bunu şu şekilde yapabilirsiniz:

```java
// Gerekli içe aktarma ifadesini ekleyin
import com.aspose.slides.*;
```

## Adım 2: PowerPoint Sunumunu Yükleyin

Daha sonra, TIFF görüntüsüne dönüştürmek istediğiniz PowerPoint sunumunu yüklemeniz gerekecektir. Değiştir `"Your Document Directory"` sunum dosyanızın gerçek yolunu içerir.

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";

// Bir Sunum dosyasını temsil eden bir Sunum nesnesi örneği oluşturun
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## Adım 3: TIFF Dönüştürme Seçeneklerini Ayarlayın

Şimdi, TIFF dönüştürme için seçenekleri ayarlayalım. Sıkıştırma türünü, DPI'yi (inç başına nokta sayısı), görüntü boyutunu ve not konumunu belirteceğiz. Bu seçenekleri gereksinimlerinize göre özelleştirebilirsiniz.

```java
// TiffOptions sınıfını örneklendirin
TiffOptions opts = new TiffOptions();

// Sıkıştırma türünü ayarlama
opts.setCompressionType(TiffCompressionTypes.Default);

// Görüntü DPI'sini ayarlama
opts.setDpiX(200);
opts.setDpiY(100);

// Resim Boyutunu Ayarla
opts.setImageSize(new Dimension(1728, 1078));

// Not pozisyonunu ayarla
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## Adım 4: TIFF olarak kaydedin

Tüm seçenekler yapılandırıldıktan sonra artık sunumunuzu belirtilen ayarlarla TIFF resmi olarak kaydedebilirsiniz.

```java
// Sunuyu belirtilen görüntü boyutuyla TIFF olarak kaydedin
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Java Slaytlarında Özel Boyutla Dönüştürmek İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir Sunum dosyasını temsil eden bir Sunum nesnesi örneği oluşturun
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// TiffOptions sınıfını örneklendirin
	TiffOptions opts = new TiffOptions();
	// Sıkıştırma türünü ayarlama
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Sıkıştırma Türleri
	// Varsayılan - Varsayılan sıkıştırma şemasını (LZW) belirtir.
	// Hiçbiri - Sıkıştırma yapılmayacağını belirtir.
	// CCITT3
	// CCITT4
	// LZW
	// RLE
	// Derinlik sıkıştırma türüne bağlıdır ve manuel olarak ayarlanamaz.
	// Çözünürlük birimi her zaman "2"ye (inç başına nokta) eşittir
	// Görüntü DPI'sini ayarlama
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Resim Boyutunu Ayarla
	opts.setImageSize(new Dimension(1728, 1078));
	// Sunuyu belirtilen görüntü boyutuyla TIFF olarak kaydedin
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Tebrikler! Aspose.Slides for Java kullanarak bir PowerPoint sunumunu özel boyutlu bir TIFF resmine başarıyla dönüştürdünüz. Bu, çeşitli amaçlar için sunumlarınızdan yüksek kaliteli resimler üretmeniz gerektiğinde değerli bir özellik olabilir.

## SSS

### TIFF resminin sıkıştırma türünü nasıl değiştirebilirim?

Sıkıştırma türünü değiştirerek değiştirebilirsiniz. `setCompressionType` yöntemde `TiffOptions` sınıf. Varsayılan, Hiçbiri, CCITT3, CCITT4, LZW ve RLE gibi farklı sıkıştırma türleri mevcuttur.

### TIFF resminin DPI'ını (inç başına nokta sayısı) ayarlayabilir miyim?

Evet, DPI'ı kullanarak ayarlayabilirsiniz. `setDpiX` Ve `setDpiY` yöntemler `TiffOptions` sınıf. Görüntü çözünürlüğünü kontrol etmek için istediğiniz değerleri ayarlamanız yeterlidir.

### TIFF görüntüsünde notların konumu için hangi seçenekler mevcuttur?

TIFF görüntüsündeki notların konumu, şu şekilde yapılandırılabilir: `setNotesPosition` BottomFull, BottomTruncated ve SlideOnly gibi seçeneklere sahip yöntem. İhtiyaçlarınıza en uygun olanı seçin.

### TIFF dönüşümü için özel bir resim boyutu belirtmek mümkün müdür?

Kesinlikle! Özel bir resim boyutunu şu şekilde ayarlayabilirsiniz: `setImageSize` yöntemde `TiffOptions` sınıf. Çıktı görüntüsü için istediğiniz boyutları (genişlik ve yükseklik) sağlayın.

### Aspose.Slides for Java hakkında daha fazla bilgiyi nerede bulabilirim?

Aspose.Slides for Java hakkında ayrıntılı belgeler ve ek bilgiler için lütfen belgeleri ziyaret edin: [Java API Referansı için Aspose.Slides](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}