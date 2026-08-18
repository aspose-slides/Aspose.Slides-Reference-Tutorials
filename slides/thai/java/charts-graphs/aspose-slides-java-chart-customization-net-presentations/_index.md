---
date: '2026-06-08'
description: เรียนรู้วิธีเพิ่มซีรีส์ในแผนภูมิและปรับแต่งแผนภูมิคอลัมน์แบบซ้อนในงานนำเสนอ
  .NET โดยใช้ Aspose.Slides for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: เพิ่มซีรีส์ในแผนภูมิด้วย Aspose.Slides for Java ใน .NET
url: /th/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เชี่ยวชาญการปรับแต่งแผนภูมิในงานนำเสนอ .NET ด้วย Aspose.Slides for Java

## บทนำ
ในโลกของการนำเสนอที่ขับเคลื่อนด้วยข้อมูล, แผนภูมิเป็นเครื่องมือที่ขาดไม่ได้ซึ่งเปลี่ยนตัวเลขดิบให้กลายเป็นเรื่องราวภาพที่น่าสนใจ เมื่อคุณต้อง **add series to chart** อย่างโปรแกรมเมติก, โดยเฉพาะในไฟล์การนำเสนอ .NET, งานนี้อาจดูท่วมท้น โชคดีที่ **Aspose.Slides for Java** มี API ที่ทรงพลังและไม่จำกัดภาษา ทำให้การสร้างและปรับแต่งแผนภูมิเป็นเรื่องง่าย—แม้เป้าหมายของคุณจะเป็นไฟล์ .NET PPTX คู่มือฉบับนี้จะพาคุณผ่านการเพิ่ม series, การสร้างแผนภูมิคอลัมน์แบบซ้อนกัน, และการปรับแต่งรายละเอียดภาพเช่นความกว้างของช่องว่าง, เพื่อให้คุณสร้างสไลด์ที่มีข้อมูลแบบไดนามิกและดูเป็นมืออาชีพ

## คำตอบอย่างรวดเร็ว
`Presentation` class แทนไฟล์ PPTX, และ `slide.getShapes().addChart(...)` แทรกรูปแผนภูมิ ใช้ `chart.getChartData().getSeries().add(...)` เพื่อเพิ่ม series, และ `setGapWidth()` ปรับระยะห่าง.

