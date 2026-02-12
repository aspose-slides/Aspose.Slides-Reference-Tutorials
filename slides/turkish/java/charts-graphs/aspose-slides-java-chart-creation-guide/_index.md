---
date: '2026-02-12'
description: Aspose.Slides for Java kullanarak grafik oluşturmayı ve grafikleri yönetmeyi
  öğrenin. Bu öğreticide, kümelenmiş sütun grafiği oluşturma, veri serilerini işleme
  ve görselleştirmeyi özelleştirme gösterilmektedir.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Aspose.Slides ile Java''da Grafik Oluşturma: Kapsamlı Bir Rehber'
url: /tr/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

- Keep URLs unchanged.

- Keep "Aspose.Slides for Java" as is (technical term). Keep "Clustered column chart" maybe keep as is but can translate? Technical term maybe keep English. The rule: keep technical terms in English, e.g., API, SDK, class names. "Clustered column chart" is a chart type; maybe keep English. We'll keep as is.

- Translate "Quick Answers" etc.

- Ensure formatting.

Let's craft.

Also note "step‑by‑step guide" etc.

Make sure to keep markdown.

Proceed.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose.Slides ile Grafik Nasıl Oluşturulur

## Java'da Grafik Oluşturma: Giriş
Dinamik sunumlar oluştururken verileri grafiklerle görselleştirmek sıkça gerekir. **Aspose.Slides for Java** ile **grafik oluşturma** nesnelerini zahmetsizce **clustered column chart** ekleyebilir, netliği artırabilir ve izleyiciniz üzerinde daha güçlü bir etki bırakabilirsiniz. Bu öğreticide kütüphaneyi kurma, **create clustered column chart** ekleme, serileri yönetme ve negatif veri noktalarını koşullu olarak tersine çevirme adımlarını göstereceğiz.

**Öğrenecekleriniz**
- Aspose.Slides for Java nasıl kurulur.
- Sunumunuza **clustered column chart** nasıl **create clustered column chart** eklenir.
- Grafik serileri ve veri noktaları nasıl yönetilir.
- Daha iyi görselleştirme için negatif veri noktaları nasıl koşullu olarak tersine çevrilir.
- Sunum güvenli bir şekilde nasıl kaydedilir.

### Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** Aspose.Slides for Java.
- **Hangi grafik türü gösteriliyor?** Clustered column chart.
- **Negatif değerleri tersine çevirebilir miyim?** Evet, `invertIfNegative` kullanarak.
- **Hangi Java sürümü gerekiyor?** JDK 16 veya daha yenisi.
- **Üretim için lisans gerekli mi?** Evet, geçerli bir Aspose lisansı gerekir.

## Clustered Column Chart Nedir?
Clustered column chart, her kategori için birden fazla veri serisini yan yana gösterir ve gruplar arasındaki değerleri karşılaştırmayı kolaylaştırır. Finansal raporlar, satış panoları ve birden fazla metriği karşılaştırmanız gereken her senaryo için idealdir.

## Aspose.Slides ile Grafik Oluşturmayı Neden Kullanmalısınız?
- **Tam kontrol**: Grafik görünümünü PowerPoint UI'ına bağımlı olmadan yönetebilirsiniz.
- **Programatik oluşturma**: Otomatik raporlama hatları oluşturmanıza olanak tanır.
- **Çapraz platform**: Kodunuz herhangi bir Java uyumlu sistemde çalışır.
- **Zengin API**: Renkler, veri etiketleri, tersine çevirme vb. gibi ince ayarlar yapabilirsiniz.

## Önkoşullar
1. **Gerekli Kütüphaneler**
   - Aspose.Slides for Java (sürüm 25.4 veya üzeri).

2. **Ortam**
   - JDK 16 veya daha yenisi.
   - Bağımlılık yönetimi için Maven veya Gradle.

3. **Bilgi**
   - Temel Java programlama.
   - Build araçları (Maven/Gradle) hakkında bilgi.

## Aspose.Slides for Java Kurulumu
### Maven Kurulumu
`pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Kurulumu
`build.gradle` dosyanıza aşağıdaki satırı ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Alternatif olarak, en yeni sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

### Lisans Edinme
- **Ücretsiz Deneme:** Lisans olmadan özellikleri keşfedin.
- **Geçici Lisans:** Değerlendirme sürecinde kullanın.
- **Tam Lisans:** Üretim dağıtımları için satın alın.

### Temel Başlatma
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Adım‑Adım Kılavuz

### Adım 1: Sunum Oluşturun ve Clustered Column Chart Ekleyin
Bu adımda **grafik oluşturma** nesnelerini oluşturup **create clustered column chart** ilk slayta ekleyeceğiz.

```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Adım 2: Grafik Serilerini Yönetme
Şimdi varsayılan serileri temizleyecek, yeni bir seri ekleyecek ve hem pozitif hem de negatif değerlerle dolduracağız.

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Adım 3: Negatif Veri Noktalarını Koşullu Olarak Tersine Çevirme
Varsayılan olarak Aspose.Slides negatif değerleri tersine çevirmez. Sadece ihtiyaç duyulan noktalar için tersine çevirmeyi etkinleştireceğiz.

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Yaygın Hatalar & İpuçları
- **`Presentation` nesnesini dispose etmeyi unuttunuz mu?** Yerel kaynakları serbest bırakmak için `finally` bloğunda her zaman `dispose()` çağırın.
- **Negatif değerler tersine çevrilmiyor mu?** Veri noktasını ekledikten **sonra** `invertIfNegative(true)` çağırdığınızdan emin olun.
- **Grafik boyut sorunları:** Koordinatlar (X, Y) ve boyutlar (width, height) puan cinsindendir; slayt düzeninize göre ayarlayın.

## Sıkça Sorulan Sorular

**S: Aynı yaklaşımla başka grafik türleri oluşturabilir miyim?**  
C: Evet, `ChartType.ClusteredColumn` ifadesini istediğiniz başka bir `ChartType` enum değeriyle (ör. `Line`, `Pie`) değiştirmeniz yeterlidir.

**S: Geliştirme sürümleri için lisans gerekiyor mu?**  
C: Tam özellik erişimi için geçici veya değerlendirme lisansı gerekir; aksi takdirde kütüphane deneme modunda filigran sınırlamalarıyla çalışır.

**S: Grafik ekledikten sonra sunumu PDF olarak nasıl dışa aktarırım?**  
C: Grafik manipülasyonunu tamamladıktan sonra `pres.save("output.pdf", SaveFormat.Pdf);` kullanın.

**S: Tek tek sütunları (renk, kenarlık) biçimlendirebilir miyim?**  
C: Evet, her `IChartDataPoint` `getFillFormat().setFillType(FillType.Solid)` ve `getLineFormat()` gibi biçimlendirme seçenekleri sunar.

**S: Sunumu kaydettikten sonra grafik verilerini güncellemem gerekirse?**  
C: `new Presentation("file.pptx")` ile sunumu tekrar yükleyin, grafik verilerini değiştirin ve yeniden kaydedin.

---

**Son Güncelleme:** 2026-02-12  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (JDK 16)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}