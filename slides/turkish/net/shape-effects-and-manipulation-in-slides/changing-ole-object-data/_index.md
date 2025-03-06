---
title: Aspose.Slides ile Sunumda OLE Nesne Verilerini Değiştirme
linktitle: Aspose.Slides ile Sunumda OLE Nesne Verilerini Değiştirme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: OLE nesne verilerini zahmetsizce değiştirme konusunda Aspose.Slides for .NET'in gücünü keşfedin. Sunumlarınızı dinamik içerikle geliştirin.
weight: 25
url: /tr/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Dinamik ve etkileşimli PowerPoint sunumları oluşturmak günümüzün dijital dünyasında yaygın bir gereksinimdir. Bunu başarmak için güçlü bir araç, geliştiricilerin PowerPoint sunumlarını programlı olarak değiştirmesine ve geliştirmesine olanak tanıyan güçlü bir kitaplık olan Aspose.Slides for .NET'tir. Bu eğitimde Aspose.Slides'ı kullanarak sunum slaytlarındaki OLE (Nesne Bağlama ve Gömme) nesne verilerini değiştirme sürecini derinlemesine inceleyeceğiz.
## Önkoşullar
Aspose.Slides for .NET ile çalışmaya başlamadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1. Geliştirme Ortamı: .NET'in yüklü olduğu bir geliştirme ortamı kurun.
2.  Aspose.Slides Kütüphanesi: Aspose.Slides for .NET kütüphanesini indirip yükleyin. Kütüphaneyi bulabilirsiniz[Burada](https://releases.aspose.com/slides/net/).
3. Temel Anlama: C# programlamanın ve PowerPoint sunumlarının temel kavramlarına aşina olun.
## Ad Alanlarını İçe Aktar
Aspose.Slides işlevlerini kullanmak için C# projenize gerekli ad alanlarını içe aktarın:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## 1. Adım: Projenizi Kurun
Yeni bir C# projesi oluşturup Aspose.Slides kütüphanesini içe aktararak başlayın. Projenizin doğru yapılandırıldığından ve gerekli bağımlılıkların mevcut olduğundan emin olun.
## Adım 2: Sunuma ve Slayta Erişim
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Adım 3: OLE Nesnesini Bulun
OLE nesne çerçevesini bulmak için slayttaki tüm şekillerde gezinin:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Adım 4: Çalışma Kitabı Verilerini Okuyun ve Değiştirin
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Çalışma Kitabındaki nesne verilerini okuma
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Çalışma kitabı verilerini değiştirme
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Ole çerçeve nesnesi verilerini değiştirme
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Adım 5: Sunuyu Kaydetme
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Çözüm
Bu adımları izleyerek Aspose.Slides for .NET'i kullanarak sunum slaytlarındaki OLE nesne verilerini sorunsuz bir şekilde değiştirebilirsiniz. Bu, özel ihtiyaçlarınıza göre uyarlanmış dinamik ve özelleştirilmiş sunumlar oluşturmak için bir fırsatlar dünyasının kapılarını açar.
## Sıkça Sorulan Sorular
### Aspose.Slides for .NET nedir?
Aspose.Slides for .NET, geliştiricilerin PowerPoint sunumlarıyla programlı olarak çalışmasına olanak tanıyan, kolay düzenleme ve geliştirme olanağı sağlayan güçlü bir kitaplıktır.
### Aspose.Slides belgelerini nerede bulabilirim?
 Aspose.Slides for .NET belgelerini burada bulabilirsiniz[Burada](https://reference.aspose.com/slides/net/).
### Aspose.Slides for .NET'i nasıl indirebilirim?
 Kütüphaneyi sürüm sayfasından indirebilirsiniz.[Burada](https://releases.aspose.com/slides/net/).
### Aspose.Slides'ın ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümüne erişebilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET için nereden destek alabilirim?
 Destek ve tartışmalar için şu adresi ziyaret edin:[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
