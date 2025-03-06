---
title: แผนภูมิสูตรเซลล์ข้อมูลใน Java Slides
linktitle: แผนภูมิสูตรเซลล์ข้อมูลใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการตั้งค่าสูตรเซลล์ข้อมูลแผนภูมิในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สร้างแผนภูมิแบบไดนามิกด้วยสูตร
weight: 11
url: /th/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับสูตรเซลล์ข้อมูลแผนภูมิใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีการทำงานกับสูตรเซลล์ข้อมูลแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java ด้วย Aspose.Slides คุณสามารถสร้างและจัดการแผนภูมิในงานนำเสนอ PowerPoint รวมถึงการตั้งค่าสูตรสำหรับเซลล์ข้อมูล

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างงานนำเสนอ PowerPoint

ขั้นแรก มาสร้างงานนำเสนอ PowerPoint ใหม่และเพิ่มแผนภูมิลงไป

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // เพิ่มแผนภูมิลงในสไลด์แรก
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // รับสมุดงานสำหรับข้อมูลแผนภูมิ
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // ดำเนินการกับเซลล์ข้อมูลต่อไป
    // -
    
    // บันทึกการนำเสนอ
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## ขั้นตอนที่ 2: ตั้งค่าสูตรสำหรับเซลล์ข้อมูล

ตอนนี้ เรามาตั้งค่าสูตรสำหรับเซลล์ข้อมูลเฉพาะในแผนภูมิกันดีกว่า ในตัวอย่างนี้ เราจะตั้งค่าสูตรสำหรับเซลล์สองเซลล์ที่แตกต่างกัน

### เซลล์ 1: การใช้สัญลักษณ์ A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

ในโค้ดด้านบน เราตั้งค่าสูตรสำหรับเซลล์ B2 โดยใช้สัญลักษณ์ A1 สูตรคำนวณผลรวมของเซลล์ F2 ถึง H5 และบวก 1 เข้ากับผลลัพธ์

### เซลล์ 2: การใช้สัญลักษณ์ R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

ที่นี่ เราตั้งสูตรสำหรับเซลล์ C2 โดยใช้สัญลักษณ์ R1C1 สูตรจะคำนวณค่าสูงสุดภายในช่วง R2C6 ถึง R5C8 แล้วหารด้วย 3

## ขั้นตอนที่ 3: คำนวณสูตร

หลังจากตั้งค่าสูตรแล้ว จำเป็นต้องคำนวณโดยใช้โค้ดต่อไปนี้:

```java
workbook.calculateFormulas();
```

ขั้นตอนนี้ช่วยให้แน่ใจว่าแผนภูมิสะท้อนถึงค่าที่อัปเดตตามสูตร

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับสูตรเซลล์ข้อมูลแผนภูมิใน Java Slides

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีการทำงานกับสูตรเซลล์ข้อมูลแผนภูมิใน Aspose.Slides สำหรับ Java เราได้ครอบคลุมถึงการสร้างงานนำเสนอ PowerPoint การเพิ่มแผนภูมิ การตั้งค่าสูตรสำหรับเซลล์ข้อมูล การคำนวณสูตร และการบันทึกงานนำเสนอ ตอนนี้คุณสามารถใช้ประโยชน์จากความสามารถเหล่านี้เพื่อสร้างแผนภูมิแบบไดนามิกและขับเคลื่อนด้วยข้อมูลในการนำเสนอของคุณ

## คำถามที่พบบ่อย

### ฉันจะเพิ่มแผนภูมิลงในสไลด์ที่ต้องการได้อย่างไร

 หากต้องการเพิ่มแผนภูมิลงในสไลด์ที่ต้องการ คุณสามารถใช้`getSlides().get_Item(slideIndex)` วิธีเข้าถึงสไลด์ที่ต้องการ จากนั้นใช้`addChart` วิธีการเพิ่มแผนภูมิ

### ฉันสามารถใช้สูตรประเภทต่างๆ ในเซลล์ข้อมูลได้หรือไม่

ใช่ คุณสามารถใช้สูตรหลายประเภท รวมถึงการดำเนินการทางคณิตศาสตร์ ฟังก์ชัน และการอ้างอิงไปยังเซลล์อื่นๆ ในสูตรเซลล์ข้อมูล

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

 คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยใช้`setChartType` วิธีการบน`IChart` วัตถุและระบุที่ต้องการ`ChartType`.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
