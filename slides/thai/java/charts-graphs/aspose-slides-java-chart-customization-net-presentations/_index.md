---
date: '2026-01-17'
description: เรียนรู้วิธีเพิ่มซีรีส์ลงในแผนภูมิและปรับแต่งแผนภูมิคอลัมน์แบบซ้อนในงานนำเสนอ
  .NET ด้วย Aspose.Slides for Java.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: เพิ่มซีรีส์ลงในแผนภูมิด้วย Aspose.Slides สำหรับ Java ใน .NET
url: /th/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# การควบคุมการปรับแต่งแผนภูมิใน .NET Presentations ด้วย Aspose.Slides for Java

## บทนำ
ในโลกของการนำเสนอที่ขับเคลื่อนด้วยข้อมูล แผนภูมิเป็นเครื่องมือที่ขาดไม่ได้ซึ่งเปลี่ยนตัวเลขดิบให้กลายเป็นเรื่องราวภาพที่น่าสนใจ เมื่อคุณต้อง **เพิ่ม series ไปยังแผนภูมิ** อย่างโปรแกรมเมติกโดยเฉพาะในไฟล์การนำเสนอ .NET งานนี้อาจดูท่วมท้น แต่ **Aspose.Slides for Java** มี API ที่ทรงพลังและไม่จำกัดภาษา ทำให้การสร้างและปรับแต่งแผนภูมิเป็นเรื่องง่าย—แม้ว่าเป้าหมายของคุณจะเป็นไฟล์ .NET PPTX ก็ตาม

ในบทเรียนนี้คุณจะได้เรียนรู้วิธี **เพิ่ม series ไปยังแผนภูมิ**, วิธี **เพิ่มแผนภูมิ** ประเภท stacked column, และวิธีปรับแต่งลักษณะภาพเช่นความกว้างของช่องว่าง (gap width) สุดท้ายคุณจะสามารถสร้างสไลด์ที่มีข้อมูลไดนามิกและดูเป็นมืออาชีพได้

**สิ่งที่คุณจะได้เรียน**
- วิธีสร้างการนำเสนอเปล่าโดยใช้ Aspose.Slides  
- วิธี **เพิ่มแผนภูมิ stacked column** ลงในสไลด์  
- วิธี **เพิ่ม series ไปยังแผนภูมิ** และกำหนดหมวดหมู่  
- วิธีเติมข้อมูลจุดและปรับตั้งค่าการแสดงผล  

มาเตรียมสภาพแวดล้อมการพัฒนากันเถอะ

## คำตอบสั้น
- **คลาสหลักที่ใช้เริ่มการนำเสนอคืออะไร?** `Presentation`  
- **เมธอดใดที่ใช้เพิ่มแผนภูมิลงในสไลด์?** `slide.getShapes().addChart(...)`  
- **จะเพิ่ม series ใหม่อย่างไร?** `chart.getChartData().getSeries().add(...)`  
- **สามารถเปลี่ยนความกว้างของช่องว่างระหว่างแท่งได้หรือไม่?** ได้ โดยใช้ `setGapWidth()` บนกลุ่ม series  
- **ต้องมีลิขสิทธิ์สำหรับการใช้งานใน production หรือไม่?** ต้องมี ลิขสิทธิ์ Aspose.Slides for Java ที่ถูกต้อง  

## “add series to chart” คืออะไร?
การเพิ่ม series ไปยังแผนภูมิหมายถึงการแทรกชุดข้อมูลใหม่ที่แผนภูมิจะเรนเดอร์เป็นองค์ประกอบภาพที่แยกจากกัน (เช่น แท่งใหม่, เส้นใหม่ หรือส่วนใหม่ของพาย) แต่ละ series สามารถมีค่า สี และการจัดรูปแบบของตนเอง ทำให้คุณเปรียบเทียบชุดข้อมูลหลายชุดได้พร้อมกัน

## ทำไมต้องใช้ Aspose.Slides for Java เพื่อแก้ไข .NET presentations?
- **ข้ามแพลตฟอร์ม**: เขียนโค้ด Java ครั้งเดียวแล้วใช้งานกับไฟล์ PPTX ของแอปพลิเคชัน .NET  
- **ไม่มีการพึ่งพา COM หรือ Office**: ทำงานบนเซิร์ฟเวอร์, CI pipelines, และคอนเทนเนอร์ได้  
- **API แผนภูมิที่ครอบคลุม**: รองรับแผนภูมิมากกว่า 50 ประเภท รวมถึง stacked column charts  

## ข้อกำหนดเบื้องต้น
1. ไลบรารี **Aspose.Slides for Java** (เวอร์ชัน 25.4 หรือใหม่กว่า)  
2. เครื่องมือสร้าง Maven หรือ Gradle, หรือดาวน์โหลด JAR ด้วยตนเอง  
3. ความรู้พื้นฐานของ Java และความคุ้นเคยกับโครงสร้าง PPTX  

## การตั้งค่า Aspose.Slides for Java
### การติดตั้งด้วย Maven
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การติดตั้งด้วย Gradle
ใส่บรรทัดนี้ในไฟล์ `build.gradle` ของคุณ:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### ดาวน์โหลดโดยตรง
หรือคุณสามารถดึง JAR ล่าสุดจากหน้า releases อย่างเป็นทางการ: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