- **คลาสหลักที่ใช้เริ่มการนำเสนอคืออะไร?** `Presentation` – มันแทนไฟล์ PPTX ในหน่วยความจำ  
- **วิธีใดที่เพิ่มแผนภูมิลงในสไลด์?** `slide.getShapes().addChart(...)` สร้างอ็อบเจ็กต์แผนภูมิบนสไลด์  
- **คุณเพิ่ม series ใหม่อย่างไร?** `chart.getChartData().getSeries().add(...)` แทรก series ข้อมูลใหม่  
- **คุณสามารถเปลี่ยนความกว้างของช่องว่างระหว่างแท่งได้หรือไม่?** ใช่—เรียก `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (ค่ามีหน่วยเป็นเปอร์เซ็นต์)  
- **ฉันต้องการไลเซนส์สำหรับการใช้งานจริงหรือไม่?** แน่นอน—ไลเซนส์ Aspose.Slides for Java ที่ถูกต้องจะเปิดใช้งานคุณสมบัติทั้งหมดและลบลายน้ำการประเมินผล

## อะไรคือ “add series to chart”?
การเพิ่ม series ไปยังแผนภูมิหมายถึงการแทรกคอลเลกชันใหม่ของจุดข้อมูลที่แผนภูมิแสดงเป็นองค์ประกอบภาพที่แยกจากกัน (เช่น กลุ่มคอลัมน์แยก) แต่ละ series สามารถมีค่า, สี, และการจัดรูปแบบของตนเอง, ทำให้สามารถเปรียบเทียบหลายชุดข้อมูลเคียงข้างกันได้

## ทำไมต้องใช้ Aspose.Slides for Java เพื่อแก้ไขการนำเสนอ .NET?
Aspose.Slides for Java ช่วยให้คุณสร้างหรือแก้ไขไฟล์ PPTX ที่เข้ากันได้อย่างเต็มที่กับโปรแกรมดู PowerPoint ของ .NET โดยไม่ต้องติดตั้ง Microsoft Office ใดๆ ใช้ Aspose.Slides for Java เมื่อคุณต้องการโซลูชันฝั่งเซิร์ฟเวอร์, ข้ามแพลตฟอร์ม ที่สร้างหรืออัปเดตไฟล์ .NET PPTX, รองรับแผนภูมิมากกว่า 50 ประเภท, และประมวลผลไฟล์ขนาดสูงสุด 500 MB โดยไม่ต้องโหลดเอกสารทั้งหมดเข้าสู่หน่วยความจำ API ของมันทำงานใน Java, Kotlin, Scala หรือภาษา JVM ใดก็ได้, ให้ผลลัพธ์เดียวกับที่นักพัฒนา .NET คาดหวัง

## ข้อกำหนดเบื้องต้น
- **Aspose.Slides for Java** library (version 25.4 หรือใหม่กว่า).  
- Maven, Gradle, หรือการดาวน์โหลด JAR ด้วยตนเอง.  
- ความรู้พื้นฐาน Java และความคุ้นเคยกับโครงสร้างไฟล์ PPTX.  

## การตั้งค่า Aspose.Slides for Java
### การติดตั้ง Maven
เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### การติดตั้ง Gradle
ใส่บรรทัดนี้ในไฟล์ `build.gradle` ของคุณ:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### การดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลด JAR ล่าสุดจากหน้าปล่อยอย่างเป็นทางการ: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**การรับไลเซนส์**  
เริ่มต้นด้วยการทดลองใช้งานฟรีโดยดาวน์โหลดไลเซนส์ชั่วคราวจาก [ที่นี่](https://purchase.aspose.com/temporary-license/). สำหรับการใช้งานในผลิตภัณฑ์, ซื้อไลเซนส์เต็มเพื่อเปิดใช้งานคุณสมบัติทั้งหมดและลบลายน้ำการประเมินผล

## คู่มือการดำเนินการแบบขั้นตอนต่อขั้นตอน
ด้านล่างแต่ละขั้นตอนคุณจะพบโค้ดสั้น ๆ (ไม่เปลี่ยนแปลงจากบทแนะนำต้นฉบับ) ตามด้วยคำอธิบายว่ามันทำอะไร

### ขั้นตอนที่ 1: สร้างการนำเสนอเปล่า
`Presentation` คือคลาสจุดเริ่มต้นที่แทนไฟล์ PowerPoint ในหน่วยความจำ.
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*เราเริ่มด้วยไฟล์ PPTX ที่ว่างเปล่า, ซึ่งเป็นผืนผ้าใบสำหรับเพิ่มแผนภูมิ.*

### ขั้นตอนที่ 2: เพิ่มแผนภูมิคอลัมน์แบบซ้อนกันลงในสไลด์
`Chart` แทนรูปแผนภูมิภายในสไลด์. `ChartType.StackedColumn` ระบุแผนภูมิคอลัมน์แบบซ้อนกัน.
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*เมธอด `addChart` สร้าง **แผนภูมิคอลัมน์แบบซ้อนกัน** และวางไว้ที่มุมบน‑ซ้ายของสไลด์.*

### ขั้นตอนที่ 3: เพิ่ม Series ไปยังแผนภูมิ (เป้าหมายหลัก)
`Series` ครอบคลุม series ข้อมูลเดียวในแผนภูมิ.
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*ที่นี่เรา **add series to chart** – แต่ละการเรียกสร้าง series ข้อมูลใหม่ที่จะแสดงเป็นกลุ่มคอลัมน์แยกกัน.*

### ขั้นตอนที่ 4: เพิ่ม Category ไปยังแผนภูมิ
`Category` กำหนดป้ายแกน X สำหรับข้อมูลแผนภูมิ.
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Categories ทำหน้าที่เป็นป้ายแกน X, ให้ความหมายกับแต่ละคอลัมน์.*

### ขั้นตอนที่ 5: เติมข้อมูลให้ Series
`DataPoint` เก็บค่าตัวเลขสำหรับ series ที่ Category เฉพาะ.
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
*Data points ให้ค่าตัวเลขกับแต่ละ series, ซึ่งแผนภูมิจะแสดงเป็นความสูงของแท่ง.*

### ขั้นตอนที่ 6: ตั้งค่า Gap Width สำหรับกลุ่ม Series ของแผนภูมิ
`SeriesGroup` ควบคุมคุณสมบัติการจัดวางสำหรับกลุ่ม series, เช่น gap width.
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*การปรับ gap width ช่วยเพิ่มความอ่านง่าย, โดยเฉพาะเมื่อมีหลาย Category.*

## กรณีการใช้งานทั่วไป
- **Financial reporting** – เปรียบเทียบรายได้ไตรมาสของแต่ละหน่วยธุรกิจ.  
- **Project dashboards** – แสดงเปอร์เซ็นต์การทำงานเสร็จของแต่ละทีม.  
- **Marketing analytics** – แสดงผลการทำแคมเปญแบบเคียงข้างกัน.  
สถานการณ์เหล่านี้ได้ประโยชน์จาก **ตัวอย่างแผนภูมิคอลัมน์แบบซ้อนกัน** เนื่องจากช่วยเน้นการมีส่วนร่วมของแต่ละ Category ต่อยอดรวม.

## เคล็ดลับด้านประสิทธิภาพ
- **Reuse the `Presentation` object** เมื่อสร้างหลายแผนภูมิเพื่อลดภาระหน่วยความจำ.  
- **Limit the number of data points** ให้เหลือเฉพาะที่จำเป็นสำหรับเรื่องราวภาพ; Aspose.Slides สามารถจัดการ 10,000 จุดได้, แต่ความเร็วการเรนเดอร์ลดลงหลังจากประมาณ 5,000 จุด.  
- **Dispose of objects** (`presentation.dispose()`) หลังจากบันทึกเพื่อปลดปล่อยทรัพยากรและหลีกเลี่ยงการรั่วไหลของหน่วยความจำ.  

## คำถามที่พบบ่อย
**ถาม: ฉันสามารถเพิ่มประเภทแผนภูมิอื่น ๆ นอกจาก stacked column ได้หรือไม่?**  
ตอบ: ใช่, Aspose.Slides รองรับแผนภูมิประเภท line, pie, area, radar, bubble, และกว่า 50 ประเภทอื่น ๆ, ทั้งหมดสามารถเข้าถึงได้ผ่านเมธอด `addChart` เดียวกัน.

**ถาม: ฉันต้องการไลเซนส์แยกสำหรับผลลัพธ์ .NET หรือไม่?**  
ตอบ: ไม่, ไลเซนส์ Java เดียวกันทำงานกับทุกรูปแบบผลลัพธ์รวมถึงไฟล์ .NET PPTX ด้วย.

**ถาม: ฉันจะเปลี่ยนพาเลตสีของแผนภูมิได้อย่างไร?**  
ตอบ: ใช้ `series.getFormat().getFill().setFillType(FillType.Solid)` แล้วตั้งค่าอ็อบเจ็กต์ `Color` ที่ต้องการสำหรับแต่ละ series.

**ถาม: สามารถเพิ่มป้ายข้อมูลโดยโปรแกรมได้หรือไม่?**  
ตอบ: แน่นอน. เรียก `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` เพื่อแสดงค่าตัวเลขบนแต่ละคอลัมน์.

**ถาม: ถ้าฉันต้องอัปเดตการนำเสนอที่มีอยู่แล้วจะทำอย่างไร?**  
ตอบ: โหลดไฟล์ด้วย `new Presentation("existing.pptx")`, แก้ไขแผนภูมิด้วยการเรียก API เดียวกัน, แล้วบันทึกกลับไปยังดิสก์.

## สรุป
คุณตอนนี้มีคู่มือครบวงจรเกี่ยวกับการ **add series to chart**, การสร้าง **แผนภูมิคอลัมน์แบบซ้อนกัน**, และการปรับแต่งลักษณะของมันในงานนำเสนอ .NET ด้วย Aspose.Slides for Java. ทดลองใช้ประเภทแผนภูมิ, สี, และแหล่งข้อมูลต่าง ๆ เพื่อสร้างรายงานภาพที่น่าประทับใจซึ่งจะทำให้ผู้มีส่วนได้ส่วนเสียประทับใจและสนับสนุนการตัดสินใจที่ขับเคลื่อนด้วยข้อมูล.

---

**อัปเดตล่าสุด:** 2026-06-08  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4 (JDK 16)  
**ผู้เขียน:** Aspose  

{{< blocks/products/products-backtop-button >}}

## บทแนะนำที่เกี่ยวข้อง

- [วิธีสร้างแผนภูมิคอลัมน์แบบซ้อนกันตามเปอร์เซ็นต์ใน .NET ด้วย Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [การสร้างและจัดการ Series ของแผนภูมิขั้นสูงด้วย Aspose.Slides .NET เพื่อการแสดงผลข้อมูลที่มีประสิทธิภาพ](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [ลบจุดข้อมูล Series ของแผนภูมิที่ระบุด้วย Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}