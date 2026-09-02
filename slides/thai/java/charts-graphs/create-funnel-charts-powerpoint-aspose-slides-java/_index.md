---
date: '2026-09-02'
description: เรียนรู้วิธีสร้างแผนภูมิ funnel ใน PowerPoint ด้วย Aspose.Slides for
  Java คู่มือขั้นตอนต่อขั้นตอนนี้ครอบคลุมการตั้งค่าข้อมูลแผนภูมิ การปรับแต่งสี และการส่งออกงานนำเสนอ
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: เรียนรู้วิธีสร้างแผนภูมิ funnel ใน PowerPoint ด้วย Aspose.Slides for
  Java คู่มือนี้จะพาคุณผ่านการตั้งค่าข้อมูล การปรับแต่งสี และการส่งออกงานนำเสนอขั้นสุดท้าย
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: สร้างแผนภูมิ funnel ใน PowerPoint ด้วย Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: สร้างแผนภูมิ funnel ใน PowerPoint ด้วย Aspose.Slides for Java
url: /th/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เชี่ยวชาญการสร้างแผนภูมิกรวยใน PowerPoint ด้วย Aspose.Slides for Java

## บทนำ
การสร้างงานนำเสนอที่น่าดึงดูดเป็นศิลปะที่ผสานการแสดงผลข้อมูล การออกแบบ และการเล่าเรื่อง ภาพที่ทรงพลังที่ทำให้กระบวนการหลายขั้นตอนชัดเจนทันทีคือแผนภูมิกรวย ไม่ว่าคุณจะต้องการอธิบายสายงานขาย กระบวนการแปลง หรือคอขวดการผลิต แผนภูมิกรวยที่ออกแบบดีจะเปลี่ยนตัวเลขดิบให้เป็นเรื่องราวที่เข้าใจง่าย ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **create funnel chart** ใน PowerPoint อย่างโปรแกรมเมติกโดยใช้ Aspose.Slides for Java ตั้งค่าข้อมูล ปรับสีของแต่ละส่วน และส่งออกสไลด์ที่เสร็จสมบูรณ์

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีเพิ่ม Aspose.Slides for Java ไปยังโครงการ Maven หรือ Gradle
- วิธีสร้างอ็อบเจ็กต์ `Presentation` และเข้าถึงสไลด์ของมัน
- วิธีแทรกแผนภูมิกรวย กำหนดหมวดหมู่ และเติมข้อมูลซีรีส์
- วิธีจัดรูปแบบแต่ละชิ้นของกรวยด้วยการเติมสีทึบหรือสีที่กำหนดตามแบรนด์
- วิธีบันทึกงานนำเสนอเป็นไฟล์ PPTX หรือส่งออกสไลด์เป็นภาพ

## คำตอบสั้น
- **ไลบรารีหลักสำหรับการแสดงผลข้อมูลใน Java คืออะไร?** Aspose.Slides for Java.  
- **คุณสร้างแผนภูมิกรวยใน PowerPoint อย่างไร?** Call `slide.addChart(ChartType.Funnel, …)` on the target slide.  
- **API ใดที่ตั้งแหล่งข้อมูลของแผนภูมิ?** Use `IChartDataWorkbook` together with `chart.getChartData()`.  
- **คุณสามารถปรับสีสำหรับแต่ละส่วนของกรวยได้หรือไม่?** Yes—set `FillFormat.setFillType(FillType.Solid)` and assign a `java.awt.Color`.  
- **คุณต้องการไลเซนส์สำหรับการใช้งานในผลิตภัณฑ์หรือไม่?** A purchased Aspose.Slides license is required for commercial deployments.

## Java data visualization คืออะไร?
Java data visualization คือการแปลงข้อมูลดิบให้เป็นแผนภูมิ กราฟ หรือกราฟิกเชิงโต้ตอบโดยตรงจากแอปพลิเคชัน Java Aspose.Slides for Java เป็นไลบรารีชั้นนำที่ช่วยให้นักพัฒนาสร้างแผนภูมิกว่า 100 ชนิด—including funnel charts—โดยไม่ต้องเปิด PowerPoint ด้วยตนเอง รองรับงานนำเสนอที่มีสไลด์สูงสุด 500 สไลด์พร้อมการใช้หน่วยความจำที่ต่ำ

