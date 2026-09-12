---
date: '2026-09-12'
description: เรียนรู้วิธีใช้ Maven Aspose Slides เพื่อเพิ่มและปรับแต่งแผนภูมิหุ้นแบบไดนามิกใน
  PowerPoint ด้วย Java รวมถึงการตั้งค่า การเพิ่มชุดข้อมูล การจัดรูปแบบเส้น และการบันทึก
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: บทแนะนำ Maven Aspose Slides แสดงวิธีสร้างและปรับแต่งแผนภูมิหุ้นแบบไดนามิกใน
  PowerPoint ด้วย Java ครอบคลุมชุดข้อมูล การจัดรูปแบบเส้น และการบันทึก
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'คู่มือ Maven Aspose Slides: สร้างแผนภูมิหุ้นแบบไดนามิกใน PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: สร้างแผนภูมิหุ้นแบบไดนามิกใน PowerPoint ด้วย Java'
url: /th/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: สร้างแผนภูมิหุ้นแบบไดนามิกใน PowerPoint ด้วย Java

## บทนำ

**Maven Aspose Slides** ช่วยให้คุณสร้างงานนำเสนอ PowerPoint ที่ซับซ้อนจาก Java อย่างโปรแกรมเมติก ในบทแนะนำนี้คุณจะได้เรียนรู้วิธีสร้างแผนภูมิหุ้นแบบไดนามิก, เพิ่มและจัดรูปแบบชุดข้อมูล, ปรับแต่งเส้นแผนภูมิ, และสุดท้ายบันทึกไฟล์ ไม่ว่าคุณจะเป็นนักวิเคราะห์การเงินที่เตรียมรายงานไตรมาสหรือเป็นนักพัฒนาที่สร้างสไลด์อัตโนมัติ ขั้นตอนต่อไปนี้จะให้โซลูชันที่ครบถ้วนพร้อมใช้งานในระดับการผลิต

**สิ่งที่คุณจะได้เรียนรู้**
- วิธีตั้งค่า Maven กับ Aspose.Slides for Java  
- วิธีเพิ่มแผนภูมิหุ้นและล้างข้อมูลเริ่มต้น  
- วิธี **เพิ่มแผนภูมิชุดข้อมูล** และ **จัดรูปแบบเส้นแผนภูมิ**  
- วิธี **ปรับแต่งองค์ประกอบภาพเฉพาะของ chart java**  
- วิธีบันทึกงานนำเสนอที่อัปเดต

พร้อมหรือยังที่จะเปลี่ยนตัวเลขดิบให้เป็นภาพหุ้นที่ดึงดูดสายตา? เริ่มกันเลย!

## คำตอบอย่างรวดเร็ว
- **ฉันต้องการ Maven artifact ใด?** `aspose-slides` version 25.4 (or newer).  
- **ฉันสามารถรันบนระบบปฏิบัติการใดก็ได้หรือไม่?** Yes – the library is pure Java and works on Windows, macOS, and Linux.  
- **ฉันต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** A free temporary license works for testing; a full license is required for production.  
- **ประเภทแผนภูมิที่รองรับมีอะไรบ้าง?** Over 70 built‑in chart types, including Stock, Line, and Bar charts.  
- **ฉันสามารถประมวลผลงานนำเสนอขนาดใหญ่ได้แค่ไหน?** Aspose.Slides can handle files with 500+ slides without loading the whole file into memory.

## Maven Aspose Slides คืออะไร?

`Aspose.Slides for Java` เป็น API ของ Java ที่ช่วยให้สร้าง, แก้ไข, และแปลงไฟล์ PowerPoint โดยไม่ต้องใช้ Microsoft Office การรวมกับ Maven ทำให้การจัดการ dependencies ง่ายขึ้น โดยคุณสามารถดึงไลบรารีโดยตรงจาก Maven Central

## ทำไมต้องใช้ Maven Aspose Slides สำหรับแผนภูมิหุ้น?

