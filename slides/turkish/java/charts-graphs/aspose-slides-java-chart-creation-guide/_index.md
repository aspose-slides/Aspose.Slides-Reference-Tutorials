---
date: '2026-06-03'
description: Aspose.Slides kullanarak Java'da kümelenmiş sütun grafiği oluşturmayı
  öğrenin. Bu rehber Maven bağımlılığını, grafik oluşturma adımlarını ve veri işleme
  konularını kapsar.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Java'da Aspose.Slides ile Kümelenmiş Sütun Grafiği Oluşturma
url: /tr/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java ile Aspose.Slides Kullanarak Küme Sütun Grafiği Oluşturma

## Java'da Grafik Oluşturma: Giriş
Dinamik sunumlar oluşturmak genellikle verileri grafikler aracılığıyla görselleştirmeyi içerir. **Aspose.Slides for Java** ile **küme sütun grafiği** nesnelerini zahmetsizce **oluşturabilir**, netliği artırabilir ve izleyiciniz üzerinde daha güçlü bir etki yaratabilirsiniz. Bu öğretici, kütüphaneyi kurma, bir küme sütun grafiği ekleme, serileri yönetme ve negatif veri noktalarını koşullu olarak tersine çevirme adımlarını size gösterir.

**Neler Öğreneceksiniz**
- Aspose.Slides for Java'ı nasıl kuracağınızı.
- Sunumunuzda **küme sütun grafiği** oluşturma adımları.
- Grafik serilerini ve veri noktalarını yönetme teknikleri.
- Daha iyi görselleştirme için negatif veri noktalarını koşullu olarak tersine çevirme yöntemleri.
- Sunumu güvenli bir şekilde kaydetme.

## Hızlı Cevaplar
- **Hangi kütüphane kullanılıyor?** Aspose.Slides for Java.  
- **Hangi grafik türü gösteriliyor?** Küme sütun grafiği.  
- **Negatif değerleri tersine çevirebilir miyim?** Evet, `invertIfNegative` kullanarak.  
- **Gerekli Java sürümü nedir?** JDK 16 veya üzeri.  
- **Üretim için lisans gerekli mi?** Evet, geçerli bir Aspose lisansı.

## Küme Sütun Grafiği Nedir?
Küme sütun grafiği, her kategori için birden fazla veri serisini yan yana yerleştirerek gruplar arasında hızlı karşılaştırma yapmayı sağlayan bir görsel temsildir. Finansal raporlar, satış panoları ve aynı anda birden fazla metriği karşılaştırmanız gereken her senaryo için mükemmeldir.

## Grafik Oluşturmak İçin Neden Aspose.Slides Kullanmalısınız?
Aspose.Slides, grafikleri programlı olarak oluşturmanıza ve tamamen özelleştirmenize olanak tanır, manuel PowerPoint düzenleme ihtiyacını ortadan kaldırır. **70+ giriş ve çıkış formatını** destekler ve **10.000 slayta** kadar olan sunumları, tüm dosyayı belleğe yüklemeden işleyebilir, büyük ölçekli raporlamada yüksek performans sağlar.

## Ön Koşullar
1. **Gerekli Kütüphaneler**  
   - Aspose.Slides for Java (sürüm 25.4 veya üzeri).  

2. **Ortam**  
   - JDK 16 veya daha yeni.  
   - Bağımlılık yönetimi için Maven veya Gradle.  

3. **Bilgi**  
   - Temel Java programlama.  
   - Derleme araçları (Maven/Gradle) hakkında bilgi.  

