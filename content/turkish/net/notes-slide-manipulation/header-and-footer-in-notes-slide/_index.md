---
title: Notes Slaytında Üstbilgi ve Altbilgiyi Yönetme
linktitle: Notes Slaytında Üstbilgi ve Altbilgiyi Yönetme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak not slaytlarındaki üstbilgi ve altbilgiyi nasıl özelleştireceğinizi öğrenin. Bu adım adım kılavuz, kaynak kodu örnekleri sağlar ve öğelere erişmeyi, bunları değiştirmeyi ve biçimlendirmeyi kapsar.
type: docs
weight: 11
url: /tr/net/notes-slide-manipulation/header-and-footer-in-notes-slide/
---

## Aspose.Slides for .NET'e Giriş

Aspose.Slides for .NET, geliştiricilerin Microsoft PowerPoint dosyalarıyla programlı olarak çalışmasına olanak tanıyan güçlü bir kitaplıktır. Sunumların, slaytların, şekillerin ve bunların içindeki çeşitli öğelerin manipülasyonuna ve oluşturulmasına olanak tanır. Bu kılavuzda, Aspose.Slides for .NET kullanarak notlar slaytındaki üstbilgi ve altbilgi öğelerinin nasıl yönetileceğine odaklanacağız.

## Sunuma Not Slaydı Ekleme

 Başlamak için Aspose.Slides for .NET'in kurulu olduğundan emin olun. Kütüphaneyi adresinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/net/). Kurulumdan sonra tercih ettiğiniz .NET geliştirme ortamında yeni bir proje oluşturun.

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

