---
title: เอนทิตีแผนภูมิใน Java Slides
linktitle: เอนทิตีแผนภูมิใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการสร้างและปรับแต่งแผนภูมิ Java Slides ด้วย Aspose.Slides ปรับปรุงการนำเสนอของคุณด้วยเอนทิตีแผนภูมิที่มีประสิทธิภาพ
weight: 13
url: /th/java/data-manipulation/chart-entities-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# เอนทิตีแผนภูมิใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับเอนทิตีแผนภูมิใน Java Slides

แผนภูมิเป็นเครื่องมืออันทรงพลังสำหรับการแสดงข้อมูลเป็นภาพในงานนำเสนอ ไม่ว่าคุณกำลังสร้างรายงานทางธุรกิจ การนำเสนอทางวิชาการ หรือเนื้อหารูปแบบอื่นใด แผนภูมิจะช่วยถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ Aspose.Slides สำหรับ Java นำเสนอฟีเจอร์ที่มีประสิทธิภาพสำหรับการทำงานกับแผนภูมิ ทำให้เป็นตัวเลือกที่นักพัฒนา Java เลือกใช้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะดำดิ่งสู่โลกของเอนทิตีแผนภูมิ ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) แล้ว
- Aspose.Slides สำหรับไลบรารี Java ที่ดาวน์โหลดและเพิ่มในโครงการของคุณ
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรม Java

ตอนนี้ เรามาเริ่มต้นสร้างและปรับแต่งแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java กันดีกว่า

## ขั้นตอนที่ 1: การสร้างงานนำเสนอ

ขั้นตอนแรกคือการสร้างงานนำเสนอใหม่ที่คุณจะเพิ่มแผนภูมิของคุณ ต่อไปนี้คือตัวอย่างโค้ดสำหรับสร้างงานนำเสนอ:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิ

เมื่อคุณเตรียมการนำเสนอเรียบร้อยแล้ว ก็ถึงเวลาเพิ่มแผนภูมิ ในตัวอย่างนี้ เราจะเพิ่มแผนภูมิเส้นแบบธรรมดาพร้อมเครื่องหมาย ต่อไปนี้คือวิธีที่คุณสามารถทำได้:

```java
// การเข้าถึงสไลด์แรก
ISlide slide = pres.getSlides().get_Item(0);

// การเพิ่มแผนภูมิตัวอย่าง
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## ขั้นตอนที่ 3: การปรับแต่งชื่อแผนภูมิ

แผนภูมิที่มีการกำหนดชัดเจนควรมีชื่อ มาตั้งชื่อแผนภูมิของเรากันดีกว่า:

```java
// การตั้งชื่อแผนภูมิ
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## ขั้นตอนที่ 4: การจัดรูปแบบเส้นกริด

คุณสามารถจัดรูปแบบเส้นกริดหลักและรองในแผนภูมิของคุณได้ มาตั้งค่าการจัดรูปแบบสำหรับเส้นตารางแกนแนวตั้ง:

```java
// การตั้งค่ารูปแบบเส้นตารางหลักสำหรับแกนค่า
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// การตั้งค่ารูปแบบเส้นกริดรองสำหรับแกนค่า
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## ขั้นตอนที่ 5: การปรับแต่งแกนค่า

คุณสามารถควบคุมรูปแบบตัวเลข ค่าสูงสุด และค่าต่ำสุดของแกนค่าได้ ต่อไปนี้เป็นวิธีปรับแต่ง:

```java
// การตั้งค่ารูปแบบตัวเลขแกนค่า
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// การตั้งค่ากราฟสูงสุดและค่าต่ำสุด
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## ขั้นตอนที่ 6: การเพิ่มชื่อแกนค่า

เพื่อให้แผนภูมิของคุณมีข้อมูลมากขึ้น คุณสามารถเพิ่มชื่อเรื่องให้กับแกนค่าได้:

```java
// การตั้งค่าชื่อแกนค่า
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## ขั้นตอนที่ 7: การจัดรูปแบบแกนหมวดหมู่

แกนหมวดหมู่ ซึ่งโดยทั่วไปจะแสดงถึงหมวดหมู่ข้อมูล ยังสามารถปรับแต่งได้:

```java
// การตั้งค่ารูปแบบเส้นตารางหลักสำหรับแกนหมวดหมู่
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// การตั้งค่ารูปแบบเส้นตารางรองสำหรับแกนประเภท
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## ขั้นตอนที่ 8: การเพิ่มตำนาน

Legends ช่วยอธิบายชุดข้อมูลในแผนภูมิของคุณ มาปรับแต่งตำนานกัน:

