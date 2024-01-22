---
title: Aspose.Slides .NET Eğitimi ile PowerPoint'te Şekilleri Gizleyin
linktitle: Aspose.Slides ile Sunum Slaytlarındaki Şekilleri Gizleme
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET kullanarak PowerPoint slaytlarındaki şekilleri nasıl gizleyeceğinizi öğrenin. Bu adım adım kılavuzla sunumlarınızı programlı bir şekilde özelleştirin.
type: docs
weight: 21
url: /tr/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---
## giriiş
Sunumların dinamik dünyasında kişiselleştirme çok önemlidir. Aspose.Slides for .NET, PowerPoint sunumlarını programlı olarak düzenlemek için güçlü bir çözüm sunar. Yaygın gereksinimlerden biri, slayttaki belirli şekilleri gizleyebilmektir. Bu eğitim, Aspose.Slides for .NET kullanarak sunum slaytlarındaki şekilleri gizleme sürecinde size rehberlik edecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Slides for .NET: Aspose.Slides kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: .NET için tercih ettiğiniz geliştirme ortamını ayarlayın.
- Temel C# Bilgisi: Sağlanan kod örnekleri bu dilde olduğundan, C#'a aşina olun.
## Ad Alanlarını İçe Aktar
Aspose.Slides ile çalışmaya başlamak için gerekli ad alanlarını C# projenize aktarın. Bu, gerekli sınıflara ve yöntemlere erişiminizi sağlar.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Şimdi, açık ve net bir anlayış için örnek kodu birden çok adıma ayıralım.
## 1. Adım: Projenizi Kurun
Yeni bir C# projesi oluşturun ve Aspose.Slides kütüphanesini eklediğinizden emin olun.
## Adım 2: Bir Sunu Oluşturun
 Örnekleyin`Presentation` PowerPoint dosyasını temsil eden sınıf. Bir slayt ekleyin ve ona bir referans alın.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## 3. Adım: Slayta Şekiller Ekleme
Slayta dikdörtgenler ve aylar gibi belirli boyutlara sahip otomatik şekiller ekleyin.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Adım 4: Alternatif Metne Göre Şekilleri Gizleyin
Alternatif bir metin belirtin ve bu metinle eşleşen şekilleri gizleyin.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Adım 5: Sunuyu Kaydetme
Değiştirilen sunumu PPTX formatında diske kaydedin.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Çözüm
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## SSS
### Aspose.Slides .NET Core ile uyumlu mu?
Evet, Aspose.Slides .NET Core'u destekleyerek geliştirme ortamınıza esneklik sağlar.
### Alternatif metin dışındaki koşullara dayalı olarak şekilleri gizleyebilir miyim?
Kesinlikle! Şekil türü, renk veya konum gibi çeşitli niteliklere göre gizleme mantığını özelleştirebilirsiniz.
### Ek Aspose.Slides belgelerini nerede bulabilirim?
 Belgeleri keşfedin[Burada](https://reference.aspose.com/slides/net/) Ayrıntılı bilgi ve örnekler için.
### Aspose.Slides için geçici lisanslar mevcut mu?
 Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/) test amaçlı.
### Aspose.Slides için topluluk desteğini nasıl alabilirim?
 Aspose.Slides topluluğuna katılın[forum](https://forum.aspose.com/c/slides/11) Tartışma ve yardım için.