---
title: การตั้งค่าสี Slice แผนภูมิวงกลมอัตโนมัติใน Java Slides
linktitle: การตั้งค่าสี Slice แผนภูมิวงกลมอัตโนมัติใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้างแผนภูมิวงกลมแบบไดนามิกด้วยสีชิ้นอัตโนมัติในงานนำเสนอ Java PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ด
weight: 24
url: /th/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่าสี Slice แผนภูมิวงกลมอัตโนมัติใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีสร้างแผนภูมิวงกลมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java และตั้งค่าสีชิ้นอัตโนมัติสำหรับแผนภูมิ เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ด

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ Aspose:[ดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: นำเข้าแพ็คเกจที่จำเป็น

ขั้นแรก คุณต้องนำเข้าแพ็คเกจที่จำเป็นจาก Aspose.Slides สำหรับ Java:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## ขั้นตอนที่ 2: สร้างงานนำเสนอ PowerPoint

 ยกตัวอย่าง`Presentation` ชั้นเรียนเพื่อสร้างงานนำเสนอ PowerPoint ใหม่:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 3: เพิ่มสไลด์

เข้าถึงสไลด์แรกของงานนำเสนอและเพิ่มแผนภูมิพร้อมข้อมูลเริ่มต้น:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## ขั้นตอนที่ 4: ตั้งชื่อแผนภูมิ

ตั้งชื่อให้กับแผนภูมิ:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## ขั้นตอนที่ 5: กำหนดค่าข้อมูลแผนภูมิ

ตั้งค่าแผนภูมิให้แสดงค่าสำหรับชุดแรกและกำหนดค่าข้อมูลแผนภูมิ:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## ขั้นตอนที่ 6: เพิ่มหมวดหมู่และซีรี่ส์

เพิ่มหมวดหมู่และซีรีส์ใหม่ลงในแผนภูมิ:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## ขั้นตอนที่ 7: เติมข้อมูลซีรี่ส์

เติมข้อมูลชุดข้อมูลสำหรับแผนภูมิวงกลม:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## ขั้นตอนที่ 8: เปิดใช้งานสี Slice ที่หลากหลาย

เปิดใช้งานสีชิ้นที่หลากหลายสำหรับแผนภูมิวงกลม:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## ขั้นตอนที่ 9: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอเป็นไฟล์ PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับการตั้งค่าสี Slice แผนภูมิวงกลมอัตโนมัติใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงถึงไฟล์ PPTX
Presentation presentation = new Presentation();
try
{
	// เข้าถึงสไลด์แรก
	ISlide slides = presentation.getSlides().get_Item(0);
	// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// การตั้งชื่อแผนภูมิ
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// ตั้งค่าชุดแรกเพื่อแสดงค่า
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
	int defaultWorksheetIndex = 0;
	// รับแผ่นงานข้อมูลแผนภูมิ
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// ลบซีรี่ส์และหมวดหมู่ที่สร้างโดยค่าเริ่มต้น
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// การเพิ่มหมวดหมู่ใหม่
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// กำลังเพิ่มซีรีส์ใหม่
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// กำลังเติมข้อมูลซีรีส์
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

คุณสร้างแผนภูมิวงกลมในงานนำเสนอ PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java และกำหนดค่าให้มีสีชิ้นอัตโนมัติ คำแนะนำทีละขั้นตอนนี้จะให้ซอร์สโค้ดที่จำเป็นแก่คุณเพื่อให้บรรลุเป้าหมายนี้ คุณสามารถปรับแต่งแผนภูมิและการนำเสนอเพิ่มเติมได้ตามต้องการ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งสีของแต่ละชิ้นในแผนภูมิวงกลมได้อย่างไร

 หากต้องการปรับแต่งสีของแต่ละชิ้นในแผนภูมิวงกลม คุณสามารถใช้`getAutomaticSeriesColors` วิธีการดึงข้อมูลโครงร่างสีเริ่มต้น จากนั้นปรับเปลี่ยนสีตามต้องการ นี่คือตัวอย่าง:

```java
//รับโทนสีเริ่มต้น
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// ปรับเปลี่ยนสีได้ตามต้องการ
colors.get_Item(0).setColor(Color.RED); // ตั้งค่าสีของชิ้นแรกเป็นสีแดง
colors.get_Item(1).setColor(Color.BLUE); // ตั้งค่าสีของชิ้นที่สองเป็นสีน้ำเงิน
// เพิ่มการปรับเปลี่ยนสีเพิ่มเติมตามต้องการ
```

### ฉันจะเพิ่มคำอธิบายลงในแผนภูมิวงกลมได้อย่างไร

 หากต้องการเพิ่มคำอธิบายแผนภูมิให้กับแผนภูมิวงกลม คุณสามารถใช้`getLegend` วิธีการและกำหนดค่าดังต่อไปนี้:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // กำหนดตำแหน่งคำอธิบายแผนภูมิ
legend.setOverlay(true); // แสดงคำอธิบายแผนภูมิบนแผนภูมิ
```

### ฉันสามารถเปลี่ยนแบบอักษรและรูปแบบของชื่อได้หรือไม่?

ได้ คุณสามารถเปลี่ยนแบบอักษรและรูปแบบของชื่อเรื่องได้ ใช้รหัสต่อไปนี้เพื่อตั้งค่าแบบอักษรและสไตล์ของชื่อเรื่อง:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // กำหนดขนาดตัวอักษร
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // ตั้งชื่อเรื่องให้เป็นตัวหนา
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // ตั้งชื่อเรื่องให้เป็นตัวเอียง
```

คุณสามารถปรับขนาดตัวอักษร ตัวหนา และลักษณะตัวเอียงได้ตามต้องการ
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
