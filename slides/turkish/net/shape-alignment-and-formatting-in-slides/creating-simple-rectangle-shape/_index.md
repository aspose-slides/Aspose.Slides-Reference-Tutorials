---
title: Aspose.Slides for .NET ile Dikdörtgen Şekiller Oluşturma
linktitle: Aspose.Slides Kullanarak Sunum Slaytlarında Basit Dikdörtgen Şekil Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET ile dinamik PowerPoint sunumlarının dünyasını keşfedin. Bu adım adım kılavuzla slaytlarda ilgi çekici dikdörtgen şekillerin nasıl oluşturulacağını öğrenin.
weight: 12
url: /tr/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
.NET uygulamalarınızı dinamik ve görsel olarak çekici PowerPoint sunumlarıyla geliştirmek istiyorsanız Aspose.Slides for .NET sizin için çözümdür. Bu eğitimde, Aspose.Slides for .NET'i kullanarak sunum slaytlarında basit bir dikdörtgen şekli oluşturma sürecinde size rehberlik edeceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşullara sahip olduğunuzdan emin olun:
- Visual Studio: Geliştirme makinenizde Visual Studio'nun kurulu olduğundan emin olun.
-  Aspose.Slides for .NET: Aspose.Slides for .NET kitaplığını şu adresten indirip yükleyin:[Burada](https://releases.aspose.com/slides/net/).
- Temel C# Bilgisi: C# programlama diline aşinalık esastır.
## Ad Alanlarını İçe Aktar
Aspose.Slides işlevlerine erişmek için C# projenizde gerekli ad alanlarını içe aktararak başlayın:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Adım 1: Projeyi Kurun
Visual Studio'da yeni bir C# projesi oluşturarak başlayın. Aspose.Slides for .NET'e projenizde doğru şekilde başvurulduğundan emin olun.
## Adım 2: Sunum Nesnesini Başlatın
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Sonraki adımlara ilişkin kodunuz buraya gelecek.
}
```
## 3. Adım: İlk Slaydı Alın
```csharp
ISlide sld = pres.Slides[0];
```
## Adım 4: Dikdörtgen Otomatik Şekil Ekle
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Bu kod, (50, 150) koordinatlarında genişliği 150, yüksekliği 50 olan bir dikdörtgen şekli ekler.
## Adım 5: Sunuyu Kaydetme
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Bu adım, sunumu eklenen dikdörtgen şekliyle belirtilen dizine kaydeder.
## Çözüm
Tebrikler! Aspose.Slides for .NET'i kullanarak bir sunum slaytında başarıyla basit bir dikdörtgen şekli oluşturdunuz. Bu sadece başlangıç – Aspose.Slides, sunumlarınızı daha da kişiselleştirmek ve geliştirmek için geniş bir özellik yelpazesi sunuyor.
## Sıkça Sorulan Sorular
### Aspose.Slides for .NET'i hem Windows hem de Linux ortamlarında kullanabilir miyim?
Evet, Aspose.Slides for .NET platformdan bağımsızdır ve hem Windows hem de Linux ortamlarında kullanılabilir.
### Aspose.Slides for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünden yararlanabilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET için nasıl destek alabilirim?
 Ziyaret edin[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11) topluluk desteği için.
### Aspose.Slides for .NET için geçici bir lisans satın alabilir miyim?
 Evet, geçici lisans satın alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
### Aspose.Slides for .NET belgelerini nerede bulabilirim?
 Belgelere bakın[Burada](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
