---
title: สีชุดแผนภูมิอัตโนมัติใน Java Slides
linktitle: สีชุดแผนภูมิอัตโนมัติใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างแผนภูมิแบบไดนามิกด้วยชุดสีอัตโนมัติในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงการแสดงภาพข้อมูลของคุณได้อย่างง่ายดาย
type: docs
weight: 14
url: /th/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับสีชุดแผนภูมิอัตโนมัติใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะสำรวจวิธีสร้างงานนำเสนอ PowerPoint ด้วยแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java และตั้งค่าสีเติมอัตโนมัติสำหรับชุดแผนภูมิ การเติมสีอัตโนมัติสามารถทำให้แผนภูมิของคุณดูน่าดึงดูดยิ่งขึ้น และช่วยคุณประหยัดเวลาโดยให้ไลบรารีเลือกสีให้กับคุณ

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides for Java ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

ขั้นแรก เราจะสร้างงานนำเสนอ PowerPoint ใหม่และเพิ่มสไลด์ลงไป

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์

ต่อไป เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์ นอกจากนี้เราจะตั้งค่าชุดแรกเพื่อแสดงค่าด้วย

```java
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// ตั้งค่าชุดแรกเพื่อแสดงค่า
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## ขั้นตอนที่ 3: เติมข้อมูลแผนภูมิ

ตอนนี้ เราจะเติมข้อมูลลงในแผนภูมิ เราจะเริ่มต้นด้วยการลบซีรี่ส์และหมวดหมู่ที่สร้างตามค่าเริ่มต้น จากนั้นเพิ่มซีรีส์และหมวดหมู่ใหม่

```java
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// ลบซีรี่ส์และหมวดหมู่ที่สร้างโดยค่าเริ่มต้น
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// กำลังเพิ่มซีรีส์ใหม่
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// การเพิ่มหมวดหมู่ใหม่
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## ขั้นตอนที่ 4: เติมข้อมูลซีรี่ส์

เราจะเติมข้อมูลซีรีส์สำหรับทั้งซีรีส์ 1 และซีรีส์ 2

```java
// ใช้แผนภูมิชุดแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// ใช้แผนภูมิชุดที่สอง
series = chart.getChartData().getSeries().get_Item(1);
//กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## ขั้นตอนที่ 5: ตั้งค่าสีเติมอัตโนมัติสำหรับซีรี่ส์

ตอนนี้ มาตั้งค่าสีเติมอัตโนมัติสำหรับชุดแผนภูมิกัน จะทำให้ห้องสมุดเลือกสีให้เราได้

```java
// การตั้งค่าสีเติมอัตโนมัติสำหรับซีรี่ส์
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้ายนี้ เราจะบันทึกงานนำเสนอพร้อมแผนภูมิลงในไฟล์ PowerPoint

```java
// บันทึกการนำเสนอด้วยแผนภูมิ
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับสีชุดแผนภูมิอัตโนมัติใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
try
{
	// เข้าถึงสไลด์แรก
	ISlide slide = presentation.getSlides().get_Item(0);
	// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// ตั้งค่าชุดแรกเพื่อแสดงค่า
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
	int defaultWorksheetIndex = 0;
	// รับแผ่นงานข้อมูลแผนภูมิ
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// ลบซีรี่ส์และหมวดหมู่ที่สร้างโดยค่าเริ่มต้น
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// กำลังเพิ่มซีรีส์ใหม่
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// การเพิ่มหมวดหมู่ใหม่
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// ใช้แผนภูมิชุดแรก
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	//กำลังเติมข้อมูลซีรีส์
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// การตั้งค่าสีเติมอัตโนมัติสำหรับซีรี่ส์
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// ใช้แผนภูมิชุดที่สอง
	series = chart.getChartData().getSeries().get_Item(1);
	//กำลังเติมข้อมูลซีรีส์
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	//การตั้งค่าสีเติมสำหรับซีรี่ส์
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// บันทึกการนำเสนอด้วยแผนภูมิ
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างงานนำเสนอ PowerPoint ด้วยแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java และตั้งค่าสีเติมอัตโนมัติสำหรับชุดแผนภูมิ สีอัตโนมัติสามารถเพิ่มความน่าสนใจให้กับแผนภูมิของคุณ และทำให้งานนำเสนอของคุณน่าสนใจยิ่งขึ้น คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมได้ตามความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะตั้งค่าสีเติมอัตโนมัติสำหรับชุดแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการตั้งค่าสีเติมอัตโนมัติสำหรับชุดแผนภูมิใน Aspose.Slides สำหรับ Java ให้ใช้โค้ดต่อไปนี้:

```java
// การตั้งค่าสีเติมอัตโนมัติสำหรับซีรี่ส์
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

รหัสนี้จะช่วยให้ไลบรารีเลือกสีสำหรับชุดแผนภูมิโดยอัตโนมัติ

### ฉันสามารถปรับแต่งสีแผนภูมิได้ตามต้องการหรือไม่

 ใช่ คุณสามารถปรับแต่งสีแผนภูมิได้ตามต้องการ ในตัวอย่างที่ให้ไว้ เราใช้สีเติมอัตโนมัติ แต่คุณสามารถตั้งค่าสีเฉพาะได้โดยการแก้ไข`FillType` และ`SolidFillColor` คุณสมบัติของรูปแบบของซีรีส์

### ฉันจะเพิ่มซีรี่ส์หรือหมวดหมู่เพิ่มเติมลงในแผนภูมิได้อย่างไร

หากต้องการเพิ่มซีรี่ส์หรือหมวดหมู่เพิ่มเติมลงในแผนภูมิ ให้ใช้`getSeries()` และ`getCategories()` วิธีการของแผนภูมิ`ChartData` วัตถุ. คุณสามารถเพิ่มซีรี่ส์และหมวดหมู่ใหม่ได้โดยระบุข้อมูลและป้ายกำกับ

### เป็นไปได้ไหมที่จะจัดรูปแบบแผนภูมิและป้ายกำกับเพิ่มเติม

ได้ คุณสามารถจัดรูปแบบแผนภูมิ ชุดข้อมูล และป้ายกำกับเพิ่มเติมได้ตามต้องการ Aspose.Slides for Java มีตัวเลือกการจัดรูปแบบที่หลากหลายสำหรับแผนภูมิ รวมถึงแบบอักษร สี สไตล์ และอื่นๆ คุณสามารถสำรวจเอกสารประกอบเพื่อดูรายละเอียดเพิ่มเติมเกี่ยวกับตัวเลือกการจัดรูปแบบได้

### ฉันจะหาข้อมูลเพิ่มเติมเกี่ยวกับการทำงานกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 สำหรับข้อมูลเพิ่มเติมและเอกสารประกอบโดยละเอียดเกี่ยวกับ Aspose.Slides สำหรับ Java คุณสามารถไปที่เอกสารอ้างอิง[ที่นี่](https://reference.aspose.com/slides/java/).