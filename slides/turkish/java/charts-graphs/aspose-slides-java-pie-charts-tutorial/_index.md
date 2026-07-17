---
date: '2026-07-17'
description: Aspose.Slides for Java kullanarak pie chart'ı döndürmeyi, pie chart renklerini
  özelleştirmeyi ve slaytı PDF olarak dışa aktarmayı öğrenin – kapsamlı bir veri görselleştirme
  rehberi.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Aspose.Slides for Java kullanarak pie chart'ı döndürün ve pie chart
  renklerini özelleştirin. Slaytı PDF olarak dışa aktarmayı ve chart data worksheet
  ile çalışmayı öğrenin.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Java'da Pie Chart'ı Döndürme ve Renkleri Özelleştirme – Aspose.Slides Rehberi
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Java ile Aspose.Slides kullanarak Pie Chart'ı Döndürme ve Renklerini Özelleştirme
url: /tr/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides for Java ile Pasta Grafikler Oluşturma: Tam Bir Kılavuz

## Giriş
Bu kılavuzda **rotate pie chart** öğelerini nasıl döndüreceğinizi, her dilimin rengini özelleştirmeyi ve son slaytı PDF olarak dışa aktarmayı Aspose.Slides for Java ile öğreneceksiniz. Satış panosu, finansal rapor veya herhangi bir veri odaklı sunum oluşturuyor olun, bu teknikleri ustalaşmak, Microsoft Office'e bağımlı olmadan net ve göz alıcı görseller sunmanızı sağlar. Araçları hazırlayalım ve başlayalım.

## Hızlı Yanıtlar
- **Yeni bir sunum başlatan sınıf nedir?** `Presentation` from `com.aspose.slides`.
- **Hangi API çağrısı bir pasta grafiği ekler?** `slide.addChart(ChartType.Pie, …)`.
- **Her dilime benzersiz bir renk nasıl verilir?** `series.setColorVaried(true)` çağırın ve veri noktasına göre katı doldurmalar ayarlayın.
- **Grafiği döndüren yöntem nedir?** `chart.setRotationAngle(double)` – 0 ile 360 derece arasında bir değer kullanın.
- **Slayt PDF olarak dışa aktarılabilir mi?** Evet, `presentation.save("output.pdf", SaveFormat.Pdf)` çağırın.

## “customize pie chart colors” nedir?
Pasta grafik renklerini özelleştirmek, pastanın her dilimine farklı doldurma renkleri atamak anlamına gelir; bu, okunabilirliği ve görsel etkiyi artırır. Aspose.Slides'te bunu, renk çeşitliliğini etkinleştirerek ve ardından bireysel veri noktaları için katı doldurma renkleri ayarlayarak elde edersiniz. Bu yaklaşım, her veri segmentinin sunumda net bir şekilde öne çıkmasını sağlar.

## Pasta grafikler oluşturmak için Aspose.Slides for Java neden kullanılmalı?
Aspose.Slides **150+ grafik türünü** destekler ve tipik bir sunucuda **5 saniyeden** az bir sürede 300 sayfalık bir sunumu oluşturabilir; Microsoft Office kurulumuna gerek yoktur. Kütüphane Windows, Linux ve macOS üzerinde çalışır ve Java tabanlı veri görselleştirme projeniz için platformlar arası esneklik sağlar.

## Önkoşullar
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 veya daha yeni
- IntelliJ IDEA, Eclipse veya NetBeans gibi IDE
- Temel Java bilgisi ve Maven veya Gradle ile aşinalık

## Aspose.Slides for Java'ı Kurma
Kütüphaneyi derleme yapılandırmanıza ekleyin.

**Maven**  
`pom.xml` dosyanıza bu kod parçacığını ekleyin:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
`build.gradle` dosyanıza aşağıdakileri ekleyin:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
Eğer manuel bir yaklaşımı tercih ediyorsanız, en son JAR'ı [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) adresinden indirin.

### Lisans Edinme Adımları
- **Free Trial** – tüm özellikleri ücretsiz keşfedin.  
- **Temporary License** – deneme sınırlarını kısa bir süre için genişletin.  
- **Purchase** – üretim kullanımı için kalıcı bir lisans edinin.

**Temel Başlatma ve Kurulum**  
`Presentation` sınıfı, bellekte bir PowerPoint dosyasını temsil eder ve slaytları manipüle etmek için yöntemler sağlar.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Uygulama Rehberi
Aşağıda, bir slayt oluşturulmasından son pasta grafiğinin döndürülmesine kadar her şeyi kapsayan adım adım bir rehber bulunmaktadır.

