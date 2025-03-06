---
title: แผนภูมิแผนที่ใน Java Slides
linktitle: แผนภูมิแผนที่ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: สร้างแผนภูมิแผนที่อันน่าทึ่งในงานนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนและซอร์สโค้ดสำหรับนักพัฒนา Java
weight: 15
url: /th/java/chart-elements/map-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## รู้เบื้องต้นเกี่ยวกับแผนภูมิแผนที่ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างแผนภูมิแผนที่ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แผนภูมิแผนที่เป็นวิธีที่ดีในการแสดงภาพข้อมูลทางภูมิศาสตร์ในงานนำเสนอของคุณ

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าโปรเจ็กต์ Java ของคุณและเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงใน classpath ของโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: สร้างงานนำเสนอ PowerPoint

ขั้นแรก มาสร้างงานนำเสนอ PowerPoint ใหม่กัน

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 3: เพิ่มแผนภูมิแผนที่

ตอนนี้ เราจะเพิ่มแผนภูมิแผนที่ลงในการนำเสนอ

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## ขั้นตอนที่ 4: เพิ่มข้อมูลลงในแผนภูมิแผนที่

มาเพิ่มข้อมูลบางส่วนลงในแผนภูมิแผนที่กัน เราจะสร้างซีรีส์และเพิ่มจุดข้อมูลลงไป

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## ขั้นตอนที่ 5: เพิ่มหมวดหมู่

เราจำเป็นต้องเพิ่มหมวดหมู่ลงในแผนภูมิแผนที่ซึ่งแสดงถึงภูมิภาคทางภูมิศาสตร์ต่างๆ

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## ขั้นตอนที่ 6: ปรับแต่งจุดข้อมูล

คุณสามารถปรับแต่งจุดข้อมูลแต่ละจุดได้ ในตัวอย่างนี้ เราเปลี่ยนสีและค่าของจุดข้อมูลเฉพาะ

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอด้วยแผนภูมิแผนที่

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณได้สร้างแผนภูมิแผนที่ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมและสำรวจคุณสมบัติอื่น ๆ ที่นำเสนอโดย Aspose.Slides เพื่อปรับปรุงการนำเสนอของคุณ

## กรอกซอร์สโค้ดสำหรับแผนภูมิแผนที่ใน Java Slides

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//สร้างแผนภูมิเปล่า
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//เพิ่มซีรี่ส์และจุดข้อมูลสองสามจุด
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//เพิ่มหมวดหมู่
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//เปลี่ยนค่าจุดข้อมูล
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//กำหนดลักษณะที่ปรากฏของจุดข้อมูล
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้อธิบายขั้นตอนการสร้างแผนภูมิแผนที่ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แล้ว แผนภูมิแผนที่เป็นวิธีที่มีประสิทธิภาพในการแสดงภาพข้อมูลทางภูมิศาสตร์ ทำให้การนำเสนอของคุณน่าสนใจและให้ข้อมูลมากขึ้น มาสรุปขั้นตอนสำคัญกัน:

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิแผนที่ได้อย่างไร

 คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแทนที่`ChartType.Map` ด้วยประเภทแผนภูมิที่ต้องการเมื่อสร้างแผนภูมิในขั้นตอนที่ 3

### ฉันจะปรับแต่งรูปลักษณ์ของแผนภูมิแผนที่ได้อย่างไร

 คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิได้โดยการแก้ไขคุณสมบัติของ`dataPoint` วัตถุในขั้นตอนที่ 6 คุณสามารถเปลี่ยนสี ค่า และอื่นๆ ได้

### ฉันสามารถเพิ่มจุดข้อมูลและหมวดหมู่เพิ่มเติมได้หรือไม่

 ได้ คุณสามารถเพิ่มจุดข้อมูลและหมวดหมู่ได้มากเท่าที่ต้องการ เพียงใช้`series.getDataPoints().addDataPointForMapSeries()` และ`chart.getChartData().getCategories().add()` วิธีการเพิ่ม

### ฉันจะรวม Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ของฉันได้อย่างไร

 ดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/) และเพิ่มลงใน classpath ของโครงการของคุณ
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