```java
// การตั้งค่าคุณสมบัติข้อความตำนาน
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// ตั้งค่าคำอธิบายแผนภูมิการแสดงโดยไม่ทับซ้อนกัน
chart.getLegend().setOverlay(true);
```

## ขั้นตอนที่ 9: บันทึกการนำเสนอ

สุดท้าย บันทึกงานนำเสนอของคุณด้วยแผนภูมิ:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับเอนทิตีแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// กำลังสร้างการนำเสนอ// กำลังสร้างการนำเสนอ
Presentation pres = new Presentation();
try
{
	// การเข้าถึงสไลด์แรก
	ISlide slide = pres.getSlides().get_Item(0);
	// การเพิ่มแผนภูมิตัวอย่าง
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// การตั้งค่าชื่อแผนภูมิ
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// การตั้งค่ารูปแบบเส้นตารางหลักสำหรับแกนค่า
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// การตั้งค่ารูปแบบเส้นกริดรองสำหรับแกนค่า
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// การตั้งค่ารูปแบบตัวเลขแกนค่า
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// การตั้งค่ากราฟสูงสุดและค่าต่ำสุด
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// การตั้งค่าคุณสมบัติข้อความแกนค่า
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// การตั้งค่าชื่อแกนค่า
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// การตั้งค่ารูปแบบเส้นแกนค่า : ตอนนี้เลิกใช้แล้ว
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// การตั้งค่ารูปแบบเส้นตารางหลักสำหรับแกนหมวดหมู่
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// การตั้งค่ารูปแบบเส้นตารางรองสำหรับแกนประเภท
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// การตั้งค่าคุณสมบัติข้อความแกนหมวดหมู่
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// การตั้งค่าหัวข้อหมวดหมู่
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// การตั้งค่าตำแหน่งฉลากแกนหมวดหมู่
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// การตั้งค่ามุมการหมุนของฉลากแกนหมวดหมู่
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// การตั้งค่าคุณสมบัติข้อความตำนาน
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// ตั้งค่าคำอธิบายแผนภูมิการแสดงโดยไม่ทับซ้อนกัน
	chart.getLegend().setOverlay(true);
	// การพล็อตอนุกรมแรกบนแกนค่าทุติยภูมิ
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = จริง;
	// การตั้งค่าแผนภูมิสีผนังด้านหลัง
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	//การตั้งค่าสีพื้นที่พล็อต
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// บันทึกการนำเสนอ
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทความนี้ เราได้สำรวจโลกของเอนทิตีแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณได้เรียนรู้วิธีสร้าง ปรับแต่ง และจัดการแผนภูมิเพื่อปรับปรุงการนำเสนอของคุณ แผนภูมิไม่เพียงแต่ทำให้ข้อมูลของคุณดูน่าดึงดูด แต่ยังช่วยให้ผู้ชมของคุณเข้าใจข้อมูลที่ซับซ้อนได้ง่ายขึ้น

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

 หากต้องการเปลี่ยนประเภทแผนภูมิ ให้ใช้`chart.setType()` วิธีการและระบุประเภทแผนภูมิที่ต้องการ

### ฉันสามารถเพิ่มชุดข้อมูลหลายชุดลงในแผนภูมิได้หรือไม่

 ใช่ คุณสามารถเพิ่มชุดข้อมูลหลายชุดลงในแผนภูมิได้โดยใช้`chart.getChartData().getSeries().addSeries()` วิธี.

### ฉันจะปรับแต่งสีแผนภูมิได้อย่างไร

คุณสามารถปรับแต่งสีแผนภูมิได้โดยการตั้งค่ารูปแบบการเติมสำหรับองค์ประกอบแผนภูมิต่างๆ เช่น เส้นตาราง ชื่อ และคำอธิบาย

### ฉันสามารถสร้างแผนภูมิ 3 มิติได้หรือไม่

 ใช่ Aspose.Slides สำหรับ Java รองรับการสร้างแผนภูมิ 3 มิติ คุณสามารถตั้งค่า`ChartType` เป็นประเภทแผนภูมิ 3 มิติเพื่อสร้าง

### Aspose.Slides สำหรับ Java เข้ากันได้กับ Java เวอร์ชันล่าสุดหรือไม่

ใช่ Aspose.Slides สำหรับ Java ได้รับการอัปเดตเป็นประจำเพื่อรองรับ Java เวอร์ชันล่าสุด และให้ความเข้ากันได้กับสภาพแวดล้อม Java ที่หลากหลาย
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
