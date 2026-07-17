---
date: '2026-07-17'
description: เรียนรู้วิธีเพิ่มแผนภูมิใน PowerPoint โดยการสร้างแผนภูมิ Pie of Pie ด้วย
  Aspose.Slides for Java รวมถึงการตั้งค่า โค้ด การปรับแต่ง และการบันทึกเป็น PPTX
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: เพิ่มแผนภูมิใน PowerPoint ด้วย Aspose.Slides for Java คู่มือนี้แสดงวิธีสร้าง
  ปรับแต่ง และบันทึกแผนภูมิ Pie of Pie เป็น PPTX ภายในไม่กี่นาที
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: เพิ่มแผนภูมิใน PowerPoint – สร้างแผนภูมิ Pie of Pie ด้วย Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: เพิ่มแผนภูมิใน PowerPoint – สร้างแผนภูมิ Pie of Pie ด้วย Java และ Aspose.Slides
url: /th/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# เพิ่มแผนภูมิลงใน PowerPoint – สร้างแผนภูมิ Pie of Pie ด้วย Java และ Aspose.Slides

## แผนภูมิและกราฟ

### บทนำ

ในงานนำเสนอที่ขับเคลื่อนด้วยข้อมูลสมัยใหม่ **การเพิ่มแผนภูมิลงใน PowerPoint** มักเป็นวิธีที่เร็วที่สุดในการเปลี่ยนตัวเลขดิบให้เป็นข้อมูลเชิงภาพ แผนภูมิวงกลมแบบปกติทำงานได้ดีสำหรับหมวดหมู่ไม่กี่รายการ แต่เมื่อบางส่วนมีขนาดเล็กมากจะอ่านไม่ออก แผนภูมิ *Pie of Pie* จะแก้ปัญหานี้โดยแยกส่วนที่เล็กเหล่านั้นออกไปเป็นวงกลมย่อย ทำให้แผนภูมิหลักสะอาดและรายละเอียดเข้าถึงได้ง่าย

ในบทแนะนำนี้คุณจะได้เรียนรู้วิธี **เพิ่มแผนภูมิลงใน PowerPoint** ด้วยการสร้างแผนภูมิ Pie of Pie ด้วย Aspose.Slides for Java เราจะพาคุณผ่านการตั้งค่าสภาพแวดล้อม การสร้างแผนภูมิ การปรับแต่งป้ายข้อมูล การปรับตำแหน่งการแยกส่วน และสุดท้ายการบันทึกงานนำเสนอเป็นไฟล์ PPTX เมื่อเสร็จคุณจะพร้อมฝังแผนภูมิขั้นสูงลงในสไลด์ใดก็ได้

## คำตอบอย่างรวดเร็ว
ใน Aspose.Slides, `Presentation` แทนไฟล์ PPTX, `ChartType.PieOfPie` เลือกแผนภูมิ Pie of Pie, `setShowValue(true)` แสดงค่าบนป้าย, และ `save` เขียนไฟล์

- **คลาสหลักสำหรับการจัดการ PowerPoint คืออะไร?** `Presentation` – แทนไฟล์ PPTX ทั้งหมดในหน่วยความจำ  
- **แผนภูมิประเภทใดสร้างวงกลมย่อยสำหรับส่วนที่เล็ก?** `ChartType.PieOfPie`  
- **จะแสดงค่าบนแต่ละส่วนอย่างไร?** ตั้งค่า `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`  
- **สามารถบันทึกไฟล์โดยตรงเป็น PPTX ได้หรือไม่?** ได้ – เรียก `presentation.save("output.pptx", SaveFormat.Pptx)`  
- **ต้องการใบอนุญาตสำหรับการพัฒนาหรือไม่?** ทดลองฟรี 30 วันใช้ได้สำหรับการทดสอบ; ใบอนุญาตถาวรจะลบลายน้ำการประเมินผล

## แผนภูมิ Pie of Pie คืออะไร?
**แผนภูมิ Pie of Pie** เป็นการแสดงผลแบบวงกลมสองระดับที่แยกส่วนเล็กหนึ่งหรือหลายส่วนออกเป็นวงกลมที่เชื่อมโยง ทำให้อ่านได้ง่ายขึ้น Aspose.Slides รองรับประเภทแผนภูมินี้โดยตรง ให้คุณควบคุมขนาดการแยก, ตำแหน่ง, และรูปแบบป้ายได้ตามต้องการ

