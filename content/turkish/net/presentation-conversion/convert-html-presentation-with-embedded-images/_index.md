---
title: Gömülü Resimlerle HTML Sunumunu Dönüştürün
linktitle: Gömülü Resimlerle HTML Sunumunu Dönüştürün
second_title: Aspose.Slides .NET PowerPoint İşleme API'si
description: Aspose.Slides for .NET'i kullanarak HTML sunumlarını gömülü görsellerle zahmetsizce dönüştürün. PowerPoint dosyalarını sorunsuz bir şekilde oluşturun, özelleştirin ve kaydedin.
type: docs
weight: 11
url: /tr/net/presentation-conversion/convert-html-presentation-with-embedded-images/
---
## Gömülü Görüntülerle HTML Sunumunu Dönüştürmeye Giriş 

Bu kılavuzda, Aspose.Slides for .NET'i kullanarak gömülü görseller içeren bir HTML sunumunu PowerPoint sunumu (PPTX) formatına dönüştürme sürecini anlatacağız. Aspose.Slides, PowerPoint sunumlarıyla programlı olarak çalışmanıza olanak tanıyan güçlü bir kütüphanedir. 

## Önkoşullar
Başlamadan önce aşağıdakilerin yerinde olduğundan emin olun:
- Visual Studio veya başka herhangi bir .NET geliştirme ortamı kurulu.
-  Aspose.Slides for .NET kitaplığı. Şuradan indirebilirsiniz[Burada](https://downloads.aspose.com/slides/net).
- C# ve .NET geliştirme konusunda temel bilgiler.

## Adımlar

1. Yeni bir C# projesi oluşturun:
   Visual Studio'nuzu açın ve yeni bir C# projesi oluşturun.

2. Aspose.Slides for .NET'i yükleyin:
   Aspose.Slides for .NET kitaplığını projenize NuGet Paket Yöneticisi'ni kullanarak veya indirilen DLL dosyasına bir referans ekleyerek yükleyin.

3. Gerekli ad alanlarını ekleyin:
   Kod dosyanıza gerekli ad alanlarını ekleyin:
   ```csharp
   using Aspose.Slides;
   using Aspose.Slides.Export;
   using System.IO;
   ```

4. HTML içeriğini yükleyin:
   Sununun HTML içeriğini bir dizeye yükleyin. HTML'yi bir dosyadan veya bir web kaynağından alabilirsiniz.
   ```csharp
   string htmlContent = File.ReadAllText("path_to_your_html_file.html");
   ```

5. Yeni bir sunu oluşturun:
    Yeni bir örneğini oluşturun`Presentation` sınıf.
   ```csharp
   using Presentation presentation = new Presentation();
   ```

6. HTML içeriğine sahip slaytlar ekleyin:
   Sunuya slaytlar ekleyin ve her slayt için HTML içeriğini ayarlayın.
   ```csharp
   ISlideCollection slides = presentation.Slides;

   // Slayt oluştur
   ISlide slide = slides.AddEmptySlide();

   // Slayta HTML içeriği ekleme
   IAutoShape textShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 600, 400);
   textShape.TextFrame.Text = htmlContent;
   ```

7. Sunuyu kaydedin:
   Sunuyu PPTX formatında kaydedin.
   ```csharp
   presentation.Save("output_presentation.pptx", SaveFormat.Pptx);
   ```

8. Uygulamayı çalıştırın:
   Uygulamanızı oluşturun ve çalıştırın. Gömülü görüntüler içeren HTML sunumunu bir PowerPoint sunumuna dönüştürecektir.

## Örnek Kod

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
using System.IO;

namespace HTMLToPPTConversion
{
    class Program
    {
        static void Main(string[] args)
        {
            // Dosyadan HTML içeriğini yükle
            string htmlContent = File.ReadAllText("path_to_your_html_file.html");

            // Yeni bir sunu oluşturma
            using Presentation presentation = new Presentation();

            // HTML içeriğine sahip bir slayt ekleyin
            ISlide slide = presentation.Slides.AddEmptySlide();
            IAutoShape textShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 600, 400);
            textShape.TextFrame.Text = htmlContent;

            // Sunuyu PPTX formatında kaydedin
            presentation.Save("output_presentation.pptx", SaveFormat.Pptx);
        }
    }
}
```

## Çözüm

Aspose.Slides for .NET ile HTML sunumlarını gömülü görsellerle PowerPoint'e dönüştürmek artık çok kolay. Bu kitaplık süreci kolaylaştırır ve dönüşümün hassas bir şekilde yönetilmesi için kapsamlı araçlar sağlar.

## SSS'ler

### HTML sunumuna harici görselleri nasıl ekleyebilirim?

HTML sununuz harici görseller içeriyorsa görseller için doğru URL'leri sağladığınızdan emin olun. Aspose.Slides, HTML içeriğini slayda eklediğinizde bu görsellerin yerleştirilmesini otomatik olarak gerçekleştirecektir.

### Dönüştürülen slaytların görünümünü özelleştirebilir miyim?

Evet, Aspose.Slides kütüphanesinin sağladığı çeşitli özellik ve yöntemleri kullanarak dönüştürülen slaytların görünümünü özelleştirebilirsiniz. Yazı tiplerini, renkleri, stilleri ve daha fazlasını değiştirebilirsiniz.

### Aspose.Slides for .NET'in tam belgelerini nerede bulabilirim?

Aspose.Slides for .NET'in tüm belgelerini ve API referansını bulabilirsiniz[Burada](https://reference.aspose.com/slides/net).

### Aspose.Slides for .NET'in en son sürümünü nereden indirebilirim?

 Aspose.Slides for .NET'in en son sürümünü Aspose sürümler sayfasından indirebilirsiniz:[Aspose.Slides for .NET'i indirin](https://releases.aspose.com/slides/net).