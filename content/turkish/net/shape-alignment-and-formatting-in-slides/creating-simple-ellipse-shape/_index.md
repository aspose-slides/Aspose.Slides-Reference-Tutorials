---
title: Aspose.Slides ile Sunum Slaytlarında Basit Elips Şekli Oluşturma
linktitle: Aspose.Slides ile Sunum Slaytlarında Basit Elips Şekli Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak sunum slaytlarında nasıl basit bir elips şekli oluşturacağınızı öğrenin. Bu adım adım kılavuz, elips şekillerinin eklenmesi, özelleştirilmesi ve kaydedilmesi için kaynak kodu ve talimatlar sağlar.
type: docs
weight: 11
url: /tr/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

## Sunum Slaytlarında Basit Elips Şekli Oluşturmaya Giriş

Sunum slaytlarınızı görsel olarak çekici şekiller ekleyerek geliştirmek istiyorsanız Aspose.Slides for .NET bunu başarmak için güçlü bir çözüm sunar. Bu adım adım kılavuzda, Aspose.Slides for .NET'i kullanarak sunum slaytlarınızda basit bir elips şekli oluşturma sürecinde size yol göstereceğiz.

## Önkoşullar

Başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:

- Visual Studio veya başka herhangi bir .NET geliştirme ortamı kurulu.
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).

## Projenizi Kurma

1. Yeni bir Visual Studio projesi oluşturun veya mevcut bir projeyi açın.
2. Projenize Aspose.Slides for .NET kitaplığına bir referans ekleyin.

## Sunum Oluşturma

Başlamak için elips şeklimizi ekleyeceğimiz yeni bir sunum oluşturalım.

```csharp
using Aspose.Slides;

// Yeni bir sunu oluşturma
Presentation presentation = new Presentation();
```

## Elips Şekli Ekleme

Artık sunumumuz hazır olduğuna göre slayta elips şekli ekleyelim.

```csharp
// Sunumun ilk slaydına erişin
ISlide slide = presentation.Slides[0];

// Elips boyutlarını ve konumunu tanımlayın
float x = 100;   // X koordinatı
float y = 100;   // Y koordinatı
float width = 200;  // Genişlik
float height = 100; // Yükseklik

// Elips şeklini slayta ekleme
IAutoShape ellipseShape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, x, y, width, height);
```

## Elipsin Özelleştirilmesi

Çeşitli özellikleri kullanarak elips şeklinin görünümünü özelleştirebilirsiniz.

```csharp
// Elipsin dolgu rengini ayarlayın
ellipseShape.FillFormat.SolidFillColor.Color = Color.Blue;

// Anahat rengini ve genişliğini ayarlama
ellipseShape.LineFormat.FillFormat.SolidFillColor.Color = Color.Red;
ellipseShape.LineFormat.Width = 2;

// Elips'e metin çerçevesi ekleme
ITextFrame textFrame = ellipseShape.TextFrame;
textFrame.Text = "Hello, Aspose.Slides!";
```

## Sunumu Kaydetme

Elips şeklini ekleyip özelleştirdikten sonra sunumu kaydetmenin zamanı geldi.

```csharp
// Sunuyu kaydet
presentation.Save("EllipsePresentation.pptx", SaveFormat.Pptx);
```

## Çözüm

Tebrikler! Aspose.Slides for .NET'i kullanarak sunum slaytlarınızda başarılı bir şekilde basit bir elips şekli oluşturdunuz. Bu kılavuz, projenizi oluşturma, sunum oluşturma, elips şekli ekleme, görünümünü özelleştirme ve son sunumu kaydetme sürecini kapsıyordu.

## SSS'ler

### Elips şeklinin konumunu nasıl değiştirebilirim?

 Değiştirebilirsiniz`x` Ve`y` Slayttaki konumunu ayarlamak için elips şekli eklenirken koordinatlar.

### Elipsin ana hatlarının rengini değiştirebilir miyim?

 Evet, anahat rengini aşağıdaki düğmeyi kullanarak ayarlayabilirsiniz:`LineFormat.FillFormat.SolidFillColor.Color` mülk.

### Elipsin içine metin eklemek mümkün mü?

 Kesinlikle! kullanarak elips şekline metin ekleyebilirsiniz.`TextFrame.Text` mülk.

### Aspose.Slides for .NET'i kullanarak başka hangi şekilleri oluşturabilirim?

Aspose.Slides for .NET dikdörtgenler, çizgiler, oklar ve daha fazlası dahil olmak üzere çeşitli şekilleri destekler.

### Aspose.Slides for .NET hakkında daha fazla bilgiyi nerede bulabilirim?

 Ayrıntılı belgeler ve örnekler için bkz.[Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/).