---
"description": "เรียนรู้วิธีการสร้างแผนภูมิเรดาร์ในการนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java API"
"linktitle": "การสร้างแผนภูมิเรดาร์ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การสร้างแผนภูมิเรดาร์ใน Java Slides"
"url": "/th/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การสร้างแผนภูมิเรดาร์ใน Java Slides


## บทนำสู่การสร้างแผนภูมิเรดาร์ในสไลด์ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างแผนภูมิเรดาร์โดยใช้ Aspose.Slides สำหรับ Java API แผนภูมิเรดาร์มีประโยชน์สำหรับการแสดงข้อมูลในรูปแบบวงกลม ทำให้เปรียบเทียบชุดข้อมูลหลายชุดได้ง่ายขึ้น เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับโค้ดต้นฉบับของ Java

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: การตั้งค่าการนำเสนอ

เริ่มต้นด้วยการตั้งค่าการนำเสนอ PowerPoint ใหม่และเพิ่มสไลด์เข้าไป

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิเรดาร์

ต่อไปเราจะเพิ่มแผนภูมิเรดาร์ลงในสไลด์ โดยจะระบุตำแหน่งและขนาดของแผนภูมิ

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## ขั้นตอนที่ 3: การตั้งค่าข้อมูลแผนภูมิ

ตอนนี้เราจะตั้งค่าข้อมูลแผนภูมิ ซึ่งเกี่ยวข้องกับการสร้างเวิร์กบุ๊กข้อมูล การเพิ่มหมวดหมู่ และการเพิ่มชุดข้อมูล

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// ตั้งชื่อแผนภูมิ
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// ลบซีรีย์และหมวดหมู่ที่สร้างตามค่าเริ่มต้น
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// การเพิ่มหมวดหมู่ใหม่
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// เพิ่มซีรีย์ใหม่
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## ขั้นตอนที่ 4: การเติมข้อมูลชุดข้อมูล

ตอนนี้เราจะเติมข้อมูลชุดให้กับแผนภูมิเรดาร์ของเรา

```java
// เติมข้อมูลซีรีย์สำหรับซีรีย์ 1
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// ตั้งค่าสีซีรีย์
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// เติมข้อมูลซีรีย์สำหรับซีรีย์ 2
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// ตั้งค่าสีซีรีย์
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## ขั้นตอนที่ 5: การปรับแต่งแกนและตำนาน

มาปรับแต่งแกนและคำอธิบายสำหรับแผนภูมิเรดาร์ของเรากัน

```java
// กำหนดตำแหน่งตำนาน
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// ตั้งค่าคุณสมบัติข้อความแกนหมวดหมู่
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

// ตั้งค่าคุณสมบัติข้อความแกนค่า
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// ตั้งค่ารูปแบบหมายเลขแกนค่า
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// แผนภูมิการตั้งค่าหน่วยหลัก
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้ายบันทึกการนำเสนอที่สร้างขึ้นด้วยแผนภูมิเรดาร์

-

```java
pres.save(outPath, SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้สร้างแผนภูมิเรดาร์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว ตอนนี้คุณสามารถปรับแต่งตัวอย่างนี้เพิ่มเติมเพื่อให้เหมาะกับความต้องการเฉพาะของคุณได้

## โค้ดต้นฉบับสมบูรณ์สำหรับการสร้างแผนภูมิเรดาร์ใน Java Slides

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// เข้าถึงสไลด์แรก
	ISlide sld = pres.getSlides().get_Item(0);
	// เพิ่มแผนภูมิเรดาร์
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
	int defaultWorksheetIndex = 0;
	// การรับข้อมูลแผนภูมิเวิร์กชีต
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// ตั้งชื่อแผนภูมิ
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// ลบซีรีย์และหมวดหมู่ที่สร้างตามค่าเริ่มต้น
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// การเพิ่มหมวดหมู่ใหม่
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// เพิ่มซีรีย์ใหม่
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// ตั้งค่าสีซีรีย์
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// ตอนนี้กำลังเพิ่มข้อมูลซีรีส์อื่น
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// ตั้งค่าสีซีรีย์
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// กำหนดตำแหน่งตำนาน
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// ตั้งค่าคุณสมบัติข้อความแกนหมวดหมู่
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
	// ตั้งค่าคุณสมบัติข้อความแกนค่า
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// ตั้งค่ารูปแบบหมายเลขแกนค่า
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// แผนภูมิการตั้งค่าหน่วยหลัก
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

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการสร้างแผนภูมิเรดาร์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถนำแนวคิดเหล่านี้ไปใช้เพื่อสร้างภาพและนำเสนอข้อมูลของคุณอย่างมีประสิทธิภาพในแอปพลิเคชัน Java

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนชื่อแผนภูมิได้อย่างไร?

หากต้องการเปลี่ยนชื่อแผนภูมิ ให้แก้ไขบรรทัดต่อไปนี้:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### ฉันสามารถเพิ่มชุดข้อมูลเพิ่มเติมลงในแผนภูมิเรดาร์ได้หรือไม่

ใช่ คุณสามารถเพิ่มชุดข้อมูลเพิ่มเติมได้โดยทำตามขั้นตอนใน "ขั้นตอนที่ 3" และ "ขั้นตอนที่ 4" สำหรับชุดข้อมูลเพิ่มเติมแต่ละชุดที่คุณต้องการรวมไว้

### ฉันจะปรับแต่งสีของแผนภูมิได้อย่างไร

คุณสามารถปรับแต่งสีของซีรีส์ได้โดยการแก้ไขเส้นที่ตั้งค่า `SolidFillColor` ทรัพย์สินของแต่ละซีรีส์ ตัวอย่างเช่น:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### ฉันจะเปลี่ยนป้ายแกนและการจัดรูปแบบได้อย่างไร

ดู "ขั้นตอนที่ 5" เพื่อปรับแต่งป้ายแกนและการจัดรูปแบบ รวมถึงขนาดและสีของแบบอักษร

### ฉันจะบันทึกแผนภูมิเป็นรูปแบบไฟล์อื่นได้อย่างไร

คุณสามารถเปลี่ยนรูปแบบผลลัพธ์ได้โดยการแก้ไขนามสกุลไฟล์ใน `outPath` ตัวแปรและการใช้ให้เหมาะสม `SaveFormat`ตัวอย่างเช่น หากต้องการบันทึกเป็น PDF ให้ใช้ `SaveFormat-Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}