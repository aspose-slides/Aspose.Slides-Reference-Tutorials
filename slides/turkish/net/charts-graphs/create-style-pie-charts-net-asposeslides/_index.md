---
"date": "2025-04-15"
"description": "Aspose.Slides ile .NET sunumlarında pasta grafiği oluşturmayı otomatikleştirmeyi öğrenin ve veri görselleştirmeyi zahmetsizce geliştirin."
"title": "Aspose.Slides Kullanarak .NET Sunularında Pasta Grafikleri Nasıl Oluşturulur ve Özelleştirilir"
"url": "/tr/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Kullanarak .NET Sunularında Pasta Grafikleri Nasıl Oluşturulur ve Özelleştirilir

## giriiş
Etkili iletişim için, ister işte veri sunuyor olun ister son proje bulgularınızı sergiliyor olun, ilgi çekici ve bilgilendirici sunumlar oluşturmak çok önemlidir. Verileri görselleştirmenin etkili bir yolu, bir bütünün parçalarını özlü bir şekilde temsil edebilen pasta grafikleridir. Ancak, bu grafikleri PowerPoint gibi sunum yazılımlarında manuel olarak oluşturmak zaman alıcı olabilir ve dinamik güncellemeler için gereken esneklikten yoksun olabilir.

İşte tam bu noktada Aspose.Slides for .NET devreye giriyor. Bu kapsamlı kütüphane, sunumları programatik olarak oluşturmanıza, değiştirmenize ve biçimlendirmenize olanak tanır ve bu da iş akışlarını otomatikleştirmek ve sunumlar arasında tutarlılık sağlamak isteyen geliştiriciler için paha biçilmez bir araç haline getirir.

Bu eğitimde, sunumlarınızda pasta grafikleri oluşturmak ve özelleştirmek için Aspose.Slides for .NET'i nasıl kullanacağınızı keşfedeceğiz. Şunları nasıl yapacağınızı öğreneceksiniz:
- **Bir sunum oluşturun ve slaytlara erişin**
- **Pasta grafikleri ekleyin ve yapılandırın**
- **Grafik verilerini ve serilerini özelleştirin**
- **Stil pasta grafiği sektörleri**
- **Özel etiketler ekleyin**
- **Görüntü özelliklerini yapılandırın ve sunumu kaydedin**

Kolayca çarpıcı pasta grafikleri oluşturmaya hazır mısınız? Hadi başlayalım!

## Ön koşullar
Başlamadan önce aşağıdaki kurulumların yapıldığından emin olun:

### Gerekli Kütüphaneler
- Aspose.Slides for .NET (21.11 veya üzeri sürüm önerilir)

### Çevre Kurulumu
- .NET Framework veya .NET Core/5+/6+ çalıştıran bir geliştirme ortamı
- Visual Studio gibi bir kod düzenleyici

### Bilgi Önkoşulları
- C# programlamanın temel anlayışı
- Nesne yönelimli kavramlara aşinalık

## Aspose.Slides'ı .NET için Ayarlama
Başlamak için Aspose.Slides kitaplığını yüklemeniz gerekir. Bunu aşağıdaki yöntemlerden herhangi birini kullanarak yapabilirsiniz:

**.NET Komut Satırı Arayüzü**
```bash
dotnet add package Aspose.Slides
```

