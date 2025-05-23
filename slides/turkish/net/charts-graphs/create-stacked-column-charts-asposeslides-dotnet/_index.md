---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET kullanarak görsel olarak ilgi çekici yüzde tabanlı yığılmış sütun grafikleri oluşturmayı öğrenin. Net veri görselleştirmesi için bu adım adım kılavuzu izleyin."
"title": "Aspose.Slides kullanarak .NET'te Yüzdeye Dayalı Yığılmış Sütun Grafikleri Nasıl Oluşturulur"
"url": "/tr/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for .NET kullanarak Yüzde Tabanlı Yığılmış Sütun Grafiği Nasıl Oluşturulur

## giriiş

Veri görselleştirme alanında, etkili karar alma için bilgileri açık ve etkili bir şekilde sunmak çok önemlidir. Karmaşık veri kümelerini sezgisel olarak görüntülemek için yüzdeye dayalı yığılmış sütun grafikleri idealdir. Bu kılavuz, sunum dosyalarını düzenlemek için tasarlanmış sağlam bir kütüphane olan Aspose.Slides for .NET kullanarak bu grafikleri oluşturmanızda size yol gösterecektir.

Bu eğitimi takip ederek şunları öğreneceksiniz:
- Grafik verilerinin ayarlanması ve sayı biçimlerinin yapılandırılması.
- Seri ekleme ve görünümlerini özelleştirme.
- Okunabilirliği artırmak için etiketleri biçimlendirme.

Dalmaya hazır mısınız? İhtiyacınız olan ön koşullarla başlayalım!

## Ön koşullar

Yüzde tabanlı yığılmış sütun grafiklerinizi oluşturmadan önce, ortamınızın doğru şekilde ayarlandığından emin olun. Şunlara ihtiyacınız olacak:

### Gerekli Kitaplıklar, Sürümler ve Bağımlılıklar
- **.NET için Aspose.Slides**: Bu kütüphanenin kurulu olduğundan emin olun.

### Çevre Kurulum Gereksinimleri
- .NET SDK'nın yüklü olduğu bir geliştirme ortamı.
- C# kodlarını çalıştırmak için Visual Studio veya uyumlu herhangi bir IDE.

### Bilgi Önkoşulları
- C# programlamanın temel bilgisi.
- .NET proje kurulumu ve paket yönetimi konusunda bilgi sahibi olmak.

## Aspose.Slides'ı .NET için Ayarlama

Aspose.Slides ile grafik oluşturmaya başlamak için öncelikle aşağıdaki yöntemlerden birini kullanarak kitaplığı yükleyin:

**.NET Komut Satırı Arayüzü**
```bash
dotnet add package Aspose.Slides
```

**Paket Yöneticisi**
```powershell
Install-Package Aspose.Slides
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü**
- "Aspose.Slides"ı arayın ve en son sürümü yükleyin.

### Lisans Edinme Adımları

Geçici bir lisans indirerek ücretsiz denemeye başlayın [Aspose'un web sitesi](https://purchase.aspose.com/temporary-license/)Sürekli kullanım için tam lisans satın almayı düşünebilirsiniz. 

Kurulum tamamlandıktan sonra projenizde Aspose.Slides'ı başlatın:
```csharp
using Aspose.Slides;
```

## Uygulama Kılavuzu

Ortam hazır olduğuna göre, yüzdeye dayalı yığılmış sütun grafiğinin oluşturulmasını adımlara ayıralım.

### Grafik Oluşturma ve Yapılandırma

#### Genel bakış
Bir örneğini oluşturun `Presentation` Slaytlarla çalışmak için olmazsa olmaz olan sınıf. Ardından, slaydınıza yığılmış bir sütun grafiği ekleyin ve yapılandırın.

#### Yığılmış Sütun Grafiği Ekleme
```csharp
// Bir Presentation sınıfı örneği oluşturun
document = new Presentation();

