---
"description": "เรียนรู้การสร้างและปรับแต่งแผนภูมิ Java Slides ด้วย Aspose.Slides เพิ่มประสิทธิภาพการนำเสนอของคุณด้วยเอนทิตีแผนภูมิอันทรงพลัง"
"linktitle": "เอนทิตีแผนภูมิใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เอนทิตีแผนภูมิใน Java Slides"
"url": "/th/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เอนทิตีแผนภูมิใน Java Slides


## บทนำเกี่ยวกับเอนทิตีแผนภูมิในสไลด์ Java

แผนภูมิเป็นเครื่องมือที่มีประสิทธิภาพสำหรับการแสดงข้อมูลในงานนำเสนอ ไม่ว่าคุณจะกำลังสร้างรายงานทางธุรกิจ งานนำเสนอทางวิชาการ หรือเนื้อหารูปแบบอื่นใด แผนภูมิก็ช่วยให้ถ่ายทอดข้อมูลได้อย่างมีประสิทธิภาพ Aspose.Slides สำหรับ Java มีคุณสมบัติที่แข็งแกร่งสำหรับการทำงานกับแผนภูมิ ทำให้เป็นตัวเลือกที่นักพัฒนา Java เลือกใช้

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกเข้าไปในโลกของแผนภูมิ โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- ติดตั้ง Java Development Kit (JDK) แล้ว
- ดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java และเพิ่มลงในโปรเจ็กต์ของคุณแล้ว
- ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java

ตอนนี้เรามาเริ่มต้นด้วยการสร้างและปรับแต่งแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java กัน

## ขั้นตอนที่ 1: การสร้างงานนำเสนอ

ขั้นตอนแรกคือการสร้างงานนำเสนอใหม่โดยที่คุณจะเพิ่มแผนภูมิของคุณ ต่อไปนี้คือตัวอย่างโค้ดสำหรับการสร้างงานนำเสนอ:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิ

เมื่อคุณเตรียมการนำเสนอของคุณเสร็จแล้ว ก็ถึงเวลาเพิ่มแผนภูมิ ในตัวอย่างนี้ เราจะเพิ่มแผนภูมิเส้นแบบง่ายพร้อมเครื่องหมาย คุณสามารถทำได้ดังนี้:

```java
// การเข้าถึงสไลด์แรก
ISlide slide = pres.getSlides().get_Item(0);

// การเพิ่มแผนภูมิตัวอย่าง
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## ขั้นตอนที่ 3: ปรับแต่งชื่อแผนภูมิ

แผนภูมิที่มีการกำหนดไว้อย่างชัดเจนควรมีชื่อเรื่อง มาตั้งชื่อให้กับแผนภูมิของเรากัน:

```java
// ตั้งค่าชื่อแผนภูมิ
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## ขั้นตอนที่ 4: การจัดรูปแบบเส้นตาราง

คุณสามารถจัดรูปแบบเส้นตารางหลักและรองของแผนภูมิของคุณได้ มาตั้งค่าการจัดรูปแบบสำหรับเส้นตารางแกนแนวตั้งกัน:

```java
// การตั้งค่ารูปแบบเส้นกริดหลักสำหรับแกนค่า
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// การตั้งค่ารูปแบบเส้นกริดย่อยสำหรับแกนค่า
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## ขั้นตอนที่ 5: ปรับแต่งแกนค่า

คุณสามารถควบคุมรูปแบบตัวเลข ค่าสูงสุด และค่าต่ำสุดของแกนค่าได้ วิธีปรับแต่งมีดังนี้:

```java
// ตั้งค่ารูปแบบหมายเลขแกนค่า
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// แผนภูมิการตั้งค่าค่าสูงสุดและต่ำสุด
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

หากต้องการให้แผนภูมิของคุณมีข้อมูลมากขึ้น คุณสามารถเพิ่มชื่อให้กับแกนค่าได้:

```java
// ตั้งค่าชื่อแกนค่า
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## ขั้นตอนที่ 7: การจัดรูปแบบแกนหมวดหมู่

แกนหมวดหมู่ ซึ่งโดยทั่วไปแสดงหมวดหมู่ข้อมูล ยังสามารถปรับแต่งได้ดังนี้:

```java
// การตั้งค่ารูปแบบเส้นกริดหลักสำหรับแกนหมวดหมู่
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// การตั้งค่ารูปแบบเส้นกริดย่อยสำหรับแกนหมวดหมู่
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## ขั้นตอนที่ 8: การเพิ่มตำนาน

คำอธิบายแผนภูมิช่วยอธิบายชุดข้อมูลในแผนภูมิของคุณ มาปรับแต่งคำอธิบายแผนภูมิกัน:

