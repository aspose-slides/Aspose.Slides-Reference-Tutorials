---
date: '2026-03-20'
description: เรียนรู้วิธีเพิ่มแผนภูมิในงานนำเสนอ Java ด้วย Aspose.Slides และสร้างไฟล์แผนภูมืองานนำเสนอได้อย่างรวดเร็ว
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: วิธีเพิ่มแผนภูมิในงานนำเสนอ Java ด้วย Aspose.Slides
url: /th/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# วิธีเพิ่มแผนภูมิในงานนำเสนอโดยใช้ Aspose.Slides for Java

## Introduction

การสร้างงานนำเสนอแบบไดนามิกที่สื่อข้อมูลได้อย่างมีประสิทธิภาพเป็นสิ่งสำคัญในสภาพแวดล้อมธุรกิจที่เร็วขึ้นในทุกวันนี้ ไม่ว่าคุณจะกำลังเตรียมรายงานการเงิน, สไลด์การตลาด, หรืออัปเดตสถานะโครงการ, **การรู้วิธีเพิ่มแผนภูมิ** ลงในสไลด์ของคุณสามารถเพิ่มการมีส่วนร่วมของผู้ชมได้อย่างมาก ในบทแนะนำนี้คุณจะได้เรียนรู้ขั้นตอนการเพิ่มแผนภูมิคอลัมน์ 3 มิติแบบสแต็ก, การกำหนดค่าข้อมูล, และการบันทึกไฟล์ขั้นสุดท้าย—ทั้งหมดด้วย Aspose.Slides for Java.

### Quick Answers
- **What is the primary library?** Aspose.Slides for Java  
- **Which chart type is demonstrated?** 3D Stacked Column  
- **Can I generate presentation chart files programmatically?** Yes, using the API methods shown below  
- **What Java version is recommended?** JDK 16 or later  
- **Do I need a license for production?** A valid Aspose.Slides license is required for commercial use  

## What is “how to add chart” in Aspose.Slides?

Aspose.Slides for Java มีชุดอ็อบเจ็กต์ที่หลากหลายซึ่งช่วยให้คุณสร้าง, แก้ไข, และส่งออกไฟล์ PowerPoint โดยไม่ต้องใช้ Microsoft Office การเพิ่มแผนภูมิเป็นเรื่องง่ายเพียงสร้างอ็อบเจ็กต์ `Presentation`, แทรกรูปแบบแผนภูมิ, และป้อนข้อมูลผ่าน workbook ที่มีมาในตัว.

## Why add chart to Java presentations?

- **Visual impact:** แผนภูมิทำให้ตัวเลขดิบกลายเป็นภาพที่เข้าใจได้ทันที.  
- **Automation:** สร้างรายงานแบบเรียลไทม์—เหมาะสำหรับสรุปอีเมลตามกำหนดหรือแดชบอร์ด.  
- **Consistency:** ใช้สไตล์และแบรนด์เดียวกันในทุกสไลด์ที่สร้าง.  
- **Portability:** ส่งออกเป็น PPTX, PDF หรือรูปภาพด้วยการเรียกเมธอดเดียว.

## Prerequisites

- **Libraries and Dependencies:** ต้องติดตั้ง Aspose.Slides for Java.  
- **Environment Setup:** ทำงานในสภาพแวดล้อม Java (แนะนำ JDK 16 หรือใหม่กว่า).  
- **Knowledge Base:** ความคุ้นเคยกับแนวคิดพื้นฐานของการเขียนโปรแกรม Java จะเป็นประโยชน์.

## Setting Up Aspose.Slides for Java

### Installation

เพื่อรวม Aspose.Slides เข้ากับโปรเจกต์ของคุณ ให้ทำตามหนึ่งในตัวเลือกด้านล่าง.

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

**Direct Download**: Alternatively, download the latest version from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
- **Free Trial:** เริ่มต้นด้วยการทดลองใช้ฟรีเพื่อสำรวจคุณลักษณะ.  
- **Temporary License:** รับใบอนุญาตชั่วคราวสำหรับการทดสอบต่อเนื่อง.  
- **Purchase:** รับใบอนุญาตเต็มรูปแบบสำหรับการใช้งานเชิงพาณิชย์.

เมื่อติดตั้งแล้ว คุณสามารถสร้างอินสแตนซ์ของคลาส `Presentation` ซึ่งทำหน้าที่เป็นจุดเริ่มต้นสำหรับการทำงานทั้งหมดที่เกี่ยวกับแผนภูมิ.

## Implementation Guide

### How to add chart to a presentation with a 3D stacked column

#### Overview
การสร้างงานนำเสนอจากศูนย์เป็นเรื่องง่ายด้วย Aspose.Slides ในส่วนนี้ เราจะเพิ่มแผนภูมิคอลัมน์ 3 มิติแบบสแต็กลงในสไลด์แรกของงานนำเสนอของเรา.

**Steps:**

1. **Initialize Presentation Object**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Explain Parameters**  
   - `ChartType.StackedColumn3D`: ระบุประเภทของแผนภูมิ.  
   - Position and size `(0, 0, 500, 500)`: กำหนดตำแหน่งที่แผนภูมิปรากฏบนสไลด์.

### Configure Chart Data

