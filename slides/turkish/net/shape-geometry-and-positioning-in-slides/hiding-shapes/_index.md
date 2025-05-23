---
"description": "Aspose.Slides for .NET kullanarak PowerPoint slaytlarındaki şekilleri nasıl gizleyeceğinizi öğrenin. Bu adım adım kılavuzla sunumları programatik olarak özelleştirin."
"linktitle": "Aspose.Slides ile Sunum Slaytlarındaki Şekilleri Gizleme"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides .NET Eğitimi ile PowerPoint'te Şekilleri Gizleme"
"url": "/tr/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET Eğitimi ile PowerPoint'te Şekilleri Gizleme

## giriiş
Sunumların dinamik dünyasında, özelleştirme anahtardır. Aspose.Slides for .NET, PowerPoint sunumlarını programatik olarak düzenlemek için güçlü bir çözüm sunar. Yaygın gereksinimlerden biri, bir slaytta belirli şekilleri gizleme yeteneğidir. Bu eğitim, Aspose.Slides for .NET kullanarak sunum slaytlarındaki şekilleri gizleme sürecinde size rehberlik edecektir.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
- .NET için Aspose.Slides: Aspose.Slides kütüphanesinin yüklü olduğundan emin olun. İndirebilirsiniz [Burada](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: .NET için tercih ettiğiniz geliştirme ortamını ayarlayın.
- C# Temel Bilgisi: Sağlanan kod örnekleri bu dilde olduğundan C# dilini öğrenin.
## Ad Alanlarını İçe Aktar
Aspose.Slides ile çalışmaya başlamak için, C# projenize gerekli ad alanlarını içe aktarın. Bu, gerekli sınıflara ve yöntemlere erişiminizin olmasını sağlar.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Şimdi, daha açık ve öz bir anlayış için örnek kodu birden fazla adıma bölelim.
## Adım 1: Projenizi Kurun
Yeni bir C# projesi oluşturun ve Aspose.Slides kütüphanesini eklediğinizden emin olun.
## Adım 2: Bir Sunum Oluşturun
Örneklemi oluştur `Presentation` sınıf, PowerPoint dosyasını temsil eder. Bir slayt ekleyin ve ona bir referans alın.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Adım 3: Slayda Şekiller Ekleyin
Slayda belirli boyutlara sahip dikdörtgenler ve aylar gibi otomatik şekiller ekleyin.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Adım 4: Alternatif Metne Dayalı Şekilleri Gizle
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
## Adım 5: Sunumu Kaydedin
Değiştirilen sunumu PPTX formatında diske kaydedin.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Çözüm
Tebrikler! Aspose.Slides for .NET kullanarak sunumunuzdaki şekilleri başarıyla gizlediniz. Bu, dinamik ve özelleştirilmiş slaytları programatik olarak oluşturmak için bir olasılıklar dünyasının kapılarını açar.
---
## SSS
### Aspose.Slides .NET Core ile uyumlu mu?
Evet, Aspose.Slides .NET Core'u destekler ve geliştirme ortamınızda esneklik sağlar.
### Alternatif metin dışındaki koşullara bağlı olarak şekilleri gizleyebilir miyim?
Kesinlikle! Gizleme mantığını şekil türü, renk veya konum gibi çeşitli niteliklere göre özelleştirebilirsiniz.
### Ek Aspose.Slides belgelerini nerede bulabilirim?
Belgeleri keşfedin [Burada](https://reference.aspose.com/slides/net/) Ayrıntılı bilgi ve örnekler için.
### Aspose.Slides için geçici lisanslar mevcut mu?
Evet, geçici bir lisans alabilirsiniz [Burada](https://purchase.aspose.com/temporary-license/) test amaçlı.
### Aspose.Slides için topluluk desteğini nasıl alabilirim?
Aspose.Slides topluluğuna katılın [forum](https://forum.aspose.com/c/slides/11) Tartışmalar ve yardım için.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}