## ทำไมต้องเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides?
Aspose.Slides สามารถสร้าง, แก้ไข, และแปลงไฟล์ PowerPoint ได้โดยไม่ต้องติดตั้ง Microsoft Office รองรับ **รูปแบบเข้าและออกกว่า 50+** ประมวลผลงานนำเสนอที่มี **สูงสุด 500 สไลด์** ในเวลาต่ำกว่าวินาทีบนเซิร์ฟเวอร์ทั่วไป และให้ **การควบคุม API เต็มรูปแบบ** สำหรับสไตล์แผนภูมิ, ป้ายข้อมูล, และการจัดวาง – เหมาะสำหรับสายงานอัตโนมัติการรายงาน

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มโปรดตรวจสอบว่าคุณมี:

- **Java Development Kit (JDK) 16+** ติดตั้งแล้ว  
- IDE เช่น **IntelliJ IDEA**, **Eclipse**, หรือ **NetBeans**  
- Maven หรือ Gradle สำหรับการจัดการ dependencies (ดูส่วนด้านล่าง)  
- ความรู้พื้นฐานด้าน Java และความคุ้นเคยกับการสร้างโปรเจกต์

## การตั้งค่า Aspose.Slides สำหรับ Java

### ข้อมูลการติดตั้ง

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

**Direct Download:** คุณสามารถดาวน์โหลดเวอร์ชันล่าสุดได้จาก [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/)

### ขั้นตอนการรับใบอนุญาต
- **Free Trial:** เริ่มต้นด้วยการทดลองใช้ 30 วันเพื่อสำรวจคุณสมบัติทั้งหมด  
- **Temporary License:** ขอคีย์ชั่วคราวสำหรับการประเมินผลระยะยาว  
- **Purchase:** รับใบอนุญาตถาวรสำหรับการใช้งานในผลิตภัณฑ์เพื่อเอาลายน้ำการประเมินผลออก

### การเริ่มต้นและตั้งค่าเบื้องต้น
`Presentation` คืออ็อบเจกต์หลักสำหรับสร้างไฟล์ PowerPoint, และ `Chart` แทนรูปแผนภูมิภายในสไลด์

```java
Presentation presentation = new Presentation();
```  

นี่จะสร้างงานนำเสนอเปล่าที่พร้อมสำหรับสไลด์และแผนภูมิ

## คู่มือการดำเนินการ

### วิธีเพิ่มแผนภูมิลงใน PowerPoint ด้วย Aspose.Slides สำหรับ Java?
โหลด `Presentation` ใหม่, เพิ่มสไลด์, แล้วแทรก `Chart` ประเภท `PieOfPie` การเรียก API สั้นและกระชับ: สร้างแผนภูมิ, เติมข้อมูลซีรีส์, ปรับการแสดงป้าย, ตั้งค่าขนาดของวงกลมย่อย, แล้วบันทึก ทั้งหมดใช้โค้ดไม่เกิน 20 บรรทัด ทำให้เหมาะกับการสร้างรายงานอัตโนมัติ

### การสร้างแผนภูมิ 'Pie of Pie'

#### ภาพรวม
เราจะสร้างแผนภูมิ Pie of Pie บนสไลด์แรก, แยกส่วนที่เล็กที่สุดออก, และใส่ค่าลงบนแต่ละส่วน

#### ขั้นตอนที่ 1: สร้างอินสแตนซ์ของคลาส Presentation
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
นี่เป็นการเริ่มต้นคอนเทนเนอร์สำหรับสไลด์และแผนภูมิทั้งหมดที่ตามมา

#### ขั้นตอนที่ 2: เพิ่มแผนภูมิ 'Pie of Pie' บนสไลด์แรก
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
ที่นี่เรากำหนด `ChartType.PieOfPie` และระบุตำแหน่ง (X, Y) และขนาด (กว้าง, สูง) ของแผนภูมิบนแคนวาสสไลด์

#### ขั้นตอนที่ 3: ตั้งค่าป้ายข้อมูลให้แสดงค่าในซีรีส์
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
การเปิด `showValue` ทำให้แต่ละส่วนแสดงค่าตัวเลข ซึ่งจำเป็นสำหรับการตีความข้อมูลอย่างรวดเร็ว