```java
// การตั้งค่าคุณสมบัติข้อความตำนาน
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// ตั้งค่าคำอธิบายแผนภูมิการแสดงโดยไม่ให้แผนภูมิทับซ้อนกัน
chart.getLegend().setOverlay(true);
```

## ขั้นตอนที่ 9: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอของคุณด้วยแผนภูมิ:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับที่สมบูรณ์สำหรับเอนทิตีแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// การสร้างตัวอย่างการนำเสนอ// การสร้างตัวอย่างการนำเสนอ
Presentation pres = new Presentation();
try
{
	// การเข้าถึงสไลด์แรก
	ISlide slide = pres.getSlides().get_Item(0);
	// การเพิ่มแผนภูมิตัวอย่าง
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// แผนภูมิการตั้งค่าชื่อเรื่อง
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// การตั้งค่ารูปแบบเส้นกริดหลักสำหรับแกนค่า
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// การตั้งค่ารูปแบบเส้นกริดย่อยสำหรับแกนค่า
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// ตั้งค่ารูปแบบหมายเลขแกนค่า
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// แผนภูมิการตั้งค่าค่าสูงสุดและต่ำสุด
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// ตั้งค่าคุณสมบัติข้อความแกนค่า
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// ตั้งค่าชื่อแกนค่า
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// รูปแบบเส้นแกนค่าการตั้งค่า: เลิกใช้แล้ว
	// แผนภูมิ.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// การตั้งค่ารูปแบบเส้นกริดหลักสำหรับแกนหมวดหมู่
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// การตั้งค่ารูปแบบเส้นกริดย่อยสำหรับแกนหมวดหมู่
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// ตั้งค่าคุณสมบัติข้อความแกนหมวดหมู่
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// การตั้งค่าหมวดหมู่ชื่อเรื่อง
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// การกำหนดตำแหน่งป้ายกำกับแกนหมวดหมู่
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// ตั้งค่ามุมหมุนของแกนหมวดหมู่
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// การตั้งค่าคุณสมบัติข้อความตำนาน
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// ตั้งค่าคำอธิบายแผนภูมิการแสดงโดยไม่ให้แผนภูมิทับซ้อนกัน
	chart.getLegend().setOverlay(true);
	// การวางแผนชุดแรกบนแกนค่ารอง
	// แผนภูมิ.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// แผนภูมิการตั้งค่าสีผนังด้านหลัง
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// การตั้งค่าสีพื้นที่พล็อต
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

ในบทความนี้ เราได้สำรวจโลกของเอนทิตีแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณได้เรียนรู้วิธีการสร้าง ปรับแต่ง และจัดการแผนภูมิเพื่อปรับปรุงการนำเสนอของคุณ แผนภูมิไม่เพียงแต่ทำให้ข้อมูลของคุณดูน่าสนใจเท่านั้น แต่ยังช่วยให้ผู้ฟังเข้าใจข้อมูลที่ซับซ้อนได้ง่ายขึ้นอีกด้วย

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

หากต้องการเปลี่ยนประเภทแผนภูมิ ให้ใช้ `chart.setType()` วิธีการและระบุประเภทแผนภูมิที่ต้องการ

### ฉันสามารถเพิ่มชุดข้อมูลหลายชุดลงในแผนภูมิได้หรือไม่

ใช่ คุณสามารถเพิ่มชุดข้อมูลหลายชุดลงในแผนภูมิได้โดยใช้ `chart.getChartData().getSeries().addSeries()` วิธี.

### ฉันจะปรับแต่งสีของแผนภูมิได้อย่างไร

คุณสามารถปรับแต่งสีแผนภูมิได้โดยการตั้งค่ารูปแบบการเติมสำหรับองค์ประกอบแผนภูมิต่าง ๆ เช่น เส้นตาราง ชื่อเรื่อง และคำอธิบายแผนภูมิ

### ฉันสามารถสร้างแผนภูมิ 3 มิติได้หรือไม่?

ใช่ Aspose.Slides สำหรับ Java รองรับการสร้างแผนภูมิ 3 มิติ คุณสามารถตั้งค่าได้ `ChartType` ให้เป็นแผนภูมิชนิด 3 มิติเพื่อสร้างอันหนึ่ง

### Aspose.Slides สำหรับ Java เข้ากันได้กับ Java เวอร์ชันล่าสุดหรือไม่

ใช่ Aspose.Slides สำหรับ Java ได้รับการอัปเดตเป็นประจำเพื่อรองรับ Java เวอร์ชันล่าสุด และให้ความเข้ากันได้กับสภาพแวดล้อม Java ที่หลากหลาย

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}