## ทำไมต้องใช้แผนภูมิกรวยใน PowerPoint?
แผนภูมิกรวยเปิดเผยอัตราการสูญเสียในแต่ละขั้นตอนอย่างรวดเร็ว ทำให้เหมาะสำหรับการวิเคราะห์สายงานขาย การวิเคราะห์การแปลง หรือการตรวจสอบประสิทธิภาพกระบวนการ Aspose.Slides ให้การควบคุมแบบพิกเซลที่สมบูรณ์แบบต่อการจัดวาง สีของส่วนต่าง ๆ และป้ายข้อมูล เพื่อให้คุณรักษาความสอดคล้องของแบรนด์และหลีกเลี่ยงความยุ่งยากในการแก้ไขแผนภูมิด้วย UI ของ PowerPoint

## ข้อกำหนดเบื้องต้น (H2)

### ไลบรารีที่ต้องการ, เวอร์ชัน, และการพึ่งพา
เพื่อใช้งาน Aspose.Slides for Java ในโครงการของคุณ ให้รวมพิกัด Maven หรือ Gradle ที่เหมาะสม ไลบรารีนี้ทำงานกับ Java 8‑21 และไม่ต้องการการพึ่งพาเนทีฟภายนอก

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

คุณสามารถดาวน์โหลด JAR โดยตรงจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) ได้เช่นกัน

### ข้อกำหนดการตั้งค่าสภาพแวดล้อม
ตรวจสอบให้แน่ใจว่าคุณมี JDK 8 หรือใหม่กว่าและ `JAVA_HOME` ชี้ไปยังไดเรกทอรี JDK ที่ถูกต้อง Aspose.Slides ทำงานบนระบบปฏิบัติการใด ๆ ที่รองรับ JDK รวมถึง Windows, macOS, และ Linux

### ความรู้เบื้องต้นที่จำเป็น
ความคุ้นเคยพื้นฐานกับไวยากรณ์ Java, การเขียนโปรแกรมเชิงวัตถุ, และแนวคิดของไฟล์งานนำเสนอจะช่วยได้ แต่โค้ดสแนปช็อตทั้งหมดอธิบายอย่างละเอียดสำหรับนักพัฒนาทุกระดับ

## การตั้งค่า Aspose.Slides for Java (H2)

