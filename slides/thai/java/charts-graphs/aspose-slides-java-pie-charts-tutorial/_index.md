---
date: '2026-07-17'
description: เรียนรู้วิธีการหมุน Pie Chart, ปรับแต่งสีของ Pie Chart, และส่งออกสไลด์เป็น
  PDF ด้วย Aspose.Slides for Java – คู่มือการสร้างภาพข้อมูลแบบครบวงจร
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: หมุน Pie Chart และปรับแต่งสีของ Pie Chart ด้วย Aspose.Slides for Java.
  เรียนรู้การส่งออกสไลด์เป็น PDF และการทำงานกับ worksheet ของข้อมูลแผนภูมิ
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: หมุน Pie Chart และปรับแต่งสีใน Java – คู่มือ Aspose.Slides
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
title: วิธีการหมุน Pie Chart และปรับแต่งสีใน Java ด้วย Aspose.Slides
url: /th/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# สร้างแผนภูมิวงกลมด้วย Aspose.Slides for Java: คู่มือฉบับสมบูรณ์

## บทนำ
ในคู่มือนี้คุณจะได้เรียนรู้วิธี **หมุนแผนภูมิวงกลม** ปรับสีของแต่ละส่วน และส่งออกสไลด์สุดท้ายเป็น PDF — ทั้งหมดด้วย Aspose.Slides for Java ไม่ว่าคุณจะสร้างแดชบอร์ดการขาย รายงานการเงิน หรือการนำเสนอใด ๆ ที่ขับเคลื่อนด้วยข้อมูล การเชี่ยวชาญเทคนิคเหล่านี้จะทำให้คุณสามารถนำเสนอภาพที่ชัดเจนและดึงดูดสายตาโดยไม่ต้องพึ่งพา Microsoft Office มาเตรียมเครื่องมือและเริ่มกันเลย

## คำตอบสั้น
- **คลาสใดที่เริ่มการนำเสนอใหม่?** `Presentation` จาก `com.aspose.slides`.
- **การเรียก API ใดที่เพิ่มแผนภูมิวงกลม?** `slide.addChart(ChartType.Pie, …)`.
- **คุณจะให้แต่ละส่วนมีสีที่แตกต่างกันได้อย่างไร?** เรียก `series.setColorVaried(true)` และตั้งสีเติมแบบทึบสำหรับแต่ละจุดข้อมูล.
- **เมธอดใดที่หมุนแผนภูมิ?** `chart.setRotationAngle(double)` – ใช้ค่ามุมจาก 0 ถึง 360.
- **สไลด์สามารถส่งออกเป็น PDF ได้หรือไม่?** ใช่, เรียก `presentation.save("output.pdf", SaveFormat.Pdf)`.

## การ “ปรับแต่งสีแผนภูมิวงกลม” คืออะไร?
การปรับแต่งสีแผนภูมิวงกลมหมายถึงการกำหนดสีเติมที่แตกต่างให้กับแต่ละส่วนของวงกลม เพื่อเพิ่มความอ่านง่ายและผลกระทบทางสายตา ใน Aspose.Slides คุณทำได้โดยเปิดใช้งานสีที่แตกต่างแล้วตั้งค่าสีเติมแบบทึบให้กับจุดข้อมูลแต่ละจุด วิธีนี้ทำให้แต่ละส่วนข้อมูลโดดเด่นชัดเจนในงานนำเสนอ

## ทำไมต้องใช้ Aspose.Slides for Java เพื่อสร้างแผนภูมิวงกลม?
Aspose.Slides รองรับ **ประเภทแผนภูมิกว่า 150** ชนิดและสามารถเรนเดอร์การนำเสนอ 300 หน้าได้ภายใน **5 วินาที** บนเซิร์ฟเวอร์ทั่วไป โดยไม่ต้องติดตั้ง Microsoft Office ไลบรารีทำงานบน Windows, Linux และ macOS ให้ความยืดหยุ่นแบบข้ามแพลตฟอร์มสำหรับโครงการการแสดงผลข้อมูลด้วย Java ใด ๆ

## ข้อกำหนดเบื้องต้น
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 หรือใหม่กว่า
- IDE เช่น IntelliJ IDEA, Eclipse หรือ NetBeans
- ความรู้พื้นฐาน Java และความคุ้นเคยกับ Maven หรือ Gradle

## การตั้งค่า Aspose.Slides for Java
เพิ่มไลบรารีลงในการกำหนดค่าการสร้างของคุณ

**Maven**  
เพิ่มโค้ดส่วนนี้ลงในไฟล์ `pom.xml` ของคุณ:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
ใส่โค้ดต่อไปนี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**ดาวน์โหลดโดยตรง**  
หากคุณต้องการวิธีการแบบแมนนวล ดาวน์โหลด JAR ล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### ขั้นตอนการรับใบอนุญาต
- **Free Trial** – ทดลองใช้ฟรี – สำรวจคุณสมบัติทั้งหมดโดยไม่มีค่าใช้จ่าย.  
- **Temporary License** – ใบอนุญาตชั่วคราว – ขยายขีดจำกัดการทดลองเป็นระยะสั้น.  
- **Purchase** – ซื้อ – รับใบอนุญาตถาวรสำหรับการใช้งานในสภาพแวดล้อมการผลิต.

**การเริ่มต้นและตั้งค่าเบื้องต้น**  
คลาส `Presentation` แสดงไฟล์ PowerPoint ในหน่วยความจำและให้เมธอดสำหรับจัดการสไลด์.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## คู่มือการดำเนินการ
ด้านล่างเป็นขั้นตอนแบบละเอียดที่ครอบคลุมตั้งแต่การสร้างสไลด์จนถึงการหมุนแผนภูมิวงกลมขั้นสุดท้าย

