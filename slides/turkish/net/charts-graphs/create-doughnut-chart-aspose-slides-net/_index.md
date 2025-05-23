---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET kullanarak dinamik halka grafikleri oluşturmayı öğrenin. Kurulum ve gelişmiş özellikler dahil olmak üzere adım adım talimatlar için bu kılavuzu izleyin."
"title": "Adım Adım Kılavuz&#58; Aspose.Slides .NET ile Halka Grafiği Oluşturun | Grafikler ve Şemalar"
"url": "/tr/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Adım Adım Kılavuz: Aspose.Slides .NET ile Halka Grafiği Oluşturun

## giriiş

Ekibinize veya müşterilerinize veri analizi sonuçlarını sunmakla görevlendirildiğinizi ve bilgileri görselleştirmek için ilgi çekici bir yola ihtiyacınız olduğunu düşünün. Ham sayıları kolayca sindirilebilir içgörülere dönüştürebilen çok yönlü bir araç olan halka grafiğine girin. .NET için Aspose.Slides ile sunum slaytlarınızda özel bir halka grafiği oluşturmak basit ve etkilidir. Bu kılavuz, Aspose.Slides'ı kullanarak görsel olarak çekici bir halka grafiği oluşturmanıza ve özel seri yapılandırmalarına sahip olmanıza yardımcı olacaktır.

**Ne Öğreneceksiniz:**
- Aspose.Slides for .NET ile geliştirme ortamınızı kurma
- Sunumlarda halka grafikleri oluşturma ve özelleştirme
- Kategori adları ve lider çizgileri gibi gelişmiş özelliklerin uygulanması
- Büyük veri kümeleri için performansı optimize etme

Başlamak için ihtiyaç duyduğunuz ön koşullara bir göz atalım.

## Ön koşullar

Bu özelliği uygulamadan önce, geliştirme ortamınızın düzgün bir şekilde ayarlandığından emin olun. Bu eğitim, .NET programlamanın temel bilgisine ve Visual Studio veya benzer bir IDE'ye aşinalığa sahip olduğunuzu varsayar.

### Gerekli Kütüphaneler ve Sürümler
- **.NET için Aspose.Slides**: En son sürümle uyumluluğu kontrol ederek emin olun [resmi belgeler](https://reference.aspose.com/slides/net/).

### Çevre Kurulum Gereksinimleri
- Çalışan bir .NET ortamı.
- Visual Studio gibi bir kod düzenleyicisine erişim.

### Bilgi Önkoşulları
- C# ve .NET framework'üne dair temel bilgi.
- Sunum yazılımı kavramlarına aşinalık (isteğe bağlı ancak yararlı).

## Aspose.Slides'ı .NET için Ayarlama

Projenizde Aspose.Slides'ı kullanmaya başlamak için NuGet aracılığıyla yüklemeniz gerekir. Kullanılabilir yöntemler şunlardır:

**.NET CLI kullanımı:**
```bash
dotnet add package Aspose.Slides
```

**Paket Yöneticisini Kullanma:**
```powershell
Install-Package Aspose.Slides
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü:**
"Aspose.Slides"ı arayın ve en son sürümü yükleyin.

### Lisans Edinme Adımları

1. **Ücretsiz Deneme**: Bir ile başlayın [ücretsiz deneme](https://releases.aspose.com/slides/net/) temel işlevleri keşfetmek için.
2. **Geçici Lisans**: Değerlendirme amacıyla tam özelliklere erişmeniz gerekiyorsa, şu adresi ziyaret ederek geçici bir lisans edinin: [Burada](https://purchase.aspose.com/temporary-license/).
3. **Satın almak**: Ticari kullanım için, şu adresten bir lisans satın alın: [Aspose web sitesi](https://purchase.aspose.com/buy).

Kurulum ve lisanslama tamamlandıktan sonra projenizde Aspose.Slides'ı başlatın:
```csharp
using Aspose.Slides;

// .NET için Aspose.Slides'ı Başlatın
var presentation = new Presentation();
```

## Uygulama Kılavuzu

### Yeni Bir Sunum Oluşturma ve Bir Halka Grafiği Ekleme

#### Genel bakış
Yeni bir sunum oluşturarak ve ilk slayda bir halka grafiği ekleyerek başlayacağız. Bu bölüm mevcut bir sunumu yüklemeyi, slaytlara erişmeyi ve grafik eklemeyi kapsar.

**Adım 1: Bir Sunum Yükleyin veya Oluşturun**
Öncelikle belge dizininizi belirtin ve mevcut bir sunumu yükleyin:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Mevcut bir dosyanız yoksa, yeni bir tane oluşturun `new Presentation()`.

**Adım 2: İlk Slayta Erişim**
Grafiğimizi ekleyeceğimiz ilk slayda erişin:
```csharp
ISlide slide = pres.Slides[0];
```

**Adım 3: Bir Çörek Grafiği Ekleyin**
Belirtilen koordinatlarda ve boyutlarda bir halka grafiği ekleyin:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Veri Çalışma Kitabını Yapılandırma

#### Genel bakış
Bu bölümde halka grafiğinizle ilişkili veri çalışma kitabının nasıl yapılandırılacağı açıklanmaktadır.

**Adım 4: Mevcut Verilere Erişim ve Temizleme**
Tablonun veri çalışma kitabına erişin. Sonra mevcut tüm serileri veya kategorileri temizleyin:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Adım 5: Efsaneyi Devre Dışı Bırakın ve Seri Ekleyin**
Tabloyu temiz tutmak için efsaneyi devre dışı bırakın, ardından özel yapılandırmalarla 15 seriye kadar ekleyin:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Kategoriler ve Veri Noktaları Ekleme

#### Genel bakış
Şimdi grafiği her seri için kategoriler ve veri noktalarıyla dolduralım.

**Adım 6: Kategorileri ekleyin**
15 kategori eklemek için döngüye girin:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Adım 7: Veri Noktalarını Doldurun**
Mevcut kategorideki her seri için veri noktaları ekleyin:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Görünümü özelleştir
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Son seri için etiket biçimini yapılandırın
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Etiket görüntüsünü yapılandır
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Sunumu Kaydetme

**Adım 8: Dosyayı Kaydedin**
Son olarak sununuzu belirtilen dizine kaydedin:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}