---
"description": "Aspose.Slides for .NET'te özel geometri oluşturmayı öğrenin. Sunumlarınızı benzersiz şekillerle yükseltin. C# geliştiricileri için adım adım kılavuz."
"linktitle": "Aspose.Slides kullanarak Geometry Shape'te Özel Geometri Oluşturma"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": ".NET için Aspose.Slides ile C#'ta Özel Geometri Oluşturma"
"url": "/tr/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# .NET için Aspose.Slides ile C#'ta Özel Geometri Oluşturma

## giriiş
Sunumların dinamik dünyasında, benzersiz şekiller ve geometriler eklemek içeriğinizi yükseltebilir, daha ilgi çekici ve görsel olarak çekici hale getirebilir. Aspose.Slides for .NET, şekiller içinde özel geometriler oluşturmak için güçlü bir çözüm sunarak geleneksel tasarımlardan kurtulmanızı sağlar. Bu eğitim, Aspose.Slides for .NET kullanarak bir GeometryShape'te özel geometri oluşturma sürecinde size rehberlik edecektir.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
- C# programlama dilinin temel düzeyde anlaşılması.
- Geliştirme ortamınıza Aspose.Slides for .NET kütüphanesi yüklendi.
- Visual Studio veya tercih ettiğiniz herhangi bir C# geliştirme ortamı kurulumu.
## Ad Alanlarını İçe Aktar
Başlamak için gerekli ad alanlarını C# projenize aktarın:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Adım 1: Projenizi Kurun
Tercih ettiğiniz geliştirme ortamında yeni bir C# projesi oluşturun. Aspose.Slides for .NET'in düzgün bir şekilde yüklendiğinden emin olun.
## Adım 2: Belge Dizininizi Tanımlayın
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Adım 3: Dış ve İç Yıldız Yarıçapını Ayarlayın
```csharp
float R = 100, r = 50; // Dış ve iç yıldız yarıçapı
```
## Adım 4: Yıldız Geometrisi Yolu Oluşturun
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Adım 5: Bir Sunum Oluşturun
```csharp
using (Presentation pres = new Presentation())
{
    // Yeni şekil oluştur
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Şekle yeni geometri yolu ayarla
    shape.SetGeometryPath(starPath);
    // Sunumu kaydet
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Adım 6: CreateStarGeometry Yöntemini Tanımlayın
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## Çözüm
Tebrikler! Aspose.Slides for .NET kullanarak bir GeometryShape'te özel geometri oluşturmayı başarıyla öğrendiniz. Bu, benzersiz ve görsel olarak çarpıcı sunumlar oluşturmak için bir olasılıklar dünyasının kapılarını açar.
## SSS
### 1. Aspose.Slides for .NET'i diğer programlama dilleriyle birlikte kullanabilir miyim?
Evet, Aspose.Slides birçok programlama dilini destekliyor, ancak bu eğitim C# üzerine odaklanıyor.
### 2. Aspose.Slides for .NET'in belgelerini nerede bulabilirim?
Ziyaret edin [belgeleme](https://reference.aspose.com/slides/net/) Detaylı bilgi için.
### 3. Aspose.Slides for .NET için ücretsiz deneme sürümü mevcut mu?
Evet, keşfedebilirsiniz [ücretsiz deneme](https://releases.aspose.com/) özelliklerini deneyimlemek için.
### 4. Aspose.Slides for .NET desteğini nasıl alabilirim?
Yardım isteyin ve toplulukla etkileşim kurun [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
### 5. Aspose.Slides for .NET'i nereden satın alabilirim?
.NET için Aspose.Slides'ı satın alabilirsiniz [Burada](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}