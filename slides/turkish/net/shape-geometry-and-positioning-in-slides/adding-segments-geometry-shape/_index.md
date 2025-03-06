---
title: Görsellerde Uzmanlaşma - .NET'te Aspose.Slides ile Segmentler Ekleme
linktitle: Aspose.Slides ile Sunumda Geometri Şekline Segment Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides ile .NET uygulamalarınızı nasıl geliştireceğinizi öğrenin. Bu eğitim, büyüleyici sunumlar için geometri şekillerine segmentler ekleme konusunda size yol gösterir.
weight: 13
url: /tr/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
.NET geliştirme dünyasında görsel olarak çekici sunumlar oluşturmak ortak bir gereksinimdir. Aspose.Slides for .NET, güçlü sunum oluşturma yeteneklerinin .NET uygulamalarınıza kusursuz entegrasyonunu kolaylaştıran güçlü bir kitaplıktır. Bu eğitim, sunum tasarımının belirli bir yönüne, yani geometri şekillerine bölümler eklemeye odaklanmaktadır.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- Temel C# programlama dili bilgisi.
- Makinenizde Visual Studio yüklü.
- Aspose.Slides for .NET kütüphanesini indirip projenizde referans olarak kullanabilirsiniz.
## Ad Alanlarını İçe Aktar
Aspose.Slides işlevlerine erişmek için C# kodunuzda gerekli ad alanlarını içe aktardığınızdan emin olun. Kodunuza aşağıdaki satırları ekleyin:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Şimdi örneği birden çok adıma ayıralım.
## 1. Adım: Projenizi Kurun
Visual Studio'da yeni bir C# projesi oluşturarak başlayın. Projenizde Aspose.Slides kütüphanesinin referans alındığından emin olun.
## Adım 2: Bir Sunu Oluşturun
Aspose.Slides kütüphanesini kullanarak yeni bir sunum nesnesi başlatın. Bu, geometri şekliniz için tuval görevi görecektir.
```csharp
using (Presentation pres = new Presentation())
{
    // Sunum oluşturmaya yönelik kodunuz buraya gelecek
}
```
## Adım 3: Geometri Şekli Ekleme
Sunumun içinde bir geometri şekli oluşturun. Örneğin ilk slayda bir dikdörtgen ekleyelim.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## Adım 4: Geometri Yolunu Alın
Segmentlerini değiştirmek için oluşturulan şeklin geometri yolunu alın.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## 5. Adım: Segmentleri Ekleyin
Geometri yoluna parçalar (çizgiler) ekleyin. Bu örnekte yola iki satır eklenmiştir.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## Adım 6: Düzenlenen Geometri Yolunu Atayın
Değişiklikleri uygulamak için değiştirilen geometri yolunu tekrar şekle atayın.
```csharp
shape.SetGeometryPath(geometryPath);
```
## Adım 7: Sunuyu Kaydet
Değiştirilen sunumu istediğiniz bir konuma kaydedin.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Bu adımlarla Aspose.Slides for .NET kullanarak bir sunumdaki geometri şekline başarılı bir şekilde segmentler eklediniz.
## Çözüm
Aspose.Slides for .NET, geliştiricilerin uygulamalarını gelişmiş sunum oluşturma yetenekleriyle geliştirmelerine olanak tanır. Geometri şekillerine segmentler eklemek, sunumlarınızın görsel öğelerini özelleştirmek için bir araç sağlar.
### Sıkça Sorulan Sorular
### Aspose.Slides'ı kullanarak farklı türde şekiller ekleyebilir miyim?
Evet, Aspose.Slides dikdörtgenler, daireler ve özel geometri şekilleri dahil olmak üzere çeşitli şekil türlerini destekler.
### Aspose.Slides'ı projemde kullanmak için lisans gerekli mi?
Evet, geçerli bir lisansa ihtiyaç var. Test amacıyla geçici bir lisans alabilir veya üretim için tam bir lisans satın alabilirsiniz.
### Aspose.Slides ile ilgili sorgular için nasıl destek alabilirim?
 Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) topluluk desteği ve tartışmalar için.
### Aspose.Slides için başka eğitimler var mı?
 Keşfedin[dokümantasyon](https://reference.aspose.com/slides/net/) Kapsamlı kılavuzlar ve örnekler için.
### Satın almadan önce Aspose.Slides'ı ücretsiz deneyebilir miyim?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