Aspose.Slides รองรับ **แผนภูมิมากกว่า 70 ชนิด** และสามารถเรนเดอร์งานนำเสนอหลายร้อยหน้าได้ภายในไม่กี่วินาทีบนฮาร์ดแวร์เซิร์ฟเวอร์ทั่วไป คุณลักษณะ **เส้น high‑low** และ **แถบ up/down** ให้การควบคุมที่แม่นยำสำหรับการแสดงผลการเงิน มากกว่าที่ UI ของ PowerPoint สามารถทำได้

## ข้อกำหนดเบื้องต้น

- **Java Development Kit (JDK)** – version 11 หรือสูงกว่า.  
- **IDE** – IntelliJ IDEA, Eclipse หรือเครื่องมือแก้ไขใด ๆ ที่คุณต้องการ.  
- **Aspose.Slides for Java** – version 25.4 (รุ่นล่าสุด ณ เวลาที่เขียน).  

### การตั้งค่า Aspose.Slides for Java

#### Maven
เพื่อรวม Aspose.Slides เข้าในโปรเจกต์ของคุณโดยใช้ Maven ให้เพิ่ม dependency ต่อไปนี้ในไฟล์ `pom.xml` ของคุณ:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
สำหรับผู้ใช้ Gradle ให้ใส่ส่วนนี้ในไฟล์ `build.gradle` ของคุณ:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### ดาวน์โหลดโดยตรง
หรือคุณสามารถดาวน์โหลด JAR ล่าสุดจาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**การรับใบอนุญาต** – เริ่มต้นด้วยการทดลองใช้ฟรีหรือขอใบอนุญาตชั่วคราว สำหรับการใช้งานเชิงพาณิชย์ ให้ซื้อใบอนุญาตเต็มรูปแบบ

