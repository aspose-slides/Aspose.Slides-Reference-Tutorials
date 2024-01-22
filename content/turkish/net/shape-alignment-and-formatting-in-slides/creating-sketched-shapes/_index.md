---
title: Aspose.Slides ile Çarpıcı Taslak Şekiller Oluşturun
linktitle: Aspose.Slides ile Sunum Slaytlarında Taslak Şekiller Oluşturma
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak sunum slaytlarınıza yaratıcı çizim şekilleri eklemeyi öğrenin. Zahmetsizce görsel çekiciliği artırın!
type: docs
weight: 13
url: /tr/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## giriiş
Aspose.Slides for .NET kullanarak sunum slaytlarında taslak şekiller oluşturmaya ilişkin adım adım kılavuzumuza hoş geldiniz. Sunumlarınıza yaratıcılık dokunuşu katmak istiyorsanız, eskiz şekilleri benzersiz ve elle çizilmiş bir estetik sağlar. Bu eğitimde, sorunsuz bir deneyim sağlamak için süreci basit adımlara bölerek size süreç boyunca yol göstereceğiz.
## Önkoşullar
Eğiticiye dalmadan önce aşağıdaki önkoşulların mevcut olduğundan emin olun:
-  Aspose.Slides for .NET: Aspose.Slides for .NET kütüphanesinin kurulu olduğundan emin olun. İndirebilirsin[Burada](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: Tercih ettiğiniz IDE ile bir .NET geliştirme ortamı kurun.
## Ad Alanlarını İçe Aktar
.NET projenize gerekli ad alanlarını içe aktararak başlayın. Bu adım, Aspose.Slides ile çalışmak için gereken sınıflara ve işlevlere erişmenizi sağlar.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Adım 1: Projeyi Kurun
Yeni bir .NET projesi oluşturarak veya mevcut bir projeyi açarak başlayın. Aspose.Slides'ı proje referanslarınıza eklediğinizden emin olun.
## Adım 2: Aspose.Slides'ı başlatın
Aşağıdaki kod parçasını ekleyerek Aspose.Slides'ı başlatın. Bu, sunumu ayarlar ve sunum dosyası ile küçük resim görüntüsü için çıktı yollarını belirtir.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Sonraki adımlara geçin...
}
```
## 3. Adım: Taslak Şekli Ekleme
Şimdi slayta çizilmiş bir şekil ekleyelim. Bu örnekte, serbest çizim efektli bir dikdörtgen ekleyeceğiz.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Şekli serbest stil taslağına dönüştürün
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## 4. Adım: Küçük Resim Oluşturun
Çizilen şekli görselleştirmek için slaydın küçük resmini oluşturun. Küçük resmi PNG dosyası olarak kaydedin.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Adım 5: Sunuyu Kaydet
Sunum dosyasını kabataslak şekille kaydedin.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Bu kadar! Aspose.Slides for .NET'i kullanarak taslak şekillerden oluşan bir sunumu başarıyla oluşturdunuz.
## Çözüm
Sunum slaytlarınıza eskiz şekilleri eklemek görsel çekiciliği artırabilir ve izleyicilerinizin ilgisini çekebilir. Aspose.Slides for .NET ile süreç basitleşir ve yaratıcılığınızı zahmetsizce ortaya çıkarmanıza olanak tanır.
## SSS
### 1. Taslak efektini özelleştirebilir miyim?
Evet, Aspose.Slides for .NET, taslak efektler için çeşitli özelleştirme seçenekleri sunar. Bakın[dokümantasyon](https://reference.aspose.com/slides/net/) detaylı bilgi için.
### 2. Ücretsiz deneme mevcut mu?
 Kesinlikle! Aspose.Slides for .NET'in ücretsiz deneme sürümünü keşfedebilirsiniz[Burada](https://releases.aspose.com/).
### 3. Nereden destek alabilirim?
 Herhangi bir yardım veya soru için şu adresi ziyaret edin:[Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
### 4. Aspose.Slides for .NET'i nasıl satın alabilirim?
 Aspose.Slides for .NET'i satın almak için şu adresi ziyaret edin:[satın alma sayfası](https://purchase.aspose.com/buy).
### 5. Geçici lisanslar sunuyor musunuz?
 Evet, geçici lisanslar mevcut[Burada](https://purchase.aspose.com/temporary-license/).