---
title: คำนวณสูตรใน Java Slides
linktitle: คำนวณสูตรใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการคำนวณสูตรใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดสำหรับการนำเสนอ PowerPoint แบบไดนามิก
type: docs
weight: 10
url: /th/java/data-manipulation/calculate-formulas-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการคำนวณสูตรใน Java Slides โดยใช้ Aspose.Slides

ในคู่มือนี้ เราจะสาธิตวิธีคำนวณสูตรใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API Aspose.Slides เป็นไลบรารีที่มีประสิทธิภาพสำหรับการทำงานกับงานนำเสนอ PowerPoint และมีคุณสมบัติในการจัดการแผนภูมิและคำนวณสูตรภายในสไลด์

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- สภาพแวดล้อมการพัฒนาจาวา
-  Aspose.Slides สำหรับไลบรารี Java (คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/)
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

ขั้นแรก มาสร้างงานนำเสนอ PowerPoint ใหม่และเพิ่มสไลด์ลงไป เราจะทำงานกับสไลด์เดียวในตัวอย่างนี้

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์

ตอนนี้ เรามาเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์ เราจะใช้แผนภูมินี้เพื่อแสดงการคำนวณตามสูตร

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## ขั้นตอนที่ 3: ตั้งค่าสูตรและค่า

ต่อไป เราจะตั้งค่าสูตรและค่าสำหรับเซลล์ข้อมูลแผนภูมิโดยใช้ Aspose.Slides API เราจะคำนวณสูตรสำหรับเซลล์เหล่านี้

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// กำหนดสูตรสำหรับเซลล์ A1
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// ตั้งค่าสำหรับเซลล์ A2
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// กำหนดสูตรสำหรับเซลล์ B2
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// กำหนดสูตรสำหรับเซลล์ C2
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// ตั้งค่าสูตรสำหรับเซลล์ A1 อีกครั้ง
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วด้วยสูตรจากการคำนวณ

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับการคำนวณสูตรใน Java Slides

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในคู่มือนี้ เราได้เรียนรู้วิธีการคำนวณสูตรใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java เราสร้างงานนำเสนอใหม่ เพิ่มแผนภูมิลงไป ตั้งค่าสูตรและค่าสำหรับเซลล์ข้อมูลแผนภูมิ และบันทึกงานนำเสนอด้วยสูตรจากการคำนวณ

## คำถามที่พบบ่อย

### ฉันจะตั้งค่าสูตรสำหรับเซลล์ข้อมูลแผนภูมิได้อย่างไร

 คุณสามารถตั้งค่าสูตรสำหรับเซลล์ข้อมูลแผนภูมิได้โดยใช้`setFormula` วิธีการของ`IChartDataCell` ใน Aspose.Slides

### ฉันจะตั้งค่าสำหรับเซลล์ข้อมูลแผนภูมิได้อย่างไร

 คุณสามารถตั้งค่าสำหรับเซลล์ข้อมูลแผนภูมิได้โดยใช้`setValue` วิธีการของ`IChartDataCell` ใน Aspose.Slides

### ฉันจะคำนวณสูตรในเวิร์กบุ๊กได้อย่างไร

 คุณสามารถคำนวณสูตรในเวิร์กบุ๊กได้โดยใช้`calculateFormulas` วิธีการของ`IChartDataWorkbook` ใน Aspose.Slides