class Program
{
    static void Main(string[] args)
    {
        // Sunuyu yükle
        using (Presentation presentation = new Presentation())
        {
            // Yeni bir slayt ekle
            ISlide slide = presentation.Slides.AddEmptySlide();
            
            // Geçerli slayda notlar slaytı ekleyin
            INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
            
            // Üstbilgi ve altbilgi öğelerini işlemeye yönelik kodunuz buraya gelecek
            
            // Değiştirilen sunuyu kaydet
            presentation.Save("output.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Üstbilgi ve Altbilgi Öğelerine Erişim

Sununuza bir notlar slaydı ekledikten sonra özelleştirme için üst bilgi ve alt bilgi öğelerine erişebilirsiniz. Üstbilgi ve altbilgi öğeleri metin, tarih ve slayt numaralarını içerebilir. Bu öğelere erişmek için aşağıdaki kodu kullanın:

```csharp
INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
INotesHeaderFooterManager headerFooterManager = notesSlide.HeaderFooterManager;

// Başlık metnine erişme
string headerText = headerFooterManager.HeaderText;

// Altbilgi metnine erişme
string footerText = headerFooterManager.FooterText;

// Tarih ve saate erişme
bool isDateTimeVisible = headerFooterManager.IsDateTimeVisible;

//Slayt numarasına erişim
bool isSlideNumberVisible = headerFooterManager.IsSlideNumberVisible;
```

## Üstbilgi ve Altbilgi Metnini Değiştirme

Bağlam veya diğer gerekli bilgileri sağlamak için üstbilgi ve altbilgi metnini kolayca değiştirebilirsiniz. Üst bilgi ve alt bilgi metnini güncellemek için aşağıdaki kodu kullanın:

```csharp
headerFooterManager.SetText(HeaderFooterType.Header, "Your header text");
headerFooterManager.SetText(HeaderFooterType.Footer, "Your footer text");
```

## Üstbilgi ve Altbilgi Öğelerini Şekillendirme

Aspose.Slides for .NET ayrıca üstbilgi ve altbilgi öğelerini sunumunuzun tasarımına göre şekillendirmenize de olanak tanır. Yazı tipini, boyutunu, rengini ve hizalamasını değiştirebilirsiniz. Öğelerin nasıl stillendirileceğine ilişkin bir örnek:

```csharp
ITextStyle textStyle = presentation.Slides[0].TextStyle;
textStyle.FontHeight = 14;
textStyle.FontColor.Color = Color.Blue;
textStyle.Alignment = TextAlignment.Center;

headerFooterManager.SetTextStyle(HeaderFooterType.Header, textStyle);
headerFooterManager.SetTextStyle(HeaderFooterType.Footer, textStyle);
```

## Tarih ve Slayt Numarasının Güncellenmesi

Tarihi ve slayt numarasını otomatik olarak güncellemek için aşağıdaki kodu kullanın:

```csharp
headerFooterManager.SetDateTimeVisible(true);
headerFooterManager.SetSlideNumberVisible(true);
```

## Değiştirilen Sunumu Kaydetme

Notlar slaytındaki üst bilgi ve alt bilgi öğelerini özelleştirdikten sonra değiştirilen sunumu bir dosyaya kaydedebilirsiniz:

```csharp
presentation.Save("modified.pptx", SaveFormat.Pptx);
```

## Kaynak Kodunu Tamamlayın

Aspose.Slides for .NET'i kullanarak notlar slaytındaki üstbilgi ve altbilgi öğelerini yönetmek için gereken kaynak kodun tamamını burada bulabilirsiniz:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

class Program
{
    static void Main(string[] args)
    {
        using (Presentation presentation = new Presentation())
        {
            ISlide slide = presentation.Slides.AddEmptySlide();
            INotesSlide notesSlide = slide.NotesSlideManager.NotesSlide;
            INotesHeaderFooterManager headerFooterManager = notesSlide.HeaderFooterManager;

            // Üstbilgi ve altbilgi öğelerini özelleştirme
            headerFooterManager.SetText(HeaderFooterType.Header, "Your header text");
            headerFooterManager.SetText(HeaderFooterType.Footer, "Your footer text");

            ITextStyle textStyle = presentation.Slides[0].TextStyle;
            textStyle.FontHeight = 14;
            textStyle.FontColor.Color = Color.Blue;
            textStyle.Alignment = TextAlignment.Center;

            headerFooterManager.SetTextStyle(HeaderFooterType.Header, textStyle);
            headerFooterManager.SetTextStyle(HeaderFooterType.Footer, textStyle);

            headerFooterManager.SetDateTimeVisible(true);
            headerFooterManager.SetSlideNumberVisible(true);

            // Değiştirilen sunuyu kaydet
            presentation.Save("modified.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Çözüm

Bu kılavuzda, bir sunumun notlar slaytındaki üstbilgi ve altbilgi öğelerini yönetmek için Aspose.Slides for .NET'in nasıl kullanılacağını araştırdık. Not slaytı eklemeyi, üstbilgi ve altbilgi öğelerine erişmeyi, metni değiştirmeyi, stil öğelerini ve tarih ile slayt numaralarını güncellemeyi öğrendiniz. Bu güçlü kitaplık, kusursuz özelleştirmeye olanak tanıyarak genel sunum deneyimini geliştirir.

## SSS'ler

### Notlar slaytındaki üstbilgi ve altbilgi öğelerine nasıl erişebilirim?

 Üstbilgi ve altbilgi öğelerine erişmek için`INotesHeaderFooterManager` Aspose.Slides for .NET tarafından sağlanan arayüz.

### Üstbilgi ve altbilgi metnine stil uygulayabilir miyim?

 Evet, üst bilgi ve alt bilgi metnine stil uygulayabilirsiniz.`SetTextStyle` yöntem. Yazı tipi boyutunu, rengini, hizalamasını ve diğer özelliklerini özelleştirebilirsiniz.

### Tarihi ve slayt numarasını otomatik olarak nasıl güncellerim?

 Şunu kullanabilirsiniz:`SetDateTimeVisible` Ve`SetSlideNumberVisible` Üstbilgi ve altbilgide tarih ve slayt numarasını otomatik olarak görüntüleme yöntemleri.

### Aspose.Slides for .NET PowerPoint dosyalarıyla uyumlu mu?

Evet, Aspose.Slides for .NET, PowerPoint dosyalarıyla tamamen uyumludur ve sunumları programlı olarak düzenlemenize ve oluşturmanıza olanak tanır.

### Üstbilgi ve altbilgi özelleştirmesine ilişkin kaynak kodunun tamamını nerede bulabilirim?

Kaynak kodu örneğinin tamamını bu kılavuzda bulabilirsiniz. Kod pasajı için "Kaynak Kodunun Tamamı" bölümüne bakın.