1. **เพิ่มการพึ่งพา** – ใช้สคริปต์ Maven หรือ Gradle ด้านบน.  
2. **Obtain a license** –  
   - **Free trial** – Download a temporary license from [Aspose's website](https://purchase.aspose.com/temporary-license/) for evaluation.  
   - **Full license** – Purchase a production license via the [purchase page](https://purchase.aspose.com/buy).  
3. **Basic initialization** –  

`Presentation` is Aspose.Slides' core class that represents a PowerPoint file in memory. It provides access to slides, shapes, and chart objects.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

โค้ดข้างต้นสร้างอินสแตนซ์ `Presentation` ใหม่ พร้อมสำหรับการจัดการสไลด์ และรับประกันว่าทรัพยากรจะถูกปล่อยด้วย `dispose()`.

## คู่มือการดำเนินการ

เราจะเดินผ่านแต่ละฟีเจอร์ที่จำเป็นสำหรับการสร้างแผนภูมิกรวยครบวงจร โดยเพิ่มข้อความอธิบายสั้น ๆ ก่อนทุกโค้ดแพลสโฮลเดอร์

### ฟีเจอร์ 1: การสร้างงานนำเสนอ (H2)

#### ภาพรวม
เริ่มต้นด้วยการสร้างอินสแตนซ์ของคลาส `Presentation` วัตถุนี้เป็นจุดเริ่มต้นสำหรับการดำเนินการต่อทั้งหมด

`Presentation` is Aspose.Slides' top‑level object that holds the slide collection and global document settings.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

โค้ดสแนปช็อตเปิดงานนำเสนอเปล่า ซึ่งคุณสามารถบันทึกเป็นไฟล์ `.pptx` ต่อไปได้

### ฟีเจอร์ 2: การเพิ่มแผนภูมิกรวยลงในสไลด์ (H2)

#### ภาพรวม
แทรกแผนภูมิกรวยบนสไลด์แรก กำหนดขนาด และตั้งค่าชนิดของแผนภูมิ

`ChartType.Funnel` tells Aspose.Slides to render a funnel‑style visualization instead of a bar or line chart.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

การเรียก `addChart` จะสร้างรูปแผนภูมิ วางที่ตำแหน่ง `(50, 50)` พอยท์ และกำหนดความกว้าง `500` และความสูง `400`

### ฟีเจอร์ 3: การล้างข้อมูลแผนภูมิ (H2)

#### ภาพรวม
ก่อนเติมข้อมูลลงในแผนภูมิ ให้ลบหมวดหมู่หรือซีรีส์ตัวอย่างที่อาจมีอยู่ในเทมเพลต

`chart.getChartData().getCategories().clear()` removes all existing category entries, while `chart.getChartData().getSeries().clear()` removes any pre‑filled series.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

ขั้นตอนนี้ทำให้แผนภูมิมีพื้นฐานว่างเปล่าเพื่อให้ข้อมูลที่คุณกำหนดปรากฏตามที่ต้องการ

### ฟีเจอร์ 4: การตั้งค่า chart data workbook (H2)

#### ภาพรวม
อ็อบเจ็กต์ `IChartDataWorkbook` เก็บค่าดิบที่ขับเคลื่อนแผนภูมิ การเริ่มต้นมันทำให้คุณเขียนข้อมูลโดยตรงลงในเซลล์

`IChartDataWorkbook` is a lightweight in‑memory spreadsheet that Aspose.Slides uses to feed chart series and categories.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

โค้ดนี้ลบเซลล์ที่มีอยู่ทั้งหมด เตรียม workbook สำหรับการใส่ข้อมูลใหม่

### ฟีเจอร์ 5: การเพิ่มหมวดหมู่ลงในแผนภูมิ (H2)

#### ภาพรวม
กำหนดป้ายข้อความที่ปรากฏด้านซ้ายของกรวย—ซึ่งแสดงแต่ละขั้นตอนของกระบวนการของคุณ

`chart.getChartData().getCategories().add()` creates a new category object linked to a specific workbook cell.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

ที่นี่เราเพิ่มสามขั้นตอน: “Prospects”, “Qualified Leads”, และ “Closed Deals”

### ฟีเจอร์ 6: การเพิ่มซีรีส์ข้อมูลลงในแผนภูมิ (H2)

#### ภาพรวม
เติมค่าตัวเลขลงในกรวยและอาจกำหนดสีเฉพาะให้แต่ละชิ้น

`IDataPoint` represents a single data point within a chart series.  

`chart.getChartData().getSeries().add()` creates a series that holds the numeric data points; each `IDataPoint` can receive its own fill color.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

ลูปนี้แสดงวิธีตั้งค่า solid fill สำหรับแต่ละจุด โดยใช้ค่าสี `java.awt.Color` ที่กำหนดตามแบรนด์หรือสีสุ่มเพื่อความหลากหลาย

## กรณีการใช้งานทั่วไป & เคล็ดลับ (H2)

- **การรายงานสายงานขาย** – แสดงจำนวนลีดที่เคลื่อนผ่านจากผู้มีโอกาสเป็นลูกค้าไปจนถึงปิดสำเร็จในแต่ละขั้นตอน.  
- **การวิเคราะห์ประสิทธิภาพกระบวนการ** – แสดงการสูญเสียวัสดุหรือความล่าช้าของเวลาในขั้นตอนการผลิต.  
- **การตรวจสอบฟันเนลการตลาด** – เปรียบเทียบอัตราการแปลงในแคมเปญหรือแหล่งที่มาของการเข้าชม.  

**Pro tip:** Instead of random colors, use your company’s brand palette (e.g., `new Color(0, 112, 192)`) to keep the presentation consistent with other marketing assets.

## คำถามที่พบบ่อย (H2)

**Q: How do I change the funnel chart’s orientation?**  
A: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical` or `ChartOrientation.Horizontal`.

**Q: Can I export the slide as an image after adding the chart?**  
A: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.

**Q: What if I need more than three categories?**  
A: Simply add additional categories using `chart.getChartData().getCategories().add(...)` and provide matching data points for each new category.

**Q: Is there a way to hide the legend?**  
A: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)` to remove both the title and legend from the visual.

**Q: Do I need a license for development builds?**  
A: A temporary license is sufficient for evaluation; a full commercial license is required for production deployments.

**อัปเดตล่าสุด:** 2026-09-02  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [วิธีเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides for Java: คู่มือขั้นตอนต่อขั้นตอน](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [วิธีแก้ไขข้อมูลแผนภูมิ PowerPoint ด้วย Aspose.Slides for Java: คู่มือครบถ้วน](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [เพิ่มแอนิเมชันให้แผนภูมิ PowerPoint ด้วย Aspose.Slides for Java – คู่มือขั้นตอนต่อขั้นตอน](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}