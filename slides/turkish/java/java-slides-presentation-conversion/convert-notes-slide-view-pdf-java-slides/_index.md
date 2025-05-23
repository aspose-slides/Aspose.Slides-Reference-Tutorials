---
"description": "Aspose.Slides for Java kullanarak notlu PowerPoint sunumlarını PDF'lere nasıl dönüştüreceğinizi öğrenin. Kaynak kodlu adım adım kılavuzumuzu izleyin."
"linktitle": "Java Slaytlarında Not Slayt Görünümünü PDF'ye Dönüştür"
"second_title": "Aspose.Slides Java PowerPoint İşleme API'si"
"title": "Java Slaytlarında Not Slayt Görünümünü PDF'ye Dönüştür"
"url": "/tr/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Java Slaytlarında Not Slayt Görünümünü PDF'ye Dönüştür


## Java Slaytlarında Not Slayt Görünümünü PDF'ye Dönüştürmeye Giriş

Bu eğitimde, Aspose.Slides for Java kütüphanesini kullanarak not slayt görünümüne sahip bir PowerPoint sunumunu PDF'ye dönüştürme sürecinde size rehberlik edeceğiz. Bu kütüphane, Java'da PowerPoint sunumlarıyla çalışmak için güçlü özellikler sunar.

## Ön koşullar
1. Java Geliştirme Kiti (JDK) kuruldu.
2. Aspose.Slides for Java kütüphanesi projenize eklendi.

## Adım 1: Gerekli Sınıfları İçe Aktarın
Başlamak için, Aspose.Slides kütüphanesinden gerekli sınıfları içe aktarmanız gerekir. Bunu yapmak için kod şudur:

```java
import com.aspose.slides.*;
```

## Adım 2: PowerPoint Sunumunu Yükleyin
PowerPoint sunum dosyanız hazır olmalı. Değiştir `"Your Document Directory"` sunum dosyanızın bulunduğu dizinin yolu ile. Sunumu yüklemek için kod şu şekilde:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## Adım 3: PDF Seçeneklerini Yapılandırın
Şimdi, PDF dışa aktarma seçeneklerini yapılandıralım. Özellikle, notlar konumunu "AltTam" olarak ayarlayıp PDF'deki slaytların altındaki notları ekleyeceğiz. İşte kod:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

İhtiyaçlarınıza göre diğer PDF seçeneklerini özelleştirebilirsiniz.

## Adım 4: Sunumu Notlarla PDF Olarak Kaydedin
Son olarak, notları da dahil ederek sunumu PDF dosyası olarak kaydedelim. Çıktı dosya adını belirtebilirsiniz (örneğin, `"Pdf_Notes_out.pdf"`) ve formatı seçin (`SaveFormat.Pdf`). Bunu yapmak için gereken kod şudur:

```java
presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Adım 5: Kaynakları Temizleyin
Sunumu tamamladıktan sonra kaynakları yayınlamayı unutmayın:

```java
if (presentation != null) presentation.dispose();
```

## Java Slaytlarında Not Slayt Görünümünü PDF'ye Dönüştürmek İçin Tam Kaynak Kodu

```java
// Belgeler dizinine giden yol.
String dataDir = "Your Document Directory";
// Bir sunum dosyasını temsil eden bir Sunum nesnesi örneği oluşturun
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Sunumu PDF notlarına kaydetme
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java kütüphanesini kullanarak not slayt görünümleri olan PowerPoint sunumlarını PDF'lere nasıl dönüştürebileceğimizi inceledik. Bu dönüşümü elde etmek için kaynak kodlu adım adım bir kılavuz izledik. İşte temel çıkarımlar:

## SSS

### PDF'deki notların konumunu nasıl değiştirebilirim?

Notların PDF'deki konumunu, `setNotesPosition` yöntem argümanı. Örneğin, bunu şu şekilde ayarlayabilirsiniz: `NotesPositions.RightFull` Notları slaytların sağ tarafına yerleştirmek için.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### PDF dışa aktarımını daha fazla özelleştirebilir miyim?

Evet, PDF dışa aktarımını çeşitli seçenekleri ayarlayarak özelleştirebilirsiniz. `PdfOptions` nesne. Örneğin, kaliteyi, sıkıştırmayı ve diğer parametreleri ihtiyaçlarınıza göre ayarlayabilirsiniz.

### Java için Aspose.Slides'ı nasıl edinebilirim?

Aspose.Slides for Java'yı web sitesinden indirebilirsiniz. [Burada](https://releases.aspose.com/slides/java/).

### Aspose.Slides'ı kullanmak için herhangi bir lisanslama gereksinimi var mı?

Evet, Aspose.Slides ticari kullanım için geçerli bir lisans gerektirir. Lisansı Aspose web sitesinden edinebilirsiniz.

### Daha fazla doküman ve örneği nerede bulabilirim?

Java için Aspose.Slides'a ilişkin kapsamlı belgeleri ve örnekleri şu adreste bulabilirsiniz: [Burada](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}