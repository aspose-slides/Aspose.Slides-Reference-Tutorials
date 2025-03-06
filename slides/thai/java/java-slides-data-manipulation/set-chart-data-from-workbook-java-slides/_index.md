---
title: ตั้งค่าข้อมูลแผนภูมิจากสมุดงานใน Java Slides
linktitle: ตั้งค่าข้อมูลแผนภูมิจากสมุดงานใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการตั้งค่าข้อมูลแผนภูมิจากสมุดงาน Excel ใน Java Slides โดยใช้ Aspose.Slides คำแนะนำทีละขั้นตอนพร้อมตัวอย่างโค้ดสำหรับการนำเสนอแบบไดนามิก
weight: 15
url: /th/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่าข้อมูลแผนภูมิจากสมุดงานใน Java Slides

Aspose.Slides for Java เป็นไลบรารีอันทรงพลังที่ช่วยให้นักพัฒนาสามารถทำงานกับงานนำเสนอ PowerPoint โดยทางโปรแกรม มีฟีเจอร์มากมายสำหรับการสร้าง จัดการ และจัดการสไลด์ PowerPoint ข้อกำหนดทั่วไปประการหนึ่งเมื่อทำงานกับงานนำเสนอคือการตั้งค่าข้อมูลแผนภูมิแบบไดนามิกจากแหล่งข้อมูลภายนอก เช่น เวิร์กบุ๊ก Excel ในบทช่วยสอนนี้ เราจะสาธิตวิธีการบรรลุเป้าหมายนี้โดยใช้ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกการนำไปใช้งาน ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) บนระบบของคุณ
- เพิ่ม Aspose.Slides สำหรับไลบรารี Java ในโครงการของคุณ
- เวิร์กบุ๊ก Excel ที่มีข้อมูลที่คุณต้องการใช้สำหรับแผนภูมิ

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

เราเริ่มต้นด้วยการสร้างงานนำเสนอ PowerPoint ใหม่โดยใช้ Aspose.Slides สำหรับ Java

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

ต่อไป เราจะเพิ่มแผนภูมิลงในสไลด์ใดสไลด์หนึ่งในงานนำเสนอ ในตัวอย่างนี้ เรากำลังเพิ่มแผนภูมิวงกลม แต่คุณสามารถเลือกประเภทแผนภูมิที่เหมาะกับความต้องการของคุณได้

## ขั้นตอนที่ 3: ล้างข้อมูลแผนภูมิ

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

เราล้างข้อมูลที่มีอยู่ออกจากแผนภูมิเพื่อเตรียมข้อมูลใหม่จากสมุดงาน Excel

## ขั้นตอนที่ 4: โหลดสมุดงาน Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

 เราโหลดเวิร์กบุ๊ก Excel ที่มีข้อมูลที่เราต้องการใช้สำหรับแผนภูมิ แทนที่`"book1.xlsx"` พร้อมเส้นทางไปยังไฟล์ Excel ของคุณ

## ขั้นตอนที่ 5: เขียนเวิร์กบุ๊กสตรีมไปยังข้อมูลแผนภูมิ

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

เราแปลงข้อมูลเวิร์กบุ๊ก Excel ให้เป็นสตรีมและเขียนลงในข้อมูลแผนภูมิ

## ขั้นตอนที่ 6: ตั้งค่าช่วงข้อมูลแผนภูมิ

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

เราระบุช่วงของเซลล์จากสมุดงาน Excel ที่ควรใช้เป็นข้อมูลสำหรับแผนภูมิ ปรับช่วงตามที่จำเป็นสำหรับข้อมูลของคุณ

## ขั้นตอนที่ 7: ปรับแต่งชุดแผนภูมิ

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของชุดแผนภูมิให้ตรงกับความต้องการของคุณได้ ในตัวอย่างนี้ เราเปิดใช้งานสีที่หลากหลายสำหรับชุดแผนภูมิ

## ขั้นตอนที่ 8: บันทึกการนำเสนอ

```java
pres.save(outPath, SaveFormat.Pptx);
```

สุดท้าย เราจะบันทึกการนำเสนอด้วยข้อมูลแผนภูมิที่อัปเดตไปยังเส้นทางเอาต์พุตที่ระบุ

## กรอกซอร์สโค้ดสำหรับตั้งค่าข้อมูลแผนภูมิจากสมุดงานใน Java Slides

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าข้อมูลแผนภูมิจากสมุดงาน Excel ใน Java Slides โดยใช้ Aspose.Slides สำหรับไลบรารี Java ด้วยการทำตามคำแนะนำทีละขั้นตอนและใช้ตัวอย่างซอร์สโค้ดที่ให้มา คุณสามารถรวมข้อมูลแผนภูมิแบบไดนามิกลงในงานนำเสนอ PowerPoint ของคุณได้อย่างง่ายดาย

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของแผนภูมิในงานนำเสนอของฉันได้อย่างไร

คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิได้โดยการแก้ไขคุณสมบัติ เช่น สี แบบอักษร ป้าย และอื่นๆ โปรดดูเอกสารประกอบ Aspose.Slides สำหรับ Java สำหรับข้อมูลโดยละเอียดเกี่ยวกับตัวเลือกการปรับแต่งแผนภูมิ

### ฉันสามารถใช้ข้อมูลจากไฟล์ Excel อื่นสำหรับแผนภูมิได้หรือไม่

ได้ คุณสามารถใช้ข้อมูลจากไฟล์ Excel ใดก็ได้โดยการระบุเส้นทางไฟล์ที่ถูกต้องเมื่อโหลดสมุดงานในโค้ด

### ฉันสามารถสร้างแผนภูมิประเภทอื่นใดด้วย Aspose.Slides สำหรับ Java ได้บ้าง

Aspose.Slides สำหรับ Java รองรับแผนภูมิหลายประเภท รวมถึงแผนภูมิแท่ง แผนภูมิเส้น แผนภูมิกระจาย และอื่นๆ คุณสามารถเลือกประเภทแผนภูมิที่เหมาะสมกับความต้องการในการแสดงข้อมูลของคุณได้มากที่สุด

### เป็นไปได้หรือไม่ที่จะอัปเดตข้อมูลแผนภูมิแบบไดนามิกในการนำเสนอที่กำลังดำเนินอยู่

ใช่ คุณสามารถอัปเดตข้อมูลแผนภูมิแบบไดนามิกในงานนำเสนอได้โดยการปรับเปลี่ยนเวิร์กบุ๊กพื้นฐานแล้วรีเฟรชข้อมูลแผนภูมิ

### ฉันจะหาตัวอย่างและแหล่งข้อมูลเพิ่มเติมสำหรับการทำงานกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 คุณสามารถสำรวจตัวอย่างและแหล่งข้อมูลเพิ่มเติมได้ที่[เว็บไซต์กำหนด](https://www.aspose.com/)- นอกจากนี้ เอกสารประกอบ Aspose.Slides สำหรับ Java ยังให้คำแนะนำที่ครอบคลุมเกี่ยวกับการทำงานกับไลบรารีอีกด้วย
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
