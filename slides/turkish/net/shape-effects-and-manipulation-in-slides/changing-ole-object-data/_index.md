---
"description": "OLE nesne verilerini zahmetsizce değiştirmede Aspose.Slides for .NET'in gücünü keşfedin. Sunumlarınızı dinamik içerikle geliştirin."
"linktitle": "Aspose.Slides ile Sunumdaki OLE Nesne Verilerini Değiştirme"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides ile Sunumdaki OLE Nesne Verilerini Değiştirme"
"url": "/tr/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides ile Sunumdaki OLE Nesne Verilerini Değiştirme

## giriiş
Günümüzün dijital dünyasında dinamik ve etkileşimli PowerPoint sunumları oluşturmak yaygın bir gerekliliktir. Bunu başarmak için güçlü bir araç, geliştiricilerin PowerPoint sunumlarını programatik olarak düzenlemelerine ve geliştirmelerine olanak tanıyan sağlam bir kütüphane olan Aspose.Slides for .NET'tir. Bu eğitimde, Aspose.Slides kullanarak sunum slaytlarındaki OLE (Nesne Bağlama ve Yerleştirme) nesne verilerini değiştirme sürecini inceleyeceğiz.
## Ön koşullar
Aspose.Slides for .NET ile çalışmaya başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
1. Geliştirme Ortamı: .NET yüklü bir geliştirme ortamı kurun.
2. Aspose.Slides Kütüphanesi: Aspose.Slides for .NET kütüphanesini indirin ve kurun. Kütüphaneyi şurada bulabilirsiniz: [Burada](https://releases.aspose.com/slides/net/).
3. Temel Anlayış: C# programlamanın temel kavramları ve PowerPoint sunumları ile tanışın.
## Ad Alanlarını İçe Aktar
C# projenizde Aspose.Slides işlevlerini kullanmak için gerekli ad alanlarını içe aktarın:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Adım 1: Projenizi Kurun
Yeni bir C# projesi oluşturarak ve Aspose.Slides kütüphanesini içe aktararak başlayın. Projenizin doğru şekilde yapılandırıldığından ve gerekli bağımlılıkların yerinde olduğundan emin olun.
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
OLE nesne çerçevesini bulmak için slayttaki tüm şekilleri dolaşın:
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
        // Çalışma Kitabında nesne verilerini okuma
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
## Adım 5: Sunumu Kaydedin
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Çözüm
Bu adımları izleyerek, Aspose.Slides for .NET kullanarak sunum slaytlarındaki OLE nesne verilerini sorunsuz bir şekilde değiştirebilirsiniz. Bu, özel ihtiyaçlarınıza göre uyarlanmış dinamik ve özelleştirilmiş sunumlar oluşturmak için bir olasılıklar dünyasının kapılarını açar.
## Sıkça Sorulan Sorular
### Aspose.Slides for .NET nedir?
Aspose.Slides for .NET, geliştiricilerin PowerPoint sunumlarıyla programlı bir şekilde çalışmasını sağlayan, kolay düzenleme ve geliştirme olanağı sağlayan güçlü bir kütüphanedir.
### Aspose.Slides belgelerini nerede bulabilirim?
.NET için Aspose.Slides'ın belgeleri şurada bulunabilir: [Burada](https://reference.aspose.com/slides/net/).
### Aspose.Slides for .NET'i nasıl indirebilirim?
Kütüphaneyi sürüm sayfasından indirebilirsiniz [Burada](https://releases.aspose.com/slides/net/).
### Aspose.Slides için ücretsiz deneme sürümü mevcut mu?
Evet, ücretsiz denemeye erişebilirsiniz [Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET için desteği nereden alabilirim?
Destek ve tartışmalar için şu adresi ziyaret edin: [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}