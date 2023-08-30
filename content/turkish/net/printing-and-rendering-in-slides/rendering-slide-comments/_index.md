---
title: Aspose.Slides'ta Slayt Yorumlarını Oluşturma
linktitle: Aspose.Slides'ta Slayt Yorumlarını Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint sunumlarında slayt yorumlarını nasıl oluşturacağınızı öğrenin. Bu adım adım kılavuz, yorumlara programlı olarak erişmek, bunları özelleştirmek ve görüntülemek için kaynak kodu örnekleri sağlar.
type: docs
weight: 12
url: /tr/net/printing-and-rendering-in-slides/rendering-slide-comments/
---

## giriiş

Slayt yorumları, bir sunumdaki belirli slaytlarla ilgili değerli bilgiler, açıklamalar ve tartışmalar sunar. Bu yorumların programlı olarak işlenmesi, inceleme ve işbirliği sürecini kolaylaştırabilir. Aspose.Slides for .NET, slayt yorumlarını yönetmek ve görüntülemek için kapsamlı bir API seti sağlayarak bu görevi basitleştirir.

## Önkoşullar

Uygulamaya geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Makinenizde Visual Studio yüklü.
- C# ve .NET geliştirmenin temel anlayışı.
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Projenin Kurulumu

1. Visual Studio'da yeni bir C# projesi oluşturun.

2. Projenize Aspose.Slides for .NET kitaplığına bir referans ekleyin.

## Sunum Yükleme

Başlamak için slayt yorumlarını içeren bir PowerPoint sunusu yükleyelim:

```csharp
using Aspose.Slides;

// Sunuyu yükle
using var presentation = new Presentation("presentation.pptx");
```

## Slayt Yorumlarına Erişim

Şimdi sunumdaki slaytları tekrarlayalım ve her slaytla ilişkili yorumlara erişelim:

```csharp
// Slaytlar arasında yineleme
foreach (var slide in presentation.Slides)
{
    // Slayt yorumlarına erişme
    var comments = slide.Comments;
    foreach (var comment in comments)
    {
        // Yorum özelliklerine erişme
        var author = comment.Author;
        var text = comment.Text;
        
        // Yorumu gerektiği gibi işleyin
    }
}
```

## Slaytlarda Yorumları Oluşturma

Şimdi slaytlardaki yorumları işleyelim. Yorumları her slaytın altına metin kutusu olarak ekleyeceğiz:

```csharp
foreach (var slide in presentation.Slides)
{
    // Slayt yorumlarına erişme
    var comments = slide.Comments;
    foreach (var comment in comments)
    {
        // Yorum için bir metin kutusu oluşturun
        var textBox = slide.Shapes.AddTextFrame("");
        var textFrame = textBox.TextFrame;
        
        // Yorum özelliklerini metin olarak ayarla
        textFrame.Text = $"{comment.Author}: {comment.Text}";
        
        // Metin kutusunu slaytın altına yerleştirin
        textBox.Left = slide.SlideSize.Size.Width / 2;
        textBox.Top = slide.SlideSize.Size.Height + 20;
        
        // Gerekirse metin kutusu görünümünü özelleştirin
        
        // Yorumu gerektiği gibi işleyin
    }
}
```

## Yorum Oluşturmayı Özelleştirme

Oluşturulan yorumların yazı tipi boyutu, rengi ve konumu gibi görünümünü daha da özelleştirebilirsiniz. Bu, yorumları sununuzun stiliyle eşleştirmenize olanak tanır:

```csharp
// Metin kutusu görünümünü özelleştirme
var fontHeight = 12;
var fontColor = Color.Black;
var margin = 20;

foreach (var slide in presentation.Slides)
{
    // ...
    foreach (var comment in comments)
    {
        // ...
        
        // Metin kutusu görünümünü özelleştirme
        textFrame.Paragraphs[0].Portions[0].PortionFormat.FontHeight = fontHeight;
        textFrame.Paragraphs[0].Portions[0].PortionFormat.FillFormat.SolidFillColor.Color = fontColor;
        
        // Metin kutusu konumunu ayarla
        textBox.Top = slide.SlideSize.Size.Height - margin;
        margin += 30; // Bir sonraki yorumun kenar boşluğunu artırın
    }
}
```

## İşlenen Sunumu Kaydetme

Slaytlardaki yorumları oluşturduktan sonra değiştirilen sunuyu kaydedebilirsiniz:

```csharp
// Değiştirilen sunuyu kaydet
presentation.Save("rendered_presentation.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu kılavuzda, Aspose.Slides for .NET kullanarak PowerPoint sunumlarında slayt yorumlarının nasıl oluşturulacağını araştırdık. Yukarıda özetlenen adımları izleyerek yorumlara programlı bir şekilde erişebilir ve bunları görüntüleyebilirsiniz, böylece slayt desteleriniz içindeki işbirliğini ve iletişimi geliştirebilirsiniz.

## SSS'ler

### Aspose.Slides for .NET'i nasıl kurabilirim?

 Aspose.Slides for .NET kütüphanesini şu adresten indirebilirsiniz:[bu bağlantı](https://releases.aspose.com/slides/net/). İndirdikten sonra Visual Studio projenize referans olarak ekleyebilirsiniz.

### Oluşturulan yorumların görünümünü özelleştirebilir miyim?

Evet, yazı tipi boyutu, rengi ve konumu dahil olmak üzere oluşturulan yorumların görünümünü özelleştirebilirsiniz. Bu, yorumları sunumunuzun stiliyle eşleştirmenize olanak tanır.

### Bireysel yorum özelliklerine nasıl erişebilirim?

 Yazar ve metin gibi yorum özelliklerine,`Author` Ve`Text` yorum nesnesinin özellikleri.

### Yorumları metin kutuları yerine belirtme çizgileri olarak görüntüleyebilir miyim?

Evet, özel şekiller oluşturup bunlara metin ekleyerek yorumları belirtme çizgileri olarak oluşturabilirsiniz. Açıklamaların konumunu ve görünümünü buna göre ayarlamanız gerekecektir.

### Aspose.Slides for .NET PowerPoint ile ilgili diğer görevler için uygun mu?

Kesinlikle! Aspose.Slides for .NET, PowerPoint sunumlarıyla çalışmak için çok çeşitli API'ler sağlar. Sunumların çeşitli yönlerini programlı olarak oluşturabilir, değiştirebilir, dönüştürebilir ve yönetebilirsiniz.