## Aspose.Slides for Java'ı Kurma
### Maven Kurulumu
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Kurulumu
Add the following line to your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Alternatif olarak, en son sürümü [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirebilirsiniz.

### Lisans Edinme
- **Ücretsiz Deneme:** Lisans olmadan özellikleri keşfedin.  
- **Geçici Lisans:** Değerlendirme sırasında kullanın.  
- **Tam Lisans:** Üretim dağıtımları için satın alın.

### Temel Başlatma
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Bir slayta nasıl küme sütun grafiği eklerim?
`Presentation` bir PowerPoint dosyasını temsil eden temel sınıftır. Yeni bir `Presentation` yükleyin, bir slayt ekleyin ve `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)` metodunu çağırın. Bu tek çağrı, belirtilen koordinatlarda konumlandırılmış tam işlevsel bir küme sütun grafiği oluşturur. Ardından grafik nesnesine erişerek serileri, veri noktalarını ve görsel stilleri değiştirebilirsiniz.

## Adım Adım Kılavuz

### Adım 1: Bir Sunum Oluşturun ve Küme Sütun Grafiği Ekleyin
`Presentation` sınıfı bir PowerPoint belgesini temsil eder ve slayt oluşturmanıza izin verir.  
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
Şimdi varsayılan serileri temizleyecek, yeni bir seri ekleyecek ve hem pozitif hem negatif değerlerle dolduracağız.  
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
`invertIfNegative` yöntemi, bir grafik serisindeki negatif değerlerin tersine çevrilmesini sağlar.  
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

## Yaygın Tuzaklar ve İpuçları
- **`Presentation` nesnesini serbest bırakmayı unuttunuz mu?** Yerel kaynakları serbest bırakmak için her zaman `finally` bloğunda `dispose()` çağırın.  
- **Negatif değerler ters çevrilmiş olarak görünmüyor mu?** Veri noktasını ekledikten **sonra** `invertIfNegative(true)` çağırdığınızdan emin olun.  
- **Grafik boyutu sorunları:** Koordinatlar (X, Y) ve boyutlar (genişlik, yükseklik) puan cinsindendir; slayt düzeninize uyacak şekilde ayarlayın.  

## Sıkça Sorulan Sorular

**S:** Aynı yaklaşımla başka grafik türleri oluşturabilir miyim?  
**C:** Evet, `ChartType.ClusteredColumn` ifadesini başka bir `ChartType` enum değeri (ör. `Line`, `Pie`) ile değiştirmeniz yeterlidir.  

**S:** Geliştirme sürümleri için lisansa ihtiyacım var mı?  
**C:** Tam özellik erişimi için geçici veya değerlendirme lisansı gerekir; aksi takdirde kütüphane, filigran sınırlamalarıyla deneme modunda çalışır.  

**S:** Grafikler eklendikten sonra sunumu PDF olarak nasıl dışa aktarırım?  
**C:** `SaveFormat.Pdf`, bir sunumu kaydederken PDF çıktısını belirtir. Grafik manipülasyonunu tamamladıktan sonra `pres.save("output.pdf", SaveFormat.Pdf);` kullanın.  

**S:** Tek tek sütunları (renk, kenarlık) biçimlendirmek mümkün mü?  
**C:** `IChartDataPoint`, bir grafikteki tek bir veri noktasını temsil eder ve biçimlendirmeye izin verir. Her `IChartDataPoint`, `getFillFormat().setFillType(FillType.Solid)` ve `getLineFormat()` gibi seçenekler sunar.  

**S:** Sunumu kaydettikten sonra grafik verilerini güncellemem gerekirse?  
**C:** `new Presentation("file.pptx")` ile sunumu tekrar yükleyin, grafik verilerini değiştirin ve yeniden kaydedin.  

---

**Son Güncelleme:** 2026-06-03  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (JDK 16)  
**Yazar:** Aspose

## İlgili Öğreticiler

- [Java ile Aspose.Slides Kullanarak Yığılmış Sütun Grafiği Nasıl Oluşturulur – Kapsamlı Rehber](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Java ile Aspose.Slides Kullanarak Grafik Oluşturma – Grafik Oluşturma ve Doğrulama Uzmanlığı](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Aspose.Slides Kullanarak Java’da Grafik Oluşturma ve Biçimlendirme: Kapsamlı Rehber](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}