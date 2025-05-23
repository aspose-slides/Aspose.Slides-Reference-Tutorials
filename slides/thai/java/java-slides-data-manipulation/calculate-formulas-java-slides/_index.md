---
"description": "เรียนรู้วิธีคำนวณสูตรใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการนำเสนอ PowerPoint แบบไดนามิก"
"linktitle": "คำนวณสูตรในสไลด์ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "คำนวณสูตรในสไลด์ Java"
"url": "/th/java/data-manipulation/calculate-formulas-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# คำนวณสูตรในสไลด์ Java


## บทนำเกี่ยวกับการคำนวณสูตรในสไลด์ Java โดยใช้ Aspose.Slides

ในคู่มือนี้ เราจะสาธิตวิธีการคำนวณสูตรใน Java Slides โดยใช้ Aspose.Slides for Java API Aspose.Slides เป็นไลบรารีที่มีประสิทธิภาพสำหรับการทำงานกับการนำเสนอ PowerPoint และมีคุณสมบัติในการจัดการแผนภูมิและคำนวณสูตรภายในสไลด์

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- สภาพแวดล้อมการพัฒนา Java
- Aspose.Slides สำหรับไลบรารี Java (สามารถดาวน์โหลดได้จาก [ที่นี่](https://releases.aspose.com/slides/java/)
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

ขั้นแรก ให้สร้างงานนำเสนอ PowerPoint ใหม่และเพิ่มสไลด์เข้าไป เราจะใช้สไลด์เดียวในตัวอย่างนี้

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์

ตอนนี้เรามาเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ลงในสไลด์กัน เราจะใช้แผนภูมินี้เพื่อแสดงการคำนวณสูตร

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## ขั้นตอนที่ 3: ตั้งค่าสูตรและค่า

ต่อไปเราจะกำหนดสูตรและค่าสำหรับเซลล์ข้อมูลแผนภูมิโดยใช้ Aspose.Slides API เราจะคำนวณสูตรสำหรับเซลล์เหล่านี้

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

สุดท้ายนี้ ให้บันทึกการนำเสนอที่แก้ไขแล้วโดยใช้สูตรที่คำนวณแล้ว

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับการคำนวณสูตรในสไลด์ Java

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
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

ในคู่มือนี้ เราได้เรียนรู้วิธีการคำนวณสูตรใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java เราสร้างงานนำเสนอใหม่ เพิ่มแผนภูมิ ตั้งค่าสูตรและค่าสำหรับเซลล์ข้อมูลแผนภูมิ และบันทึกงานนำเสนอด้วยสูตรที่คำนวณแล้ว

## คำถามที่พบบ่อย

### ฉันจะตั้งค่าสูตรให้กับเซลล์ข้อมูลแผนภูมิได้อย่างไร

คุณสามารถตั้งค่าสูตรสำหรับเซลล์ข้อมูลแผนภูมิได้โดยใช้ `setFormula` วิธีการของ `IChartDataCell` ใน Aspose.Slides

### ฉันจะตั้งค่าให้กับเซลล์ข้อมูลแผนภูมิได้อย่างไร

คุณสามารถตั้งค่าค่าสำหรับเซลล์ข้อมูลแผนภูมิได้โดยใช้ `setValue` วิธีการของ `IChartDataCell` ใน Aspose.Slides

### ฉันจะคำนวณสูตรในสมุดงานได้อย่างไร?

คุณสามารถคำนวณสูตรในสมุดงานได้โดยใช้ `calculateFormulas` วิธีการของ `IChartDataWorkbook` ใน Aspose.Slides


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}