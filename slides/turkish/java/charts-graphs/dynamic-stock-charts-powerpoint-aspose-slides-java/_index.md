---
date: '2026-09-12'
description: Maven Aspose Slides kullanarak Java ile PowerPoint'te dinamik stock charts
  eklemeyi ve özelleştirmeyi öğrenin. Kurulum, veri serileri ekleme, çizgi biçimlendirme
  ve kaydetme adımlarını içerir.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Maven Aspose Slides öğreticisi, Java kullanarak PowerPoint'te dinamik
  stock charts oluşturma ve özelleştirme, veri serileri, çizgi biçimlendirme ve kaydetme
  konularını kapsar.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Maven Aspose Slides rehberi: Java ile PowerPoint''te dinamik stock charts
  oluşturun'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: Java ile PowerPoint''te dinamik stock charts oluşturun'
url: /tr/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: Java ile PowerPoint'te dinamik hisse senedi grafiklerini oluşturun

## Giriş

**Maven Aspose Slides**, Java'dan programlı olarak gelişmiş PowerPoint sunumları oluşturmanıza olanak tanır. Bu öğreticide dinamik hisse senedi grafiklerini nasıl oluşturacağınızı, veri serilerini ekleyip biçimlendireceğinizi, grafik çizgilerini özelleştireceğinizi ve sonunda dosyayı kaydedeceğinizi öğreneceksiniz. Çeyrek raporları hazırlayan bir finans analisti ya da otomatik slayt desteleri oluşturan bir geliştirici olun, aşağıdaki adımlar size eksiksiz, üretim‑hazır bir çözüm sunar.

**Öğrenecekleriniz**
- Maven ile Aspose.Slides for Java'ı nasıl kuracağınızı  
- Bir hisse senedi grafiği ekleyip varsayılan verileri nasıl temizleyeceğinizi  
- **add data series chart** ve **format chart lines** nasıl ekleyeceğinizi  
- **customize chart java**‑specific visual elements nasıl özelleştirileceğini  
- Güncellenmiş sunumu nasıl kaydedeceğinizi

Ham sayıları göz alıcı hisse senedi görsellerine dönüştürmeye hazır mısınız? Hadi başlayalım!

## Hızlı cevaplar
- **Hangi Maven artefaktına ihtiyacım var?** `aspose-slides` version 25.4 (or newer).  
- **Herhangi bir işletim sisteminde çalıştırabilir miyim?** Yes – the library is pure Java and works on Windows, macOS, and Linux.  
- **Geliştirme için lisansa ihtiyacım var mı?** A free temporary license works for testing; a full license is required for production.  
- **Hangi grafik türleri destekleniyor?** Over 70 built‑in chart types, including Stock, Line, and Bar charts.  
- **Ne kadar büyük bir sunumu işleyebilirim?** Aspose.Slides can handle files with 500+ slides without loading the whole file into memory.

## Maven Aspose Slides nedir?

`Aspose.Slides for Java`, Microsoft Office olmadan PowerPoint dosyaları oluşturmayı, manipüle etmeyi ve dönüştürmeyi sağlayan bir Java API'sidir. Maven entegrasyonu, bağımlılık yönetimini basitleştirir ve kütüphaneyi doğrudan Maven Central'dan çekmenizi sağlar.

## Neden Maven Aspose Slides'ı hisse senedi grafikleri için kullanmalısınız?

Aspose.Slides **70+ grafik türünü** destekler ve tipik sunucu donanımında bir saniyeden kısa sürede çok sayfalı sunumları oluşturabilir. **high‑low line** ve **up/down bar** özellikleri, PowerPoint'in kullanıcı arayüzünün çok ötesinde, finansal görselleştirmeler üzerinde kesin kontrol sağlar.

## Önkoşullar

- **Java Development Kit (JDK)** – version 11 veya üzeri.  
- **IDE** – IntelliJ IDEA, Eclipse veya tercih ettiğiniz herhangi bir editör.  
- **Aspose.Slides for Java** – version 25.4 (yazım zamanındaki en son sürüm).

### Aspose.Slides for Java'ı Kurma

#### Maven

Aspose.Slides'ı Maven kullanarak projenize entegre etmek için `pom.xml` dosyanıza aşağıdaki bağımlılığı ekleyin:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle

