---
date: '2026-01-24'
description: คู่มือแบบขั้นตอนต่อขั้นตอนในการสร้างแผนภูมิกระจายด้วย Java โดยใช้ Aspose.Slides,
  เพิ่มจุดข้อมูลกระจายและทำงานกับแผนภูมิกระจายหลายชุดข้อมูล
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: สร้างแผนภูมิกระจายใน Java ด้วย Aspose.Slides – ปรับแต่งและบันทึก
url: /th/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้าง Scatter Chart Java ด้วย Aspose.Slides

ในบทเรียนนี้คุณจะ **สร้าง scatter chart java** ตั้งแต่เริ่มต้น, เพิ่มจุดข้อมูลแบบกระจาย, และเรียนรู้วิธีทำงานกับ scatter chart ที่มีหลายซีรีส์—ทั้งหมดโดยใช้ Aspose.Slides for Java เราจะเดินผ่านการตั้งค่าโฟลเดอร์, การท้ายการบันทึกพรีเซนเรียน**
- การตั้งค่าโฟลเดอร์สำหรับเก็บไฟล์พรีเซนเทชัน  
- การเริ่มต้นและจัดการพรีเซนเทชันด้วย Aspose.Slides  
- การสร้าง scatter chart บนสไลด์  
- การเพิ่มและจัดการจุดข้อมูลสำหรับแต่ละซีรีส์  
- การปรับแต่งประเภทซีรีส์, มาร์คเกอร์, และการจัดการหลายซีรีส์ scatter chart  
- การบันทึกพรีเซนเทชันที่เสร็จสมบูรณ์  

มาเริ่มต้นด้วยข้อกำหนดเบื้องต้นกันเลย

## Quick Answers
- **ไลบรารีหลักคืออะไร?** Aspose.Slides for Java  
- **ต้องใช้ Java เวอร์ชันใด?** JDK 8 หรือสูงกว่า (แนะนำ JDK 16)  
- **สามารถเพิ่มซีรีส์มากกว่าสองชุดได้หรือไม่?** ได้ – คุณสามารถเพิ่มจำนวนซีรีส์ใด ๆ ลงใน scatter chart  
- **จะเปลี่ยนสีมาร์คเกอร์อย่างไร?** ใช้ `series.getMarker().getFillFormat().setFillColor(Color)`  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานในโปรดักชันหรือไม่?** ต้องมี, ลิขสิทธิ์เชิงพาณิชย์จะลบข้อจำกัดการประเมินผล  

## Prerequisites

เพื่อทำตามบทเรียนนี้ โปรดตรวจสอบว่าคุณมี:
- **Aspose.Slides for Java** – เวอร์ชัน 25.4 หรือใหม่กว่า  
- **JavaDK 8 หรือใหม่กว่า  
- ความรู้พื้นฐานของ Java และความคุ้นเคยกับ Maven หรือ Gradle  

## Setting Up Aspose.Slides for Java

ผสาน Aspose.Slides เข้ากับโปรเจกต์ของคุณด้วยวิธีใดวิธีหนึ่งต่อไปนี้

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

หรือดาวน์โหลดแพคเกจล่าสุดจาก [Aspose Releases](https://releases.aspose.com/slides/java/)

#### License Acquisition
- **Free Trial** – การประเมินผล 30 วัน  
- **Temporary License** – การทดสอบต่อเนื่อง  
- **Commercial License** – การใช้งานเต็มรูปแบบในโปรดักชัน  

ตอนนี้มาดูโค้ดกันต่อ

## Implementation Guide

### Step 1: Directory Setup
ก่อนอื่นให้ตรวจสอบว่าโฟลเดอร์ output มีอยู่แล้ว เพื่อให้พรีเซนเทชันสามารถบันทึกได้โดยไม่มีข้อผิดพลาด

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Step 2: Presentation Initialization
สร้างพรีเซนเทชันใหม่และดึงสไลด์แรกออกมา

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Step 3: Add a Scatter Chart
แทรก scatter chart ที่มีเส้นโค้ง (smooth lines) ลงบนสไลด์

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Step 4: Manage Chart Data (Clear & Add Series)
ล้างซีรีส์เริ่มต้นและเพิ่มซีรีส์ของเราสำหรับ **multiple series scatter chart**

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

### Step 5: Add Data Points Scatter
เติมค่าพิกัด X‑Y ให้แต่ละซีรีส์โดยใช้ **add data points scatter**

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Step 6: Customize Series Types & Markers
ปรับสไตล์การแสดงผล – เปลี่ยนเป็นเส้นตรงพร้อมมาร์คเกอร์และกำหนดสัญลักษณ์มาร์คเกอร์ที่แตกต่างกัน

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

### Step 7: Save the Presentation
บันทึกไฟล์ลงดิสก์

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Practical Applications
- **Financial Analysis** – แสดงการเคลื่อนที่ของราคาหุ้นด้วยหลายซีรีส์ scatter chart  
- **Scientific Research** – แสดงผลการทดลองโดยใช้ add data points scatter เพื่อความแม่นยำของข้อมูล  
- **Project Management** – แสดงแนวโน้มการจัดสรรทรัพยากรในหลายโครงการบน scatter chart เดียว  

## Performance Considerations
- ปิดการใช้งานอ็อบเจ็กต์ `Presentation` หลังการบันทึกเพื่อคืนหน่วยความจำ  
- สำหรับชุดข้อมูลขนาดใหญ่ ให้เติมข้อมูลใน workbook เป็นชุด ๆ แทนการเติมทีละรายการ  
- หลีกเลี่ยงการกำหนดสไตล์มากเกินไปภายในลูปที่แคบ; ให้กำหนดสไตล์หลังจากใส่ข้อมูลเสร็จแล้ว  

## Common Issues & Solutions
| Issue | Solution |
|-------|----------|
| **Chart appears empty** | ตรวจสอบว่าจุดข้อมูลถูกเพิ่มในซีรีส์ที่ถูกต้องและดัชนีของ workbook ตรงกัน |
| **Markers not visible** | ตรวจสอบให้ `series.getMarker().setSize()` มีค่ามากกว่า 0 และกำหนดสัญลักษณ์มาร์คเกอร์ |
| **OutOfMemoryError on large charts** | ใช้ `pres.dispose()` หลังการบันทึกและพิจารณาเพิ่มขนาด heap ของ JVM (`-Xmx`) |

## Frequently Asked Questions

### How do I change the color of the markers?
ใช้ `series.getMarker().getFillFormat().setFillColor(Color)` โดยที่ `Color` เป็นอ็อบเจ็กต์ของ `java.awt.Color`

### Can I add more than two series to a scatter chart?
ได้แน่นอน. ทำซ้ำบล็อกการสร้างซีรีส์ (ขั้นตอน 4) สำหรับแต่ละซีรีส์ที่ต้องการเพิ่ม

### Is it possible to export the chart as an image?
ได้. เรียก `chart.exportChartImage("chart.png", ImageFormat.Png)` หลังจากเพิ่มข้อมูลทั้งหมดแล้ว

### Does Aspose.Slides support interactive tooltips on scatter points?
แม้ PowerPoint จะไม่มี tooltip แบบเรียลไทม์, คุณสามารถฝังป้ายข้อมูลโดยใช้ `series.getDataPoints().get_Item(i).getLabel().setText("Your text")`

### How can I animate the scatter series?
ใช้ `chart.getChartData().getSeries().get_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)` เพื่อเพิ่มเอฟเฟกต์การปรากฏแบบง่าย

---

**Last Updated:** 2026-01-24  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}