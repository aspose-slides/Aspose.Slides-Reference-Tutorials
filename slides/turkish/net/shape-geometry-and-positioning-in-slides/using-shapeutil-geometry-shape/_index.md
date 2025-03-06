---
title: ShapeUtil ile Geometri Şekillerinde Ustalaşmak - Aspose.Slides .NET
linktitle: Sunum Slaytlarında Geometri Şekli için ShapeUtil'i Kullanma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Dinamik geometri şekilleri için Aspose.Slides for .NET'in gücünü ShapeUtil ile keşfedin. Zahmetsizce ilgi çekici sunumlar oluşturun. Hemen indirin! Aspose.Slides ile PowerPoint sunumlarını nasıl geliştireceğinizi öğrenin. Geometri şekillerinin işlenmesi için ShapeUtil'i keşfedin. .NET kaynak kodunu içeren adım adım kılavuz. Sunumları etkili bir şekilde optimize edin.
weight: 17
url: /tr/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## giriiş
Görsel olarak çekici ve dinamik sunum slaytları oluşturmak önemli bir beceridir ve Aspose.Slides for .NET bunu başarmak için güçlü bir araç seti sağlar. Bu derste, sunum slaytlarındaki geometri şekillerini işlemek için ShapeUtil'in kullanımını inceleyeceğiz. İster tecrübeli bir geliştirici olun ister Aspose.Slides'a yeni başlıyor olun, bu kılavuz sunumlarınızı geliştirmek için ShapeUtil'i kullanma sürecinde size yol gösterecektir.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
- C# ve .NET programlamanın temel anlayışı.
-  Aspose.Slides for .NET kütüphanesi kuruldu. Değilse indirebilirsiniz[Burada](https://releases.aspose.com/slides/net/).
- .NET uygulamalarını çalıştırmak için ayarlanmış bir geliştirme ortamı.
## Ad Alanlarını İçe Aktar
Aspose.Slides işlevlerine erişmek için C# kodunuzda gerekli ad alanlarını içe aktardığınızdan emin olun. Komut dosyanızın başına aşağıdakileri ekleyin:
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
Şimdi, sunum slaytlarındaki geometri şekilleri için ShapeUtil'i kullanmaya yönelik adım adım bir kılavuz oluşturmak üzere verilen örneği birden çok adıma ayıralım.
## 1. Adım: Belge Dizininizi Kurun
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
"Belge Dizininiz"i, sununuzu kaydetmek istediğiniz asıl yolla değiştirdiğinizden emin olun.
## Adım 2: Çıktı Dosyası Adını Tanımlayın
```csharp
string resultPath = Path.Combine(dataDir, "GeometryShapeUsingShapeUtil.pptx");
```
Dosya uzantısı da dahil olmak üzere istenen çıktı dosyası adını belirtin.
## 3. Adım: Bir Sunum Oluşturun
```csharp
using (Presentation pres = new Presentation())
```
Aspose.Slides kütüphanesini kullanarak yeni bir sunum nesnesi başlatın.
## Adım 4: Geometri Şekli Ekleme
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
Sununun ilk slaydına dikdörtgen şekli ekleyin.
## Adım 5: Orijinal Geometri Yolunu Alın
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
Şeklin geometri yolunu alın ve doldurma modunu ayarlayın.
## Adım 6: Metinle Grafik Yolu Oluşturun
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
Şekle eklenecek metni içeren bir grafik yolu oluşturun.
## Adım 7: Grafik Yolunu Geometri Yoluna Dönüştürün
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
Grafik yolunu bir geometri yoluna dönüştürmek ve dolgu modunu ayarlamak için ShapeUtil'i kullanın.
## Adım 8: Birleştirilmiş Geometri Yollarını Şekle Ayarlayın
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
Yeni geometri yolunu orijinal yolla birleştirin ve onu şekle ayarlayın.
## Adım 9: Sunuyu Kaydetme
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Değiştirilen sunumu yeni geometri şekliyle kaydedin.
## Çözüm
Tebrikler! Aspose.Slides for .NET kullanarak sunum slaytlarındaki geometri şekillerini işlemek için ShapeUtil'in kullanımını başarıyla keşfettiniz. Bu güçlü özellik, kolaylıkla dinamik ve ilgi çekici sunumlar oluşturmanıza olanak tanır.
## SSS
### Aspose.Slides for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
Aspose.Slides öncelikle .NET dillerini destekler. Ancak Aspose diğer platformlar ve diller için de benzer kütüphaneler sağlıyor.
### Aspose.Slides for .NET'in ayrıntılı belgelerini nerede bulabilirim?
 Belgeler mevcut[Burada](https://reference.aspose.com/slides/net/).
### Aspose.Slides for .NET'in ücretsiz deneme sürümü mevcut mu?
 Evet, ücretsiz deneme sürümünü bulabilirsiniz[Burada](https://releases.aspose.com/).
### Aspose.Slides for .NET için nasıl destek alabilirim?
 Topluluk destek forumunu ziyaret edin[Burada](https://forum.aspose.com/c/slides/11).
### Aspose.Slides for .NET için geçici bir lisans satın alabilir miyim?
 Evet, geçici lisans alabilirsiniz[Burada](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
