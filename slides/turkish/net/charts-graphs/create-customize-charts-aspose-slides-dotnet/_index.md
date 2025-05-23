---
"date": "2025-04-15"
"description": "Aspose.Slides for .NET kullanarak yüzdeleri veri etiketleri olarak görüntüleme dahil olmak üzere grafiklerin nasıl oluşturulacağını ve özelleştirileceğini öğrenin. Bu adım adım kılavuzu izleyin."
"title": "Aspose.Slides .NET ile Grafikler Nasıl Oluşturulur ve Özelleştirilir? Yüzdeleri Etiket Olarak Görüntüleme"
"url": "/tr/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides .NET ile Grafikler Nasıl Oluşturulur ve Özelleştirilir: Yüzdeleri Etiket Olarak Görüntüleme

## giriiş

Verileri etkili bir şekilde sunmak birçok alanda önemlidir ve grafikler karmaşık bilgileri net görsellere dönüştürerek hayati bir rol oynar. Mükemmel grafiği oluşturmak, etiketlerde yüzdeleri görüntüleme gibi özelleştirme görevlerini içerir; bu görev Aspose.Slides for .NET ile daha kolay hale getirildi. Bu kitaplık, PowerPoint sunumlarında grafik oluşturma ve düzenleme sürecini basitleştirir.

Bu eğitimde, sıfırdan yığılmış bir sütun grafiği oluşturmak ve yüzde değerlerini veri etiketleri olarak görüntüleyerek özelleştirmek için Aspose.Slides for .NET'i nasıl kullanacağınızı öğreneceksiniz. Bu adımları izleyerek slaytlarınızı hassas ve görsel olarak çekici veri gösterimleriyle geliştireceksiniz.

**Ne Öğreneceksiniz:**
- .NET için Aspose.Slides'ı Başlatma
- Yığılmış sütun grafiği oluşturma
- Veri etiketlerinde yüzdelerin hesaplanması ve görüntülenmesi
- Grafik performansının en iyi uygulamalarını optimize etme

Uygulamaya geçmeden önce, başlamak için her şeyin hazır olduğundan emin olalım.

## Ön koşullar

Bu eğitimi etkili bir şekilde takip edebilmek için şunlara sahip olduğunuzdan emin olun:
- **.NET Çekirdek SDK'sı** makinenize kurulu.
- C# ve .NET uygulama geliştirme konusunda temel anlayış.
- C# kodu yazmak ve çalıştırmak için Visual Studio veya benzeri bir IDE.

Grafik oluşturmak için Aspose.Slides for .NET'e ihtiyacınız olacak, bu nedenle aşağıda açıklandığı gibi ayarladığınızdan emin olun.

## Aspose.Slides'ı .NET için Ayarlama

Aspose.Slides for .NET, PowerPoint sunumlarıyla programatik olarak çalışmanıza olanak tanıyan güçlü bir kütüphanedir. İşte projenize nasıl ekleyebileceğiniz:

### Kurulum

**.NET Komut Satırı Arayüzü:**
```bash
dotnet add package Aspose.Slides
```

**Paket Yöneticisi Konsolu:**
```powershell
Install-Package Aspose.Slides
```

**NuGet Paket Yöneticisi Kullanıcı Arayüzü:** 
- NuGet Paket Yöneticisini açın ve "Aspose.Slides"ı arayın. En son sürümü yükleyin.

### Lisans Edinimi

Aspose.Slides'ı tam olarak kullanmak için ücretsiz denemeyle başlayın. Uzun süreli kullanım için geçici bir lisans edinmeyi veya şuradan bir tane satın almayı düşünün: [Aspose](https://purchase.aspose.com/buy)Lisansınızı proje ortamınızda kurmak için onların yönergelerini izleyin.

### Temel Başlatma

Kurulduktan sonra, başlatın `Presentation` Sınıf slayt oluşturmaya başlayacak:
```csharp
using Aspose.Slides;

// Sunum sınıf örneğini başlat
tPresentation presentation = new Presentation();
```

Şimdi Aspose.Slides for .NET kullanarak grafik oluşturma ve özelleştirme özelliğimizi uygulamaya geçelim.

## Uygulama Kılavuzu

### Yığılmış Sütun Grafiği Oluşturun

Amacımız, yığılmış bir sütun grafiği oluşturmak ve bunu veri etiketleri olarak yüzdeleri göstererek özelleştirmektir. İşte nasıl:

#### Sunumu Başlat

