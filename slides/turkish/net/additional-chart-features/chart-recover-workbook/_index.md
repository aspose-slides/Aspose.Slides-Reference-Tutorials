---
"description": "Aspose.Slides for .NET kullanarak PowerPoint sunumlarındaki bir grafikten bir çalışma kitabını nasıl kurtaracağınızı öğrenin. Verileri verimli bir şekilde çıkarmak için adım adım kılavuzumuzu izleyin."
"linktitle": "Çalışma Kitabını Grafikten Kurtar"
"second_title": "Aspose.Slides .NET PowerPoint İşleme API'si"
"title": "Aspose.Slides .NET'i Grafikten Çalışma Kitabını Kurtarmak İçin Nasıl Kullanabilirsiniz"
"url": "/tr/net/additional-chart-features/chart-recover-workbook/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides .NET'i Grafikten Çalışma Kitabını Kurtarmak İçin Nasıl Kullanabilirsiniz


.NET'te PowerPoint sunumlarıyla çalışmak istiyorsanız, Aspose.Slides for .NET hedeflerinize ulaşmanıza yardımcı olabilecek güçlü bir kütüphanedir. Bu eğitimde, Aspose.Slides for .NET kullanarak bir PowerPoint sunumundaki bir grafikten bir çalışma kitabını kurtarma sürecinde size rehberlik edeceğiz. Bu güçlü özellik, sunumlarınızdaki grafiklerden veri çıkarmanız gerektiğinde faydalı olabilir. Süreci, takip etmesi kolay adımlara bölerek bu görevi nasıl başaracağınıza dair net bir anlayışa sahip olmanızı sağlayacağız.

## Ön koşullar

Başlamadan önce aşağıdaki ön koşulların mevcut olduğundan emin olun:

### 1. .NET için Aspose.Slides

.NET geliştirme ortamınızda Aspose.Slides for .NET yüklü ve ayarlanmış olmalıdır. Henüz yapmadıysanız, web sitesinden indirip yükleyebilirsiniz.

[.NET için Aspose.Slides'ı indirin](https://releases.aspose.com/slides/net/)

### 2. PowerPoint Sunumu

Çalışma kitabını kurtarmak istediğiniz bir grafik içeren bir PowerPoint sunumuna ihtiyacınız olacak. Sunum dosyanızın hazır olduğundan emin olun.

## Gerekli Ad Alanlarını İçe Aktarma

Bu adımda, Aspose.Slides for .NET ile etkili bir şekilde çalışmak için gerekli ad alanlarını içe aktarmanız gerekecektir.

### Adım 1: Ad Alanlarını İçe Aktar

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Şimdi, bir PowerPoint sunumundaki bir grafikten çalışma kitabını kurtarma sürecini birden fazla adıma bölelim.

## Adım 1: Belge Dizinini Tanımlayın

```csharp
// Belgeler dizinine giden yol.
string dataDir = "Your Document Directory";
```

Bu adımda PowerPoint sunumunuzun bulunduğu dizini belirtmeniz gerekiyor.

## Adım 2: Sunumu Yükleyin ve Çalışma Kitabı Kurtarmayı Etkinleştirin

```csharp
string pptxFile = Path.Combine(dataDir, "YourPresentation.pptx");
string outPptxFile = Path.Combine(RunExamples.OutPath, "RecoveredWorkbook.pptx");

LoadOptions lo = new LoadOptions();
lo.SpreadsheetOptions.RecoverWorkbookFromChartCache = true;

using (Presentation pres = new Presentation(pptxFile, lo))
{
    // Grafik kurtarma kodunuz buraya gelir
    pres.Save(outPptxFile, SaveFormat.Pptx);
}
```

Bu adımda, PowerPoint sunumunu belirtilen dosyadan yüklersiniz ve grafik önbelleğinden çalışma kitabı kurtarmayı etkinleştirirsiniz. `LoadOptions` nesne bu amaçla kullanılır.

## Adım 3: Grafik Verilerine Erişim ve Bunlarla Çalışma

```csharp
IChart chart = pres.Slides[0].Shapes[0] as IChart;
IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;
```

Bu adımda, ilk slayttaki grafiğe erişirsiniz ve grafik veri çalışma kitabını alırsınız. Artık çalışma kitabı verileriyle gerektiği gibi çalışabilirsiniz.

## Çözüm

Bu eğitimde, bir PowerPoint sunumundaki bir grafikten bir çalışma kitabını kurtarmak için Aspose.Slides for .NET'in nasıl kullanılacağını gösterdik. Bu kılavuzda özetlenen adımları izleyerek, sunumlarınızdan verileri verimli bir şekilde çıkarabilir ve bunları özel ihtiyaçlarınız için kullanabilirsiniz.

Herhangi bir sorunuz varsa veya herhangi bir sorunla karşılaşırsanız, Aspose.Slides topluluğundan yardım istemekten çekinmeyin. [Aspose.Slides Forum](https://forum.aspose.com/)Aspose.Slides for .NET yolculuğunuzda size yardımcı olmak için oradalar.

## Sıkça Sorulan Sorular

### 1. Aspose.Slides for .NET nedir?

Aspose.Slides for .NET, Microsoft PowerPoint dosyalarıyla çalışmak için güçlü bir .NET kütüphanesidir ve sunumları programlı bir şekilde oluşturmanıza, düzenlemenize ve dönüştürmenize olanak tanır.

### 2. Satın almadan önce Aspose.Slides for .NET'i deneyebilir miyim?

Evet, Aspose.Slides for .NET'in özelliklerini ve yeteneklerini değerlendirmek için ücretsiz deneme sürümünü edinebilirsiniz. [Ücretsiz denemeyi buradan edinin](https://releases.aspose.com/).

### 3. Aspose.Slides for .NET belgelerini nerede bulabilirim?

Aspose.Slides for .NET belgelerine erişebilirsiniz [Burada](https://reference.aspose.com/slides/net/)Detaylı bilgi, örnekler ve API referansları içerir.

### 4. Aspose.Slides for .NET için lisansı nasıl satın alabilirim?

Aspose.Slides for .NET için bir lisans satın almak üzere Aspose web sitesini ziyaret edin ve aşağıdaki bağlantıyı kullanın: [.NET için Aspose.Slides'ı satın alın](https://purchase.aspose.com/buy).

### 5. SEO optimizasyonu için maksimum başlık uzunluğu nedir?

SEO optimizasyonu için başlığınızı arama motoru sonuçlarında düzgün görüntülenmesini sağlamak amacıyla 60 karakterin altında tutmanız önerilir.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}