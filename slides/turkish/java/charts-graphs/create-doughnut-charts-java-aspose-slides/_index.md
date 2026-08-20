---
date: '2026-08-16'
description: Aspose.Slides kullanarak Java'da doughnut chart eklemeyi öğrenin. Bu
  adım adım kılavuz, Maven bağımlılık kurulumu, chart yapılandırması, renkler, etiketler
  ve PPTX kaydetmeyi kapsar.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Aspose.Slides kullanarak Java'da doughnut chart ekleme. Maven'i kurmak,
  renkleri ve etiketleri özelleştirmek ve PPTX dosyaları oluşturmak için bu kılavuzu
  izleyin.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Java'da Aspose.Slides ile doughnut chart ekleme
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Java'da Aspose.Slides ile doughnut chart ekleme
url: /tr/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Java'da Aspose.Slides ile halka grafiği ekleme

## Giriş

Programatik olarak **doughnut chart** oluşturmak, ham sayıları anında bir hikaye anlatan göz alıcı bir görsele dönüştürebilir. Java'da **Aspose.Slides**, bu süreci basitleştirir ve PowerPoint'i hiç açmadan sunuma hazır grafikler oluşturmanıza olanak tanır. Bu öğreticide, **how to add doughnut** grafiklerini bir PPTX dosyasına adım adım eklemeyi öğreneceksiniz— Maven Aspose Slides bağımlılığını kurmaktan serileri, kategorileri, renkleri ve etiketleri özelleştirmeye ve sonunda sunumu kaydetmeye kadar.

Bu rehberin sonunda, raporlar, gösterge tabloları veya otomatik slayt desteleri için mükemmel olan dinamik doughnut grafiklerini herhangi bir PPTX dosyasına yerleştirebileceksiniz.

### Hızlı Yanıtlar
- **Hangi kütüphane kullanılıyor?** Aspose.Slides for Java  
- **Ana görev?** PPTX dosyasına bir doughnut grafiği ekleme  
- **Kütüphane nasıl eklenir?** Maven Aspose Slides bağımlılığını (veya Gradle) kullanın  
- **Minimum Java sürümü?** JDK 16 veya daha üstü  
- **Renkleri ve etiketleri özelleştirebilir miyim?** Evet, API tam biçimlendirme kontrolü sağlar  

## Doughnut grafiği nedir ve neden kullanılır?

Doughnut grafiği, boş bir merkezle bir pasta grafiğinin bir varyasyonudur ve birden çok veri serisinin konsantrik halkalar olarak gösterilmesini sağlar. **Bölümler‑bütün ilişkisini birden çok kategori üzerinde görselleştirirken, merkezde ek bilgi için alan bırakır.** Bu, birden çok çeyrek boyunca bölge bazında satışları, departmanlar arasındaki bütçe tahsislerini veya hiyerarşik oran verilerini göstermeniz gereken herhangi bir senaryoyu karşılaştırmak için idealdir.

## Java için Aspose.Slides neden kullanılmalı?

Microsoft Office kurmadan bir doughnut grafiği ekleyebilirsiniz ve kütüphane **50'den fazla giriş ve çıkış formatını** işleyerek 500'den fazla slaytı olan sunumları yönetebilir. Aspose.Slides, aynı donanımda yerel Office otomasyonuna göre **3 katına kadar daha hızlı render** sağlar ve Windows, Linux ve macOS'ta çalışır. Bu ölçülebilir avantajlar, büyük slayt destelerini başsız (headless) sunucularda öngörülebilir performansla oluşturabileceğiniz anlamına gelir.

## Önkoşullar

- **Gerekli kütüphaneler**  
  - Aspose.Slides for Java 25.4 veya daha yeni (doughnut grafiklerini eklemenizi sağlayan kütüphane).  

- **Ortam**  
  - Makinenizde yüklü JDK 16 veya daha üstü.  
  - IntelliJ IDEA, Eclipse veya NetBeans gibi bir IDE.  

- **Bilgi**  
  - Temel Java sözdizimi ve nesne yönelimli kavramlar.  
  - Bağımlılık yönetimi için Maven veya Gradle konusunda aşinalık.  

## Maven Aspose Slides bağımlılığı

`pom.xml` dosyanıza aşağıdaki Maven bağımlılığını ekleyin. Bu, kütüphaneyi projenize çekmek için gereken **maven aspose slides dependency**'dir.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Gradle tercih ediyorsanız, aşağıdaki eşdeğer kodu kullanın.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

JAR dosyasını resmi sürüm sayfasından doğrudan da indirebilirsiniz:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Lisans edinme

