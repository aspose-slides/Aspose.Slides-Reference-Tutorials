---
title: แผนภูมิซ่านใน Java Slides
linktitle: แผนภูมิซ่านใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: สร้างแผนภูมิ Sunburst อันน่าทึ่งใน Java Slides ด้วย Aspose.Slides เรียนรู้การสร้างแผนภูมิทีละขั้นตอนและการจัดการข้อมูล
weight: 16
url: /th/java/chart-elements/sunburst-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิซ่านใน Java Slides


## รู้เบื้องต้นเกี่ยวกับแผนภูมิ Sunburst ใน Java Slides ด้วย Aspose.Slides

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีสร้างแผนภูมิ Sunburst ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java API แผนภูมิ Sunburst คือแผนภูมิรัศมีที่ใช้เพื่อแสดงข้อมูลแบบลำดับชั้น เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ด

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ขั้นแรก นำเข้าไลบรารีที่จำเป็นเพื่อทำงานกับ Aspose.Slides และสร้างแผนภูมิ Sunburst ในแอปพลิเคชัน Java ของคุณ

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ

เริ่มต้นงานนำเสนอ PowerPoint และระบุไดเร็กทอรีที่จะบันทึกไฟล์งานนำเสนอของคุณ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ขั้นตอนที่ 3: สร้างแผนภูมิซ่าน

สร้างแผนภูมิ Sunburst บนสไลด์ เราระบุตำแหน่ง (X, Y) และขนาด (ความกว้าง ความสูง) ของแผนภูมิ

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## ขั้นตอนที่ 4: เตรียมข้อมูลแผนภูมิ

ล้างหมวดหมู่และข้อมูลชุดข้อมูลที่มีอยู่ออกจากแผนภูมิ และสร้างสมุดงานข้อมูลสำหรับแผนภูมิ

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## ขั้นตอนที่ 5: กำหนดลำดับชั้นของแผนภูมิ

กำหนดโครงสร้างลำดับชั้นของแผนภูมิ Sunburst คุณสามารถเพิ่มกิ่ง ก้าน และใบเป็นหมวดหมู่ได้

```java
// สาขา 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// สาขา 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## ขั้นตอนที่ 6: เพิ่มข้อมูลลงในแผนภูมิ

เพิ่มจุดข้อมูลลงในชุดแผนภูมิ Sunburst

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

สุดท้าย บันทึกงานนำเสนอด้วยแผนภูมิ Sunburst

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับแผนภูมิ Sunburst ใน Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//สาขา 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//สาขา 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างแผนภูมิ Sunburst ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java API คุณได้เห็นวิธีการเริ่มต้นงานนำเสนอ สร้างแผนภูมิ กำหนดลำดับชั้นของแผนภูมิ เพิ่มจุดข้อมูล และบันทึกงานนำเสนอ ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อสร้างแผนภูมิ Sunburst แบบโต้ตอบและให้ข้อมูลในแอปพลิเคชัน Java ของคุณ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งรูปลักษณ์ของแผนภูมิ Sunburst ได้อย่างไร

คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิ Sunburst ได้โดยการแก้ไขคุณสมบัติ เช่น สี ป้าย และสไตล์ โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับตัวเลือกการปรับแต่งโดยละเอียด

### ฉันสามารถเพิ่มจุดข้อมูลลงในแผนภูมิได้หรือไม่

 ใช่ คุณสามารถเพิ่มจุดข้อมูลลงในแผนภูมิได้โดยใช้`series.getDataPoints().addDataPointForSunburstSeries()` วิธีการสำหรับแต่ละจุดข้อมูลที่คุณต้องการรวม

### ฉันจะเพิ่มคำแนะนำเครื่องมือลงในแผนภูมิ Sunburst ได้อย่างไร

หากต้องการเพิ่มคำแนะนำเครื่องมือลงในแผนภูมิ Sunburst คุณสามารถตั้งค่ารูปแบบป้ายกำกับข้อมูลเพื่อแสดงข้อมูลเพิ่มเติม เช่น ค่าหรือคำอธิบาย เมื่อวางเมาส์เหนือส่วนของแผนภูมิ

### เป็นไปได้ไหมที่จะสร้างแผนภูมิ Sunburst แบบโต้ตอบพร้อมไฮเปอร์ลิงก์

ได้ คุณสามารถสร้างแผนภูมิ Sunburst แบบโต้ตอบด้วยไฮเปอร์ลิงก์ได้โดยการเพิ่มไฮเปอร์ลิงก์ไปยังองค์ประกอบหรือส่วนแผนภูมิเฉพาะ โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับรายละเอียดเกี่ยวกับการเพิ่มไฮเปอร์ลิงก์
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
