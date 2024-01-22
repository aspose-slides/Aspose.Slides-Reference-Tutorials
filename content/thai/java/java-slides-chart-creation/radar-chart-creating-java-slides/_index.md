---
title: การสร้างแผนภูมิเรดาร์ใน Java Slides
linktitle: การสร้างแผนภูมิเรดาร์ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างแผนภูมิเรดาร์ในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java API
type: docs
weight: 10
url: /th/java/chart-creation/radar-chart-creating-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการสร้างแผนภูมิเรดาร์ใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดกระบวนการสร้างแผนภูมิเรดาร์โดยใช้ Aspose.Slides สำหรับ Java API แผนภูมิเรดาร์มีประโยชน์ในการแสดงภาพข้อมูลในรูปแบบวงกลม ทำให้เปรียบเทียบชุดข้อมูลหลายชุดได้ง่ายขึ้น เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ด Java

## ข้อกำหนดเบื้องต้น

 ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: การตั้งค่าการนำเสนอ

เริ่มต้นด้วยการตั้งค่างานนำเสนอ PowerPoint ใหม่และเพิ่มสไลด์ลงไป

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิเรดาร์

ต่อไป เราจะเพิ่มแผนภูมิเรดาร์ลงในสไลด์ เราจะระบุตำแหน่งและขนาดของแผนภูมิ

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## ขั้นตอนที่ 3: การตั้งค่าข้อมูลแผนภูมิ

ตอนนี้เราจะตั้งค่าข้อมูลแผนภูมิ ซึ่งเกี่ยวข้องกับการสร้างสมุดงานข้อมูล การเพิ่มประเภท และการเพิ่มชุดข้อมูล

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// ตั้งชื่อแผนภูมิ
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// ลบซีรี่ส์และหมวดหมู่ที่สร้างโดยค่าเริ่มต้น
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// การเพิ่มหมวดหมู่ใหม่
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// กำลังเพิ่มซีรีส์ใหม่
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## ขั้นตอนที่ 4: การเติมข้อมูลซีรี่ส์

ตอนนี้ เราจะเติมข้อมูลชุดข้อมูลสำหรับแผนภูมิเรดาร์ของเรา

```java
// เติมข้อมูลชุดข้อมูลสำหรับชุดที่ 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// ตั้งค่าสีซีรีส์
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// เติมข้อมูลชุดข้อมูลสำหรับชุดที่ 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// ตั้งค่าสีซีรีส์
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## ขั้นตอนที่ 5: การปรับแต่งแกนและตำนาน

มาปรับแต่งแกนและคำอธิบายสำหรับแผนภูมิเรดาร์ของเรากัน

```java
// กำหนดตำแหน่งคำอธิบาย
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// การตั้งค่าคุณสมบัติข้อความแกนหมวดหมู่
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// การตั้งค่าคุณสมบัติข้อความตำนาน
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// การตั้งค่าคุณสมบัติข้อความแกนค่า
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// การตั้งค่ารูปแบบตัวเลขแกนค่า
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// การตั้งค่าแผนภูมิมูลค่าหน่วยหลัก
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้าย บันทึกการนำเสนอที่สร้างขึ้นด้วยแผนภูมิเรดาร์

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณสร้างแผนภูมิเรดาร์ในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java ตอนนี้คุณสามารถปรับแต่งตัวอย่างนี้เพิ่มเติมเพื่อให้เหมาะกับความต้องการเฉพาะของคุณได้

## กรอกซอร์สโค้ดสำหรับการสร้างแผนภูมิเรดาร์ใน Java Slides

```java
String outPath = RunExamples.getOutPath() + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// เข้าถึงสไลด์แรก
	ISlide sld = pres.getSlides().get_Item(0);
	// เพิ่มแผนภูมิเรดาร์
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
	int defaultWorksheetIndex = 0;
	// รับข้อมูลแผนภูมิแผ่นงาน
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// ตั้งชื่อแผนภูมิ
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// ลบซีรี่ส์และหมวดหมู่ที่สร้างโดยค่าเริ่มต้น
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// การเพิ่มหมวดหมู่ใหม่
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// กำลังเพิ่มซีรีส์ใหม่
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// กำลังเติมข้อมูลซีรีส์
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// ตั้งค่าสีซีรีส์
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// กำลังเติมข้อมูลชุดอื่น
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// ตั้งค่าสีซีรีส์
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// กำหนดตำแหน่งคำอธิบาย
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// การตั้งค่าคุณสมบัติข้อความแกนหมวดหมู่
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// การตั้งค่าคุณสมบัติข้อความตำนาน
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// การตั้งค่าคุณสมบัติข้อความแกนค่า
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// การตั้งค่ารูปแบบตัวเลขแกนค่า
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// การตั้งค่าแผนภูมิมูลค่าหน่วยหลัก
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// บันทึกการนำเสนอที่สร้างขึ้น
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างแผนภูมิเรดาร์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถใช้แนวคิดเหล่านี้เพื่อแสดงภาพและนำเสนอข้อมูลของคุณอย่างมีประสิทธิภาพในแอปพลิเคชัน Java ของคุณ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนชื่อแผนภูมิได้อย่างไร?

หากต้องการเปลี่ยนชื่อแผนภูมิ ให้แก้ไขบรรทัดต่อไปนี้:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### ฉันสามารถเพิ่มชุดข้อมูลเพิ่มเติมลงในแผนภูมิเรดาร์ได้หรือไม่

ได้ คุณสามารถเพิ่มชุดข้อมูลเพิ่มเติมได้โดยทำตามขั้นตอนใน "ขั้นตอนที่ 3" และ "ขั้นตอนที่ 4" สำหรับแต่ละชุดข้อมูลเพิ่มเติมที่คุณต้องการรวม

### ฉันจะปรับแต่งสีแผนภูมิได้อย่างไร

 คุณสามารถปรับแต่งสีของซีรี่ส์ได้โดยแก้ไขเส้นที่กำหนด`SolidFillColor` คุณสมบัติของแต่ละซีรีย์ ตัวอย่างเช่น:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### ฉันจะเปลี่ยนป้ายกำกับแกนและการจัดรูปแบบได้อย่างไร

โปรดดู "ขั้นตอนที่ 5" เพื่อปรับแต่งป้ายกำกับแกนและการจัดรูปแบบ รวมถึงขนาดตัวอักษรและสี

### ฉันจะบันทึกแผนภูมิเป็นรูปแบบไฟล์อื่นได้อย่างไร

 คุณสามารถเปลี่ยนรูปแบบเอาต์พุตได้โดยแก้ไขนามสกุลไฟล์ในรูปแบบ`outPath` ตัวแปรและการใช้ให้เหมาะสม`SaveFormat` . ตัวอย่างเช่น หากต้องการบันทึกเป็น PDF ให้ใช้`SaveFormat.Pdf`.