Değerlendirme filigranını kaldırmak ve tam özellik setini açmak için:

- **Ücretsiz deneme** – geçici bir lisansla başlayın.  
- **Geçici lisans** – birini [Aspose web sitesinden](https://purchase.aspose.com/temporary-license/) talep edin.  
- **Ticari lisans** – üretim kullanımı için satın alın.

Lisansı kodunuzda uygulayın:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Uygulama rehberi

### Sunumu başlatma ve doughnut grafiği ekleme

Presentation, bir PowerPoint sunumunu temsil eden Aspose.Slides sınıfıdır. Mevcut bir PPTX dosyasını yükleyin veya yeni bir `Presentation` nesnesi oluşturun, ardından ilk slayta bir doughnut grafiği ekleyin.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Grafik veri çalışma kitabını yapılandırma ve mevcut verileri temizleme

Çalışma kitabı, grafiğin verilerini depolayan dahili bir elektronik tablodur. Grafiği destekleyen çalışma kitabını elde edin, ardından temiz bir başlangıç için varsayılan serileri veya kategorileri temizleyin.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Grafiğe seri ekleme

Bir seri, grafikte çizilen veri noktalarının bir koleksiyonunu temsil eder. En fazla 15 seri ekleyebilirsiniz. Her seri özelleştirilebilir—burada patlamayı, doughnut‑hole boyutunu ve ilk dilim açısını ayarlıyoruz.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Kategoriler ve veri noktaları ekleme

Kategoriler, grafiğin ekseni boyunca her veri noktasının etiketleridir. 15 kategori oluşturun ve her seriyi bir veri noktasıyla doldurun. Son seri özel etiket biçimlendirmesi alır.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Renkleri ve veri etiketlerini özelleştirme

`FillType.Solid`, grafik öğeleri için katı bir dolgu rengi belirtir. Her seri için katı bir dolgu rengi ayarlayın ve veri etiketlerini etkinleştirin. Son seri için etiket yazı tipi rengini de değiştiririz.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Sunumu kaydetme

`save`, seçilen formatta sunumu bir dosyaya yazar. Güncellenen sunumu PPTX formatında diske yazın veya gerekirse PDF olarak dışa aktarın.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Yaygın sorunlar ve çözümler

- **License not found** – `license.lic` dosyasının yolunun doğru ve dosyanın okunabilir olduğunu doğrulayın.  
- **Chart appears blank** – Yeni serileri/kategorileri eklemeden önce mevcut serileri/kategorileri temizlediğinizden emin olun.  
- **Incorrect colors** – Hem dolgu hem de çizgi formatları için `FillType.Solid` ayarlandığını doğrulayın.  
- **Performance with many series** – Bellek kullanımını kontrol altında tutmak için seri/kategori sayısını sınırlayın veya çalışma kitabı hücrelerini yeniden kullanın.  

## Sıkça Sorulan Sorular

**S: Önceden var olan bir PPTX dosyası olmadan bir doughnut grafiği oluşturabilir miyim?**  
C: Evet, `new Presentation()` oluşturup boş bir slayt destesiyle başlayabilir, ardından yukarıda gösterildiği gibi bir grafik ekleyebilirsiniz.

**S: Aspose.Slides PDF'ye dışa aktarmayı destekliyor mu?**  
C: Kesinlikle. Grafik oluşturduktan sonra `pres.save("output.pdf", SaveFormat.Pdf);` çağrısıyla slaytın PDF sürümünü alabilirsiniz.

**S: doughnut delik boyutunu nasıl değiştiririm?**  
C: `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` kodunu kullanın; `value` 0‑100 arasında bir değerdir.

**S: Tüm serilere, sadece son seriye değil, veri etiketleri eklemek mümkün mü?**  
C: Evet, etiket‑biçimlendirme bloğunu `if (i == ...)` koşulunun dışına taşıyıp her `dataPoint` için uygulayabilirsiniz.

**S: Hangi Java sürümleri destekleniyor?**  
C: Aspose.Slides 25.4, JDK 16 ve üzerini destekler. Daha eski JDK'lar için Maven bağımlılığında uygun sınıflandırıcı (classifier) gerekir.

---

**Son Güncelleme:** 2026-08-16  
**Test Edilen:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Yazar:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## İlgili Öğreticiler

- [Java için Aspose.Slides Kullanarak PowerPoint'e Grafik Ekleme: Adım Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java'da Aspose.Slides ile Pasta Grafiği Renklerini Özelleştirme – Tam Kılavuz](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Aspose.Slides for Java ile PowerPoint Grafik Kategorilerini Canlandırma | Adım Adım Kılavuz](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}