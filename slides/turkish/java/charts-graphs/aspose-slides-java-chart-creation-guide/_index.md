---
date: '2026-01-14'
description: Aspose.Slides kullanarak Java’da kümelenmiş sütun grafiği oluşturmayı
  öğrenin. Boş sunum, sunuma grafik ekleme ve serileri yönetme konularını adım adım
  kapsayan rehber.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Java'da Aspose.Slides ile kümelenmiş sütun grafiği nasıl oluşturulur
url: /tr/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java ile Aspose.Slides'de Grafik Oluşturmayı Ustalıkla Öğrenin

## Aspose.Slides for Java Kullanarak Grafik Oluşturma ve Yönetme

### Giriş
Dinamik sunumlar oluşturmak, genellikle verileri grafiklerle görselleştirmeyi içerir. **Aspose.Slides for Java** ile **clustered column chart** oluşturmak ve çeşitli grafik türlerini yönetmek son derece kolaydır; bu da netlik ve etkiyi artırır. Bu öğreticide, boş bir sunum oluşturma, clustered column chart ekleme, serileri yönetme ve veri noktası tersine çevirmeyi özelleştirme konularında adım adım rehberlik edeceğiz—hepsi Aspose.Slides for Java kullanılarak.

**Ne Öğreneceksiniz:**
- Aspose.Slides for Java'ı nasıl kuracağınızı.
- Boş bir sunum oluşturma ve sunuma bir grafik ekleme adımları.
- Grafik serilerini ve veri noktalarını etkili bir şekilde yönetme teknikleri.
- Daha iyi görselleştirme için negatif veri noktalarını koşullu olarak tersine çevirme yöntemleri.
- Sunumu güvenli bir şekilde kaydetme.

Haydi, başlamadan önce ön koşullara göz atalım.

## Hızlı Yanıtlar
- **Başlamak için birincil sınıf nedir?** `Presentation` from `com.aspose.slides`.
- **Hangi grafik türü clustered column chart oluşturur?** `ChartType.ClusteredColumn`.
- **Bir slayta grafik nasıl eklenir?** Use `addChart()` on the slide's shape collection.
- **Negatif değerleri tersine çevirebilir misiniz?** Yes, with `invertIfNegative(true)` on a data point.
- **Gerekli sürüm nedir?** Aspose.Slides for Java 25.4 or later.

## Clustered column chart nedir?
Clustered column chart, her kategori için birden çok veri serisini yan yana gösterir; bu da gruplar arasındaki değerleri karşılaştırmak için idealdir. Aspose.Slides, PowerPoint'i açmadan bu grafiği programlı olarak oluşturmanıza olanak tanır.

## Sunuma grafik eklemek için Aspose.Slides for Java neden kullanılmalı?
- **Tam kontrol** grafik verileri, görünümü ve düzeni üzerinde.
- **Office kurulumu** sunucuda gerekli değildir.
- **Tüm ana grafik türlerini** destekler, clustered column chart'lar dahil.
- **Maven/Gradle** ile kolay entegrasyon.

## Ön Koşullar
Başlamadan önce aşağıdakilerin mevcut olduğundan emin olun:

1. **Gerekli Kütüphaneler:**
   - Aspose.Slides for Java (versiyon 25.4 veya üzeri).

2. **Ortam Kurulum Gereksinimleri:**
   - Uyumluluk sağlayan bir JDK sürümü (ör. JDK 16).
   - Bağımlılık yönetimini tercih ediyorsanız Maven veya Gradle kurulu.

3. **Bilgi Gereksinimleri:**
   - Java programlamaya temel bir anlayış.
   - Geliştirme ortamınızda bağımlılıkları yönetme konusunda aşinalık.

## Aspose.Slides for Java Kurulumu
Aspose.Slides kullanmaya başlamak için şu adımları izleyin:

