---
date: '2026-07-22'
description: Aspose Slides Maven Dependency'yi kullanarak Java'da stacked column chart
  oluşturmayı, data labels eklemeyi, vertical axis sayı formatını değiştirmeyi ve
  sonucu PPTX dosyası olarak dışa aktarmayı öğrenin.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency, Java'da stacked column chart oluşturmanıza,
  data labels'ı özelleştirmenize, vertical axis formatını ayarlamanıza ve PPTX olarak
  kaydetmenize olanak tanır – hepsi kısa ve üretim‑hazır kodla.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Java''da Stacked Column Chart'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Java''da Stacked Column Chart'
url: /tr/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Bağımlılığı: Java'da Yığılmış Sütun Grafiği

## Giriş

Sunumlarınızı, **Aspose.Slides for Java** gücüyle içgörülü veri görselleştirmeleri ekleyerek yükseltin. Bu rehberde, iş raporları hazırlarken ya da proje istatistiklerini sergilerken profesyonel görünümlü **yığılmış sütun grafiği** oluşturacaksınız. Bu öğreticinin sonunda şunları yapabilecek durumdasınız:

- **Aspose Slides Maven bağımlılığı** ile ortamınızı kurun
- Sıfırdan bir sunum oluşturun
- Yüzde‑yığılmış bir grafik ekleyin ve görünümünü özelleştirin
- Grafik veri etiketlerini biçimlendirin ve dikey eksen sayı formatını değiştirin
- Sunumu tek bir kod satırıyla PPTX olarak kaydedin

## Hızlı Cevaplar
- **Hangi kütüphane gerekiyor?** `aspose-slides` Maven/Gradle bağımlılığını ekleyin (aşağıdaki “Aspose Slides Maven Dependency” bölümüne bakın).  
- **Hangi grafik tipi yığılmış görünüm oluşturur?** Yüzde‑yığılmış sütun grafiği için `ChartType.PercentsStackedColumn` kullanın.  
- **Eksen sayı formatını nasıl değiştiririm?** `IAxis.setNumberFormat()` çağırın ve `setNumberFormatLinkedToSource(false)` ayarlayın.  
- **Veri etiketlerini özelleştirebilir miyim?** Evet – her `IChartDataPoint` üzerinden döngü yaparak özel bir `ITextFrame` atayın.  
- **Dosyayı nasıl kaydederim?** `presentation.save("output.pptx", SaveFormat.Pptx)` çağırın.

## Yığılmış sütun grafiği nedir?
Yığılmış sütun grafiği, her kategori sütununda birden fazla veri serisini dikey olarak üst üste gösterir; **yüzde‑yığılmış** varyantı her sütunu %100’e normalleştirerek oran karşılaştırmasını kolaylaştırır. Bu format, izleyicilerin farklı kategorilerde her bileşenin bütün içindeki katkısını hızlıca değerlendirmesini sağlar ve eğilimleri ile göreceli boyutları anında netleştirir.

## Neden Aspose.Slides for Java kullanmalı?
Aspose.Slides for Java, **Microsoft Office** gerektirmeden PowerPoint dosyaları oluşturmanıza, düzenlemenize ve dönüştürmenize olanak tanır ve **Windows, Linux ve macOS** üzerinde **50+ çıktı formatı** destekler. Kütüphane tamamen bir JRE üzerinde çalışır, bu da sunucu‑tarafı otomasyon ve yüksek‑hızlı raporlama sağlar. Ayrıca grafik nesneleri, slayt düzenleri ve belge özellikleri üzerinde ince ayar kontrolü sunarak kurumsal düzeyde sunum üretimi için idealdir.

## Önkoşullar
- **Java Development Kit (JDK):** 8 veya üzeri  
- **IDE:** IntelliJ IDEA, Eclipse veya herhangi bir Java‑uyumlu editör  
- **Derleme Aracı:** Maven veya Gradle (isteğe bağlı ancak önerilir)  
- **Temel Java bilgisi** – sınıflar ve metodlarla rahat olmalısınız  

## Aspose.Slides for Java Kurulumu
Başlamak için, Aspose.Slides kütüphanesini projenize ekleyin.

