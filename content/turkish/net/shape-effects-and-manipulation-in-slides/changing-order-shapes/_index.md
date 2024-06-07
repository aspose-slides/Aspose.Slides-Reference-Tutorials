---
title: Aspose.Slides for .NET ile Sunum Slaytlarını Yeniden Şekillendirme
linktitle: Aspose.Slides Kullanarak Sunum Slaytlarındaki Şekillerin Sırasını Değiştirme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak sunum slaytlarını nasıl yeniden şekillendireceğinizi öğrenin. Şekilleri yeniden sıralamak ve görsel çekiciliği artırmak için bu adım adım kılavuzu izleyin.
type: docs
weight: 26
url: /tr/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---
## giriiş
Görsel olarak çekici sunum slaytları oluşturmak, etkili iletişimin çok önemli bir yönüdür. Aspose.Slides for .NET, geniş bir işlevsellik yelpazesi sunarak geliştiricilerin slaytları programlı olarak değiştirmesine olanak tanır. Bu eğitimde Aspose.Slides for .NET'i kullanarak sunum slaytlarındaki şekillerin sırasını değiştirme sürecini inceleyeceğiz.
## Önkoşullar
Bu yolculuğa çıkmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Slides for .NET: Aspose.Slides kütüphanesinin .NET projenize entegre olduğundan emin olun. Değilse, adresinden indirebilirsiniz.[sürümler sayfası](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: Visual Studio veya başka herhangi bir .NET geliştirme aracıyla çalışan bir geliştirme ortamı oluşturun.
- Temel C# Anlayışı: C# programlama dilinin temellerine aşina olun.
## Ad Alanlarını İçe Aktar
Aspose.Slides işlevselliğine erişmek için C# projenize gerekli ad alanlarını ekleyin:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 1. Adım: Projenizi Kurun
Visual Studio'da veya tercih ettiğiniz .NET geliştirme ortamında yeni bir proje oluşturun. Projenizde Aspose.Slides for .NET'e başvurulduğundan emin olun.
## 2. Adım: Sunuyu Yükleyin
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## 3. Adım: Slayt ve Şekillere Erişin
```csharp
ISlide slide = presentation.Slides[0];
```
## 4. Adım: Yeni Bir Şekil Ekleyin
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## Adım 5: Şekildeki Metni Değiştirin
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## Adım 6: Başka Bir Şekil Ekleyin
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Adım 7: Şekillerin Sırasını Değiştirin
```csharp
slide.Shapes.Reorder(2, shp3);
```
## Adım 8: Değiştirilen Sunumu Kaydedin
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
Bu, Aspose.Slides for .NET kullanarak sunum slaytlarındaki şekillerin sırasını değiştirmeye yönelik adım adım kılavuzu tamamlıyor.
## Çözüm
Aspose.Slides for .NET, sunum slaytlarını programlı olarak değiştirme görevini basitleştirir. Bu öğreticiyi izleyerek, sunumlarınızın görsel çekiciliğini artırmanıza olanak tanıyacak şekilde şekilleri nasıl yeniden sıralayacağınızı öğrendiniz.
## SSS
### S: Aspose.Slides for .NET'i hem Windows hem de Linux ortamlarında kullanabilir miyim?
C: Evet, Aspose.Slides for .NET hem Windows hem de Linux ortamlarıyla uyumludur.
### S: Aspose.Slides'ı ticari bir projede kullanmak için herhangi bir lisanslama hususu var mı?
 C: Evet, lisanslama ayrıntılarını ve satın alma seçeneklerini şurada bulabilirsiniz:[Aspose.Slides satın alma sayfası](https://purchase.aspose.com/buy).
### S: Aspose.Slides for .NET'in ücretsiz deneme sürümü mevcut mu?
 C: Evet, özellikleri keşfedebilirsiniz.[ücretsiz deneme](https://releases.aspose.com/) Aspose.Slides web sitesinde mevcuttur.
### S: Aspose.Slides for .NET ile ilgili desteği nerede bulabilirim veya soru sorabilirim?
C: Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) destek almak ve toplulukla etkileşime geçmek için.
### S: Aspose.Slides for .NET için nasıl geçici lisans alabilirim?
 C: Bir[geçici lisans](https://purchase.aspose.com/temporary-license/) değerlendirme amaçlı.