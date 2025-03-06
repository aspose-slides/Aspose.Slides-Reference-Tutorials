---
title: OLE Nesneleri Kılavuzunu Aspose.Slides for .NET'e Gömme
linktitle: Sunum Slaytlarında OLE Nesne Çerçevesinin Resim Başlığını Değiştirme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak sunum slaytlarınızı dinamik OLE nesneleriyle nasıl geliştireceğinizi öğrenin. Sorunsuz entegrasyon için adım adım kılavuzumuzu izleyin.
weight: 15
url: /tr/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## giriiş
Dinamik ve ilgi çekici sunum slaytları oluşturmak genellikle çeşitli multimedya öğelerinin dahil edilmesini içerir. Bu eğitimde, güçlü Aspose.Slides for .NET kütüphanesini kullanarak bir OLE (Nesne Bağlama ve Gömme) Nesne Çerçevesinin resim başlığını sunum slaytlarında nasıl değiştireceğimizi keşfedeceğiz. Aspose.Slides, OLE nesnelerini işleme sürecini basitleştirerek geliştiricilere sunumlarını kolaylıkla geliştirebilecekleri araçlar sağlar.
## Önkoşullar
Adım adım kılavuza geçmeden önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Slides for .NET Library: Aspose.Slides for .NET kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[Aspose.Slides .NET Belgeleri](https://reference.aspose.com/slides/net/).
- Örnek Veriler: Sunuma OLE nesnesi olarak eklemek istediğiniz örnek bir Excel dosyası (örneğin, "ExcelObject.xlsx") hazırlayın. Ayrıca, OLE nesnesi için simge görevi görecek bir görüntü dosyasına (örneğin, "Image.png") sahip olun.
- Geliştirme Ortamı: Visual Studio veya .NET geliştirme için tercih edilen herhangi bir IDE gibi gerekli araçlarla bir geliştirme ortamı oluşturun.
## Ad Alanlarını İçe Aktar
.NET projenizde Aspose.Slides ile çalışmak için gerekli ad alanlarını içe aktardığınızdan emin olun:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## 1. Adım: Belge Dizinini Ayarlayın
```csharp
string dataDir = "Your Document Directory";
```
"Belge Dizininiz"i belge dizininizin gerçek yolu ile değiştirdiğinizden emin olun.
## Adım 2: OLE Kaynak Dosyasını ve Simge Dosya Yollarını Tanımlayın
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Bu yolları, örnek Excel dosyanızın ve görüntü dosyanızın gerçek yollarıyla güncelleyin.
## 3. Adım: Bir Sunum Örneği Oluşturun
```csharp
using (Presentation pres = new Presentation())
{
    // Sonraki adımların kodu buraya gelecek
}
```
 Yeni bir örneğini başlat`Presentation` sınıf.
## Adım 4: OLE Nesne Çerçevesi Ekleme
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Konumunu ve boyutlarını belirterek slayda bir OLE nesne çerçevesi ekleyin.
## Adım 5: Resim Nesnesi Ekle
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Resim dosyasını okuyun ve sunuma bir resim nesnesi olarak ekleyin.
## Adım 6: Başlığı OLE Simgesine Ayarlayın
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
OLE simgesi için istediğiniz başlığı ayarlayın.
## Çözüm
Aspose.Slides for .NET kullanarak OLE nesnelerini sunum slaytlarınıza eklemek basit bir işlemdir. Bu eğitim, belge dizinini ayarlamaktan OLE nesnelerini eklemeye ve özelleştirmeye kadar temel adımlarda size rehberlik etmiştir. Sunumlarınızın görsel çekiciliğini artırmak için farklı dosya türleri ve başlıklarla denemeler yapın.
## SSS
### Aspose.Slides'ı kullanarak diğer dosya türlerini OLE nesneleri olarak gömebilir miyim?
Evet, Aspose.Slides, Excel elektronik tabloları, Word belgeleri ve daha fazlası gibi çeşitli dosya türlerinin gömülmesini destekler.
### OLE nesne simgesi özelleştirilebilir mi?
Kesinlikle. Sununuzun temasına daha iyi uyum sağlamak için varsayılan simgeyi seçtiğiniz herhangi bir görüntüyle değiştirebilirsiniz.
### Aspose.Slides, OLE nesneleri içeren animasyonlar için destek sağlıyor mu?
En son sürümden itibaren Aspose.Slides, OLE nesnesi yerleştirme ve görüntülemeye odaklanıyor ve OLE nesneleri içindeki animasyonları doğrudan ele almıyor.
### OLE nesnelerini bir slayda ekledikten sonra programlı olarak değiştirebilir miyim?
Kesinlikle. OLE nesneleri üzerinde tam programatik denetime sahip olursunuz ve bu sayede özelliklerini ve görünümlerini gerektiği gibi değiştirebilirsiniz.
### Katıştırılmış OLE nesnelerinin boyutunda herhangi bir sınırlama var mı?
Boyut sınırlamaları olsa da genellikle cömerttirler. Optimum performans sağlamak için özel kullanım durumunuzla test etmeniz önerilir.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
