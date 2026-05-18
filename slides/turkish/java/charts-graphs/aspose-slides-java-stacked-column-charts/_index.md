---
date: '2026-02-22'
description: Aspose.Slides kullanarak Java’da yığılmış sütun grafik nasıl oluşturulur
  öğrenin. Bu öğreticide Aspose Slides Maven bağımlılığı, yüzde yığılmış grafik ekleme,
  grafik veri etiketlerini biçimlendirme ve sunumu PPTX olarak kaydetme konuları ele
  alınmaktadır.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Aspose.Slides ile Java’da Yığılmış Sütun Grafiği Nasıl Oluşturulur – Kapsamlı
  Bir Rehber
url: /tr/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose.Slides ile yığılmış sütun grafiği nasıl oluşturulur – Kapsamlı Bir Rehber

## Giriş

Sunumlarınızı, Java için Aspose.Slides gücüyle içgörülü veri görselleştirmeleri ekleyerek yükseltin. Bu rehberde **yığılmış sütun grafiği** slaytları oluşturacaksınız; ister iş raporları hazırlayın, ister proje istatistiklerini sergileyin, profesyonel görünecekler. Bu öğreticinin sonunda şunları yapabilecek duruma geleceksiniz:

- Aspose Slides Maven bağımlılığı ile ortamınızı kurun
- Sıfırdan bir sunum oluşturun
- **Yüzde‑yığılmış grafik** ekleyin ve görünümünü özelleştirin
- **Grafik veri etiketlerini biçimlendirin** ve **dikey eksen formatını değiştirin**
- **Tek bir kod satırıyla sunumu PPTX olarak kaydedin**

Her adımı birlikte inceleyelim, böylece etkileyici sunumlar oluşturmaya hemen başlayabilirsiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** `aspose-slides` Maven/Gradle bağımlılığı (aşağıdaki “aspose slides maven dependency” bölümüne bakın)  
- **Hangi grafik türü kullanılıyor?** `ChartType.PercentsStackedColumn` yüzde‑yığılmış sütun grafik için  
- **Eksen sayı formatını nasıl değiştiririm?** `IAxis.setNumberFormat()` kullanın ve kaynağa bağlamayı devre dışı bırakın  
- **Veri etiketlerini özelleştirebilir miyim?** Evet – `IChartDataPoint` nesneleri üzerinden döngü kurarak özel bir `ITextFrame` ayarlayın  
- **Dosyayı nasıl kaydederim?** `presentation.save("output.pptx", SaveFormat.Pptx)` çağırın

## Yığılmış sütun grafiği nedir?
Yığılmış sütun grafiği, birden çok veri serisini dikey sütunlar içinde üst üste gösterir. **Yüzde‑yığılmış** varyantı kullanıldığında, her sütun her zaman %100 toplamına ulaşır; bu da kategoriler arasındaki oranları karşılaştırmayı kolaylaştırır.

## Java için Aspose.Slides neden kullanılmalı?
Aspose.Slides, Microsoft Office yüklü olmasa da herhangi bir platformda çalışan saf‑Java API sağlar. Grafik nesneleri üzerinde ince ayar kontrolü sunar, geniş bir format yelpazesini destekler ve sunumları programatik olarak oluşturmanıza olanak tanır—otomatik raporlama veya sunucu‑tarafı belge üretimi için mükemmeldir.

## Önkoşullar
- **Java Development Kit (JDK):** 8 veya üzeri  
- **IDE:** IntelliJ IDEA, Eclipse veya herhangi bir Java‑uyumlu editör  
- **Derleme Aracı:** Maven veya Gradle (isteğe bağlı ama önerilir)  
- **Temel Java bilgisi** – sınıflar ve metodlarla rahat olmalısınız  

## Aspose.Slides for Java'ı Kurma
Başlamak için Aspose.Slides kütüphanesini projenize ekleyin.

