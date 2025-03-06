---
title: Slaytları Notlarla PDF'ye Dönüştürün
linktitle: Slaytları Notlarla PDF'ye Dönüştürün
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak konuşmacı notlarının bulunduğu sunum slaytlarını zahmetsizce PDF'ye dönüştürün. İçeriği ve bağlamı sorunsuz bir şekilde koruyun.
weight: 18
url: /tr/net/presentation-conversion/convert-slides-to-pdf-with-notes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


# Aspose.Slides for .NET Kullanarak Slaytları Notlarla PDF'ye Dönüştürmeye İlişkin Adım Adım Eğitim Kılavuzu Yazma

Tüm önemli notları korurken PowerPoint slaytlarınızı PDF formatına dönüştürmenin güvenilir bir yolunu mu arıyorsunuz? Başka yerde arama! Bu kapsamlı eğitimde, bu görevi adım adım gerçekleştirmek için Aspose.Slides for .NET'i kullanma sürecinde size rehberlik edeceğiz.

## 1. Giriş

PowerPoint slaytlarını notlarla birlikte PDF'ye dönüştürmek, önemli bağlam ve yorumların korunmasını sağlarken sunumları paylaşmak için değerli bir araç olabilir. Aspose.Slides for .NET bu görev için güçlü bir çözüm sunar.

## 2. Ortamınızı Kurmak

Kodlama sürecine geçmeden önce gerekli ortamın kurulduğundan emin olun. İhtiyacın olacak:

- Visual Studio veya tercih ettiğiniz .NET geliştirme ortamı.
- Aspose.Slides for .NET kütüphanesi kuruldu.
- Dönüştürmek istediğiniz notları içeren bir PowerPoint sunumu.

## 3. Sunumun Yüklenmesi

C# kodunuzda dönüştürmek istediğiniz PowerPoint sunumunu yüklemeniz gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Slaytın Klonlanması

PDF'nizin notlarla birlikte gerekli tüm slaytları içerdiğinden emin olmak için bunları orijinal sunumdan kopyalayabilirsiniz. İşte nasıl:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Slayt Boyutunun Ayarlanması

Slayt boyutunu PDF'nize uyacak şekilde ayarlamak isteyebilirsiniz. Aspose.Slides for .NET bunu kolaylıkla yapmanızı sağlar:

```csharp
auxPresentation.SlideSize.SetSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## 6. PDF Seçeneklerini Yapılandırma

Notlarınızın PDF'de nasıl görüntüleneceğini kontrol etmek için PDF seçeneklerini yapılandırabilirsiniz:

```csharp
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.NotesCommentsLayouting;
options.NotesPosition = NotesPositions.BottomFull;
```

## 7. Notlarla PDF olarak kaydetme

Son olarak sunumunuzu notlarla birlikte PDF olarak kaydedebilirsiniz:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Sonuç

Tebrikler! Tüm önemli notları korurken PowerPoint slaytlarınızı başarıyla PDF biçimine dönüştürdünüz. Aspose.Slides for .NET bu süreci basit ve verimli hale getirir.

## 9. SSS

### S1: PDF'deki notların düzenini özelleştirebilir miyim?

 Evet, notların düzenini kullanarak özelleştirebilirsiniz.`INotesCommentsLayoutingOptions` PDF seçeneklerinde.

### S2: Aspose.Slides for .NET, PDF'nin yanı sıra diğer çıktı formatlarını da destekliyor mu?

Evet, Aspose.Slides for .NET, PPTX, DOCX ve daha fazlası dahil olmak üzere çeşitli çıktı formatlarını destekler.

### S3: Aspose.Slides for .NET'in deneme sürümü mevcut mu?

 Evet, Aspose.Slides for .NET'in ücretsiz deneme sürümünü şu adresten edinebilirsiniz:[https://releases.aspose.com/](https://releases.aspose.com/).

### S4: Aspose.Slides for .NET desteğini nereden alabilirim?

 Destek ve topluluk tartışmalarını şu adreste bulabilirsiniz:[https://forum.aspose.com/](https://forum.aspose.com/).

### S5: Aspose.Slides for .NET için geçici bir lisans satın alabilir miyim?

 Evet, şu adresten geçici bir lisans satın alabilirsiniz:[https://purchase.aspose.com/temporary-license/](https://purchase.aspose.com/temporary-license/).

Sonuç olarak, Aspose.Slides for .NET'i kullanarak PowerPoint slaytlarını notları bozulmadan kolayca PDF formatına dönüştürebilirsiniz. Önemli bağlamın kaybolmamasını sağlarken sunumlarını iş arkadaşları ve müşterileriyle paylaşmaya ihtiyaç duyan profesyoneller için değerli bir araçtır.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