Bir örnek oluşturarak başlayın `Presentation`:
```csharp
using Aspose.Slides;

// Sunum sınıf örneğini başlat
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Slayda Bir Grafik Ekleyin

İlk slaydınıza belirtilen koordinatlarda ve boyutlarda yığılmış sütun grafiği ekleyin:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Bu satır bir `StackedColumn` (20, 20) pozisyonunda, genişliği ve yüksekliği 400 olan grafik.

#### Yüzde Hesaplaması için Toplam Değerleri Hesaplayın

Yüzdeleri görüntülemek için, tüm serilerdeki her kategori için toplam değeri hesaplayın:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Her kategori için tüm serilerin değerlerini topla
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Yüzde Değerlerini Göstermek İçin Veri Etiketlerini Özelleştirin

Daha sonra her seriyi tekrar gözden geçirin ve veri etiketlerini özelleştirin:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Yüzdeyi hesapla
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Çakışmayı önlemek için metni temizleyin
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Varsayılan veri etiketlerini gizlemek için etiket biçimini yapılandırın
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Bu bölüm, her veri noktası için yüzdeyi hesaplar ve varsayılan etiketlerle çakışma olmamasını sağlayarak bunu özel bir etiket olarak ayarlar.

#### Sunumu Kaydet

Son olarak, sonucu görüntülemek için sununuzu kaydedin:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Pratik Uygulamalar

Yüzdeleri grafiklerde göstermek özellikle şu gibi durumlarda faydalı olabilir:
1. **Finansal Raporlama:** Portföy dağılımlarını veya yatırım getirilerini yüzde olarak gösterin.
2. **Satış Analizi:** Bölgeler genelindeki performansı vurgulamak için pazar payı verilerini yüzde olarak gösterin.
3. **Anket Sonuçları:** Daha iyi görsel karşılaştırma için anket yanıtlarını yüzde olarak görüntüleyin.
4. **Proje Yönetimi:** Kaynak dağıtımını göstermek için yüzdelik dilimler içeren pasta grafikleri kullanın.
5. **Eğitim:** İstatistiksel kavramları net, yüzdeye dayalı görseller kullanarak açıklayın.

Bu özelleştirilmiş grafiklerin CRM veya ERP gibi sistemlere entegre edilmesi, gösterge panellerini ve raporları geliştirerek karar alma süreçlerine yardımcı olabilir.

## Performans Hususları

Özellikle büyük veri kümeleriyle Aspose.Slides for .NET ile çalışırken:
- **Bellek Yönetimi:** Belleği boşaltmak için sunum nesnelerini uygun şekilde elden çıkarın. `using` Uygun durumlarda ifadeler.
- **Verimli Veri İşleme:** Hesaplama yükünü azaltmak için mümkün olduğunda hesaplamaları döngülerin dışında gerçekleştirin.
- **Yük Dengeleme:** Web uygulamaları için, eş zamanlı grafik oluşturma istekleri için sunucu kaynaklarının yeterli şekilde sağlandığından emin olun.

## Çözüm

Bu eğitim, yüzde değerlerini etiketler olarak görüntüleyerek Aspose.Slides for .NET kullanarak grafikler oluşturmayı ve özelleştirmeyi kapsıyordu. Bu tekniklerde ustalaşmak, sunumlarınızı ayrıntılı ve görsel olarak çekici veri gösterimleriyle geliştirmenize olanak tanır.

Bir sonraki adım olarak, Aspose.Slides'ta bulunan diğer grafik türlerini ve özelleştirme seçeneklerini keşfedin. Farklı veri kümeleriyle deney yaparak bunları, içgörüleri açıkça ileten güçlü görsellere dönüştürün.

## SSS Bölümü

**S1: Aspose.Slides for .NET ile grafik oluştururken büyük veri kümelerini nasıl işlerim?**
A1: Büyük veri kümeleri için hesaplamaları optimize edin ve verimli bellek yönetimi teknikleri kullanın. Bellek aşırı yüklenmesini önlemek için işleme görevlerini parçalayın.

**S2: Aspose.Slides for .NET'i bir web uygulamasında kullanabilir miyim?**
C2: Evet, ASP.NET uygulamalarına entegre edilebilir. Optimum performans için uygun sunucu kaynak tahsisini sağlayın.

**S3: Aspose.Slides ile oluşturulan grafikleri diğer formatlara aktarmak mümkün müdür?**
A3: Kesinlikle! Özelleştirilmiş grafiklerinizi içeren sunumları, kütüphanenin yeteneklerini kullanarak PDF ve resim dosyaları gibi çeşitli formatlara aktarabilirsiniz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}