// İlk slayta referans alın
slide = document.Slides[0];

// (20, 20) konumuna (500x400) boyutunda PercentsStackedColumn grafiğini ekleyin
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Sayı Biçimini Yapılandırma
Verilerinizin yüzde olarak görüntülendiğinden emin olun:
```csharp
// Dikey eksen için sayı biçimini yapılandırın
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Sayı biçimini yüzdeye ayarla
```

#### Veri Serileri ve Noktaları Ekleme
Mevcut seri verilerini temizleyin ve yenilerini ekleyin:
```csharp
// Mevcut tüm seri verilerini temizle
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Erişim çizelgesi veri çalışma kitabı
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Yeni bir veri serisi "Kırmızılar" ekleyin
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Serinin dolgu rengini Kırmızı olarak ayarlayın
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// "Reds" serisi için etiket biçimi özelliklerini yapılandırın
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Yüzde biçimini ayarla
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Başka bir seri daha ekle "Blues"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Serinin dolgu rengini Mavi olarak ayarlayın
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Yüzde biçimini ayarla
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Sunumu Kaydetme
Sununuzu bir dosyaya kaydedin:
```csharp
// Sunumu PPTX formatında kaydedin
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Sorun Giderme İpuçları
- Tüm ad alanlarının doğru şekilde içe aktarıldığından emin olun.
- Özellik adlarında ve metot çağrılarında yazım hatalarını kontrol edin.
- Dosyaları kaydetmek için yollarınızın mevcut olduğunu ve doğru izinlere sahip olduğunu doğrulayın.

## Pratik Uygulamalar

İşte yüzdeye dayalı yığılmış sütun grafiklerinin değerli olabileceği bazı senaryolar:
1. **Satış Analizi**:Ürün performansının toplam satışlara oranını farklı bölgelerde görselleştirin.
2. **Bütçe Tahsisi**: Departmanların bütçelerini şirketin genel harcamalarına göre nasıl tahsis ettiğini gösterin.
3. **Pazar araştırması**: Tüketicilerin zaman içinde çeşitli ürün kategorilerine yönelik tercihlerini karşılaştırın.
4. **Eğitim Verileri**: Öğrencilerin farklı derslerdeki not dağılımlarını görüntüler.
5. **Sağlık İstatistikleri**: Birden fazla sağlık koşuluna ait hasta demografisini temsil eder.

## Performans Hususları

En iyi performans için şunları göz önünde bulundurun:
- Veri noktalarının sayısını gerekli olanla sınırlamak.
- Çalışma zamanı işlemlerini en aza indirmek için verileri önceden yükleme.
- Aspose.Slides for .NET ile verimli bellek yönetimi uygulamalarını kullanma.

## Çözüm

Tebrikler! Aspose.Slides for .NET kullanarak yüzde tabanlı yığılmış sütun grafiği oluşturmayı başarıyla öğrendiniz. Bu araç, karmaşık verileri daha anlaşılır ve görsel olarak çekici hale getirerek sunumları geliştirir.

Sonraki adımlar? Aspose.Slides'ta bulunan diğer grafik türlerini keşfedin veya bu işlevselliği daha büyük uygulamalara entegre edin. İyi kodlamalar!

## SSS Bölümü

**S1: Aspose.Slides'ı ücretsiz kullanabilir miyim?**
C1: Evet, Aspose.Slides'ın özelliklerini test etmek için ücretsiz denemeye başlayabilirsiniz.

**S2: Aspose.Slides for .NET tarafından hangi grafik türleri destekleniyor?**
A2: Pasta, çubuk, sütun, çizgi gibi çeşitli grafikleri destekler.

**S3: Aspose.Slides for .NET'i kullanmaya nasıl başlarım?**
A3: Yukarıda açıklandığı gibi NuGet veya .NET CLI kullanarak kütüphaneyi yükleyin. İlk grafiğinizi oluşturmak için dokümantasyonumuzu izleyin.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}