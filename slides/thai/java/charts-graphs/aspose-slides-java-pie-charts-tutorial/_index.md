---
date: '2026-01-22'
description: เรียนรู้วิธีปรับแต่งสีของแผนภูมิวงกลมและเพิ่มชื่อแผนภูมิด้วย Aspose.Slides
  for Java รวมการตั้งค่า Maven Aspose Slides และวิธีบันทึกไฟล์พรีเซนเทชัน pptx.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: 'วิธีปรับแต่งสีของแผนภูมิวงกลมใน Java ด้วย Aspose.Slides: คู่มือฉบับสมบูรณ์'
url: /th/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิวงกลมด้วย Aspose.Slides for Java: วิธี **ปรับแต่งสีของแผนภูมิวงกลม** – การสอนแบบครบถ้วน

## Introduction
การนำเสนอเรื่องราวที่ขับเคลื่อนด้วยข้อมูลในงานพรีเซนเทชันจะง่ายขึ้นเมื่อคุณสามารถ **ปรับแต่งสีของแผนภูมิวงกลม** ให้ตรงกับแบรนด์หรือเน้นค่าที่สำคัญได้ ในบทเรียนนี้คุณจะได้เห็นขั้นตอนการสร้างแผนภูมิวงกลม, เพิ่มหัวข้อแผนภูมิ, ทำงานกับจุดข้อมูลของแผนภูมิวงกลม, และปรับสีของแต่ละส่วนอย่างละเอียดโดยใช้ Aspose.Slides for Java. เมื่อจบคุณจะรู้วิธี **บันทึกพรีเซนเทชันเป็นไฟล์ pptx** และรวมไลบรารีกับ Maven Aspose Slides.

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีสร้างแผนภูมิวงกลม (how to create pie) และตั้งค่าโครงการ Java
- ขั้นตอนการเพิ่มหัวข้อแผนภูมิและจัดการจุดข้อมูลของแ- เทคนิคการ **ปรับแต่งสีของแผนภูมิose Slides
- การบันทึกไฟล์สุดท้ายเป็นพรีเซนเทชัน PPTX

มาเริ่มกันเลย!

## Quick Answers
- **จะเพิ่มหัวข้อแผนภูมิอย่างไร?** ใช้ `chart.getChartTitle().addTextFrameForOverriding("Your Title")`.
- **เครื่องมือสร้างใดทำงานดีที่สุด?** ทั้ง Maven และ Gradle รองรับ; Maven Aspose Slides เป็นที่นิยมที่สุด.
- **สามารถเปลี่ยนสีของส่วนได้หรือไม่?** ได้ — ตั้งค่า `setColorVaried(true)` แล้วปรับสี fill ของแต่ละ `DataPointึกเป็นรูปแบบใด?** ใช้ `presentation.save("MyChart.pptx", SaveFormat.Pptx)`.
- **ต้องมีลิขสิทธิ์หรือไม่?** เวอร์ชันทดลองฟรีใช้ได้สำหรับการพัฒนา; ต้องมีลิขสิทธิ์ถาวรสำหรับ4 (แนะนำให้ใช้เวอร์ชันล่าสุด)
- **JDK 16+** ติดตั้งและตั้งค่าแล้ว
- IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
- ความรู้พื้นฐาน Java และความคุ้นเคยกับ Maven หรือ Gradle

## Setting Up Aspose.Slides for Java
เพื่อเริ่มใช้ Aspose.Slides ให้เพิ่มไลบรารีลงในโครงการของคุณ

**Maven** (maven aspose slides)  
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

**Direct Download**  
หากคุณไม่ต้องการใช้เครื่องมือสร้าง ให้ดาวน์โหลดเวอร์ชันล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition Steps
- **Free Trial** – เริ่มทดลองใช้โดยไม่ต้องมีลิขสิทธิ์
- **Temporary License** – ขยายระยะเวลาการทดลอง
- **Purchase** – ซื้อลิขสิทธิ์เต็มรูปแบบสำหรับการใช้งานจริง

### Basic Initialization
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementation Guide
ด้านล่างเป็นขั้นตอนแบบละเอียดที่รักษาโค้ดให้ตรงกับที่ไลบรารีกำหนด

### Step 1: Initialize Presentation and Slide
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
islide slides = presentation.getSlides().get_Item(0);
```

### Step 2: Add a Pie Chart to the Slide
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Step 3: Add Chart Title
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Step 4: Show Data Labels for the First Series
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Step 5: Prepare the Chart Data Worksheet
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Step 6: Add Categories (pie chart data points)
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Step 7: Add Series and Populate Data Points
```java
import com.aspose.slides.*;

// Add a new series and set its name.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Step 8: **Customize Pie Chart Colors** – The Core of This Tutorial
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Step 9: Configure Custom Data Labels
```java
import com.aspose.slides.*;

// Configure custom labels.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Step 10: Set Rotation Angle and **Save Presentation PPTX**
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Common Issues & Troubleshooting
- **สีหายหลังการส่งออก** – ตรวจสอบว่าได้เรียก `setColorVaried(true)` ก่อนแก้ไขจุดข้อมูลแต่ละรายการ
- **จุดข้อมูลไม่แสดง** – ยืนยันว่าหมวดหมู่และซีรีส์ถูกล้างก่อนเพิ่มใหม่ (ดูขั้นตอน 5)
- **ลิขสิทธิ์ไม่ทำงาน** – โหลดไฟล์ลิขสิทธิ์ก่อนสร้างอ็อบเจกต์ `Presentation` เพื่อหลีกเลี่ยงลายน้ำเวอร์ชันทดลอง

## Frequently Asked Questions

**Q: สามารถใช้โค้ดนี้กับ JDK เวอร์ชันเก่าได้หรือไม่?**  
A: ไลบTitle().addTextFrameForOverr สามารถส่งออกเป็นรูปแบบอื่นนอกจาก PPTX ได้หรือไม่?**  
A: ได้ — Aspose, ODP และหลายรูปแบบภาพผ่าน enum `SaveFormat`

**Q: ถ้าต้องการทำแอนิเมชันให้ส่วนของแผนภูมิวงกลมทำอย่างไร?**  
A: ใช้ API `SlideShow` เพื่อเพิ่มการเปลี่ยนสไลด์หรือแอนิเมชันรูปทรงหลังจากสร้างแผนภูมิ

**Q: Dependency ของ Maven Asp ที่จำเป็นโดยอัตโนมัติ; ไม่ต้องทำขั้นตอนเพิ่มเติม

## Conclusion
ตอนนี้คุณมีตัวอย่างเต็มรูปแบบพร้อมใช้งานในระดับ production ที่แสดง **วิธีปรับแต่งสีของแผนภูมิวงกลม**, เพิ่มหัวข้อแผนภูมิ, ทำงานกับจุด และให้สอดคล้องกับสไตล์แบรนด์ของคุณได้ตามต้องการ

---

**อัปเดตล่าสุด:** 2024 (JDK 16)  
**ผู้เขียน:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}