**Paket Yöneticisi Konsolu**
```powershell
Install-Package Aspose.Slides
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü**
- Projenizi Visual Studio’da açın.
- "Araçlar" > "NuGet Paket Yöneticisi" > "Çözüm için NuGet Paketlerini Yönet" seçeneğine gidin.
- "Aspose.Slides"ı arayın ve en son sürümü yükleyin.

### Lisans Edinme Adımları
Aspose.Slides'ı kullanmak için geçici bir lisans indirerek ücretsiz denemeye başlayabilirsiniz. Ziyaret edin [Aspose'un web sitesi](https://purchase.aspose.com/temporary-license/) edinmek için. Devam eden kullanım için tam lisans satın almayı düşünün.

### Temel Başlatma ve Kurulum
Kurulum tamamlandıktan sonra PPTX dosyanızı temsil eden Presentation sınıfını başlatın:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Uygulama Kılavuzu
Pasta grafiği oluşturma sürecini yönetilebilir bölümlere ayıracağız. Her bölüm belirli bir özelliğe odaklanacak şekilde tasarlanmıştır ve bu sayede bilginizi kademeli olarak artırabilirsiniz.

### Bir Sunum Oluşturun ve Slaytlara Erişin
**Genel Bakış:** Yeni bir sunum oluşturarak ve ilk slaydına erişerek başlayın. Bu, grafikler ve diğer öğeleri eklemek için ortamı hazırlar.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // PPTX dosyasını temsil eden bir Sunum sınıfı örneği oluşturun
    Presentation presentation = new Presentation();
    
    // İlk slayda erişin
    ISlide slides = presentation.Slides[0];
}
```

### Pasta Grafiği Ekle ve Yapılandır
**Genel Bakış:** Slaydınıza pasta grafiği eklemeyi ve bağlam için başlığını ayarlamayı öğrenin.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // PPTX dosyasını temsil eden bir Sunum sınıfı örneği oluşturun
    Presentation presentation = new Presentation();
    
    // İlk slayda erişin
    ISlide slides = presentation.Slides[0];
    
    // Slayda varsayılan verilerle grafik ekleyin
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Ayar çizelgesi Başlığı
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Grafik Verilerini ve Serilerini Özelleştirin
**Genel Bakış:** Veri kategorilerini ve serilerini özel gereksinimlerinize uyacak şekilde özelleştirin.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // PPTX dosyasını temsil eden bir Sunum sınıfı örneği oluşturun
    Presentation presentation = new Presentation();
    
    // İlk slayda erişin
    ISlide slides = presentation.Slides[0];
    
    // Slayda varsayılan verilerle grafik ekleyin
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // İlk seriyi Değerleri Göster olarak ayarlayın
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Grafik veri sayfasının indeksini ayarlama
    int defaultWorksheetIndex = 0;
    
    // Grafik veri çalışma sayfasını alma
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Varsayılan olarak oluşturulan serileri ve kategorileri sil
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Yeni kategoriler ekleniyor
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Yeni seri ekleniyor
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Şimdi seri verileri dolduruluyor
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Pasta Grafiği Sektör Stillerini Özelleştir
**Genel Bakış:** Görsel çekiciliği artırmak ve önemli veri noktalarını vurgulamak için pasta grafiğinizin her bir bölümünü ayrı ayrı şekillendirin.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // PPTX dosyasını temsil eden bir Sunum sınıfı örneği oluşturun
    Presentation presentation = new Presentation();
    
    // İlk slayda erişin
    ISlide slides = presentation.Slides[0];
    
    // Slayda varsayılan verilerle grafik ekleyin
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Seriyi grafikten al
    IChartSeries series = chart.ChartData.Series[0];
    
    // Serideki her veri noktası için sektör stillerinin özelleştirilmesi
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Sektör sınırının ayarlanması
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Sektör sınırının ayarlanması
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Sektör sınırının ayarlanması
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Pasta Grafiğine Özel Etiketler Ekleme
**Genel Bakış:** Daha net veri gösterimi için özel etiketler ekleyerek pasta grafiğinizi geliştirin.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // Etiket konumunu gerektiği gibi ayarlayın
    }
}
```

### Çözüm
Artık Aspose.Slides kullanarak .NET sunumlarında pasta grafikleri oluşturmayı ve özelleştirmeyi öğrendiniz. Bu otomasyon, veri görselleştirme çabalarınızı önemli ölçüde iyileştirebilir, zamandan tasarruf sağlayabilir ve sunumlar arasında tutarlılık sağlayabilir.

Aspose.Slides for .NET'in yeteneklerini daha fazla keşfetmek için, diğer grafik türleri oluşturma veya slaytlarınıza daha karmaşık tasarım öğeleri entegre etme gibi ek özellikleri incelemeyi düşünün.

Keyifli kodlamalar!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}