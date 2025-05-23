---
"description": "Aspose.Slides for .NET kullanarak konuşmacı notları içeren sunum slaytlarını zahmetsizce PDF'e dönüştürün. İçeriği ve bağlamı sorunsuz bir şekilde koruyun."
"linktitle": "Slaytları Notlarla PDF'ye Dönüştür"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Slaytları Notlarla PDF'ye Dönüştür"
"url": "/tr/net/presentation-conversion/convert-slides-to-pdf-with-notes/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Slaytları Notlarla PDF'ye Dönüştür


# Aspose.Slides for .NET kullanarak Slaytları Notlarla PDF'ye Dönüştürmeyle İlgili Adım Adım Eğitim Kılavuzu Yazın

Tüm önemli notları koruyarak PowerPoint slaytlarınızı PDF formatına dönüştürmenin güvenilir bir yolunu mu arıyorsunuz? Başka yere bakmayın! Bu kapsamlı eğitimde, bu görevi adım adım başarmak için Aspose.Slides for .NET'i kullanma sürecinde size rehberlik edeceğiz.

## 1. Giriş

PowerPoint slaytlarını notlarla PDF'ye dönüştürmek, önemli bağlam ve yorumların korunduğundan emin olurken sunumları paylaşmak için değerli bir araç olabilir. Aspose.Slides for .NET bu görev için güçlü bir çözüm sunar.

## 2. Ortamınızı Ayarlama

Kodlama sürecine dalmadan önce, gerekli ortamı kurduğunuzdan emin olun. İhtiyacınız olacaklar:

- Visual Studio veya tercih ettiğiniz .NET geliştirme ortamı.
- Aspose.Slides for .NET kütüphanesi kuruldu.
- Dönüştürmek istediğiniz notların bulunduğu bir PowerPoint sunumu.

## 3. Sunumu Yükleme

C# kodunuzda, dönüştürmek istediğiniz PowerPoint sunumunu yüklemeniz gerekir. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## 4. Slaytın Klonlanması

PDF'inizin notlarla birlikte gerekli tüm slaytları içerdiğinden emin olmak için bunları orijinal sunumdan kopyalayabilirsiniz. İşte nasıl:

```csharp
Presentation auxPresentation = new Presentation();
ISlide slide = presentation.Slides[0];
auxPresentation.Slides.InsertClone(0, slide);
```

## 5. Slayt Boyutunu Ayarlama

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

## 7. Notlarla PDF Olarak Kaydetme

Son olarak sunumunuzu notlarla birlikte PDF olarak kaydedebilirsiniz:

```csharp
auxPresentation.Save(outPath + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## 8. Sonuç

Tebrikler! Tüm önemli notları koruyarak PowerPoint slaytlarınızı başarıyla PDF formatına dönüştürdünüz. Aspose.Slides for .NET bu süreci basit ve etkili hale getirir.

## 9. SSS

### S1: PDF'deki notların düzenini özelleştirebilir miyim?

Evet, notların düzenini kullanarak özelleştirebilirsiniz. `INotesCommentsLayoutingOptions` PDF seçeneklerinde.

### S2: Aspose.Slides for .NET PDF dışında başka çıktı formatlarını da destekliyor mu?

Evet, Aspose.Slides for .NET, PPTX, DOCX ve daha fazlası dahil olmak üzere çeşitli çıktı biçimlerini destekler.

### S3: Aspose.Slides for .NET için deneme sürümü mevcut mu?

Evet, Aspose.Slides for .NET'in ücretsiz deneme sürümünü şu adresten edinebilirsiniz: [https://releases.aspose.com/](https://releases.aspose.com/).

### S4: Aspose.Slides for .NET için desteği nereden alabilirim?

Destek ve topluluk tartışmalarını şu adreste bulabilirsiniz: [https://forum.aspose.com/](https://forum.aspose.com/).

### S5: Aspose.Slides for .NET için geçici bir lisans satın alabilir miyim?

Evet, geçici bir lisans satın alabilirsiniz [https://purchase.aspose.com/geçici-lisans/](https://purchase.aspose.com/temporary-license/).

Sonuç olarak, Aspose.Slides for .NET kullanarak PowerPoint slaytlarını notlar bozulmadan PDF formatına kolayca dönüştürebilirsiniz. Önemli bağlamın kaybolmamasını sağlarken sunumları meslektaşları ve müşterileriyle paylaşması gereken profesyoneller için değerli bir araçtır.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}