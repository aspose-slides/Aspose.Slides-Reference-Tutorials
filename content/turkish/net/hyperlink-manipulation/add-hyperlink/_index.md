---
title: Slayda Köprü Ekleme
linktitle: Slayda Köprü Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak PowerPoint'te slaytlara nasıl köprü ekleyeceğinizi öğrenin. Sunumlarınızı etkileşimli içerikle geliştirin.
type: docs
weight: 12
url: /tr/net/hyperlink-manipulation/add-hyperlink/
---

## Aspose.Slides for .NET'e Giriş

Aspose.Slides for .NET, geliştiricilerin Microsoft Office'e güvenmeden PowerPoint sunumları oluşturmasına, değiştirmesine ve işlemesine olanak tanıyan kapsamlı bir kitaplıktır. Slaytlara köprü eklemek ve bunları yönetmek de dahil olmak üzere çok çeşitli özellikler sunar.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Sisteminizde Visual Studio yüklü.
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://downloads.aspose.com/slides/net).

## Slayttaki Metne Köprü Ekleme

1. Visual Studio'da yeni bir C# projesi oluşturun.
2. Projenize Aspose.Slides DLL dosyasına bir referans ekleyin.
3. Slayttaki bir metne köprü eklemek için aşağıdaki kodu kullanın:

```csharp
using Aspose.Slides;

// Sunuyu yükle
Presentation presentation = new Presentation("presentation.pptx");

// Bir slayta erişme
ISlide slide = presentation.Slides[0];

// Bir metin kutusuna erişme
ITextFrame textFrame = slide.Shapes[0] as ITextFrame;

// Köprü içeren metnin bir bölümünü ekleme
textFrame.Paragraphs[0].Portions[0].Text = "Visit our website!";
textFrame.Paragraphs[0].Portions[0].PortionFormat.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Slayttaki Şekle Köprü Ekleme

1. Yeni bir C# projesi oluşturmak ve Aspose.Slides referansını eklemek için yukarıdaki adımları izleyin.
2. Slayttaki bir şekle köprü eklemek için aşağıdaki kodu kullanın:

```csharp
using Aspose.Slides;

// Sunuyu yükle
Presentation presentation = new Presentation("presentation.pptx");

// Bir slayta erişme
ISlide slide = presentation.Slides[0];

// Bir şekle erişme
IShape shape = slide.Shapes[1];

// Şekle köprü ekleme
shape.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Slayta Köprü Ekleme

1. C# projenizi ayarlamak ve Aspose.Slides kütüphanesine başvurmak için ilk adımları izleyin.
2. Slayta köprü eklemek için aşağıdaki kodu kullanın:

```csharp
using Aspose.Slides;

// Sunuyu yükle
Presentation presentation = new Presentation("presentation.pptx");

// Bir slayta erişme
ISlide slide = presentation.Slides[2];

// Slayta köprü ekleme
slide.HyperlinkClick = new HyperlinkInfo("https://www.example.com", HyperlinkAction.MouseClick);
```

## Harici Köprüler Ekleme

Slaytlarınıza dahili köprülerin yanı sıra harici köprüler de ekleyebilirsiniz. Yukarıdaki yaklaşımın aynısını kullanın ancak harici URL'yi köprü hedefi olarak sağlayın.

## Köprüleri Değiştirme ve Kaldırma

Mevcut bir köprüyü değiştirmek veya kaldırmak için ilgili slayt öğesinin köprü özelliklerine erişebilir ve gerekli değişiklikleri yapabilirsiniz.

## Çözüm

Aspose.Slides for .NET kullanarak slaytlara köprü eklemek, sunumlarınızın etkileşimini büyük ölçüde artırabilecek basit bir işlemdir. İster harici kaynaklara bağlanmak ister slaytlarınızda gezinme oluşturmak isteyin, Aspose.Slides bu görevleri verimli bir şekilde gerçekleştirmek için ihtiyacınız olan araçları sağlar.

## SSS'ler

### Metnin bir kısmından köprüyü nasıl kaldırabilirim?

 Metnin bir bölümünden bir köprüyü kaldırmak için, yalnızca`HyperlinkClick` mülkiyet`null` bu kısım için.

### Metin kutuları dışındaki şekillere köprüler ekleyebilir miyim?

Evet, resimler ve özel şekiller de dahil olmak üzere çeşitli şekillere köprüler ekleyebilirsiniz.`HyperlinkClick` mülk.

### Aspose.Slides farklı PowerPoint formatlarıyla uyumlu mu?

Evet, Aspose.Slides, PPTX, PPT ve daha fazlası dahil olmak üzere çeşitli PowerPoint formatlarını destekler.

### Sunumumdaki köprüleri nasıl test edebilirim?

Köprülerin işlevselliğini test etmek için sunuyu bir PowerPoint görüntüleyicide veya düzenleyicide çalıştırabilirsiniz.

### Aspose.Slides for .NET kütüphanesini nereden indirebilirim?

 Aspose.Slides for .NET kütüphanesini Aspose web sitesinden indirebilirsiniz:[Aspose.Slides for .NET'i indirin](https://releases.aspose.com/slides/net).