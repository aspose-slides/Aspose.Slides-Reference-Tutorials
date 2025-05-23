---
"description": "Aspose.Slides for .NET kullanarak sunum slaytlarınıza yaratıcı çizimlerin nasıl ekleneceğini öğrenin. Görsel çekiciliği zahmetsizce artırın!"
"linktitle": "Aspose.Slides ile Sunum Slaytlarında Çizilmiş Şekiller Oluşturma"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides ile Çarpıcı Çizilmiş Şekiller Oluşturun"
"url": "/tr/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides ile Çarpıcı Çizilmiş Şekiller Oluşturun

## giriiş
.NET için Aspose.Slides kullanarak sunum slaytlarında taslak şekiller oluşturma konusunda adım adım kılavuzumuza hoş geldiniz. Sunumlarınıza biraz yaratıcılık katmak istiyorsanız, taslak şekiller benzersiz ve elle çizilmiş bir estetik sunar. Bu eğitimde, sorunsuz bir deneyim sağlamak için süreci basit adımlara bölerek size yol göstereceğiz.
## Ön koşullar
Eğitime başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:
- .NET için Aspose.Slides: .NET için Aspose.Slides kitaplığının yüklü olduğundan emin olun. İndirebilirsiniz [Burada](https://releases.aspose.com/slides/net/).
- Geliştirme Ortamı: Tercih ettiğiniz IDE ile bir .NET geliştirme ortamı kurun.
## Ad Alanlarını İçe Aktar
.NET projenize gerekli ad alanlarını içe aktararak başlayın. Bu adım, Aspose.Slides ile çalışmak için gereken sınıflara ve işlevlere erişiminizin olmasını sağlar.
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
Yeni bir .NET projesi oluşturarak veya mevcut bir projeyi açarak başlayın. Proje referanslarınıza Aspose.Slides'ı eklediğinizden emin olun.
## Adım 2: Aspose.Slides'ı Başlatın
Aşağıdaki kod parçacığını ekleyerek Aspose.Slides'ı başlatın. Bu, sunumu ayarlar ve sunum dosyası ve küçük resim görüntüsü için çıktı yollarını belirtir.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Bir sonraki adımlara geçin...
}
```
## Adım 3: Çizilmiş Şekil Ekle
Şimdi, slayta çizilmiş bir şekil ekleyelim. Bu örnekte, serbest çizim efektli bir dikdörtgen ekleyeceğiz.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Şekli serbest el stilinde bir taslağa dönüştürün
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Adım 4: Küçük Resim Oluşturun
Çizilen şekli görselleştirmek için slaydın küçük resmini oluşturun. Küçük resmi PNG dosyası olarak kaydedin.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Adım 5: Sunumu Kaydedin
Çizimi yapılmış şeklin bulunduğu sunum dosyasını kaydedin.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
İşte bu kadar! Aspose.Slides for .NET kullanarak çizilmiş şekillerle bir sunum oluşturmayı başardınız.
## Çözüm
Sunum slaytlarınıza çizilmiş şekiller eklemek görsel çekiciliği artırabilir ve izleyicilerinizin ilgisini çekebilir. Aspose.Slides for .NET ile süreç basitleşir ve yaratıcılığınızı zahmetsizce serbest bırakmanıza olanak tanır.
## SSS
### 1. Çizdiğim efekti özelleştirebilir miyim?
Evet, Aspose.Slides for .NET, çizilmiş efektler için çeşitli özelleştirme seçenekleri sunar. [belgeleme](https://reference.aspose.com/slides/net/) Detaylı bilgi için.
### 2. Ücretsiz deneme imkanı var mı?
Elbette! Aspose.Slides for .NET'in ücretsiz deneme sürümünü keşfedebilirsiniz [Burada](https://releases.aspose.com/).
### 3. Nereden destek alabilirim?
Herhangi bir yardım veya soru için şu adresi ziyaret edin: [Aspose.Slides forumu](https://forum.aspose.com/c/slides/11).
### 4. Aspose.Slides for .NET'i nasıl satın alabilirim?
Aspose.Slides for .NET'i satın almak için şu adresi ziyaret edin: [satın alma sayfası](https://purchase.aspose.com/buy).
### 5. Geçici lisans veriyor musunuz?
Evet, geçici lisanslar mevcuttur [Burada](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}