### เริ่มต้น Presentation และ Slide
สร้างอินสแตนซ์ `Presentation` ใหม่และดึงสไลด์แรกมาเป็นผ้าใบสำหรับแผนภูมิ.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### เพิ่มแผนภูมิวงกลมลงในสไลด์
`addChart` จะเพิ่มรูปร่างแผนภูมิประเภทที่ระบุลงในสไลด์ตามพิกัดที่กำหนด.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### ตั้งชื่อแผนภูมิ
`setTitle` กำหนดชื่อข้อความให้กับแผนภูมิและจัดตำแหน่งให้อยู่กึ่งกลาง.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### กำหนดค่าป้ายข้อมูลสำหรับ Series
`setShowValue(true)` เปิดใช้งานป้ายค่าตัวเลขบนแต่ละจุดข้อมูลของ series.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### เตรียม Worksheet ข้อมูลแผนภูมิ
`ChartDataWorkbook` เก็บตารางข้อมูลพื้นฐานที่เป็นแหล่งข้อมูลให้กับ series และ categories ของแผนภูมิ.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### เพิ่มหมวดหมู่ลงในแผนภูมิ
`addCategory` สร้างป้ายชื่อหมวดหมู่ใหม่สำหรับ series ของแผนภูมิ.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### เพิ่ม Series และเติมข้อมูลจุด
`addSeries` สร้าง series ข้อมูล, และ `addDataPointForBarSeries` ใส่ค่าตัวเลขสำหรับแต่ละหมวดหมู่.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### ปรับแต่งสีและขอบของ Series
`setColorVaried(true)` เปิดใช้งานสีที่แตกต่างต่อส่วน, และ `setFillFormat` กำหนดสีเติมแบบทึบให้แต่ละจุดข้อมูล.  
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

### กำหนดค่าป้ายข้อมูลแบบกำหนดเอง
`setDataLabelFormat` ปรับลักษณะ, ตำแหน่งและแบบอักษรของป้ายเพื่อให้คำอธิบายแผนภูมิเข้าใจง่ายขึ้น.  
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

### ตั้งค่ามุมการหมุนและบันทึก Presentation
`setRotationAngle` หมุนแผนภูมิวงกลมทั้งหมด, และ `save` เขียนไฟล์การนำเสนอลงดิสก์.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## วิธีการหมุนแผนภูมิวงกลม?
โหลดอ็อบเจกต์แผนภูมิ, เรียก `chart.setRotationAngle(45.0)` (หรือค่ามุมใดก็ได้) แล้วบันทึกการนำเสนอ การหมุนแผนภูมิวงกลมจะเปลี่ยนมุมเริ่มต้น ทำให้คุณสามารถเน้นส่วนที่ต้องการโดยไม่ต้องแก้ไขข้อมูล เมธอดเดียวนี้ทำงานกับอ็อบเจกต์ `Chart` ใด ๆ ใน Aspose.Slides คุณยังสามารถผสมการหมุนกับสีส่วนที่แตกต่างเพื่อดึงความสนใจไปยังข้อมูลที่สำคัญที่สุดได้อีกด้วย

## ปัญหาทั่วไปและวิธีแก้
| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|-------|-----|
| **ส่วนทั้งหมดแสดงสีเดียวกัน** | `setColorVaried(true)` ไม่ได้ถูกเรียกใช้ | ตรวจสอบให้แน่ใจว่าคุณเปิดใช้งานสีที่แตกต่างกันในกลุ่ม series |
| **ป้ายข้อมูลไม่แสดง** | แฟล็ก `showValue` ถูกปิด | เรียก `setShowValue(true)` บนรูปแบบป้าย |
| **การหมุนไม่มีผล** | ใช้เวอร์ชัน Aspose.Slides ที่เก่ากว่า | อัปเกรดเป็นเวอร์ชัน 25.4 หรือใหม่กว่า |
| **ข้อยกเว้นใบอนุญาตขณะทำงาน** | ไฟล์ใบอนุญาตหายหรือไม่ถูกต้อง | โหลดใบอนุญาตของคุณด้วย `License license = new License(); license.setLicense("Aspose.Slides.lic");` ก่อนสร้าง `Presentation` |

## คำถามที่พบบ่อย

**Q: จะขอรับใบอนุญาต Aspose.Slides สำหรับ Java ได้อย่างไร?**  
A: ขอทดลองใช้ฟรีจากเว็บไซต์ Aspose แล้วซื้อใบอนุญาตถาวร โหลดใบอนุญาตในระหว่างการทำงานตามที่แสดงในตารางปัญหาทั่วไป

**Q: สามารถใช้โค้ดนี้กับ JDK เวอร์ชันเก่าได้หรือไม่?**  
A: API ต้องการ JDK 16 หรือสูงกว่า; ไม่รองรับเวอร์ชันเก่า

**Q: สามารถส่งออกแผนภูมิเป็นรูปภาพแทน PPTX ได้หรือไม่?**  
A: ได้ — หลังจากเรนเดอร์แล้วเรียก `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`

**Q: หากต้องการมากกว่าหนึ่ง series ในแผนภูมิวงกลมจะทำอย่างไร?**  
A: แผนภูมิวงกลมออกแบบมาสำหรับ series เดียว; หากต้องการหลาย series ควรใช้แผนภูมิดอนัท

**Q: Aspose.Slides ทำงานบนเซิร์ฟเวอร์ Linux หรือไม่?**  
A: แน่นอน — Aspose.Slides for Java เป็นอิสระแพลตฟอร์มและทำงานบน OS ใดก็ได้ที่มี JDK ที่เข้ากันได้

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [How to Create Pie Charts in Java Presentations Using Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Master Pie Charts in Java Using Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Rotate Chart Texts in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}