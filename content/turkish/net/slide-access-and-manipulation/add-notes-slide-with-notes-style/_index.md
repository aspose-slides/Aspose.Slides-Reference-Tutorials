---
title: Şık Not Biçimlendirmesiyle Not Slaydı Ekle
linktitle: Şık Not Biçimlendirmesiyle Not Slaydı Ekle
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak şık not formatlamalarıyla PowerPoint sunumlarınızı nasıl geliştireceğinizi öğrenin. Bu adım adım kılavuz, not slaytı eklemeyi, çekici biçimlendirme uygulamayı ve daha fazlasını kapsar.
type: docs
weight: 14
url: /tr/net/slide-access-and-manipulation/add-notes-slide-with-notes-style/
---

## Aspose.Slides for .NET'e giriş:

Aspose.Slides for .NET, geliştiricilerin .NET uygulamalarında PowerPoint sunumlarıyla çalışmasına olanak tanıyan kapsamlı bir kitaplıktır. Slaytlar, şekiller, metinler, resimler ve daha fazlasını oluşturma, okuma, yazma ve değiştirme dahil çok çeşitli özellikler sunar. Bu eğitimde not slaytı eklemeye ve notlara şık biçimlendirme uygulamaya odaklanacağız.

## Önkoşullar:

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio veya başka herhangi bir .NET geliştirme ortamı.
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Projenin Kurulumu:

1. Tercih ettiğiniz geliştirme ortamında yeni bir .NET projesi oluşturun.
2. Projenize Aspose.Slides for .NET kitaplığına bir referans ekleyin.

## Sunum Oluşturma:

Aspose.Slides for .NET'i kullanarak yeni bir PowerPoint sunumu oluşturarak başlayalım. Daha sonra bu sunuma bir notlar slaytı ekleyeceğiz.

```csharp
using Aspose.Slides;
using System;

namespace NotesSlideTutorial
{
    class Program
    {
        static void Main(string[] args)
        {
            // Yeni bir sunu oluşturma
            Presentation presentation = new Presentation();

            // Sunuyu kaydet
            presentation.Save("MyPresentation.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Not Slaydı Ekleme:

Daha sonra sunuma bir notlar slaytı ekleyeceğiz. Notlar slaytı genellikle ana slaydın içeriğiyle ilgili ek bilgiler veya konuşmacı notları içerir.

```csharp
// İlk slayttan sonra notlar slaytı ekleme
NotesSlide notesSlide = presentation.Slides[0].NotesSlideManager.AddNotesSlide();

// Notlar slaytına içerik ekleme
notesSlide.NotesTextFrame.Text = "These are the speaker notes for the first slide.";
```

## Notlar için Şık Biçimlendirme:

Notları görsel olarak daha çekici hale getirmek için Aspose.Slides for .NET'i kullanarak şık formatlama uygulayabiliriz. Buna yazı tipinin, renginin, boyutunun ve diğer biçimlendirme seçeneklerinin değiştirilmesi de dahildir.

```csharp
// Notlar slaytının metin çerçevesine erişme
ITextFrame notesTextFrame = notesSlide.NotesTextFrame;

// Metne biçimlendirme uygulama
IParagraph paragraph = notesTextFrame.Paragraphs[0];
IPortion portion = paragraph.Portions[0];

// Yazı tipini, yazı tipi boyutunu ve rengini değiştirme
portion.PortionFormat.LatinFont = new FontData("Arial");
portion.PortionFormat.FontHeight = 14;
portion.PortionFormat.FillFormat.SolidFillColor.Color = Color.DarkBlue;
```

## Çözüm:

Bu eğitimde, bir PowerPoint sunumuna şık biçimlendirmeli bir not slaydı eklemek için Aspose.Slides for .NET'i nasıl kullanacağımızı öğrendik. Sunum oluşturmayı, not slaytı eklemeyi ve not içeriğine biçimlendirme uygulamayı anlattık. Aspose.Slides for .NET, geliştiricilere PowerPoint sunumlarını programlı olarak geliştirmeleri için güçlü bir araç seti sağlar.

## SSS'ler

### Notlar slaytındaki notların konumunu nasıl değiştirebilirim?

 Notların metin çerçevesinin konumunu aşağıdaki düğmeyi kullanarak ayarlayabilirsiniz:`notesSlide.NotesTextFrame.X` Ve`notesSlide.NotesTextFrame.Y` özellikler.

### Notlar slaytına resim ekleyebilir miyim?

 Evet, notlar slaytına resim ekleyebilirsiniz.`notesSlide.Shapes.AddPicture()` yöntem.

### Aspose.Slides for .NET farklı PowerPoint formatlarıyla uyumlu mu?

Evet, Aspose.Slides for .NET, PPTX, PPT ve daha fazlası dahil olmak üzere çeşitli PowerPoint formatlarını destekler.

### Not metninin belirli bölümlerine biçimlendirmeyi nasıl uygulayabilirim?

 Paragraf içindeki kısımlara erişebilir ve biçimlendirmeyi aşağıdaki düğmeyi kullanarak uygulayabilirsiniz:`portion.PortionFormat` mülk.

### Aspose.Slides for .NET hakkında daha fazla bilgiyi nerede bulabilirim?

 Ayrıntılı belgeler ve örnekler için şu adresi ziyaret edebilirsiniz:[Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/).