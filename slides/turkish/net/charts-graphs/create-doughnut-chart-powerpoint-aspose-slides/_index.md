---
"date": "2025-04-15"
"description": "Güçlü Aspose.Slides for .NET kütüphanesini kullanarak PowerPoint sunumlarında dinamik ve görsel olarak çekici halka grafiklerinin nasıl oluşturulacağını öğrenin."
"title": "Aspose.Slides for .NET Kullanarak PowerPoint'te Çörek Grafiği Nasıl Oluşturulur"
"url": "/tr/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET Kullanarak PowerPoint'te Çörek Grafiği Nasıl Oluşturulur
Görsel olarak ilgi çekici grafikler oluşturmak, etkili veri sunumu için olmazsa olmazdır. Halka grafikler, bir bütünün parçalarını göstermek için mükemmeldir ve bu da onları yüzde tabanlı veri görselleştirmesi için ideal hale getirir. Bu eğitim, güçlü Aspose.Slides for .NET kitaplığını kullanarak PowerPoint'te dinamik bir halka grafik oluşturma konusunda size rehberlik edecektir.

## giriiş
Sunumlar genellikle geleneksel çubuk veya çizgi grafiklerinin yetersiz kalabileceği karmaşık veri kümelerinin görsel temsillerini gerektirir. Halka grafiği, yüzde tabanlı verileri stil ve açıklıkla etkili bir şekilde iletmek için çok yönlü bir araç olarak ortaya çıkar. Bu eğitimde, Aspose.Slides for .NET'in bu grafikleri doğrudan PowerPoint içinde oluşturma sürecini nasıl basitleştirdiğini inceleyeceğiz.

**Ne Öğreneceksiniz:**
- Aspose.Slides'ı .NET için ayarlama
- Halka grafiği oluşturmaya ilişkin adım adım talimatlar
- Grafiğinize seriler ve kategoriler ekleme
- Gelişmiş netlik için veri etiketlerini yapılandırma
- Son sunumun kaydedilmesi

Sunularınızı özel halka grafiklerle zenginleştirmek için Aspose.Slides for .NET'i nasıl kullanabileceğinize bir göz atalım.

## Ön koşullar
Başlamadan önce aşağıdakilerin mevcut olduğundan emin olun:
- **Aspose.Slides for .NET kitaplığı**: NuGet üzerinden veya doğrudan indirilerek kullanılabilir.
- **Geliştirme Ortamı**.NET projeleri için Visual Studio önerilir.
- Temel C# bilgisi ve PowerPoint yapısına aşinalık.

## Aspose.Slides'ı .NET için Ayarlama
Grafik oluşturmaya başlamak için öncelikle projenizde Aspose.Slides kütüphanesini kurmanız gerekir. İşte onu kurmanın birkaç yolu:

**.NET CLI kullanımı:**

```bash
dotnet add package Aspose.Slides
```

**Paket Yöneticisi Konsolunu Kullanma:**

```powershell
Install-Package Aspose.Slides
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü aracılığıyla:**
"Aspose.Slides"ı arayın ve en son sürümü yükleyin.

Kurulduktan sonra projenizi kurmaya başlayabilirsiniz. Aspose.Slides'a yeniyseniz, sınırlamalar olmadan tüm yeteneklerini keşfetmek için geçici bir lisans veya ücretsiz deneme edinmeyi düşünün.

### Projenizi Başlatın
Uygulamanızda Aspose.Slides'ı nasıl başlatabileceğiniz aşağıda açıklanmıştır:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Bir Presentation sınıfı örneği oluşturun
        Presentation presentation = new Presentation();
        
        // Sunumu düzenleme kodunuz buraya gelir
        
        // Sunumu kaydet
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Uygulama Kılavuzu
### Bir Çörek Grafiği Oluşturma
#### Genel bakış
İlk olarak, bir PowerPoint slaydında boş bir halka grafiği oluşturacağız. Bu, veri ekleme ve görünümünü özelleştirmenin temeli olarak hizmet eder.

**Adım 1: Bir Çörek Grafiği Ekleyin**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // İlk slayda (10, 10) pozisyonuna (500, 500) boyutunda bir halka grafiği ekleyin
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Mevcut serileri ve kategorileri temizle
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Daha temiz bir görünüm için efsaneyi devre dışı bırakın
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Açıklama:**
- **Grafik ekle**: Slayda yeni bir halka grafiği ekler.
- **getChartDataWorkbook**: Grafikteki veri hücrelerine düzenleme amacıyla erişim sağlar.

### Seri ve Kategori Ekleme
#### Genel bakış
Daha sonra seriler ve kategoriler ekleyerek grafiğinizi anlamlı verilerle dolduracağız.

**Adım 2: Veri Serilerini Ekleyin**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Seri ekle
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Donut deliğini ve başlangıç açısını özelleştirme
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Kategorileri ekle
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Veri noktasının dolgusunu ve satırını biçimlendirme
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Açıklama:**
- **eklemek**: Grafiğe yeni seriler ve kategoriler ekler.
- **DonutDeliğiBoyutunuAyarla**:Çörek deliğinin boyutunu yapılandırarak görsel çekiciliğini arttırır.

### Veri Etiketlerini Yapılandırma
#### Genel bakış
Veri etiketleri grafik verilerinize bağlam sağlar. Bunları özelleştirerek okunabilirliği artıralım.

**Adım 3: Veri Etiketlerini Özelleştirin**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Veri etiketlerini özelleştirme
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Açıklama:**
- **IDataEtiketi**: Veri etiketlerini açıklık ve sunum açısından özelleştirir.
- **Merkez Metni Ayarla**, **gösterYüzde**: Metni ortalayarak ve yüzdeleri göstererek etiket okunabilirliğini artırın.

## Çözüm
Bu kılavuzu takip ederek, Aspose.Slides for .NET kullanarak PowerPoint'te dinamik bir halka grafiğinin nasıl oluşturulacağını öğrendiniz. Bu güçlü kitaplık, grafiklerinizi sunum ihtiyaçlarınıza göre tam olarak uyarlamanıza olanak tanıyan kapsamlı özelleştirmeye olanak tanır.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}