---
"description": "Aspose.Slides for .NET ile dinamik PowerPoint sunumlarının dünyasını keşfedin. Bu adım adım kılavuzla slaytlarda ilgi çekici dikdörtgen şekillerin nasıl oluşturulacağını öğrenin."
"linktitle": "Aspose.Slides Kullanarak Sunum Slaytlarında Basit Dikdörtgen Şekli Oluşturma"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides for .NET ile Dikdörtgen Şekiller Oluşturma"
"url": "/tr/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for .NET ile Dikdörtgen Şekiller Oluşturma

## giriiş
.NET uygulamalarınızı dinamik ve görsel olarak çekici PowerPoint sunumlarıyla geliştirmek istiyorsanız, Aspose.Slides for .NET sizin için en iyi çözümdür. Bu eğitimde, Aspose.Slides for .NET kullanarak sunum slaytlarında basit bir dikdörtgen şekli oluşturma sürecinde size rehberlik edeceğiz.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşullara sahip olduğunuzdan emin olun:
- Visual Studio: Geliştirme makinenizde Visual Studio'nun yüklü olduğundan emin olun.
- Aspose.Slides for .NET: Aspose.Slides for .NET kitaplığını şu adresten indirin ve yükleyin: [Burada](https://releases.aspose.com/slides/net/).
- Temel C# Bilgisi: C# programlama diline aşinalık şarttır.
## Ad Alanlarını İçe Aktar
C# projenizde, Aspose.Slides işlevlerine erişmek için gerekli ad alanlarını içe aktararak başlayın:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Adım 1: Projeyi Kurun
Visual Studio'da yeni bir C# projesi oluşturarak başlayın. Projenizde Aspose.Slides for .NET'in doğru şekilde referans alındığından emin olun.
## Adım 2: Sunum Nesnesini Başlat
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Bundan sonraki adımlar için kodunuz buraya gelecek.
}
```
## Adım 3: İlk Slaydı Alın
```csharp
ISlide sld = pres.Slides[0];
```
## Adım 4: Dikdörtgen Otomatik Şekil Ekle
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Bu kod (50, 150) koordinatlarına genişliği 150 ve yüksekliği 50 olan bir dikdörtgen şekli ekler.
## Adım 5: Sunumu Kaydedin
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Bu adım, sunuyu eklenen dikdörtgen şekliyle belirtilen dizine kaydeder.
## Çözüm
Tebrikler! Aspose.Slides for .NET kullanarak bir sunum slaydında basit bir dikdörtgen şekli başarıyla oluşturdunuz. Bu sadece bir başlangıç – Aspose.Slides sunumlarınızı daha da özelleştirmek ve geliştirmek için geniş bir özellik yelpazesi sunar.
## Sıkça Sorulan Sorular
### Aspose.Slides for .NET'i hem Windows hem de Linux ortamlarında kullanabilir miyim?
Evet, Aspose.Slides for .NET platformdan bağımsızdır ve hem Windows hem de Linux ortamlarında kullanılabilir.
### Aspose.Slides for .NET için ücretsiz deneme sürümü mevcut mu?
Evet, ücretsiz deneme alabilirsiniz [Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET desteğini nasıl alabilirim?
Ziyaret edin [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) Toplum desteği için.
### Aspose.Slides for .NET için geçici bir lisans satın alabilir miyim?
Evet, geçici bir lisans satın alabilirsiniz [Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for .NET'in belgelerini nerede bulabilirim?
Belgelere bakın [Burada](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}