**การรับลิขสิทธิ์**  
เริ่มต้นด้วยการทดลองใช้ฟรีโดยดาวน์โหลดลิขสิทธิ์ชั่วคราวจาก [ที่นี่](https://purchase.aspose.com/temporary-license/). สำหรับการใช้งานใน production ให้ซื้อลิขสิทธิ์เต็มเพื่อเปิดใช้งานฟีเจอร์ทั้งหมด

## คู่มือการทำตามขั้นตอน
ด้านล่างแต่ละขั้นตอนจะมีโค้ดสั้น ๆ (ไม่เปลี่ยนแปลงจากบทเรียนต้นฉบับ) พร้อมคำอธิบายว่ามันทำอะไร

### ขั้นตอนที่ 1: สร้างการนำเสนอเปล่า
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*เราเริ่มด้วยไฟล์ PPTX ที่ว่างเปล่า ซึ่งเป็นผืนผ้าใบสำหรับการเพิ่มแผนภูมิ*

### ขั้นตอนที่ 2: เพิ่มแผนภูมิ Stacked Column ลงในสไลด์
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*เมธอด `addChart` สร้าง **add stacked column chart** และวางไว้ที่มุมบน‑ซ้ายของสไลด์*

### ขั้นตอนที่ 3: เพิ่ม Series ไปยังแผนภูมิ (เป้าหมายหลัก)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*ที่นี่เราจะ **add series to chart** – การเรียกแต่ละครั้งจะสร้าง series ข้อมูลใหม่ที่จะแสดงเป็นกลุ่มคอลัมน์แยกกัน*

### ขั้นตอนที่ 4: เพิ่ม Categories ไปยังแผนภูมิ
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Categories ทำหน้าที่เป็นป้ายแกน X ให้ความหมายกับแต่ละคอลัมน์*

### ขั้นตอนที่ 5: เติมข้อมูลให้ Series
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*Data points ให้ค่าตัวเลขกับแต่ละ series ซึ่งแผนภูมิจะเรนเดอร์เป็นความสูงของแท่ง*

### ขั้นตอนที่ 6: ตั้งค่า Gap Width สำหรับกลุ่ม Series ของแผนภูมิ
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*การปรับ Gap Width ช่วยให้การอ่านข้อมูลง่ายขึ้น โดยเฉพาะเมื่อมีหลาย Categories*

## กรณีการใช้งานทั่วไป
- **รายงานการเงิน** – เปรียบเทียบรายได้ไตรมาสระหว่างหน่วยธุรกิจต่าง ๆ  
- **แดชบอร์ดโครงการ** – แสดงเปอร์เซ็นต์การทำงานเสร็จของแต่ละทีม  
- **การวิเคราะห์การตลาด** – แสดงผลการทำแคมเปญแบบข้างเคียงกัน  

## เคล็ดลับด้านประสิทธิภาพ
- **ใช้วัตถุ `Presentation` ซ้ำ** เมื่อสร้างหลายแผนภูมิเพื่อลดการใช้หน่วยความจำ  
- **จำกัดจำนวน Data Points** ให้เท่าที่จำเป็นสำหรับการเล่าเรื่องภาพ  
- **ทำลายวัตถุ** (`presentation.dispose()`) หลังบันทึกเพื่อคืนทรัพยากร  

## คำถามที่พบบ่อย
**ถาม: สามารถเพิ่มประเภทแผนภูมิอื่น ๆ นอกจาก stacked column ได้หรือไม่?**  
ตอบ: ได้, Aspose.Slides รองรับ line, pie, area และหลายประเภทอื่น ๆ

**ถาม: ต้องการลิขสิทธิ์แยกสำหรับผลลัพธ์ .NET หรือไม่?**  
ตอบ: ไม่จำเป็น, ลิขสิทธิ์ Java เดียวกันทำงานกับทุกฟอร์แมตรวมถึงไฟล์ PPTX ของ .NET

**ถาม: จะเปลี่ยนพาเลตสีของแผนภูมิอย่างไร?**  
ตอบ: ใช้ `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` แล้วตั้งค่า `Color` ที่ต้องการ

**ถาม: สามารถเพิ่มป้ายข้อมูล (data labels) ผ่านโปรแกรมได้หรือไม่?**  
ตอบ: แน่นอน. เรียก `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` เพื่อแสดงค่า

**ถาม: หากต้องการอัปเดตการนำเสนอที่มีอยู่แล้วทำอย่างไร?**  
ตอบ: โหลดไฟล์ด้วย `new Presentation("existing.pptx")`, แก้ไขแผนภูมิ, แล้วบันทึกกลับไป

## สรุป
คุณได้เรียนรู้วิธี **add series to chart**, สร้าง **stacked column chart**, และปรับแต่งลักษณะของมันใน .NET presentations ด้วย Aspose.Slides for Java อย่างครบถ้วนแล้ว ลองทดลองใช้ประเภทแผนภูมิ สี และแหล่งข้อมูลต่าง ๆ เพื่อสร้างรายงานภาพที่น่าประทับใจและดึงดูดผู้มีส่วนได้ส่วนเสีย

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**อัปเดตล่าสุด:** 2026-01-17  
**ทดสอบกับ:** Aspose.Slides for Java 25.4 (jdk16)  
**ผู้เขียน:** Aspose