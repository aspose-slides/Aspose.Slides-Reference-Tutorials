---
date: '2026-03-07'
description: Pelajari cara membuat diagram garis di Java menggunakan Aspose.Slides,
  menambahkan judul diagram, menambahkan garis kisi, memformat label diagram, dan
  menyimpan presentasi profesional.
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: Cara Membuat Diagram Garis dengan Aspose.Slides di Java – Panduan Lengkap
url: /id/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cara membuat diagram garis dengan Aspose.Slides di Java

## Cara membuat diagram garis di Java Menggunakan Aspose.Slides

### Introduction
Membuat presentasi yang menarik secara visual sangat penting untuk komunikasi yang efektif. Apakah Anda seorang profesional bisnis atau pendidik, Anda sering perlu **membuat diagram garis** yang informatif dan estetis. Dalam tutorial ini kami akan menjelaskan cara menggunakan **Aspose.Slides for Java** untuk menghasilkan diagram garis, menambahkan judul diagram, menambahkan garis kisi, memformat label diagram, dan menyimpan hasilnya sebagai file PowerPoint.

#### Quick Answers
- **Library apa yang terbaik untuk membuat diagram di Java?** Aspose.Slides for Java
- **Tipe diagram apa yang dibahas dalam panduan ini?** Diagram garis dengan penanda
- **Apakah saya memerlukan lisensi untuk menjalankan contoh?** Lisensi sementara gratis dapat digunakan untuk evaluasi
- **IDE apa yang dapat saya gunakan?** IDE Java apa pun seperti IntelliJ IDEA, Eclipse, atau NetBeans
- **Bagaimana elemen diagram diformat?** Menggunakan pemanggilan API fluent untuk judul, sumbu, garis kisi, legenda, dan latar belakang

### What is a line chart and why use Aspose.Slides?
Diagram garis menampilkan titik data yang dihubungkan oleh garis lurus, menjadikannya ideal untuk menunjukkan tren seiring waktu. Aspose.Slides memungkinkan Anda membuat dan menyesuaikan diagram ini secara programatik, menghilangkan kebutuhan untuk mengedit PowerPoint secara manual.

### Prerequisites
- **Java Development Kit (JDK) 8+** terpasang
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, dll.)
- **Aspose.Slides for Java** library (ditambahkan melalui Maven atau Gradle)

#### Required Libraries and Dependencies
**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Sebagai alternatif, unduh JAR terbaru dari [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition
- Dapatkan [lisensi percobaan gratis](https://purchase.aspose.com/temporary-license/) untuk pengujian.
- Beli lisensi penuh dari [situs resmi Aspose](https://purchase.aspose.com/buy) untuk penggunaan produksi.

### Setting Up Aspose.Slides for Java
1. **Add the dependency** yang ditampilkan di atas ke proyek Anda.
2. **Apply the license** (jika Anda memilikinya) sebelum membuat objek presentasi apa pun.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Step‑by‑Step Implementation

### Step 1: Create the output directory (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```
*Why this matters:* Memastikan folder ada mencegah `FileNotFoundException` saat Anda menyimpan presentasi nanti.

### Step 2: Add a slide and insert a line chart
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
*Explanation:* Ini membuat slide baru dan menempatkan **diagram garis dengan penanda** pada koordinat yang ditentukan.

### Step 3: Add chart title (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
*Tip:* Menggunakan judul tebal berwarna abu‑abu membuat diagram langsung dikenali.

### Step 4: Format axes and add grid lines (add grid lines)
#### Vertical Axis Formatting
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```

#### Horizontal Axis Formatting
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
*Why this matters:* Garis kisi yang jelas dan label yang diputar meningkatkan keterbacaan, terutama ketika titik data padat.

### Step 5: Customize the legend (add chart title – already covered, but legend is part of overall formatting)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### Step 6: Set background colors (format chart labels – part of overall visual styling)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### Step 7: Save the presentation
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*Result:* Anda kini **memiliki file PowerPoint (`FormattedChart_out.pptx`) yang berisi diagram garis yang telah diformat sepenuhnya.**

## Practical Applications
- **Business Reports:** Menampilkan kinerja kuartalan dengan garis tren.
- **Educational Slides:** Memvisualisasikan data ilmiah untuk kuliah.
- **Project Proposals:** Menyoroti tonggak penting dan perkiraan.
- **Marketing Analysis:** Menyajikan tren ROI kampanye.
- **Dashboard Integration:** Mengekspor data langsung ke PowerPoint untuk pertemuan pemangku kepentingan.

## Performance Considerations
- **Memory Management:** Selalu panggil `dispose()` pada objek `Presentation` untuk melepaskan sumber daya native dengan cepat.

## Common Issues and Solutions
| Issue | Solution |
|-------|----------|
| **License not applied** | Muat lisensi percobaan/ penuh sebelum membuat objek `Presentation` apa pun. |
| **Chart appears blank** | Pastikan slide benar‑benar berisi seri data; tambahkan seri jika diperlukan. |
| **File not saved** | Pastikan direktori output ada (gunakan langkah “create directory java”). |
| **Colors not applied** | Gunakan konstanta `Color` dari `java.awt.Color` atau `PresetColor`. |

## Frequently Asked Questions

**Q: Can I create other chart types besides line charts?**  
A: Yes, Aspose.Slides supports bar, pie, scatter, and many more chart types.

**Q: How do I add multiple data series to the line chart?**  
A: Use `chart.getChartData().getSeries().add(...)` to insert additional series before formatting.

**Q: Is it possible to export the chart as an image?**  
A: Absolutely. Call `chart.getChartData().getChartDataWorkbook().save(...)` or render the slide to an image format.

**Q: Do I need a paid license for development?**  
A: A free temporary license works for evaluation; a commercial license is required for production deployments.

**Q: Which Java versions are supported?**  
A: The library works with JDK 8 through JDK 22 (use the appropriate classifier, e.g., `jdk16`). 

---

**Last Updated:** 2026-03-07  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}