#### Overview
เพื่อทำให้แผนภูมิของคุณมีความหมาย ให้กำหนดค่าชุดข้อมูลและหมวดหมู่ของมัน ส่วนนี้จะแสดงวิธีการเพิ่มจุดข้อมูลเฉพาะลงในแผนภูมิของคุณ.

**Steps:**

1. **Access Chart's Data Workbook**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Set Rotation3D Properties for Chart

#### Overview
เพิ่มความน่าสนใจให้กับแผนภูมิของคุณด้วยคุณสมบัติการหมุน 3 มิติ การปรับแต่งนี้ช่วยให้คุณปรับมุมมองและความลึกได้.

**Steps:**

1. **Configure 3D Rotations**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Explain Parameters**  
   - `setRightAngleAxes(true)`: ทำให้แกนตั้งฉากกัน.  
   - Rotation values: ปรับมุมและความลึกของมุมมอง 3 มิติ.

### Populate Series Data in Chart

#### Overview
การเติมข้อมูลลงในแผนภูมิเป็นสิ่งสำคัญสำหรับการวิเคราะห์ ที่นี่เราจะเพิ่มค่าต่าง ๆ ลงในชุดข้อมูลของแผนภูมิ.

**Steps:**

1. **Add Data Points**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Adjust Series Overlap in Chart

#### Overview
การปรับแต่งลักษณะการแสดงผลของแผนภูมิสามารถช่วยให้อ่านง่ายขึ้น ส่วนนี้อธิบายวิธีการปรับค่า overlap เพื่อการแสดงผลข้อมูลที่ดียิ่งขึ้น.

**Steps:**

1. **Set Series Overlap**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Save Presentation

#### Overview
เมื่อกำหนดค่าการนำเสนอเรียบร้อยแล้ว ให้บันทึกลงดิสก์ในรูปแบบที่ต้องการ ขั้นตอนนี้ทำให้การเปลี่ยนแปลงทั้งหมดถูกบันทึก.

**Steps:**

1. **Save the Presentation**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Common Issues and Solutions

| ปัญหา | สาเหตุ | วิธีแก้ |
|-------|--------|----------|
| **แผนภูมิดูแบน** | ไม่ได้ตั้งค่าการหมุน 3 มิติ | เรียก `setRotation3D` พร้อมค่าพิกัด X/Y ที่เหมาะสม. |
| **ข้อมูลไม่แสดง** | เซลล์ใน Workbook ไม่ได้เชื่อมโยง | ตรวจสอบให้ `fact.getCell` อ้างอิงแถว/คอลัมน์ที่ถูกต้อง. |
| **ไฟล์ไม่บันทึก** | เส้นทางไม่ถูกต้องหรือไม่มีสิทธิ์ | ตรวจสอบว่า `outputFilePath` สามารถเขียนได้และโฟลเดอร์มีอยู่. |

## Frequently Asked Questions

**Q: ฉันสามารถสร้างไฟล์แผนภูมิในรูปแบบอื่นนอกจาก PPTX ได้หรือไม่?**  
A: ใช่, Aspose.Slides รองรับ PDF, ODP, และรูปแบบภาพผ่าน enum `SaveFormat`.

**Q: ฉันต้องการใบอนุญาตเพื่อรันโค้ดในขั้นตอนการพัฒนาหรือไม่?**  
A: ใบอนุญาตชั่วคราวหรือทดลองใช้งานได้สำหรับการพัฒนา, แต่ต้องมีใบอนุญาตเต็มรูปแบบสำหรับการใช้งานในสภาพแวดล้อมการผลิต.

**Q: สามารถเพิ่มแผนภูมิมากกว่าหนึ่งแผนภูมิในสไลด์เดียวได้หรือไม่?**  
A: แน่นอน. เรียก `slide.getShapes().addChart` หลายครั้งโดยกำหนดตำแหน่งหรือขนาดที่แตกต่างกัน.

**Q: ฉันจะเปลี่ยนพาเลตสีของแผนภูมิได้อย่างไร?**  
A: ใช้ `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` แล้วกำหนด `SolidFillColor`.

**Q: ฉันสามารถเชื่อมแผนภูมิกับแหล่งข้อมูลภายนอกเช่นฐานข้อมูลได้หรือไม่?**  
A: ได้. ดึงข้อมูลด้วย JDBC แล้วเติมเซลล์ใน workbook อย่างโปรแกรมก่อนบันทึก.

## Conclusion

คุณได้เรียนรู้ **วิธีเพิ่มแผนภูมิ** ลงในงานนำเสนอ Java, กำหนดค่าข้อมูล, ปรับการหมุน 3 มิติ, ปรับค่า overlap ของชุดข้อมูล, และบันทึกไฟล์ขั้นสุดท้ายแล้ว ความรู้นี้ทำให้คุณสามารถอัตโนมัติการสร้างรายงาน, สร้างแบรนด์ที่สอดคล้อง, และนำเสนอข้อมูลโดยไม่ต้องทำด้วยมือ สำหรับการปรับแต่งเชิงลึกเพิ่มเติม เช่น การจัดรูปแบบคำอธิบาย, แกน, หรือการใช้ธีม, ค้นหาความสามารถทั้งหมดในเอกสารอย่างเป็นทางการ.

For more advanced features and customization options, refer to the [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-03-20  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose