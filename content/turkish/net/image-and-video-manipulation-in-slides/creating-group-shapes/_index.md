---
title: Aspose.Slides - .NET'te Grup Şekilleri Oluşturma
linktitle: Aspose.Slides ile Sunum Slaytlarında Grup Şekilleri Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET ile PowerPoint'te grup şekilleri oluşturmayı öğrenin. Görsel olarak çekici sunumlar için adım adım kılavuzumuzu izleyin.
type: docs
weight: 11
url: /tr/net/image-and-video-manipulation-in-slides/creating-group-shapes/
---
## giriiş
Sunum slaytlarınızın görsel çekiciliğini artırmak ve içeriği daha verimli bir şekilde düzenlemek istiyorsanız grup şekillerini birleştirmek güçlü bir çözümdür. Aspose.Slides for .NET, PowerPoint sunumlarınızda grup şekilleri oluşturmanın ve değiştirmenin kusursuz bir yolunu sunar. Bu eğitimde Aspose.Slides'ı kullanarak grup şekilleri oluşturma sürecini takip edilmesi kolay adımlara ayırarak anlatacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdakilere sahip olduğunuzdan emin olun:
-  Aspose.Slides for .NET: Aspose.Slides kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[İnternet sitesi](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: Visual Studio gibi .NET uyumlu bir IDE ile bir çalışma ortamı kurun.
- Temel C# Bilgisi: C# programlama dilinin temellerine aşina olun.
## Ad Alanlarını İçe Aktar
C# projenizde gerekli ad alanlarını içe aktararak başlayın:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Adım 1: Sunum Sınıfını Başlatın

 Bir örneğini oluşturun`Presentation` class'ı seçin ve belgelerinizin saklandığı dizini belirtin:

```csharp
string dataDir = "Your Documents Directory";
using (Presentation pres = new Presentation())
{
    // Bu kullanım bloğu içerisinde aşağıdaki adımlarla devam edin
}
```

## Adım 2: İlk Slayta Erişin

Sunumdan ilk slaydı alın:

```csharp
ISlide sld = pres.Slides[0];
```

## 3. Adım: Şekil Koleksiyonuna Erişim

Slayttaki şekil koleksiyonuna erişin:

```csharp
IShapeCollection slideShapes = sld.Shapes;
```

## Adım 4: Grup Şekli Ekleme

Slayta bir grup şekli ekleyin:

```csharp
IGroupShape groupShape = slideShapes.AddGroupShape();
```

## Adım 5: Grup Şeklinin İçine Şekiller Ekleme

Grup şeklini ayrı şekillerle doldurun:

```csharp
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 100, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 300, 300, 100, 100);
groupShape.Shapes.AddAutoShape(ShapeType.Rectangle, 500, 300, 100, 100);
```

## Adım 6: Grup Şekil Çerçevesi Ekleme

Tüm grup şeklinin çerçevesini tanımlayın:

```csharp
groupShape.Frame = new ShapeFrame(100, 300, 500, 40, NullableBool.False, NullableBool.False, 0);
```

## Adım 7: Sunuyu Kaydet

Değiştirilen sunumu belirttiğiniz dizine kaydedin:

```csharp
pres.Save(dataDir + "GroupShape_out.pptx", SaveFormat.Pptx);
```

Aspose.Slides'ı kullanarak sunum slaytlarınızda başarıyla grup şekilleri oluşturmak için C# uygulamanızda bu adımları tekrarlayın.

## Çözüm
Bu eğitimde Aspose.Slides for .NET ile grup şekilleri oluşturma sürecini inceledik. Bu adımları izleyerek PowerPoint sunumlarınızın görsel çekiciliğini ve organizasyonunu geliştirebilirsiniz.
## Sıkça Sorulan Sorular
### Aspose.Slides .NET'in en son sürümüyle uyumlu mu?
 Evet, Aspose.Slides en son .NET sürümlerini destekleyecek şekilde düzenli olarak güncellenmektedir. Kontrol edin[dokümantasyon](https://reference.aspose.com/slides/net/) uyumluluk ayrıntıları için.
### Satın almadan önce Aspose.Slides'ı deneyebilir miyim?
 Kesinlikle! Ücretsiz deneme sürümünü indirebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Slides ile ilgili sorgular için nereden destek bulabilirim?
 Aspose.Slides'ı ziyaret edin[forum](https://forum.aspose.com/c/slides/11) topluluk desteği ve tartışmalar için.
### Aspose.Slides için geçici lisansı nasıl edinebilirim?
 Geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides'ın tam lisansını nereden satın alabilirim?
 Lisansı şuradan satın alabilirsiniz:[satın alma sayfası](https://purchase.aspose.com/buy).
