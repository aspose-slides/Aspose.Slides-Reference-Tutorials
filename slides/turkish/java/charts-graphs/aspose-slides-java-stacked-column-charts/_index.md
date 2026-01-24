---
date: '2026-01-24'
description: Aspose.Slides for Java kullanarak yüzde yığılmış sütun ayarı, eksen biçimlendirme
  ve veri etiketi özelleştirmesi dahil olmak üzere nasıl grafik oluşturulacağını öğrenin.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Aspose.Slides Java ile Yığılmış Sütun Grafiği Oluşturma
url: /tr/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose.Slides ile Yığılmış Sütun Grafiklerinde Ustalık: Kapsamiriş

Sunumlarınızı, Aspose.Slides for Java gücüyle içgörülü veri görselleştirmeleri ekleyerek yükseltin. Bu öğreticide **grafik oluşturma**‑tabanlı slaytlar oluşturmayı öğrenecek ve ham sayıları net hikayelere dönüştüreceksiniz—iş raporları, proje panoları veya pazarlama sunumları hazırlıyor olun.  

Ortamınızı kurmaktan, bir **percentage stacked column** grafiği eklemeye ve eksenleri, serileri ve veri etiketlerini özelleştirerek son sunumunuzu cilalı ve profesyonel görünür hâle getirmeye kadar adım adım ilerleyeceğiz.

Hadi, izleyicilerinizi büyüleyecek sunumlar oluşturmaya dalalım.

## Hızlı Yanıtlar
- **Ana kütüphane nedir?** Aspose.Slides for Java
- **Hangi Maven artefaktı kütüphaneyi ekler?** `com.aspose:aspose-slides` (see *aspose slides maven* section)
- **Yüzde yığılmış sütun grafiği nasıl eklenir?** Use `ChartType.PercentsStackedColumn` when calling `addChart`
- **Grafik eksen sayıları biçimlendirilebilir mi?** Yes – set `verticalAxis.setNumberFormat("0.00%")`
- **Veri etiketi metni nasıl özelleştirilir?** Override each point’s `ITextFrame` via `point.getLabel().getTextFrameForOverriding()`

## Yığılmış Sütun Grafiği Nedir?
Yığılmış sütun grafiği, birden çok veri serisini tek bir sütunda gruplayarak toplam boyutu karşılaştırmanıza ve aynı zamanda her bileşenin katkısını görmenize olanak tanır. **percentage stacked column** varyantı, her sütunu %100’e normalleştirir ve kategoriler arasında orantısal verileri göstermek için idealdir.

## Neden Aspose.Slides for Java Kullanmalı?
- **Office kurulumu gerektirmez** – herhangi bir sunucuda PPTX dosyaları oluşturun.
- **Tam özellikli grafik API’si** – yüzde yığılmış sütun dahil tüm grafik türlerini destekler.
- **Çapraz platform uyumluluğu** – Windows, Linux ve macOS’ta çalışır.
- **Kolay Maven/Gradle entegrasyonu** – aşağıdaki *aspose slides maven* snippet’ine bakın.

## Önkoşullar
- **Java Development Kit (JDK):** 8 ve üzeri.
- **IDE:** IntelliJ IDEA, Eclipse veya herhangi bir Java uyumlu editör.
- **Derleme aracı (isteğe bağlı):** Bağımlılık yönetimi için Maven veya Gradle.
- **Temel Java bilgisi** – sınıflar, metodlar ve koleksiyonlarla rahat olmalısınız.

