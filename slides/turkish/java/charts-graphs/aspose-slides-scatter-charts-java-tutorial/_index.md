---
date: '2026-07-27'
description: Aspose.Slides for Java kullanarak grafiği nasıl özelleştireceğinizi öğrenin.
  PowerPoint grafiği oluşturmayı, scatter serilerini biçimlendirmeyi ve sunumları
  verimli bir şekilde kaydetmeyi öğrenin.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Aspose.Slides for Java ile grafiği nasıl özelleştireceğinizi öğrenin.
  Bu kılavuz, PowerPoint grafiği oluşturmayı, scatter noktalarını biçimlendirmeyi
  ve sunumları dışa aktarmayı gösterir.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Grafiği Özelleştirme: Scatter Chart Aspose Java''da'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Grafiği Özelleştirme: Scatter Chart Aspose Java''da'
url: /tr/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose ile Dağılım Grafiğini Özelleştirme

Bu öğreticide **grafiği nasıl özelleştireceğinizi** keşfedeceksiniz — özellikle bir dağılım grafiğini — güçlü Aspose.Slides for Java kütüphanesini kullanarak. Proje kurulumunu, bir dağılım grafiği oluşturmayı, seri tiplerini ve işaretçileri ayarlamayı ve sonunda sunumu kaydetmeyi adım adım göstereceğiz. Sonunda, programlı olarak profesyonel görünümlü dağılım grafiklerini oluşturabilecek ve her görsel detayı markanıza veya raporlama ihtiyaçlarınıza göre özelleştirebileceksiniz.

