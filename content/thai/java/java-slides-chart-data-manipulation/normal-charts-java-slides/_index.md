---
title: แผนภูมิปกติใน Java Slides
linktitle: แผนภูมิปกติใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: สร้างแผนภูมิปกติใน Java Slides ด้วย Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนและซอร์สโค้ดสำหรับการสร้าง ปรับแต่ง และบันทึกแผนภูมิในงานนำเสนอ PowerPoint
type: docs
weight: 21
url: /th/java/chart-data-manipulation/normal-charts-java-slides/
---

## รู้เบื้องต้นเกี่ยวกับแผนภูมิปกติใน Java Slides

ในบทช่วยสอนนี้ เราจะอธิบายขั้นตอนการสร้างแผนภูมิปกติใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API เราจะใช้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ดเพื่อสาธิตวิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มในงานนำเสนอ PowerPoint

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. ติดตั้ง Aspose.Slides สำหรับ Java API แล้ว
2. ตั้งค่าสภาพแวดล้อมการพัฒนา Java
3. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ตรวจสอบให้แน่ใจว่าคุณมีไดเรกทอรีสำหรับโครงการของคุณ เรียกมันว่า "Your Document Directory" ตามที่กล่าวไว้ในโค้ด คุณสามารถแทนที่สิ่งนี้ด้วยเส้นทางจริงไปยังไดเรกทอรีโครงการของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## ขั้นตอนที่ 2: การสร้างงานนำเสนอ

ตอนนี้ เรามาสร้างงานนำเสนอ PowerPoint และเข้าถึงสไลด์แรกกันดีกว่า

```java
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
Presentation pres = new Presentation();
// เข้าถึงสไลด์แรก
ISlide sld = pres.getSlides().get_Item(0);
```

## ขั้นตอนที่ 3: การเพิ่มแผนภูมิ

เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์และตั้งชื่อ

```java
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// การตั้งชื่อแผนภูมิ
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## ขั้นตอนที่ 4: การตั้งค่าข้อมูลแผนภูมิ

ต่อไป เราจะตั้งค่าข้อมูลแผนภูมิโดยกำหนดซีรี่ส์และหมวดหมู่

```java
// ตั้งค่าชุดแรกเพื่อแสดงค่า
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;

//รับแผ่นงานข้อมูลแผนภูมิ
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

## ขั้นตอนที่ 5: การเติมข้อมูลซีรี่ส์

ตอนนี้ เรามาเติมจุดข้อมูลชุดข้อมูลสำหรับแผนภูมิกัน

```java
// ใช้แผนภูมิชุดแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// การตั้งค่าสีเติมสำหรับซีรี่ส์
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// ใช้แผนภูมิชุดที่สอง
series = chart.getChartData().getSeries().get_Item(1);

// กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// การตั้งค่าสีเติมสำหรับซีรี่ส์
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## ขั้นตอนที่ 6: การปรับแต่งฉลาก

มาปรับแต่งป้ายกำกับข้อมูลสำหรับชุดแผนภูมิกัน

```java
// ป้ายกำกับแรกจะแสดงชื่อหมวดหมู่
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// แสดงค่าสำหรับป้ายกำกับที่สามพร้อมชื่อซีรีส์และตัวคั่น
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

สุดท้าย บันทึกงานนำเสนอพร้อมแผนภูมิลงในไดเร็กทอรีโครงการของคุณ

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งแผนภูมินี้เพิ่มเติมได้ตามความต้องการของคุณ

## กรอกซอร์สโค้ดสำหรับแผนภูมิปกติใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
Presentation pres = new Presentation();
// เข้าถึงสไลด์แรก
ISlide sld = pres.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// การตั้งชื่อแผนภูมิ
// Chart.getChartTitle().getTextFrameForOverriding().setText("ชื่อตัวอย่าง");
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// ตั้งค่าชุดแรกเพื่อแสดงค่า
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
//รับแผ่นงานข้อมูลแผนภูมิ
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
// กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// การตั้งค่าสีเติมสำหรับซีรี่ส์
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// ใช้แผนภูมิชุดที่สอง
series = chart.getChartData().getSeries().get_Item(1);
// กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// การตั้งค่าสีเติมสำหรับซีรี่ส์
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
//ป้ายกำกับแรกจะแสดงชื่อหมวดหมู่
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// แสดงค่าสำหรับป้ายกำกับที่สาม
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// บันทึกการนำเสนอด้วยแผนภูมิ
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างแผนภูมิปกติใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API เราได้อธิบายคำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ในงานนำเสนอ PowerPoint

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

 หากต้องการเปลี่ยนประเภทแผนภูมิ ให้แก้ไข`ChartType` พารามิเตอร์เมื่อเพิ่มแผนภูมิโดยใช้`sld.getShapes().addChart()`. คุณสามารถเลือกจากแผนภูมิประเภทต่างๆ ที่มีอยู่ใน Aspose.Slides

### ฉันสามารถเปลี่ยนสีของชุดแผนภูมิได้หรือไม่

 ได้ คุณสามารถเปลี่ยนสีของชุดแผนภูมิได้โดยการตั้งค่าสีเติมสำหรับแต่ละชุดที่ใช้`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### ฉันจะเพิ่มหมวดหมู่หรือซีรีส์ลงในแผนภูมิได้อย่างไร

 คุณสามารถเพิ่มหมวดหมู่หรือชุดข้อมูลลงในแผนภูมิได้โดยการเพิ่มจุดข้อมูลและป้ายกำกับใหม่โดยใช้`chart.getChartData().getCategories().add()` และ`chart.getChartData().getSeries().add()` วิธีการ

### ฉันจะปรับแต่งชื่อแผนภูมิเพิ่มเติมได้อย่างไร

 คุณสามารถปรับแต่งชื่อแผนภูมิเพิ่มเติมได้โดยการแก้ไขคุณสมบัติของ`chart.getChartTitle()` เช่น การจัดตำแหน่งข้อความ ขนาดตัวอักษร และสี

### ฉันจะบันทึกแผนภูมิเป็นรูปแบบไฟล์อื่นได้อย่างไร

หากต้องการบันทึกแผนภูมิเป็นรูปแบบไฟล์อื่น ให้เปลี่ยน`SaveFormat` พารามิเตอร์ใน`pres.save()` วิธีการในรูปแบบที่ต้องการ (เช่น PDF, PNG, JPEG)