## Aspose.Slides for Java Kurulumu
Başlamak için, projenize Aspose.Slides kütüphanesini eklemeniz gerekir.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Doğrudan İndirme:**  
Alternatif olarak, en son JAR dosyasını [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

### Lisans Edinimi
Aspose.Slides özelliklerini keşfetmek için ücretsiz deneme ile başlayabilirsiniz. Değerlendirme sınırlamalarını kaldırmak için geçici ya da satın alınmış bir lisans almayı düşünün.

- **Ücretsiz Deneme:** Anında maliyet olmadan sınırlı özelliklere erişim.  
- **Geçici Lisans:** [Aspose sitesinden](https://purchase.aspose.com/temporary-license/) talep edin.  
- **Satın Alma:** Tam erişim için satın alma sayfasını ziyaret edin.

### Temel Başlatma
Java uygulamanızda Aspose.Slides'ı nasıl başlatacağınız aşağıdadır:
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

## Grafik Oluşturma: Adım Adım Kılavuz

### Sunum Oluşturma ve Slayt Ekleme
**Genel Bakış:** Başlangıç slaytıyla basit bir sunum oluşturun. Bu, sonraki geliştirmeler için temelinizdir.

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
```java
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Slayta Yüzde Yığılmış Sütun Grafiği Ekleme
**Genel Bakış:** Slaytınızı bir **percentage stacked column** grafiği ekleyerek geliştirin; bu, verileri kolayca karşılaştırmanızı sağlar.

#### Adım 1: Slaytı Başlat ve Eriş
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

#### Adım 2: Slayta Grafik Ekle
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Grafik Ekseni Sayı Formatını Özelleştirme
**Genel Bakış:** Grafiğinizin dikey ekseninin sayı formatını, okunabilirliği artırmak için özelleştirin.

#### Adım 1: Grafik Ekle ve Eriş
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

#### Adım 2: Özel Sayı Formatı Ayarla
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Grafik'e Seri ve Veri Noktaları Ekleme
**Genel Bakış:** Grafiğinizi **add series data** ile doldurun; böylece bilgilendirici ve görsel açıdan çekici olur.

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
**Genel Bakış:** Her serinin dolgu rengini biçimlendirerek grafiğinizin estetiğini artırın.

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
**Genel Bakış:** **format chart data labels** kullanarak veri etiketlerinizi özelleştirilmiş metin gösterecek şekilde daha okunabilir hâle getirin.

#### Adım 1: Grafik Serilerine ve Veri Noktalarına Eriş
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

## Yaygın Kullanım Durumları
- **Üç aylık satış panoları** – ürün hattı katkılarını toplam gelirin yüzdesi olarak görselleştirin.
- **Proje kaynak tahsisi** – ekip üyelerinin görevler arasında tek bir sütunda nasıl dağıldığını gösterin.
- **Anket sonuçları** – birden çok sorudaki yanıt dağılımlarını karşılaştırın.

## Sıkça Sorulan Sorular

**S: Yığılmış sütun grafikleri oluşturmak için ücretli lisansa ihtiyacım var mı?**  
C: Ücretsiz deneme grafik oluşturmanıza izin verir, ancak kalıcı lisans değerlendirme filigranlarını kaldırır ve tam işlevselliği açar.

**S: Grafik oluşturulduktan sonra türünü değiştirebilir miyim?**  
C: Evet, mevcut şekli kaldırıp farklı bir `ChartType` ile yeni bir grafik ekleyerek değiştirebilirsiniz.

**S: Sunumu PDF olarak nasıl dışa aktarırım?**  
C: Slaytları düzenlemeyi tamamladıktan sonra `presentation.save("output.pdf", SaveFormat.Pdf);` komutunu kullanın.

**S: API Java 11 ve üzeriyle uyumlu mu?**  
C: Kesinlikle. Kütüphane JDK 8'den JDK 21'e kadar çalışır; sadece uygun sınıflandırıcıyı (ör. `jdk16`) seçmeniz yeterlidir.

**S: Üçten fazla seri eklemem gerekirse ne yapmalıyım?**  
C: Seri ekleme bloğunu sadece tekrarlayın ve her yeni seri için çalışma sayfası hücre referanslarını ayarlayın.

## Sonuç
Bu rehberi izleyerek artık Aspose.Slides for Java ile **grafik oluşturma** görselleştirmelerini nasıl yapacağınızı biliyorsunuz; Maven/Gradle bağımlılığını kurmaktan yüzde yığılmış sütun grafiğinin eksenlerini, seri renklerini ve veri etiketlerini özelleştirmeye kadar. Farklı veri setleriyle deney yapın, kendi kurumsal renklerinizi uygulayın ve bu slaytları otomatik raporlama hatlarına entegre edin.

---

**Son Güncelleme:** 2026-01-24  
**Test Edilen Versiyon:** Aspose.Slides 25.4 (jdk16 classifier)  
**Yazar:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}