## Hızlı Yanıtlar
- **Hangi kütüphane gerekiyor?** Aspose.Slides for Java (v25.4+).  
- **Hangi Java sürümü destekleniyor?** JDK 8 or higher.  
- **İşaretçi şekillerini değiştirebilir miyim?** Yes – use `MarkerStyleType` to pick stars, circles, etc.  
- **Dosyayı nasıl kaydederim?** Call `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Lisans gerekli mi?** A free trial works for development; a commercial license is needed for production.

## Aspose.Slides ile Java'da Grafiği Nasıl Özelleştirirsiniz?
`Presentation` bir PowerPoint dosyasını bellekte temsil eden Aspose.Slides sınıfıdır. Yeni bir `Presentation` yükleyin, ilk slayta bir dağılım grafiği ekleyin, seri ve işaretçi stillerini yapılandırın, ardından `save` çağırın. Bu tek iş akışı, sadece birkaç Java kod satırıyla tamamen biçimlendirilmiş bir grafik oluşturur ve herhangi bir PowerPoint sunumuna eklemeye hazırdır.

## “customize scatter chart aspose” nedir?
Aspose ile bir dağılım grafiğini özelleştirmek, grafiğin verilerini, görünümünü ve davranışını programlı olarak tanımlamak anlamına gelir — nokta koordinatlarından işaretçi sembollerine kadar her şey — PowerPoint'i manuel olarak açmadan. Bu yaklaşım, otomatik raporlama, veri‑odaklı sunumlar veya tekrarlanabilir, yüksek‑kaliteli görselleştirmelere ihtiyaç duyulan herhangi bir senaryo için idealdir.

## Aspose.Slides ile dağılım grafiklerini neden özelleştirirsiniz?
Aspose.Slides, geliştiricilere grafik görünümü üzerinde tam programatik kontrol sağlar; bu sayede yüksek‑kaliteli görselleştirmelerin otomatik oluşturulması, raporlama hatlarına sorunsuz entegrasyonu ve PowerPoint'i manuel olarak açmadan her görsel öğenin özelleştirilebilmesi mümkün olur; bu da zaman tasarrufu sağlar ve sunumlar arasında tutarlılık garantiler.

- **Full control** – modify series types, marker styles, colors, and more via Java code.  
- **Automation** – generate dozens of charts on the fly for dashboards or batch reports.  
- **Cross‑platform** – works on any OS that supports Java, no Office installation required.  
- **Performance** – lightweight API that processes **150+ chart types** and handles multi‑hundred‑page presentations without loading the whole file into memory.

## Önkoşullar

Bu öğreticiyi takip edebilmek için şunlara sahip olduğunuzdan emin olun:

- **Aspose.Slides for Java** (v25.4 or later).  
- **Java Development Kit (JDK)** 8 + installed.  
- Maven veya Gradle bağımlılık yönetimi için (ya da JAR dosyasını manuel olarak indirebilirsiniz).  
- Temel Java bilgisi ve tercih ettiğiniz yapı aracına aşinalık.

## Aspose.Slides for Java'ı Kurma

Kütüphaneyi projenize aşağıdaki yöntemlerden birini kullanarak entegre edin.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Veya en son sürümü [Aspose Releases](https://releases.aspose.com/slides/java/) adresinden alın.

#### Lisans Edinimi
- **Free Trial** – 30‑day evaluation.  
- **Temporary License** – extended testing period.  
- **Full License** – production use with premium support.

## Dağılım Grafiğini Aspose ile Özelleştirme Adım‑Adım Kılavuzu

### 1️⃣ Sunum dosyalarınız için bir klasör hazırlayın
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Neden önemli:* Çıktı klasörünün var olduğundan emin olmak, PPTX'i daha sonra kaydettiğinizde `FileNotFoundException` oluşmasını önler.

### 2️⃣ Yeni bir sunum oluşturun ve ilk slaytı alın
`Presentation` bir PowerPoint belgesini temsil eder ve slaytlara ve şekillere erişim sağlar. `Presentation` sınıfı bellekte tüm bir PowerPoint dosyasını temsil eder.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Pürüzsüz hatlı bir dağılım grafiği ekleyin
`ChartType.ScatterWithSmoothLines` noktaların pürüzsüz hatlarla bağlandığı bir dağılım grafiği oluşturur.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Varsayılan serileri temizleyin ve kendi serinizi ekleyin
`IChartSeries` bir grafikteki veri serisini temsil eder.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ İlk seriyi veri noktalarıyla doldurun
`addDataPointForScatterSeries` bir dağılım serisine tek bir X‑Y noktası ekler.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Seri tipini ve işaretçi görünümünü özelleştirin
`Marker` bir grafik serisindeki her veri noktası için kullanılan görsel sembolü kontrol eder.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Sunumu kaydedin
`save` sunumu belirtilen formatta bir dosyaya yazar.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Özelleştirilmiş Dağılım Grafiklerinin Yaygın Kullanım Senaryoları
- **Financial dashboards** – plot stock price vs. volume.  
- **Scientific research** – display experimental measurements with error markers.  
- **Project management** – compare planned vs. actual effort across tasks.  

## Performans İpuçları
- `pres.dispose()` çağrısını kaydettikten sonra yapın, böylece yerel bellek serbest bırakılır.  
- Büyük veri setleri için önce çalışma kitabını doldurun, ardından serileri bağlayın; bu, tekrar eden UI yenilemelerini önler.  
- Çok sayıda seri eklerken bellek kullanımını düşük tutmak için tek bir `IChartDataWorkbook` örneğini yeniden kullanın.

## Sıkça Sorulan Sorular

**S: İşaretçilerin rengini nasıl değiştiririm?**  
C: `series.getMarker().getFillFormat().setFillColor(Color)` kullanın; burada `Color`, `java.awt.Color` örneği (ör. `Color.RED`) olur.

**S: Bir dağılım grafiğine iki seriden fazla ekleyebilir miyim?**  
C: Evet. Her ek seri için `chart.getChartData().getSeries().add(...)` çağırın ve noktalarını uygun şekilde doldurun.

**S: Her seri için özel bir lejand ayarlamak mümkün mü?**  
C: Kesinlikle. Bir seri oluşturduktan sonra `series.getLegend().setText("Your Legend Text")` çağırarak varsayılan adı geçersiz kılabilirsiniz.

**S: Grafiği PPTX yerine bir görüntü olarak dışa aktarabilir miyim?**  
C: Grafiği yapılandırdıktan sonra `chart.getImage().save("chart.png", ImageFormat.Png)` çağırın. Bu, bağımsız bir PNG dosyası üretir.

**S: Dağılım noktalarını animasyonlu yapmak istersem ne yapmalıyım?**  
C: Aspose.Slides animasyon efektlerini destekler. `chart.getTimeline().getMainSequence().addEffect(...)` kullanarak grafiğe veya bireysel serilere giriş ya da vurgu animasyonları ekleyebilirsiniz.

---

**Son Güncelleme:** 2026-07-27  
**Test Edilen:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Öğreticiler

- [Create and Customize PowerPoint Charts in Java Using Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [How to Create Bubble Chart in PowerPoint Using Aspose.Slides for Java (Tutorial)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Create and Customize Charts with Trend Lines in Aspose.Slides for Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}