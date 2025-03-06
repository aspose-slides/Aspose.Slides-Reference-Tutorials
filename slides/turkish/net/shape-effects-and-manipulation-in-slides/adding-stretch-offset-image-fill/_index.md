---
title: PowerPoint Sunumlarında Görüntü Dolgusu için Uzatma Uzaklığı Ekleme
linktitle: Slaytlarda Görüntü Dolgusu için Uzatma Uzaklığı Ekleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET ile PowerPoint sunumlarını nasıl geliştireceğinizi öğrenin. Görüntü dolgusuna uzatma ofseti eklemek için adım adım kılavuzu izleyin.
weight: 18
url: /tr/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# PowerPoint Sunumlarında Görüntü Dolgusu için Uzatma Uzaklığı Ekleme

## giriiş
Sunumların dinamik dünyasında görseller izleyicinin dikkatini çekmede önemli bir rol oynar. Aspose.Slides for .NET, güçlü özellikler sunarak geliştiricilerin PowerPoint sunumlarını geliştirmelerine olanak sağlar. Bu özelliklerden biri, yaratıcı ve görsel olarak çekici slaytlara olanak tanıyan görüntü dolgusu için bir uzatma ofseti ekleme yeteneğidir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların yerine getirildiğinden emin olun:
1.  Aspose.Slides for .NET Library: Kitaplığı şuradan indirip yükleyin:[Aspose.Slides for .NET belgeleri](https://reference.aspose.com/slides/net/).
2. Geliştirme Ortamı: Çalışan bir .NET geliştirme ortamı kurduğunuzdan emin olun.
Şimdi adım adım kılavuza başlayalım.
## Ad Alanlarını İçe Aktar
İlk olarak, .NET uygulamanızda Aspose.Slides işlevselliğinden yararlanmak için gerekli ad alanlarını içe aktarın.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## 1. Adım: Projenizi Kurun
Tercih ettiğiniz geliştirme ortamında yeni bir .NET projesi oluşturun. Aspose.Slides for .NET'e doğru şekilde başvurulduğundan emin olun.
## Adım 2: Sunum Sınıfını Başlatın
 Örnekleyin`Presentation` PowerPoint dosyasını temsil edecek sınıf.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Kodunuz buraya gelecek
}
```
## 3. Adım: İlk Slaydı Alın
Üzerinde çalışmak için sunumdan ilk slaydı alın.
```csharp
ISlide sld = pres.Slides[0];
```
## Adım 4: ImageEx Sınıfını Örneklendirin
 Bir örneğini oluşturun`ImageEx`Slayda eklemek istediğiniz görüntüyü işlemek için class.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## 5. Adım: Resim Çerçevesi Ekleyin
 Kullanın`AddPictureFrame` Slayta resim çerçevesi ekleme yöntemi. Çerçevenin boyutlarını ve konumunu belirtin.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Adım 6: Sunuyu Kaydetme
Değiştirilen sunumu diske kaydedin.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
Bu kadar! Aspose.Slides for .NET'i kullanarak slaytlara görüntü dolgusu için başarılı bir şekilde uzatma ofseti eklediniz.
## Çözüm
Aspose.Slides for .NET ile PowerPoint sunumlarınızı geliştirmek artık her zamankinden daha kolay. Bu öğreticiyi takip ederek, slaytlarınıza yeni bir yaratıcılık düzeyi getirerek görüntü dolgusu için uzatma ofsetini nasıl dahil edeceğinizi öğrendiniz.
## SSS
### Aspose.Slides for .NET'i web uygulamalarımda kullanabilir miyim?
Evet, Aspose.Slides for .NET hem masaüstü hem de web uygulamaları için uygundur.
### Aspose.Slides for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü şuradan indirebilirsiniz:[Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET için nasıl destek alabilirim?
 Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) topluluk desteği için.
### Aspose.Slides for .NET'in tam belgelerini nerede bulabilirim?
 Bakın[dokümantasyon](https://reference.aspose.com/slides/net/) detaylı bilgi için.
### Aspose.Slides for .NET'i satın alabilir miyim?
 Evet ürünü satın alabilirsiniz[Burada](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
