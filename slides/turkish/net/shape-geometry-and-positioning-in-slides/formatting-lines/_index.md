---
title: Aspose.Slides .NET Eğitimi ile Sunum Satırlarını Formatlama
linktitle: Aspose.Slides kullanarak Sunum Slaytlarındaki Satırları Formatlama
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET ile sunum slaytlarınızı geliştirin. Çizgileri zahmetsizce biçimlendirmek için adım adım kılavuzumuzu izleyin. Ücretsiz deneme sürümünü şimdi indirin!
weight: 10
url: /tr/net/shape-geometry-and-positioning-in-slides/formatting-lines/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Etkili iletişim için görsel olarak çekici sunum slaytları oluşturmak çok önemlidir. Aspose.Slides for .NET, sunum öğelerini programlı olarak değiştirmek ve biçimlendirmek için güçlü bir çözüm sunar. Bu eğitimde Aspose.Slides for .NET kullanarak sunum slaytlarındaki satırları biçimlendirmeye odaklanacağız.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Slides for .NET Library: Kütüphaneyi şu adresten indirip yükleyin:[Aspose.Slides .NET Belgeleri](https://reference.aspose.com/slides/net/).
- Geliştirme Ortamı: Visual Studio veya başka bir uyumlu IDE ile bir .NET geliştirme ortamı kurun.
## Ad Alanlarını İçe Aktar
Aspose.Slides'ın işlevselliğinden yararlanmak için C# kod dosyanıza gerekli ad alanlarını ekleyin:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## 1. Adım: Projenizi Kurun
Tercih ettiğiniz geliştirme ortamında yeni bir proje oluşturun ve Aspose.Slides kütüphanesine bir referans ekleyin.
## Adım 2: Sunumu Başlatın
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
```
## 3. Adım: İlk Slayta Erişin
```csharp
ISlide sld = pres.Slides[0];
```
## Adım 4: Dikdörtgen Otomatik Şekil Ekle
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 75);
```
## Adım 5: Dikdörtgen Dolgu Rengini Ayarlayın
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.White;
```
## Adım 6: Satıra Formatlama Uygulayın
```csharp
shp.LineFormat.Style = LineStyle.ThickThin;
shp.LineFormat.Width = 7;
shp.LineFormat.DashStyle = LineDashStyle.Dash;
```
## Adım 7: Çizgi Rengini Ayarlayın
```csharp
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Blue;
```
## Adım 8: Sunuyu Kaydetme
```csharp
pres.Save(dataDir + "RectShpLn_out.pptx", SaveFormat.Pptx);
}
```
Artık Aspose.Slides for .NET'i kullanarak bir sunum slaytındaki satırları başarıyla formatladınız!
## Çözüm
Aspose.Slides for .NET, sunum öğelerini programlı olarak değiştirme sürecini basitleştirir. Bu adım adım kılavuzu izleyerek slaytlarınızın görsel çekiciliğini zahmetsizce artırabilirsiniz.
## Sıkça Sorulan Sorular
### S1: Aspose.Slides for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
Evet, Aspose.Slides, Java ve Python dahil çeşitli programlama dillerini destekler.
### S2: Aspose.Slides'ın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Aspose.Slides Ücretsiz Deneme](https://releases.aspose.com/).
### S3: Nerede ek destek bulabilirim veya soru sorabilirim?
 Ziyaret edin[Aspose.Slides Forumu](https://forum.aspose.com/c/slides/11) destek ve topluluk yardımı için.
### S4: Aspose.Slides için geçici lisansı nasıl edinebilirim?
 adresinden geçici lisans alabilirsiniz.[Aspose.Slides Geçici Lisansı](https://purchase.aspose.com/temporary-license/).
### S5: Aspose.Slides for .NET'i nereden satın alabilirim?
 Ürünü adresinden satın alabilirsiniz.[Aspose.Slides Satın Alma](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