**Maven Installation:**  
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle Installation:**  
Add the following line to your `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Lisans Edinme
- **Ücretsiz Deneme:** Özellikleri keşfetmek için ücretsiz deneme ile başlayabilirsiniz.  
- **Geçici Lisans:** Değerlendirme süreniz boyunca tam erişim için geçici bir lisans alın.  
- **Satın Alma:** Uzun vadeli ihtiyaçlarınıza uygunsa satın almayı düşünün.

### Temel Başlatma
Yeni bir sunum örneği oluşturmak için gereken minimum kod aşağıdadır:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Uygulama Kılavuzu
Şimdi, her özelliği yönetilebilir adımlara ayıralım.

### Clustered Column Chart ile Sunum Oluşturma
#### Genel Bakış
Bu bölüm, **boş sunum oluşturma**, **clustered column chart** ekleme ve ilk slayta konumlandırma işlemlerini gösterir.

**Adımlar:**
1. **Presentation Nesnesini Başlat** – yeni bir `Presentation` oluşturun.
2. **Clustered Column Chart Ekle** – uygun tip ve boyutlarla `addChart()` çağırın.

**Kod Örneği:**
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

### Grafik Serilerini Yönetme
#### Genel Bakış
Varsayılan serileri temizleme, yeni bir seri ekleme ve pozitif‑negatif değerlerle doldurma konularını öğrenin.

**Adımlar:**
1. **Mevcut Serileri Temizle** – önceden doldurulmuş verileri kaldırın.
2. **Yeni Bir Seri Ekle** – çalışma kitabı hücresini seri adı olarak kullanın.
3. **Veri Noktaları Ekle** – daha sonra tersine çevirmeyi göstermek için negatifler dahil değerler ekleyin.

**Kod Örneği:**
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

### Koşullara Göre Seri Veri Noktalarını Tersine Çevirme
#### Genel Bakış
Varsayılan olarak Aspose.Slides negatif değerleri tersine çevirebilir. Bu davranışı hem global hem de veri noktası bazında kontrol edebilirsiniz.

**Adımlar:**
1. **Global Tersine Çevirme Ayarla** – tüm seri için otomatik tersine çevirmeyi devre dışı bırakın.
2. **Koşullu Tersine Çevirme Uygula** – sadece belirli negatif noktalarda tersine çevirmeyi etkinleştirin.

**Kod Örneği:**
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

### Yaygın Sorunlar ve Çözümler
| Sorun | Çözüm |
|-------|----------|
| Grafik boş görünüyor | Slayt indeksi (`0`) mevcut olduğundan ve grafik boyutlarının slayt sınırları içinde olduğundan emin olun. |
| Negatif değerler tersine çevrilmiyor | Seride `invertIfNegative(false)` ve belirli veri noktasında `invertIfNegative(true)` ayarlandığını doğrulayın. |
| Lisans hatası | `Presentation` nesnesini oluşturmadan önce geçerli bir Aspose lisansı uygulayın. |

## Sıkça Sorulan Sorular

**S: Clustered column dışındaki başka grafik türleri ekleyebilir miyim?**  
C: Evet, Aspose.Slides line, pie, bar, area ve daha birçok grafik türünü destekler.

**S: Geliştirme için lisansa ihtiyacım var mı?**  
C: Değerlendirme için ücretsiz deneme yeterlidir, ancak üretim kullanımı için ticari lisans gereklidir.

**S: Grafiği resim olarak nasıl dışa aktarırım?**  
C: Render ettikten sonra `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` kodunu kullanın.

**S: Grafiği (renkler, yazı tipleri) biçimlendirmek mümkün mü?**  
C: Kesinlikle. Her `IChartSeries` ve `IChartDataPoint` stil özellikleri sunar.

**S: Mevcut bir PPTX dosyasına grafik eklemek istersem ne yapmalıyım?**  
C: `new Presentation("existing.pptx")` ile dosyayı yükleyin, ardından istediğiniz slayta grafiği ekleyin.

## Sonuç
Bu öğreticide, Java'da **clustered column chart** oluşturma, serileri yönetme ve negatif veri noktalarını koşullu olarak tersine çevirme konularını Aspose.Slides ile öğrendiniz. Bu tekniklerle, programlı olarak etkileyici, veri odaklı sunumlar oluşturabilirsiniz.

**Sonraki Adımlar:**
- Aspose.Slides for Java tarafından sunulan diğer grafik türleriyle deneyler yapın.  
- Özel renkler, veri etiketleri ve eksen biçimlendirme gibi gelişmiş stil seçeneklerine dalın.  
- Grafik oluşturmayı raporlama veya analiz boru hatlarınıza entegre edin.

---

**Son Güncelleme:** 2026-01-14  
**Test Edilen Sürüm:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}