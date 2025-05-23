---
"description": "เรียนรู้วิธีตั้งค่าสูตรเซลล์ข้อมูลแผนภูมิในงานนำเสนอ PowerPoint ของ Java โดยใช้ Aspose.Slides สำหรับ Java สร้างแผนภูมิแบบไดนามิกด้วยสูตร"
"linktitle": "สูตรเซลล์ข้อมูลแผนภูมิในสไลด์ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "สูตรเซลล์ข้อมูลแผนภูมิในสไลด์ Java"
"url": "/th/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# สูตรเซลล์ข้อมูลแผนภูมิในสไลด์ Java


## บทนำสู่สูตรเซลล์ข้อมูลแผนภูมิใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะมาสำรวจวิธีการทำงานกับสูตรเซลล์ข้อมูลแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java ด้วย Aspose.Slides คุณสามารถสร้างและจัดการแผนภูมิในงานนำเสนอ PowerPoint รวมถึงการตั้งค่าสูตรสำหรับเซลล์ข้อมูล

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าได้ติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างการนำเสนอ PowerPoint

ขั้นแรกให้สร้างการนำเสนอ PowerPoint ใหม่และเพิ่มแผนภูมิลงไป

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // เพิ่มแผนภูมิลงในสไลด์แรก
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // รับสมุดงานสำหรับข้อมูลแผนภูมิ
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // ดำเนินการต่อด้วยการดำเนินการเซลล์ข้อมูล
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

ตอนนี้เรามาตั้งค่าสูตรสำหรับเซลล์ข้อมูลเฉพาะในแผนภูมิกัน ในตัวอย่างนี้ เราจะตั้งค่าสูตรสำหรับเซลล์ที่แตกต่างกันสองเซลล์

### เซลล์ 1: ใช้สัญลักษณ์ A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

ในโค้ดด้านบน เราตั้งค่าสูตรสำหรับเซลล์ B2 โดยใช้รูปแบบ A1 สูตรจะคำนวณผลรวมของเซลล์ F2 ถึง H5 แล้วบวก 1 ลงในผลลัพธ์

### เซลล์ 2: การใช้สัญลักษณ์ R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

ที่นี่ เรากำหนดสูตรสำหรับเซลล์ C2 โดยใช้รูปแบบ R1C1 สูตรจะคำนวณค่าสูงสุดภายในช่วง R2C6 ถึง R5C8 จากนั้นหารค่าด้วย 3

## ขั้นตอนที่ 3: คำนวณสูตร

หลังจากตั้งสูตรแล้ว จำเป็นต้องคำนวณโดยใช้โค้ดต่อไปนี้:

```java
workbook.calculateFormulas();
```

ขั้นตอนนี้จะช่วยให้แน่ใจว่าแผนภูมิสะท้อนค่าที่อัปเดตตามสูตร

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้ายให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับสูตรเซลล์ข้อมูลแผนภูมิในสไลด์ Java

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

ในบทช่วยสอนนี้ เราได้ศึกษาวิธีการทำงานกับสูตรเซลล์ข้อมูลแผนภูมิใน Aspose.Slides สำหรับ Java เราได้ครอบคลุมถึงการสร้างงานนำเสนอ PowerPoint การเพิ่มแผนภูมิ การกำหนดสูตรสำหรับเซลล์ข้อมูล การคำนวณสูตร และการบันทึกงานนำเสนอ ตอนนี้คุณสามารถใช้ประโยชน์จากความสามารถเหล่านี้เพื่อสร้างแผนภูมิแบบไดนามิกและตามข้อมูลในงานนำเสนอของคุณ

## คำถามที่พบบ่อย

### ฉันจะเพิ่มแผนภูมิลงในสไลด์ที่ต้องการได้อย่างไร

หากต้องการเพิ่มแผนภูมิลงในสไลด์เฉพาะ คุณสามารถใช้ `getSlides().get_Item(slideIndex)` วิธีการเข้าถึงสไลด์ที่ต้องการแล้วใช้ `addChart` วิธีการเพิ่มแผนภูมิ

### ฉันสามารถใช้สูตรประเภทต่างๆ ในเซลล์ข้อมูลได้หรือไม่

ใช่ คุณสามารถใช้สูตรหลากหลายประเภท รวมถึงการดำเนินการทางคณิตศาสตร์ ฟังก์ชัน และการอ้างอิงไปยังเซลล์อื่น ๆ ในสูตรเซลล์ข้อมูลได้

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยใช้ `setChartType` วิธีการบน `IChart` วัตถุและระบุสิ่งที่ต้องการ `ChartType`-

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}