#### ขั้นตอนที่ 4: กำหนดขนาดของ Pie ที่สองและแยกตามเปอร์เซ็นต์
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
ตัวเลือกเหล่านี้ให้คุณกำหนดว่ากี่เปอร์เซ็นต์ของแผนภูมิจะถูกจัดสรรให้กับวงกลมย่อยและส่วนใดบ้างที่ถูกย้ายตามเกณฑ์เปอร์เซ็นต์

#### ขั้นตอนที่ 5: บันทึกการนำเสนอลงดิสก์ในรูปแบบ PPTX
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Pro tip:** ใช้พาธแบบเต็มหรือ `Paths.get()` ของ Java เพื่อหลีกเลี่ยงตัวคั่นที่แตกต่างกันตามแพลตฟอร์ม

## ปัญหาและวิธีแก้ไขทั่วไป

คลาส `License` โหลดไฟล์ใบอนุญาตเพื่อเอาลายน้ำการประเมินผลออก

- **Missing license warning:** หากเห็นข้อความ “Evaluation Only” บนแผนภูมิ ให้ตรวจสอบว่าคุณได้ตั้งค่าไฟล์ใบอนุญาตที่ถูกต้องผ่าน `License license = new License(); license.setLicense("Aspose.Slides.lic");`  
- **Incorrect slice split:** ตรวจสอบว่า property `splitBy` ตั้งเป็น `SplitBy.Percentage` และ `secondPieSize` อยู่ในช่วง 0‑100  
- **Data not displaying:** ยืนยันว่าซีรีส์ของแผนภูมิมีจุดข้อมูลอย่างน้อยหนึ่งจุด มิฉะนั้นแผนภูมิจะว่างเปล่า

## คำถามที่พบบ่อย

`IChart` แทนอ็อบเจกต์แผนภูมิที่สามารถเพิ่มลงในสไลด์ได้

**Q: สามารถสร้างแผนภูมิหลายอันในงานนำเสนอเดียวได้หรือไม่?**  
A: ได้, สร้าง `IChart` ใหม่สำหรับแต่ละสไลด์หรือแต่ละตำแหน่ง; API อนุญาตให้มีอ็อบเจกต์แผนภูมิไม่จำกัดต่อไฟล์

`SaveFormat.Pdf` ระบุรูปแบบการบันทึกเป็น PDF

**Q: Aspose.Slides รองรับการบันทึกเป็น PDF ด้วยหรือไม่?**  
A: แน่นอน – เรียก `presentation.save("output.pdf", SaveFormat.Pdf)` เพื่อส่งออกสไลด์เดิมเป็นไฟล์ PDF

`IPortion` แทนส่วนย่อยของแผนภูมิวงกลม

**Q: จำนวนจุดข้อมูลสูงสุดที่แผนภูมิ Pie of Pie สามารถจัดการได้คือเท่าไหร่?**  
A: ไลบรารีรองรับจุดข้อมูลสูงสุด **10,000** จุดต่อซีรีส์, จำกัดเพียงตามหน่วยความจำที่มี

**Q: สามารถปรับสีของส่วนย่อยแต่ละส่วนได้หรือไม่?**  
A: ได้, เข้าถึงแต่ละ `IPortion` ผ่าน `chart.getChartData().getSeries().get_Item(0).getPortions()` แล้วตั้งค่า `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`

**Q: จะฝังไฟล์ PPTX ที่สร้างขึ้นในเว็บแอปพลิเคชันอย่างไร?**  
A: หลังบันทึกไฟล์, ส่งสตรีมโดยตรงไปยังไคลเอนต์ด้วย `HttpServletResponse` พร้อม `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`

## สรุป

คุณมีสูตรครบถ้วนและพร้อมใช้งานสำหรับ **การเพิ่มแผนภูมิลงใน PowerPoint** ด้วยการสร้างแผนภูมิ Pie of Pie ด้วย Aspose.Slides for Java ทดลองปรับค่าเกณฑ์การแยก, รูปแบบป้าย, และสไตล์สีเพื่อให้สอดคล้องกับแนวทางแบรนด์ของคุณ ต่อไปสำรวจประเภทแผนภูมิอื่น ๆ เช่น stacked bar หรือ radar เพื่อเพิ่มความหลากหลายให้กับสไลด์อัตโนมัติของคุณ

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## บทแนะนำที่เกี่ยวข้อง

- [Create Dynamic Chart Java – PowerPoint Charts Tutorials for Aspose.Slides](/slides/java/charts-graphs/)
- [How to add pie chart PowerPoint with Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑by‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}