### Aspose Slides Maven Bağımlılığı
Projenizin `pom.xml` dosyasına aşağıdakileri ekleyin (bu, ihtiyacınız olan **aspose slides maven dependency**'dir):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Alternatifi
Gradle tercih ediyorsanız, `build.gradle` dosyanıza şu satırı ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan İndirme
Alternatif olarak, en son JAR dosyasını [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

### Lisans Edinimi
Aspose.Slides özelliklerini keşfetmek için ücretsiz deneme ile başlayabilirsiniz. Değerlendirme sınırlamalarını kaldırmak için geçici ya da satın alınmış bir lisans almayı düşünün.

- **Ücretsiz Deneme:** Anında maliyet olmadan sınırlı özelliklere erişim.  
- **Geçici Lisans:** [Aspose sitesinden](https://purchase.aspose.com/temporary-license/) talep edin.  
- **Satın Alma:** Tam erişim için satın alma sayfasını ziyaret edin.

### Temel Başlatma
`Presentation`, Aspose.Slides'ın bellek içindeki bir PowerPoint dosyasını temsil eden temel sınıfıdır. Aşağıdaki minimal kod parçacığı bir `Presentation` nesnesi oluşturmayı gösterir:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Uygulama Kılavuzu

### Sunum Oluşturma ve Slayt Ekleme
**Genel Bakış:**  
İlk olarak, boş bir sunum oluşturacağız ve bir slaytın mevcut olduğunu doğrulayacağız.

#### Adım 1: Presentation Nesnesini Başlatma
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Adım 2: Sunumu Kaydetme
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Yüzde Yığılmış Sütun Grafiği Ekleme
**Genel Bakış:**  
Şimdi, ilk slayta **yüzde yığılmış bir grafik** ekleyeceğiz.

`ChartType.PercentsStackedColumn` yüzde‑yığılmış sütun grafik tipini belirtir.

#### Adım 1: Slaytı Başlatma ve Erişme
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Adım 2: Grafiği Slayta Ekleme
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Grafik Eksen Sayı Formatını Özelleştirme
**Genel Bakış:**  
Daha iyi okunabilirlik için **dikey eksen formatını** yüzde gösterecek şekilde değiştireceğiz.

`IAxis` grafik eksenini temsil eden bir arayüzdür ve formatlama ile ölçek ayarlarını sağlar.

#### Adım 1: Grafiği Ekle ve Eriş
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Adım 2: Özel Sayı Formatını Ayarla
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Seri ve Veri Noktaları Ekleme
**Genel Bakış:**  
Grafiği örnek veri serileriyle dolduracağız.

#### Adım 1: Sunumu ve Grafiği Başlat
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Adım 2: Veri Serileri Ekle
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Seri Dolgu Rengini Biçimlendirme
**Genel Bakış:**  
Her seriye farklı bir renk vererek grafiği daha okunabilir hâle getirin.

#### Adım 1: Grafiği Başlat ve Eriş
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Adım 2: Dolgu Renklerini Ayarla
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Veri Etiketlerini Biçimlendirme
**Genel Bakış:**  
Şimdi **grafik veri etiketlerini** özelleştirilmiş metin gösterecek şekilde biçimlendireceğiz.

`IChartDataPoint` bir grafik serisindeki tek bir veri noktasını temsil eder, `ITextFrame` ise etiket metnini tutar.

#### Adım 1: Grafik Serilerini ve Veri Noktalarını Eriş
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Adım 2: Veri Etiketlerini Özelleştir
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Yaygın Sorunlar ve Çözümler
- **Grafik boş görünüyor:** Kaydetmeden önce en az bir veri serisi ve veri noktası eklediğinizden emin olun.  
- **Eksen sayıları yüzde olarak görünmüyor:** `verticalAxis.setNumberFormatLinkedToSource(false)` ayarlamayı unutmayın; aksi takdirde özel format göz ardı edilir.  
- **Lisans değerlendirme mesajı:** Değerlendirme bannerını kaldırmak için `Presentation` nesnesini oluşturmadan önce geçerli bir lisans dosyası uygulayın.

## Sıkça Sorulan Sorular

**S: Bu kodu Java 11 veya daha yeni bir sürümde kullanabilir miyim?**  
**C:** Evet. Kütüphane JDK 8+ destekler; sadece uygun sınıflandırıcıyı (örneğin JDK 16 veya sonrası için `jdk16`) kullanın.

**S: Grafiği PPTX yerine görüntü olarak nasıl dışa aktarırım?**  
**C:** Grafiği slayta ekledikten sonra `chart.getImage().save("chart.png", ImageFormat.Png);` kullanın.

**S: Yığılmış sütun grafiğine bir lejant eklemek mümkün mü?**  
**C:** Kesinlikle. `chart.getChartTitle().addTextFrameForOverriding("My Chart");` çağırın ve gerektiği gibi `chart.getLegend()` yapılandırın.

**S: Sunum oluşturulduktan sonra veriyi güncellemem gerekirse?**  
**C:** `ChartDataWorkbook` hücrelerini değiştirebilir ve ardından `chart.refresh();` çağırarak değişiklikleri yansıtabilirsiniz.

**S: Aspose.Slides Linux sunucularda çalışır mı?**  
**C:** Evet. Kütüphane saf Java'dır ve uyumlu bir JRE'ye sahip herhangi bir işletim sisteminde çalışır.

## Sonuç
Bu kılavuzu izleyerek **Aspose Slides Maven bağımlılığı** kullanarak Java'da **yığılmış sütun grafiği** oluşturmayı, ortam kurulumundan ince ayarlı görsel stiline kadar öğrendiniz. Raporlarınızı gerçekten öne çıkarmak için farklı veri setleri, renkler ve etiket formatlarıyla deneyler yapın.

---

**Son Güncelleme:** 2026-07-22  
**Test Edilen:** Aspose.Slides 25.4 (jdk16 classifier)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Java'da Aspose.Slides ile kümelenmiş sütun grafiği oluşturma](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Aspose.Slides for Java kullanarak Grafik Veri Noktalarında Sayı Formatlarını Ayarlama](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Aspose.Slides for Java kullanarak Sunumlara Grafik Ekleme ve Yapılandırma](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}