สำหรับอ้างอิง API อย่างละเอียด ดูที่ [Aspose.Slides documentation](https://docs.aspose.com/slides/java/)

## วิธีสร้างแผนภูมิหุ้นแบบไดนามิกขั้นตอนโดยขั้นตอน

โหลดงานนำเสนอของคุณ, เพิ่มแผนภูมิหุ้น, ล้างข้อมูลเริ่มต้น, แล้วใส่ชุดข้อมูลและหมวดหมู่ของคุณเอง คำตอบโดยตรงของคำถามหลักคือ:

> โหลดไฟล์ PPTX ที่มีอยู่ด้วย `new Presentation("template.pptx")`, เพิ่ม `Chart` ชนิด `ChartType.Stock`, ล้างชุดข้อมูลและหมวดหมู่เริ่มต้น, แล้วเติมข้อมูลของคุณเองพร้อมตัวเลือกการจัดรูปแบบ สุดท้ายเรียก `presentation.save("output.pptx", SaveFormat.Pptx)`.

### เริ่มต้นงานนำเสนอ
#### ภาพรวม
เริ่มต้นโดยการโหลดไฟล์ PowerPoint ที่มีอยู่เพื่อให้คุณสามารถแก้ไขได้โดยตรง

#### ขั้นตอนโดยละเอียด
1. **นำเข้าไลบรารี** – คลาส `Presentation` เป็นจุดเริ่มต้นสำหรับการทำงานกับสไลด์ทั้งหมด.

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **โหลดไฟล์งานนำเสนอ** – ระบุพาธไปยังไฟล์ PPTX เทมเพลตของคุณ.

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### เพิ่มแผนภูมิหุ้นลงในสไลด์
#### ภาพรวม
แทรกแผนภูมิหุ้นลงในสไลด์แรกของงานนำเสนอ

คลาส `Chart` แทนรูปแบบแผนภูมิที่สามารถเพิ่มลงในสไลด์ได้.

#### คำตอบโดยตรง
คุณสามารถเพิ่มแผนภูมิหุ้นโดยเรียก `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. นี้จะสร้างอ็อบเจกต์แผนภูมิที่คุณสามารถจัดการได้ทันที.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### ล้างชุดข้อมูลและหมวดหมู่ที่มีอยู่ในแผนภูมิ
#### ภาพรวม
ลบชุดข้อมูลหรือหมวดหมู่ที่มีอยู่ล่วงหน้าเพื่อให้คุณเริ่มต้นด้วยชุดข้อมูลที่สะอาด

อ็อบเจกต์ `ChartData` เก็บชุดข้อมูลและหมวดหมู่สำหรับแผนภูมิ

#### คำตอบโดยตรง
เรียก `chart.getChartData().getSeries().clear()` และ `chart.getChartData().getCategories().clear()` เพื่อเคลียร์เนื้อหาเริ่มต้นก่อนเพิ่มของคุณเอง.

```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### เพิ่มหมวดหมู่ลงในข้อมูลแผนภูมิ
#### ภาพรวม
กำหนดหมวดหมู่แกน X (เช่น วันที่) ที่จัดกลุ่มค่าหุ้นของคุณ

`ChartCategory` แทนป้ายแกน X สำหรับแผนภูมิ

#### คำตอบโดยตรง
สร้าง `ChartCategory` ใหม่สำหรับแต่ละป้ายโดยใช้ `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")` และทำซ้ำสำหรับแต่ละเดือนหรือช่วงเวลา.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### เพิ่มชุดข้อมูลลงในแผนภูมิ
#### ภาพรวม
เพิ่มชุดข้อมูลสำคัญสี่ชุด: Open, High, Low, และ Close

`ChartSeries` เก็บคอลเลกชันของจุดข้อมูลสำหรับชุดข้อมูลเฉพาะในแผนภูมิ

#### คำตอบโดยตรง
สำหรับแต่ละชุดข้อมูล ให้เรียก `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. นี้จะลงทะเบียนชุดข้อมูลกับ data workbook ของแผนภูมิ.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### เพิ่มจุดข้อมูลลงในชุดข้อมูล
#### ภาพรวม
เติมค่าตัวเลขที่แสดงราคาหุ้นลงในแต่ละชุดข้อมูล

`DataPoint` แทนค่าหนึ่งค่าในชุดข้อมูล

#### คำตอบโดยตรง
วนลูปผ่านคอลเลกชันข้อมูลของคุณและใช้ `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (หรือเมธอดที่เหมาะสมสำหรับประเภทชุดข้อมูล) เพื่อแทรกแต่ละจุด.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### จัดรูปแบบเส้น high‑low และแถบ up/down
#### ภาพรวม
ปรับสไตล์การแสดงของตัวเชื่อมต่อ high‑low และการเติมสีของแถบ up/down

`Marker` กำหนดสัญลักษณ์ภาพสำหรับจุดข้อมูล

#### คำตอบโดยตรง
ตั้งค่า `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` และกำหนดค่า `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)` เพื่อควบคุมความหนาและสีของเส้น.

```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### แสดงแถบ up/down
ใช้เมธอด `setShowUpDownBars(true)` ของแผนภูมิเพื่อทำให้แถบ up/down ปรากฏ.

```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### ปรับแต่งป้ายข้อมูลบนเส้น high‑low
#### ภาพรวม
แสดงค่าตัวเลขโดยตรงบนเส้น high‑low เพื่ออ้างอิงอย่างรวดเร็ว

`DataLabel` ควบคุมลักษณะของป้ายที่แนบกับจุดข้อมูล

#### คำตอบโดยตรง
เปิดใช้งานป้ายข้อมูลด้วย `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` และจัดรูปแบบตามต้องการ.

```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### ตั้งค่าสีเติมของแถบ up/down
#### ภาพรวม
ให้แถบขึ้นเติมสีเขียวและแถบลงเติมสีแดงเพื่อสื่อถึงการเคลื่อนที่ของตลาดอย่างชัดเจน

อ็อบเจกต์ `UpDownBars` ให้การเข้าถึงการจัดรูปแบบของแถบขึ้นและแถบลง

#### คำตอบโดยตรง
ใช้ `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` และตั้งค่าสีทึบเป็น `Color.GREEN`; ทำซ้ำสำหรับแถบลงด้วย `Color.RED`.

```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### บันทึกไฟล์ PowerPoint
#### ภาพรวม
บันทึกการเปลี่ยนแปลงของคุณเป็นไฟล์ PPTX ใหม่

เมธอด `save` จะเขียนงานนำเสนอลงดิสก์ในรูปแบบที่ระบุ

#### คำตอบโดยตรง
เรียก `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – นี้จะเขียนงานนำเสนอที่แก้ไขแล้วลงดิสก์ในรูปแบบ PowerPoint มาตรฐาน.

```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## ปัญหาทั่วไปและการแก้ไขข้อผิดพลาด
- **แผนภูมิไม่แสดง** – ตรวจสอบให้แน่ใจว่า พิกัด X/Y และขนาดของแผนภูมิเยอะแนบอยู่ในขอบเขตของสไลด์.  
- **จุดข้อมูลหาย** – ตรวจสอบว่าดัชนีเซลล์ใน data workbook ตรงกับชุดข้อมูล/แถวที่คุณต้องการเติม.  
- **ข้อยกเว้นใบอนุญาต** – ใบอนุญาตทดลองชั่วคราวหมดอายุหลัง 30 วัน; แทนที่ด้วยใบอนุญาตถาวรสำหรับการสร้างในสภาพการผลิต.  
- **ประสิทธิภาพช้าลงกับไฟล์ขนาดใหญ่** – ใช้ `Presentation.setCacheSize(0)` เพื่อปิดการแคชหากคุณประมวลผลหลายพันสไลด์ในชุด.

## คำถามที่พบบ่อย

**Q: ฉันสามารถใช้โค้ดนี้ในแอปพลิเคชันเว็บได้หรือไม่?**  
A: ใช่. ไลบรารีเป็น Java แท้ ๆ ดังนั้นคุณสามารถรันได้ในคอนเทนเนอร์ servlet ใด ๆ หรือบริการ Spring Boot

**Q: Aspose.Slides รองรับประเภทแผนภูมิอื่น ๆ นอกจาก Stock หรือไม่?**  
A: แน่นอน. รองรับแผนภูมิมากกว่า 70 ชนิด รวมถึง Line, Bar, Pie, และ Radar

**Q: ฉันจะเพิ่มหัวข้อแผนภูมิโดยโปรแกรมได้อย่างไร?**  
A: ใช้ `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")` แล้วจัดรูปแบบหัวข้อตามต้องการ.

**Q: มีขีดจำกัดจำนวนจุดข้อมูลต่อชุดหรือไม่?**  
A: โดยปฏิบัติคุณสามารถเพิ่มจุดหลายหมื่นจุด; การใช้หน่วยความจำเพิ่มตามเชิงเส้น และไลบรารีสตรีมข้อมูลเพื่อรักษาขนาดต่ำ.

**Q: ควรใช้ Maven coordinates ใดสำหรับเวอร์ชันล่าสุด?**  
A: เวอร์ชันล่าสุดจะมีให้เสมอภายใต้ `com.aspose:aspose-slides:25.4` (หรือใหม่กว่า) บน Maven Central.

---

**อัปเดตล่าสุด:** 2026-09-12  
**ทดสอบด้วย:** Aspose.Slides for Java 25.4  
**ผู้เขียน:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [aspose slides maven dependency: เพิ่มและกำหนดค่าแผนภูมิในงานนำเสนอโดยใช้ Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [สร้างแผนภูมิ PowerPoint ด้วย Java – บันทึกงานนำเสนอพร้อมแผนภูมิโดยใช้ Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [สร้างและจัดรูปแบบแผนภูมิ PowerPoint ด้วย Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}