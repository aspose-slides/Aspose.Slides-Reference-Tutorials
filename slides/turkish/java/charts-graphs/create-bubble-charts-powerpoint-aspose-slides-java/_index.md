---
date: '2026-09-17'
description: Aspose.Slides for Java kullanarak bubble chart PowerPoint nasıl oluşturulacağını
  öğrenin. Bu kılavuz, chart'ı slide'a eklemeyi, bubble size'ı yapılandırmayı ve PPTX'i
  verimli bir şekilde kaydetmeyi gösterir.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Aspose.Slides for Java kullanarak bubble chart PowerPoint nasıl oluşturulacağını
  öğrenin. Bu öğretici, chart'ı slide'a eklemeyi, adjust bubble sizes'ı ve presentation'ı
  verimli bir şekilde kaydetmeyi açıklar.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Aspose.Slides for Java ile bubble chart PowerPoint oluşturma
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Aspose.Slides for Java ile bubble chart PowerPoint oluşturma
url: /tr/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides for Java ile balon grafik PowerPoint oluşturma

## Giriş
If you need to **create bubble chart powerpoint** presentations programmatically, Aspose.Slides for Java gives you a clean, server‑side API that works without Microsoft Office. In this tutorial you’ll learn how to add a chart to a slide, control bubble sizes, and save the final PPTX while efficiently managing resources. The steps are broken down so you can copy‑paste the code into any Java project and see results instantly.

## Hızlı cevaplar
- **Hangi kütüphane gerekiyor?** Aspose.Slides for Java
- **Hangi Java sürümü gerekiyor?** JDK 16 or higher
- **Balon grafik nasıl eklenir?** Call `addChart(ChartType.Bubble, …)` on a slide
- **Balon boyutunu değiştirebilir miyim?** Yes, via `setBubbleSizeScale()`
- **Dosya nasıl kaydedilir?** Use `pres.save("Result.pptx", SaveFormat.Pptx)`

## Balon grafik PowerPoint oluşturma nedir?
Creating a bubble chart in PowerPoint means programmatically generating a chart where each data point is represented by a bubble whose X‑position, Y‑position, and size encode three dimensions of data. Aspose.Slides for Java handles the rendering, so you don’t need PowerPoint installed.

## Neden Aspose.Slides for Java kullanılmalı?
Aspose.Slides supports **50+ chart types**, can process presentations up to **2 GB** without loading the entire file into memory, and runs on any platform that supports Java 16+. These quantified capabilities make it a reliable choice for enterprise‑grade reporting.

## Önkoşullar
- **Java Development Kit** 16 or newer installed.
- **Aspose.Slides for Java** library (add via Maven, Gradle, or direct JAR download).
- Basic familiarity with Java syntax and object‑oriented programming.

## Aspose.Slides for Java kurulumu
To start using Aspose.Slides, include the library in your build system.

### Maven
Add the following dependency to your `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include this in your `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Doğrudan indirme
You can also obtain the latest JAR from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Lisans edinimi
- **Ücretsiz deneme** – explore all features without cost.  
- **Geçici lisans** – extended evaluation for larger projects.  
- **Tam lisans** – required for production deployments.

### Temel başlatma ve kurulum
The `Presentation` class is the entry point for creating or loading PowerPoint files.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Uygulama rehberi
Below is a step‑by‑step walk‑through for creating a bubble chart and managing resources.

## Balon grafik PowerPoint nasıl oluşturulur
In this section you will learn the exact sequence of API calls needed to generate a bubble chart, configure its visual properties, and persist the result as a PPTX file. The approach works for any Java project that includes Aspose.Slides and follows best‑practice resource handling.

Load the presentation, add a bubble chart, configure its appearance, and save the file.

### Doğrudan cevap
Create a new `Presentation`, call `addChart(ChartType.Bubble, …)` on the desired slide, adjust the bubble size scale with `setBubbleSizeScale(150)`, then save using `pres.save("Result.pptx", SaveFormat.Pptx)`. This sequence adds a fully functional bubble chart in just a few lines of Java.