Gradle kullanıcıları için, bunu `build.gradle` dosyanıza ekleyin:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Doğrudan indirme

Alternatif olarak, en son JAR dosyasını [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

**License acquisition** – ücretsiz deneme ile başlayabilir veya geçici bir lisans talep edebilirsiniz. Ticari kullanım için tam lisans satın alın.

Ayrıntılı API referansı için [Aspose.Slides documentation](https://docs.aspose.com/slides/java/) adresine bakın.

## Dinamik hisse senedi grafiği oluşturma adım adım

Sunumunuzu yükleyin, bir hisse senedi grafiği ekleyin, varsayılan verileri temizleyin ve ardından kendi serilerinizi ve kategorilerinizi ekleyin. Temel sorunun doğrudan yanıtı:

> Load an existing PPTX with `new Presentation("template.pptx")`, add a `Chart` of type `ChartType.Stock`, clear its default series and categories, then populate it with your own data points and formatting options. Finally, call `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Sunumu Başlatma
#### Genel Bakış
Yerinde değiştirebilmek için mevcut bir PowerPoint dosyasını yükleyerek başlayın.

#### Adım‑adım
1. **Kütüphaneyi içe aktar** – `Presentation` sınıfı tüm slayt işlemleri için giriş noktasıdır.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Load the presentation file** – şablon PPTX dosyanızın yolunu sağlayın.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Slayta hisse senedi grafiği ekleme
#### Genel Bakış
Sunumun ilk slaytına bir Stock (hisse senedi) grafiği ekleyin.

`Chart` sınıfı, bir slayta eklenebilen bir grafik şekli temsil eder.

#### Doğrudan yanıt
Bir hisse senedi grafiği eklemek için `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)` metodunu çağırırsınız. Bu, hemen manipüle edebileceğiniz bir grafik nesnesi oluşturur.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Grafikteki mevcut veri serilerini ve kategorileri temizleme
#### Genel Bakış
Temiz bir veri setiyle başlayabilmek için önceden doldurulmuş serileri veya kategorileri kaldırın.

`ChartData` nesnesi, bir grafiğin serilerini ve kategorilerini tutar.

#### Doğrudan yanıt
Kendi verilerinizi eklemeden önce varsayılan içeriği silmek için `chart.getChartData().getSeries().clear()` ve `chart.getChartData().getCategories().clear()` metodlarını çağırın.

```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Grafik verisine kategoriler ekleme
#### Genel Bakış
X‑eksenindeki kategorileri (ör. tarihler) tanımlayarak hisse değerlerinizi gruplandırın.

`ChartCategory`, bir grafiğin X‑eksen etiketi temsil eder.

#### Doğrudan yanıt
Her etiket için `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")` kullanarak yeni bir `ChartCategory` oluşturun ve her ay veya dönem için tekrarlayın.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Grafiğe veri serileri ekleme
#### Genel Bakış
Dört temel seriyi ekleyin: Açılış (Open), En Yüksek (High), En Düşük (Low) ve Kapanış (Close).

`ChartSeries`, grafikteki belirli bir seri için veri noktalarının koleksiyonunu tutar.

#### Doğrudan yanıt
Her seri için `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())` metodunu çağırın. Bu, seriyi grafiğin veri çalışma kitabına kaydeder.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Serilere veri noktaları ekleme
#### Genel Bakış
Her seriyi hisse fiyatlarını temsil eden sayısal değerlerle doldurun.

`DataPoint`, bir serideki tek bir değeri temsil eder.

#### Doğrudan yanıt
Veri koleksiyonunuzda döngü yapın ve `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (veya seri tipi için uygun yöntemi) kullanarak her bir noktayı ekleyin.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Yüksek‑düşük çizgileri ve yükseliş/düşüş çubuklarını biçimlendirme
#### Genel Bakış
Yüksek‑düşük bağlayıcıların ve yükseliş/düşüş çubuk doldurmalarının görsel stilini ayarlayın.

`Marker`, bir veri noktasının görsel sembolünü tanımlar.

#### Doğrudan yanıt
`chart.getChartData().getSeries().get(0).getMarker().setSize(10)` ayarlayın ve `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` yapılandırarak çizgi kalınlığını ve rengini kontrol edin.

```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Yükseliş/düşüş çubuklarını göster
Grafiğin `setShowUpDownBars(true)` metodunu kullanarak yükseliş/düşüş çubuklarını görünür hâle getirin.

```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Yüksek‑düşük çizgilerindeki veri etiketlerini özelleştirme
#### Genel Bakış
Hızlı referans için sayısal değerleri yüksek‑düşük çizgileri üzerinde doğrudan gösterin.

`DataLabel`, veri noktalarına eklenen etiketlerin görünümünü kontrol eder.

#### Doğrudan yanıt
`chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` ile veri etiketlerini etkinleştirin ve gerektiği gibi biçimlendirin.

```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Yükseliş/düşüş çubuklarının dolgu rengini ayarlama
#### Genel Bakış
Yükseliş çubuklarına yeşil, düşüş çubuklarına kırmızı dolgu vererek piyasa hareketini sezgisel olarak iletin.

`UpDownBars` nesnesi, yükseliş ve düşüş çubuklarının biçimlendirmesine erişim sağlar.

#### Doğrudan yanıt
`chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` uygulayın ve katı rengi `Color.GREEN` olarak ayarlayın; düşüş çubuğu için `Color.RED` ile tekrarlayın.

```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### PowerPoint dosyasını kaydetme
#### Genel Bakış
Değişikliklerinizi yeni bir PPTX dosyasına kaydedin.

`save` metodu, sunumu belirtilen formatta diske yazar.

#### Doğrudan yanıt
`presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` metodunu çağırın – bu, değiştirilmiş sunumu standart PowerPoint formatında diske yazar.

```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Yaygın sorunlar ve hata ayıklama

- **Chart not appearing** – grafiğin X/Y koordinatlarının ve boyutlarının slayt sınırları içinde olduğundan emin olun.  
- **Data points missing** – veri çalışma kitabı hücre indekslerinin doldurmak istediğiniz seri/satırla eşleştiğini doğrulayın.  
- **License exception** – geçici deneme lisansı 30 gün sonra sona erer; üretim sürümleri için kalıcı bir lisansla değiştirin.  
- **Performance slowdown on large files** – toplu olarak binlerce slayt işliyorsanız önbelleği devre dışı bırakmak için `Presentation.setCacheSize(0)` kullanın.

## Sıkça Sorulan Sorular

**Q:** Bu kodu bir web uygulamasında kullanabilir miyim?  
**A:** Evet. Kütüphane saf Java'dır, bu yüzden herhangi bir servlet konteynerinde veya Spring Boot hizmetinde çalıştırabilirsiniz.

**Q:** Aspose.Slides, Stock dışındaki diğer grafik türlerini destekliyor mu?  
**A:** Kesinlikle. Line, Bar, Pie ve Radar grafikleri dahil olmak üzere 70'ten fazla grafik türünü destekler.

**Q:** Grafik başlığını programlı olarak nasıl eklerim?  
**A:** `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` metodunu kullanın ve ardından başlığı gerektiği gibi biçimlendirin.

**Q:** Bir seri için veri noktası sayısında bir limit var mı?  
**A:** Pratikte on binlerce nokta ekleyebilirsiniz; bellek kullanımı lineer olarak artar ve kütüphane, ayak izini düşük tutmak için verileri akış olarak işler.

**Q:** En son sürüm için hangi Maven koordinatlarını kullanmalıyım?  
**A:** En son sürüm her zaman Maven Central'da `com.aspose:aspose-slides:25.4` (veya daha yeni) olarak mevcuttur.

---

**Son Güncelleme:** 2026-09-12  
**Test Edildiği Versiyon:** Aspose.Slides for Java 25.4  
**Yazar:** Aspose

## İlgili Öğreticiler

- [aspose slides maven bağımlılığı: Aspose.Slides for Java kullanarak Sunumlarda Grafik Ekleme ve Yapılandırma](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [PowerPoint Grafik Oluşturma Java – Aspose.Slides Kullanarak Grafiklerle Sunumları Kaydetme](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [PowerPoint Grafiklerini Oluşturma ve Biçimlendirme Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}