### Sunumu ve Slaytı Başlatma
Yeni bir `Presentation` örneği oluşturun ve grafiğin tuvali olarak kullanılacak ilk slaytı alın.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Slayta Pasta Grafik Ekleme
`addChart`, belirtilen türde bir grafik şekli ekler ve slayta verilen koordinatlarda yerleştirir.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Grafik Başlığını Ayarlama
`setTitle`, grafiğe bir metin başlığı atar ve ortalanmış şekilde konumlandırır.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Seri İçin Veri Etiketlerini Yapılandırma
`setShowValue(true)`, serinin her veri noktasında sayısal değer etiketlerini etkinleştirir.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Grafik Veri Çalışma Sayfasını Hazırlama
`ChartDataWorkbook`, grafik serileri ve kategorilerine veri sağlayan temel veri tablosunu saklar.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Grafiğe Kategoriler Ekleme
`addCategory`, grafiğin veri serileri için yeni bir kategori etiketi oluşturur.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Seri Ekleme ve Veri Noktalarını Doldurma
`addSeries`, bir veri serisi oluşturur ve `addDataPointForBarSeries`, her kategori için sayısal değerler ekler.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Seri Renklerini ve Kenarlıklarını Özelleştirme
`setColorVaried(true)`, dilim başına renkleri etkinleştirir ve `setFillFormat`, her veri noktasına katı bir doldurma atar.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Özel Veri Etiketlerini Yapılandırma
`setDataLabelFormat`, etiket görünümünü, konumunu ve yazı tipini özelleştirerek daha net grafik açıklamaları sağlar.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Dönüş Açısını Ayarlama ve Sunumu Kaydetme
`setRotationAngle`, tüm pasta grafiğini döndürür ve `save`, sunumu bir dosyaya yazar.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Pasta grafiği nasıl döndürülür?
Grafik nesnesini yükleyin, `chart.setRotationAngle(45.0)` (veya istediğiniz derece değerini) çağırın ve ardından sunumu kaydedin. Bir pasta grafiğini döndürmek, başlangıç açısını değiştirir ve veriyi değiştirmeden belirli bir segmenti vurgulamanıza olanak tanır. Bu tek yöntem çağrısı, Aspose.Slides'teki herhangi bir `Chart` örneği için çalışır. Döndürmeyi, çeşitli dilim renkleriyle birleştirerek en önemli veri noktasına dikkat çekebilirsiniz.

## Yaygın Sorunlar ve Çözümler
| Sorun | Neden | Çözüm |
|-------|-------|-----|
| **Tüm dilimler aynı renkte görünüyor** | `setColorVaried(true)` çağrılmadı | Seri grubunda renk çeşitliliğini etkinleştirdiğinizden emin olun. |
| **Veri etiketleri görünmüyor** | `showValue` bayrağı devre dışı | Etiket formatında `setShowValue(true)` çağırın. |
| **Döndürme etkisiz** | Eski bir Aspose.Slides sürümü kullanılıyor | Sürümü 25.4 veya daha yenisine yükseltin. |
| **Çalışma zamanında lisans istisnası** | Lisans dosyası eksik veya geçersiz | `Presentation` oluşturulmadan önce `License license = new License(); license.setLicense("Aspose.Slides.lic");` kodu ile lisansınızı yükleyin. |

## Sık Sorulan Sorular

**S: Aspose.Slides Java lisansını nasıl elde edebilirim?**  
C: Aspose web sitesinden ücretsiz deneme talep edin, ardından kalıcı bir lisans satın alın. Çalışma zamanında, Yaygın Sorunlar tablosunda gösterildiği gibi yükleyin.

**S: Bu kodu eski JDK sürümleriyle kullanabilir miyim?**  
C: API, JDK 16 veya üzeri gerektirir; eski sürümler desteklenmez.

**S: Grafiği PPTX yerine görüntü olarak dışa aktarmak mümkün mü?**  
C: Evet—render işlemi sonrası `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` çağırın.

**S: Pasta grafiğinde birden fazla seri ihtiyacım olursa ne yapmalıyım?**  
C: Pasta grafikler tek bir veri serisi için tasarlanmıştır; birden fazla seri gerekiyorsa, donut grafiği kullanmayı düşünün.

**S: Aspose.Slides Linux sunucularda çalışır mı?**  
C: Kesinlikle—Aspose.Slides for Java platformdan bağımsızdır ve uyumlu bir JDK ile herhangi bir işletim sisteminde çalışır.

---

**Son Güncelleme:** 2026-07-17  
**Test Edilen Versiyon:** Aspose.Slides for Java 25.4 (JDK 16)  
**Yazar:** Aspose  

{{< blocks/products/products-backtop-button >}}

## İlgili Eğitimler

- [Java Sunumlarında Aspose.Slides Kullanarak Pasta Grafik Oluşturma: Kapsamlı Bir Rehber](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Aspose.Slides ile Java'da Pasta Grafiklerde Uzmanlaşma: Kapsamlı Bir Rehber](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Aspose.Slides ile Java'da Grafik Metinlerini Döndürme: Kapsamlı Bir Rehber](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}