---
title: PowerPoint Şekil Küçük Resimleri Oluşturma - Aspose.Slides .NET
linktitle: Aspose.Slides'ta Shape için Küçük Resim Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint sunumlarındaki şekiller için küçük resimler oluşturmayı öğrenin. Geliştiriciler için kapsamlı, adım adım kılavuz.
weight: 14
url: /tr/net/image-and-video-manipulation-in-slides/creating-thumbnail-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
Aspose.Slides for .NET, geliştiricilerin PowerPoint sunumlarıyla sorunsuz bir şekilde çalışmasına olanak tanıyan güçlü bir kitaplıktır. Dikkate değer özelliklerinden biri, bir sunumdaki şekiller için küçük resimler oluşturma yeteneğidir. Bu eğitim, Aspose.Slides for .NET kullanarak şekiller için küçük resimler oluşturma sürecinde size rehberlik edecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
1.  Aspose.Slides for .NET: Aspose.Slides kütüphanesinin kurulu olduğundan emin olun. adresinden indirebilirsiniz.[yayın sayfası](https://releases.aspose.com/slides/net/).
2. Geliştirme Ortamı: Visual Studio gibi uygun bir geliştirme ortamı kurun ve C# programlama konusunda temel bir anlayışa sahip olun.
## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını C# kodunuza aktarmanız gerekir. Bu ad alanları Aspose.Slides kütüphanesiyle iletişimi kolaylaştırır. C# dosyanızın başına aşağıdaki satırları ekleyin:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## 1. Adım: Projenizi Kurun
Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun. Projenizde Aspose.Slides kütüphanesine başvurulduğundan emin olun.
## Adım 2: Sunumu Başlatın
PowerPoint dosyasını temsil edecek bir Sunum sınıfı oluşturun. Sunum dosyanızın yolunu şu şekilde belirtin:`dataDir` değişken.
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Küçük resim oluşturma kodunuz buraya gelecek
}
```
## 3. Adım: Tam Ölçekli Bir Görüntü Oluşturun
Küçük resmini oluşturmak istediğiniz şeklin tam ölçekli görüntüsünü oluşturun. Bu örnekte, ilk slayttaki ilk şekli kullanıyoruz (`presentation.Slides[0].Shapes[0]`).
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail())
{
    // Küçük resim oluşturma kodunuz buraya gelecek
}
```
## Adım 4: Görüntüyü Kaydedin
Oluşturulan küçük resim görüntüsünü diske kaydedin. Görüntüyü kaydetmek istediğiniz formatı seçebilirsiniz. Bu örnekte PNG formatında kaydediyoruz.
```csharp
bitmap.Save(dataDir + "Shape_thumbnail_out.png", ImageFormat.Png);
```
## Çözüm
Tebrikler! Aspose.Slides for .NET'te şekiller için başarıyla küçük resimler oluşturdunuz. Bu güçlü özellik, PowerPoint sunumlarından bilgi çıkarma ve değiştirme yeteneğinize yeni bir boyut katar.
## Sıkça Sorulan Sorular
### S: Bir sunumda birden çok şekil için küçük resimler oluşturabilir miyim?
C: Evet, bir slayttaki tüm şekiller arasında geçiş yapabilir ve her biri için küçük resimler oluşturabilirsiniz.
### S: Aspose.Slides farklı PowerPoint dosya formatlarıyla uyumlu mudur?
C: Aspose.Slides, PPTX, PPT ve daha fazlası dahil olmak üzere çeşitli dosya formatlarını destekler.
### S: Küçük resim oluşturma sırasındaki hataları nasıl halledebilirim?
C: İstisnaları yönetmek için try-catch bloklarını kullanarak hata işleme mekanizmalarını uygulayabilirsiniz.
### S: Küçük resimlerin bulunabileceği şekillerin boyutu veya türü konusunda herhangi bir sınırlama var mı?
C: Aspose.Slides, metin kutuları, resimler ve daha fazlası dahil olmak üzere çeşitli şekiller için küçük resimler oluşturma konusunda esneklik sağlar.
### S: Oluşturulan küçük resimlerin boyutunu ve çözünürlüğünü özelleştirebilir miyim?
 C: Evet, çağrı yaparken parametreleri ayarlayabilirsiniz.`GetThumbnail` boyutu ve çözünürlüğü kontrol etme yöntemi.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
