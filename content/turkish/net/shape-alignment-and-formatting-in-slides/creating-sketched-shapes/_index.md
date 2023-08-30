---
title: Aspose.Slides ile Sunum Slaytlarında Taslak Şekiller Oluşturma
linktitle: Aspose.Slides ile Sunum Slaytlarında Taslak Şekiller Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak taslak şekillerle büyüleyici sunum slaytları oluşturmayı öğrenin. Slaytlarınıza kişiselleştirilmiş ve yaratıcı öğeler eklemek için kaynak kodunun tamamını içeren bu adım adım kılavuzu izleyin.
type: docs
weight: 13
url: /tr/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

## Sunum Slaytlarında Taslak Şekiller Oluşturmaya Giriş

Sunum slaytları, bilgiyi görsel olarak aktarmak için güçlü bir araçtır. Bazen sunumlarınızı daha ilgi çekici ve yaratıcı kılmak için taslak şekiller ekleyerek slaytlarınıza kişisel bir dokunuş eklemek isteyebilirsiniz. Bu adım adım kılavuzda Aspose.Slides for .NET kitaplığını kullanarak bunu nasıl başaracağımızı keşfedeceğiz. Bu eğitimin sonunda, dikkat çekici eskiz şekilleriyle sunum slaytları oluşturabileceksiniz. Hadi dalalım!

## Projenin Kurulumu

 Başlamadan önce makinenizde .NET geliştirme ortamının kurulu olduğundan emin olun. Aspose.Slides'ın en son sürümünü web sitesinden indirebilirsiniz.[Burada](https://releases.aspose.com/slides/net/). İndirdikten sonra kütüphaneyi projenize yükleyin.

## Yeni Bir Sunu Oluşturma

Aspose.Slides'ı kullanarak yeni bir sunum oluşturarak başlayalım. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Slides;

// Yeni bir sunu oluşturma
Presentation presentation = new Presentation();
```

## Çizilmiş Şekiller Ekleme

Slaytlarınıza taslak şekiller eklemek için Aspose.Slides'ta bulunan serbest biçimli şekilleri kullanabilirsiniz. Bu şekiller elle çizilmiş eskizlere benzeyecek şekilde özelleştirilebilir. Slayta çizilmiş bir dikdörtgenin nasıl ekleneceğine dair bir örnek:

```csharp
// İlk slayda erişin
ISlide slide = presentation.Slides[0];

// Çizilen dikdörtgenin noktalarını tanımlayın
PointF[] points = new PointF[]
{
    new PointF(100, 100),
    new PointF(200, 100),
    new PointF(200, 200),
    new PointF(100, 200)
};

// Slayda serbest biçimli bir şekil ekleme
IFreeformShape freeformShape = slide.Shapes.AddFreeform(ShapeType.Rectangle, points);

// Çizilen şeklin görünümünü özelleştirme
freeformShape.LineFormat.Style = LineStyle.Single;
freeformShape.LineFormat.Width = 2;
freeformShape.FillFormat.FillType = FillType.Solid;
freeformShape.FillFormat.SolidFillColor.Color = Color.LightGray;
```

## Taslak Şekilleri Özelleştirme

Çizilen şekillerin renklerini, çizgi stillerini ve diğer özelliklerini ayarlayarak daha da özelleştirebilirsiniz. İstediğiniz elle çizilmiş efekti elde etmek için farklı ayarlarla denemeler yapın.

## Sunumu Kaydetme ve Dışa Aktarma

Sununuza taslak şekiller ekledikten sonra onu kaydedebilir ve PPTX veya PDF gibi çeşitli formatlara aktarabilirsiniz. Bunu nasıl yapabileceğiniz aşağıda açıklanmıştır:

```csharp
// Sunuyu bir dosyaya kaydetme
presentation.Save("SketchedShapesPresentation.pptx", SaveFormat.Pptx);
```

## Çözüm

Bu eğitimde Aspose.Slides for .NET kullanarak eskiz şekilleriyle sunum slaytlarının nasıl oluşturulacağını araştırdık. Slaytlarınıza eskiz şekilleri ekleyerek sunumlarınıza yaratıcı ve kişiselleştirilmiş bir dokunuş katabilir, onları izleyicileriniz için daha ilgi çekici hale getirebilirsiniz. Kalıcı bir etki bırakan görsel olarak çekici slaytlar oluşturmak için farklı şekiller ve özelleştirme seçeneklerini denemekten çekinmeyin.

## SSS'ler

### Aspose.Slides for .NET'i nasıl indirebilirim?

 Aspose.Slides for .NET'in en son sürümünü sürümler sayfasından indirebilirsiniz.[Burada](https://releases.aspose.com/slides/net/).

### Çizilen şekillerin görünümünü özelleştirebilir miyim?

Evet, Aspose.Slides'ı kullanarak renklerini, çizgi stillerini ve diğer özelliklerini ayarlayarak çizilmiş şekillerin görünümünü özelleştirebilirsiniz.

### Aspose.Slides hem yeni başlayanlar hem de deneyimli geliştiriciler için uygun mu?

Evet, Aspose.Slides hem yeni başlayanlar hem de deneyimli geliştiriciler için uygun, kullanıcı dostu bir API sağlar. Başlamanıza yardımcı olacak kapsamlı belgeler sunar.

### Taslak şekiller içeren sunumumu PDF'ye aktarabilir miyim?

Kesinlikle! Aspose.Slides'ın sağladığı dışa aktarma seçeneklerini kullanarak sunumunuzu taslak şekillerle birlikte PDF dahil çeşitli formatlara aktarabilirsiniz.

### Daireler veya çizgiler gibi diğer çizim şekillerini nasıl ekleyebilirim?

 Noktaları ve şekil türünü değiştirerek, daire veya çizgi gibi diğer çizilmiş şekil türlerini ekleyebilirsiniz.`AddFreeform` yöntem. İstediğiniz şekilleri oluşturmak için farklı nokta konfigürasyonlarını deneyin.