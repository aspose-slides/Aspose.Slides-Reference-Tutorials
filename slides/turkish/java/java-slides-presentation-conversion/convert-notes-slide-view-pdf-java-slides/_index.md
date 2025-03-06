---
title: Java Slaytlarında Not Slayt Görünümünü PDF'ye Dönüştürme
linktitle: Java Slaytlarında Not Slayt Görünümünü PDF'ye Dönüştürme
second_title: Aspose.Slides Java PowerPoint İşleme API'si
description: Aspose.Slides for Java'yı kullanarak notlar içeren PowerPoint sunumlarını PDF'lere nasıl dönüştüreceğinizi öğrenin. Kaynak kodunu içeren adım adım kılavuzumuzu izleyin.
type: docs
weight: 16
url: /tr/java/presentation-conversion/convert-notes-slide-view-pdf-java-slides/
---

## Java Slaytlarında Not Slayt Görünümünü PDF'ye Dönüştürmeye Giriş

Bu eğitimde, notlar içeren bir PowerPoint sunumunu Aspose.Slides for Java kütüphanesini kullanarak slayt görünümünü PDF'ye dönüştürme sürecinde size rehberlik edeceğiz. Bu kitaplık, Java'da PowerPoint sunumlarıyla çalışmak için güçlü özellikler sağlar.

## Önkoşullar
1. Java Geliştirme Kiti (JDK) yüklü.
2. Aspose.Slides for Java kütüphanesi projenize eklendi.

## 1. Adım: Gerekli Sınıfları İçe Aktarın
Başlamak için gerekli sınıfları Aspose.Slides kütüphanesinden içe aktarmanız gerekir. İşte bunu yapacak kod:

```java
import com.aspose.slides.*;
```

## Adım 2: PowerPoint Sunumunu Yükleyin
 PowerPoint sunum dosyanızı hazır bulundurmalısınız. Yer değiştirmek`"Your Document Directory"` sunum dosyanızın bulunduğu dizinin yolu ile birlikte. Sunumu yüklemek için gereken kod:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
```

## 3. Adım: PDF Seçeneklerini Yapılandırın
Şimdi PDF dışa aktarma seçeneklerini yapılandıralım. Özellikle, notların PDF'deki slaytların altına dahil edilmesi için notların konumunu "BottomFull" olarak ayarlayacağız. İşte kod:

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

Diğer PDF seçeneklerini gereksinimlerinize göre özelleştirebilirsiniz.

## 4. Adım: Sunuyu Notlarla PDF Olarak Kaydetme
 Son olarak sunuyu notlarla birlikte PDF dosyası olarak kaydedelim. Çıktı dosyasının adını belirleyebilirsiniz (örn.`"Pdf_Notes_out.pdf"`) ve biçimi seçin (`SaveFormat.Pdf`). İşte bunu yapacak kod:

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
// Belgeler dizininin yolu.
String dataDir = "Your Document Directory";
// Bir sunum dosyasını temsil eden bir Sunum nesnesinin örneğini oluşturun
Presentation presentation = new Presentation(dataDir + "NotesFile.pptx");
try
{
	PdfOptions pdfOptions = new PdfOptions();
	INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
	options.setNotesPosition(NotesPositions.BottomFull);
	// Sunuyu PDF notlarına kaydetme
	presentation.save(dataDir + "Pdf_Notes_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Çözüm

Bu eğitimde, Aspose.Slides for Java kütüphanesini kullanarak not slayt görünümleri içeren PowerPoint sunumlarını PDF'lere nasıl dönüştürebileceğimizi araştırdık. Bu dönüşümü gerçekleştirmek için kaynak kodlu adım adım bir kılavuz izledik. İşte önemli çıkarımlar:

## SSS'ler

### PDF'deki notların konumunu nasıl değiştiririm?

 PDF'deki notların konumunu değiştirerek değiştirebilirsiniz.`setNotesPosition` yöntem argümanı. Örneğin, bunu şu şekilde ayarlayabilirsiniz:`NotesPositions.RightFull` Notları slaytların sağ tarafına yerleştirmek için.

```java
options.setNotesPosition(NotesPositions.RightFull);
```

### PDF dışa aktarımını daha da özelleştirebilir miyim?

 Evet, PDF dışa aktarımını, çeşitli seçenekleri ayarlayarak özelleştirebilirsiniz.`PdfOptions` nesne. Örneğin kaliteyi, sıkıştırmayı ve diğer parametreleri ihtiyaçlarınıza göre ayarlayabilirsiniz.

### Aspose.Slides for Java'yı nasıl edinebilirim?

 Aspose.Slides for Java'yı şu adresteki web sitesinden indirebilirsiniz:[Burada](https://releases.aspose.com/slides/java/).

### Aspose.Slides'ı kullanmak için herhangi bir lisans gereksinimi var mı?

Evet, Aspose.Slides ticari kullanım için geçerli bir lisans gerektirir. Aspose web sitesinden lisans alabilirsiniz.

### Daha fazla belge ve örneği nerede bulabilirim?

 Aspose.Slides for Java ile ilgili kapsamlı belgeleri ve örnekleri şu adreste bulabilirsiniz:[Burada](https://reference.aspose.com/slides/java/).