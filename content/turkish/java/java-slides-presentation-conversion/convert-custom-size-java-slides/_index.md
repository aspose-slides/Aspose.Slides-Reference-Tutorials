---
title: Java Slaytlarında Özel Boyutla Dönüştürme
linktitle: Java Slaytlarında Özel Boyutla Dönüştürme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak PowerPoint sunumlarını özel boyutlu TIFF görüntülerine nasıl dönüştüreceğinizi öğrenin. Geliştiriciler için kod örnekleri içeren adım adım kılavuz.
type: docs
weight: 31
url: /tr/java/presentation-conversion/convert-custom-size-java-slides/
---

## Java Slaytlarında Özel Boyutla Dönüştürmeye Giriş

Bu makalede, Aspose.Slides for Java API'sini kullanarak PowerPoint sunumlarını özel boyutlu TIFF görsellerine nasıl dönüştürebileceğinizi inceleyeceğiz. Aspose.Slides for Java, geliştiricilerin PowerPoint dosyalarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kitaplıktır. Adım adım ilerleyeceğiz ve bu görevi gerçekleştirmek için size gerekli Java kodunu sağlayacağız.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Java Geliştirme Kiti (JDK) yüklü
- Aspose.Slides for Java kütüphanesi

 Aspose.Slides for Java kütüphanesini web sitesinden indirebilirsiniz:[Java için Aspose.Slides'ı indirin](https://releases.aspose.com/slides/java/)

## 1. Adım: Aspose.Slides Kitaplığını İçe Aktarın

Başlamak için Aspose.Slides kütüphanesini Java projenize aktarmanız gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```java
// Gerekli içe aktarma ifadesini ekleyin
import com.aspose.slides.*;
```

## Adım 2: PowerPoint Sunumunu Yükleyin

Daha sonra, TIFF görüntüsüne dönüştürmek istediğiniz PowerPoint sunumunu yüklemeniz gerekecek. Yer değiştirmek`"Your Document Directory"` sunum dosyanızın gerçek yolunu belirtin.

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";

// Bir Sunum dosyasını temsil eden bir Sunum nesnesini örnekleyin
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
```

## 3. Adım: TIFF Dönüştürme Seçeneklerini Ayarlayın

Şimdi TIFF dönüşümüne ilişkin seçenekleri ayarlayalım. Sıkıştırma türünü, DPI'yi (inç başına nokta sayısı), görüntü boyutunu ve notların konumunu belirleyeceğiz. Bu seçenekleri ihtiyaçlarınıza göre özelleştirebilirsiniz.

```java
// TiffOptions sınıfını örnekleyin
TiffOptions opts = new TiffOptions();

// Sıkıştırma türünü ayarlama
opts.setCompressionType(TiffCompressionTypes.Default);

// Görüntü DPI'sını ayarlama
opts.setDpiX(200);
opts.setDpiY(100);

// Resim Boyutunu Ayarla
opts.setImageSize(new Dimension(1728, 1078));

// Notların konumunu ayarla
INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
notesOptions.setNotesPosition(NotesPositions.BottomFull);
```

## 4. Adım: TIFF olarak kaydedin

Tüm seçenekler yapılandırıldığında artık sunuyu belirtilen ayarlarla TIFF görüntüsü olarak kaydedebilirsiniz.

```java
// Sunuyu belirtilen görüntü boyutuyla TIFF'e kaydedin
pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
```

## Java Slaytlarında Özel Boyutla Dönüştürmek İçin Tam Kaynak Kodu

```java
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Bir Sunum dosyasını temsil eden bir Sunum nesnesini örnekleyin
Presentation pres = new Presentation(dataDir + "Convert_Tiff_Custom.pptx");
try
{
	// TiffOptions sınıfını örnekleyin
	TiffOptions opts = new TiffOptions();
	// Sıkıştırma türünü ayarlama
	opts.setCompressionType(TiffCompressionTypes.Default);
	INotesCommentsLayoutingOptions notesOptions = opts.getNotesCommentsLayouting();
	notesOptions.setNotesPosition(NotesPositions.BottomFull);
	// Sıkıştırma Türleri
	// Varsayılan - Varsayılan sıkıştırma düzenini (LZW) belirtir.
	// Yok - Sıkıştırma olmadığını belirtir.
	// CCITT3
	// CCITT4
	//LZW
	// RLE
	// Derinlik sıkıştırma türüne bağlıdır ve manuel olarak ayarlanamaz.
	// Çözünürlük birimi her zaman “2”ye eşittir (inç başına nokta sayısı)
	// Görüntü DPI'sını ayarlama
	opts.setDpiX(200);
	opts.setDpiY(100);
	// Resim Boyutunu Ayarla
	opts.setImageSize(new Dimension(1728, 1078));
	// Sunuyu belirtilen görüntü boyutuyla TIFF'e kaydedin
	pres.save(dataDir + "TiffWithCustomSize_out.tiff", SaveFormat.Tiff, opts);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Çözüm

Tebrikler! Aspose.Slides for Java'yı kullanarak bir PowerPoint sunumunu özel boyutlu bir TIFF görüntüsüne başarıyla dönüştürdünüz. Çeşitli amaçlarla sunumlarınızdan yüksek kaliteli görüntüler oluşturmanız gerektiğinde bu değerli bir özellik olabilir.

## SSS'ler

### TIFF görüntüsünün sıkıştırma türünü nasıl değiştirebilirim?

 Sıkıştırma türünü değiştirerek değiştirebilirsiniz.`setCompressionType` yöntemdeki`TiffOptions` sınıf. Varsayılan, Yok, CCITT3, CCITT4, LZW ve RLE gibi farklı sıkıştırma türleri mevcuttur.

### TIFF görüntüsünün DPI'sini (inç başına nokta sayısı) ayarlayabilir miyim?

 Evet, DPI'yi kullanarak ayarlayabilirsiniz.`setDpiX` Ve`setDpiY` içindeki yöntemler`TiffOptions` sınıf. Görüntü çözünürlüğünü kontrol etmek için istediğiniz değerleri ayarlamanız yeterlidir.

### TIFF görüntüsündeki notların konumu için mevcut seçenekler nelerdir?

TIFF görüntüsündeki notların konumu,`setNotesPosition` BottomFull, BottomTruncated ve SlideOnly gibi seçeneklerle yöntem. İhtiyaçlarınıza en uygun olanı seçin.

### TIFF dönüşümü için özel bir görüntü boyutu belirlemek mümkün müdür?

 Kesinlikle! kullanarak özel bir görüntü boyutu ayarlayabilirsiniz.`setImageSize` yöntemdeki`TiffOptions` sınıf. Çıktı görüntüsü için istediğiniz boyutları (genişlik ve yükseklik) sağlayın.

### Aspose.Slides for Java hakkında daha fazla bilgiyi nerede bulabilirim?

 Aspose.Slides for Java hakkında ayrıntılı belgeler ve ek bilgiler için lütfen belgeleri ziyaret edin:[Java API Referansı için Aspose.Slides](https://reference.aspose.com/slides/java/).