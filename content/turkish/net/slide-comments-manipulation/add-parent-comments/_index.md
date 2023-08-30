---
title: Aspose.Slides'ı kullanarak Slayta Ana Yorumları Ekleme
linktitle: Slayta Ebeveyn Yorumları Ekle
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak ana yorumlar ekleyerek sunumlarınızı etkileşimli öğelerle nasıl geliştireceğinizi öğrenin. Slaytlarınızda etkileşimi ve netliği artırın.
type: docs
weight: 12
url: /tr/net/slide-comments-manipulation/add-parent-comments/
---

Sunumlarınızı etkileşimli öğelerle geliştirmek istiyorsanız Aspose.Slides API'sini kullanarak slaytlarınıza ebeveyn yorumları eklemek oyunun kurallarını değiştirebilir. Bu güçlü özellik, slaytlarınıza ek bağlam ve bilgiler sunarak sunumlarınızı daha ilgi çekici ve bilgilendirici hale getirmenize olanak tanır.

## Ebeveyn Yorumlarının Önemini Anlamak

Ana yorumlar, slayttaki içerik hakkında daha derin açıklamalar sağlayan değerli ek açıklamalar görevi görür. Ebeveyn yorumlarını kullanarak hedef kitlenizin sunulan bilgiyi tam olarak kavramasını sağlayabilirsiniz. Bu, özellikle ayrıntılı açıklama gerektiren karmaşık görselleriniz veya karmaşık verileriniz olduğunda kullanışlıdır.

## Aspose.Slides for .NET'e Başlarken

Uygulama ayrıntılarına girmeden önce Aspose.Slides for .NET'in kurulu olduğundan emin olun. En son sürümü Aspose web sitesinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/net/).

## Adım adım rehber

### 1. Sunumun Başlatılması

Başlamak için tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun. Aspose.Slides kütüphanesine referanslar ekleyin. Yeni bir sunum nesnesini başlatarak başlayın:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;

// ...

Presentation presentation = new Presentation();
```

### 2. Slayt ve İçerik Ekleme

Ardından, gerekli slaytları sununuza ekleyin ve açıklama eklemek istediğiniz içeriği ebeveyn yorumlarıyla birlikte ekleyin:

```csharp
ISlide slide = presentation.Slides.AddEmptySlide(presentation.SlideSize);
ITextFrame textFrame = slide.Shapes.AddTextFrame("Title");
textFrame.Text = "This is the slide content that needs annotation.";
```

### 3. Ebeveyn Yorumlarını Ekleme

Şimdi heyecan verici kısım geliyor: slaydınıza ebeveyn yorumları ekleme:

```csharp
IParentComment comment = slide.ParentComments.AddParentComment();
comment.Text = "This comment provides additional context for the slide content.";
```

### 4. Sunumun Kaydedilmesi

Ana yorumları ekledikten sonra değişiklikleri görmek için sunuyu kaydedin:

```csharp
presentation.Save("output.pptx", SaveFormat.Pptx);
```

## SSS

### Eklendikten sonra ana yorumlara nasıl erişebilirim?

Ebeveyn yorumlarına erişmek için aşağıdaki kodu kullanabilirsiniz:

```csharp
foreach (IParentComment parentComment in slide.ParentComments)
{
    string commentText = parentComment.Text;
    // Yorumu gerektiği gibi işleyin
}
```

### Ana yorumların görünümünü özelleştirebilir miyim?

Evet, yazı tipi, renk ve konumlandırma dahil olmak üzere ana yorumların görünümünü özelleştirebilirsiniz. Özelleştirme seçenekleri hakkında daha fazla ayrıntı için Aspose.Slides belgelerine bakın.

### Ebeveyn yorumlarına yanıt eklemek mümkün müdür?

Aspose.Slides'ın mevcut sürümünden itibaren yalnızca ana yorumlar eklenebilmektedir. Yorumlara verilen yanıtlar desteklenmiyor.

## Çözüm

Aspose.Slides for .NET kullanarak ebeveyn yorumlarını slaytlarınıza eklemek, sunumlarınızın kalitesini ve etkisini artırmanın harika bir yoludur. Bilgilendirici ek açıklamalar sağlayarak hedef kitlenizin içeriği net bir şekilde kavramasını sağlarsınız. Peki neden bekleyelim? Bu özellikten bugün yararlanmaya başlayın ve hedef kitlenizi daha önce hiç olmadığı gibi büyüleyin!