- **`ChartType.Bubble`** represents the bubble chart type.  
- **`addChart`** inserts a new chart of the specified type onto a slide.  
- **`setBubbleSizeScale`** adjusts the overall size of bubbles in the chart.  
- **`SaveFormat.Pptx`** specifies the PPTX file format for saving.  

#### Adım‑adım uygulama
**1. Initialize presentation** – instantiate the `Presentation` object.  
```java
Presentation pres = new Presentation();
```

**2. Add bubble chart** – insert the chart at the chosen coordinates.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` tells Aspose.Slides to create a bubble chart.  
- The numeric parameters define the X/Y position and width/height in points.

**3. Configure bubble size scale** – enlarge bubbles for better visual impact.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Setting the scale to **150 %** makes each bubble 1.5 × larger than the default.

**4. Save presentation** – write the PPTX to disk.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Sorun giderme ipuçları
- Verify write permissions for the output folder.  
- Confirm that the Aspose.Slides JAR matches the JDK version you are using.

## PowerPoint kaynaklarını etkili bir şekilde yönetma
Effective resource handling prevents memory leaks and keeps the JVM footprint low, especially when processing large decks or running in a server environment. Follow the pattern below to guarantee that native resources are released even if an exception occurs.

Efficient resource handling prevents memory leaks, especially when processing large decks.

### Doğrudan cevap
After you finish working with a `Presentation`, always call `pres.dispose()` inside a `try‑finally` block; this releases native resources and allows the JVM to reclaim memory promptly.

- **`pres.dispose()`** releases native resources used by the presentation.

**1. Create and modify** – work with the presentation as needed.  
```java
Presentation pres = new Presentation();
```

**2. Dispose resources** – free memory once processing is complete.  
```java
if (pres != null) pres.dispose();
```

## Pratik uygulamalar
Bubble charts excel in scenarios where three data dimensions need simultaneous visualization:

1. **Market analysis** – bubble size represents revenue while X/Y axes show growth and market share.  
2. **Performance metrics** – compare employee productivity (X), satisfaction (Y), and impact (size).  
3. **Geographical data** – plot cities with population encoded in bubble size.  
4. **Project management** – visualize timeline (X), cost (Y), and risk (size) on a single slide.

## Performans değerlendirmeleri
- **Resource usage** – dispose of presentations promptly to keep heap usage low.  
- **Java memory management** – wrap presentation work in `try‑finally` to guarantee disposal even on exceptions.  
- **Stay current** – upgrade to the latest Aspose.Slides version to benefit from performance optimizations and bug fixes.

## Sıkça Sorulan Sorular

**S: Aspose.Slides for Java nedir?**  
C: Aspose.Slides for Java is a standalone library that lets you create, edit, and convert PowerPoint files without needing Microsoft Office.

**S: Aspose.Slides'ı mevcut Java projemle nasıl entegre ederim?**  
C: Add the Maven or Gradle dependency shown earlier, or drop the JAR into your classpath, then import `com.aspose.slides.*`.

**S: Büyük sunumlar için Aspose.Slides kullanabilir miyim?**  
C: Yes, the library efficiently handles presentations up to **2 GB** and supports streaming to avoid loading the whole file into memory.

**S: Balon grafikler dışında hangi grafik tipleri mevcuttur?**  
C: Over **50 chart types** are supported, including bar, line, pie, radar, and waterfall charts.

**S: Grafik öğelerinin stilini özelleştirmek için yerleşik destek var mı?**  
C: Absolutely. You can customize colors, fonts, borders, and data labels via the chart’s `ChartSeries` and `ChartTitle` objects.

## Kaynaklar
- **Documentation**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free trial**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary license**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Son Güncelleme:** 2026-09-17  
**Test Edilen:** Aspose.Slides for Java 25.4 (jdk16)  
**Yazar:** Aspose

## İlgili Eğitimler

- [PowerPoint'e Grafik Ekleme Aspose.Slides for Java Kullanarak: Adım‑Adım Kılavuz](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java ile Aspose.Slides kullanarak PowerPoint grafiği oluşturma](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [PowerPoint Grafik Oluşturma Java – Aspose.Slides ile Grafikli Sunumları Kaydetme](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}