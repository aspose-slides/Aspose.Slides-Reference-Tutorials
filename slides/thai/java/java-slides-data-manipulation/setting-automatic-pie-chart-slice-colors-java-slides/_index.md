---
"description": "เรียนรู้วิธีสร้างแผนภูมิวงกลมแบบไดนามิกพร้อมสีส่วนอัตโนมัติในงานนำเสนอ PowerPoint ของ Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ"
"linktitle": "การตั้งค่าสีชิ้นส่วนของแผนภูมิวงกลมอัตโนมัติใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "การตั้งค่าสีชิ้นส่วนของแผนภูมิวงกลมอัตโนมัติใน Java Slides"
"url": "/th/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าสีชิ้นส่วนของแผนภูมิวงกลมอัตโนมัติใน Java Slides


## การแนะนำการตั้งค่าสีชิ้นส่วนของแผนภูมิวงกลมอัตโนมัติใน Java Slides

ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการสร้างแผนภูมิวงกลมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java และตั้งค่าสีสไลซ์อัตโนมัติสำหรับแผนภูมิ เราจะให้คำแนะนำทีละขั้นตอนพร้อมทั้งโค้ดต้นฉบับ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ Aspose: [ดาวน์โหลด Aspose.Slides สำหรับ Java](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: นำเข้าแพ็คเกจที่จำเป็น

ก่อนอื่น คุณต้องนำเข้าแพ็คเกจที่จำเป็นจาก Aspose.Slides สำหรับ Java:

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

## ขั้นตอนที่ 2: สร้างการนำเสนอ PowerPoint

สร้างตัวอย่าง `Presentation` ชั้นเรียนเพื่อสร้างการนำเสนอ PowerPoint ใหม่:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 3: เพิ่มสไลด์

เข้าถึงสไลด์แรกของการนำเสนอและเพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## ขั้นตอนที่ 4: ตั้งชื่อแผนภูมิ

ตั้งชื่อเรื่องให้กับแผนภูมิ:

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

## ขั้นตอนที่ 6: เพิ่มหมวดหมู่และซีรีส์

เพิ่มหมวดหมู่และชุดใหม่ลงในแผนภูมิ:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## ขั้นตอนที่ 7: เติมข้อมูลชุดข้อมูล

เติมข้อมูลชุดให้กับแผนภูมิวงกลม:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## ขั้นตอนที่ 8: เปิดใช้งานสีสไลซ์ที่หลากหลาย

เปิดใช้งานสีชิ้นที่หลากหลายสำหรับแผนภูมิวงกลม:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## ขั้นตอนที่ 9: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอลงในไฟล์ PowerPoint:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการตั้งค่าสีชิ้นส่วนแผนภูมิวงกลมอัตโนมัติใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
Presentation presentation = new Presentation();
try
{
	// เข้าถึงสไลด์แรก
	ISlide slides = presentation.getSlides().get_Item(0);
	// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
	IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
	// ตั้งค่าแผนภูมิชื่อ
	chart.getChartTitle().addTextFrameForOverriding("Sample Title");
	chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
	chart.getChartTitle().setHeight(20);
	chart.setTitle(true);
	// ตั้งค่าซีรีส์แรกให้แสดงค่า
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
	int defaultWorksheetIndex = 0;
	// การรับแผ่นงานข้อมูลแผนภูมิ
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// ลบซีรีย์และหมวดหมู่ที่สร้างตามค่าเริ่มต้น
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	// การเพิ่มหมวดหมู่ใหม่
	chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
	chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
	// เพิ่มซีรีย์ใหม่
	IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
	// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
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

คุณได้สร้างแผนภูมิวงกลมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว และกำหนดค่าให้มีสีสไลซ์อัตโนมัติ คำแนะนำทีละขั้นตอนนี้จะให้โค้ดต้นฉบับที่จำเป็นแก่คุณเพื่อให้บรรลุสิ่งนี้ คุณสามารถปรับแต่งแผนภูมิและงานนำเสนอเพิ่มเติมตามต้องการได้

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งสีของแต่ละชิ้นในแผนภูมิวงกลมได้อย่างไร

หากต้องการปรับแต่งสีของแต่ละชิ้นในแผนภูมิวงกลม คุณสามารถใช้ `getAutomaticSeriesColors` วิธีการดึงรูปแบบสีเริ่มต้นและปรับเปลี่ยนสีตามต้องการ นี่คือตัวอย่าง:

```java
// รับรูปแบบสีเริ่มต้น
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// ปรับเปลี่ยนสีตามต้องการ
colors.get_Item(0).setColor(Color.RED); // ตั้งค่าสีของชิ้นแรกเป็นสีแดง
colors.get_Item(1).setColor(Color.BLUE); // ตั้งค่าสีของชิ้นที่สองเป็นสีน้ำเงิน
// เพิ่มการปรับแต่งสีเพิ่มเติมตามความต้องการ
```

### ฉันจะเพิ่มคำอธิบายลงในแผนภูมิวงกลมได้อย่างไร

หากต้องการเพิ่มคำอธิบายลงในแผนภูมิวงกลม คุณสามารถใช้ `getLegend` วิธีการและกำหนดค่าดังต่อไปนี้:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // ตั้งค่าตำแหน่งตำนาน
legend.setOverlay(true); // แสดงคำอธิบายเหนือแผนภูมิ
```

### ฉันสามารถเปลี่ยนแบบอักษรและรูปแบบชื่อเรื่องได้หรือไม่

ใช่ คุณสามารถเปลี่ยนแบบอักษรและรูปแบบของชื่อเรื่องได้ ใช้โค้ดต่อไปนี้เพื่อตั้งค่าแบบอักษรและรูปแบบของชื่อเรื่อง:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // ตั้งค่าขนาดตัวอักษร
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // ทำให้ชื่อเรื่องเป็นตัวหนา
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // ทำให้ชื่อเรื่องเป็นตัวเอียง
```

คุณสามารถปรับขนาดตัวอักษร ความหนา และรูปแบบตัวเอียงตามที่ต้องการได้

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}