### Aspose Slides Maven Bağımlılığı
`pom.xml` dosyanıza aşağıdakileri ekleyin (bu, ihtiyacınız olan **aspose slides maven dependency** dir):

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
Alternatif olarak, en yeni JAR dosyasını [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

### Lisans Alımı
Aspose.Slides özelliklerini keşfetmek için ücretsiz deneme sürümüyle başlayabilirsiniz. Değerlendirme sınırlamalarını kaldırmak için geçici ya da satın alınmış bir lisans edinmeyi düşünün.

- **Ücretsiz Deneme:** Sınırlı özelliklere erişim, ek maliyet olmadan.  
- **Geçici Lisans:** [Aspose’un sitesinden](https://purchase.aspose.com/temporary-license/) talep edebilirsiniz.  
- **Satın Alma:** Tam erişim için satın alma sayfasını ziyaret edin.

### Temel Başlatma
`Presentation` nesnesi oluşturmayı gösteren minimal bir kod parçacığı:

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

## Uygulama Rehberi

### Sunum Oluşturma ve Slayt Ekleme
**Genel Bakış:**  
İlk olarak boş bir sunum oluşturacağız ve bir slaytın varlığını doğrulayacağız.

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

### Slayta Yüzde‑Yığılmış Sütun Grafiği Ekleme
**Genel Bakış:**  
Şimdi **yüzde‑yığılmış grafik**i ilk slayta yerleştireceğiz.

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

#### Adım 2: Slayta Grafik Ekleme
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Grafik Ekseni Sayı Formatını Özelleştirme
**Genel Bakış:**  
Okunabilirliği artırmak için **dikey eksen formatını** yüzde gösterecek şekilde değiştireceğiz.

#### Adım 1: Grafiği Ekleme ve Erişme
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

#### Adım 2: Özel Sayı Formatı Ayarlama
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Grafiğe Seri ve Veri Noktaları Ekleme
**Genel Bakış:**  
Grafiği örnek veri serileriyle dolduracağız.

#### Adım 1: Sunumu ve Grafiği Başlatma
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

#### Adım 2: Veri Serileri Ekleme
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
Her seriye farklı bir renk vererek grafiği daha okunabilir hâle getireceğiz.

#### Adım 1: Grafiği Başlatma ve Erişme
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

#### Adım 2: Dolgu Renklerini Ayarlama
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Veri Etiketlerini Biçimlendirme
**Genel Bakış:**  
Şimdi **grafik veri etiketlerini** özelleştirerek özel metin göstermesini sağlayacağız.

#### Adım 1: Grafik Serilerine ve Veri Noktalarına Erişme
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

#### Adım 2: Veri Etiketlerini Özelleştirme
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
- **Grafik boş görünüyor:** En az bir veri serisi ve veri noktası eklediğinizden emin olun, ardından kaydedin.  
- **Eksen sayıları yüzde olarak görünmüyor:** `verticalAxis.setNumberFormatLinkedToSource(false)` ayarını yaptığınızdan emin olun; aksi takdirde özel format yok sayılır.  
- **Lisans değerlendirme mesajı:** `Presentation` nesnesini oluşturmadan önce geçerli bir lisans dosyası uygulayın, böylece değerlendirme banner'ı ortadan kalkar.

## Sık Sorulan Sorular

**S: Bu kodu Java 11 veya daha yeni bir sürümde kullanabilir miyim?**  
C: Evet. Kütüphane JDK 8+ destekler; sadece uygun sınıflandırıcıyı (ör. `jdk16` JDK 16 ve üzeri için) kullanın.

**S: Grafiği PPTX yerine bir resim olarak dışa aktarmak istiyorum, nasıl?**  
C: Slayta grafiği ekledikten sonra `chart.getImage().save("chart.png", ImageFormat.Png);` kullanın.

**S: Yığılmış sütun grafiğine bir lejant eklemek mümkün mü?**  
C: Kesinlikle. `chart.getChartTitle().addTextFrameForOverriding("My Chart");` çağırın ve `chart.getLegend()` ayarlarını gerektiği gibi yapılandırın.

**S: Sunum oluşturulduktan sonra verileri güncellemem gerekirse ne yapmalıyım?**  
C: `ChartDataWorkbook` hücrelerini değiştirin ve ardından `chart.refresh();` çağırarak değişiklikleri yansıtın.

**S: Aspose.Slides Linux sunucularda çalışır mı?**  
C: Evet. Kütüphane saf Java olduğundan uyumlu bir JRE'ye sahip herhangi bir işletim sisteminde çalışır.

## Sonuç
Bu rehberi izleyerek Aspose.Slides for Java ile **yığılmış sütun grafiği** sunumları oluşturmayı, ortam kurulumundan ince ayarlı görsel stilize etmeye kadar öğrendiniz. Farklı veri setleri, renkler ve etiket formatlarıyla deneyler yapın; raporlarınız gerçekten öne çıksın.

---

**Son Güncelleme:** 2026-02-22  
**Test Edilen Versiyon:** Aspose.Slides 25.4 (jdk16 classifier)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}