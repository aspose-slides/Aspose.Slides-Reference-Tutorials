---
"description": "เรียนรู้วิธีการสร้างแผนภูมิแบบไดนามิกพร้อมการลงสีชุดข้อมูลอัตโนมัติในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงการแสดงภาพข้อมูลของคุณได้อย่างง่ายดาย"
"linktitle": "แผนภูมิสีชุดอัตโนมัติใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิสีชุดอัตโนมัติใน Java Slides"
"url": "/th/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิสีชุดอัตโนมัติใน Java Slides


## การแนะนำแผนภูมิสีอัตโนมัติใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะมาเรียนรู้วิธีการสร้างงานนำเสนอ PowerPoint ที่มีแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java และตั้งค่าสีเติมอัตโนมัติสำหรับชุดแผนภูมิ สีเติมอัตโนมัติสามารถทำให้แผนภูมิของคุณดูน่าสนใจยิ่งขึ้นและประหยัดเวลาของคุณได้โดยให้ไลบรารีเลือกสีให้กับคุณ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าได้ติดตั้งไลบรารี Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

ขั้นแรกเราจะสร้างการนำเสนอ PowerPoint ใหม่และเพิ่มสไลด์เข้าไป

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิลงในสไลด์

ต่อไปเราจะเพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์ลงในสไลด์ เราจะตั้งค่าชุดข้อมูลแรกให้แสดงค่าด้วย

```java
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// ตั้งค่าซีรีส์แรกให้แสดงค่า
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## ขั้นตอนที่ 3: เติมข้อมูลแผนภูมิ

ตอนนี้เราจะเพิ่มข้อมูลลงในแผนภูมิ เราจะเริ่มต้นด้วยการลบชุดข้อมูลและหมวดหมู่ที่สร้างขึ้นตามค่าเริ่มต้น จากนั้นจึงเพิ่มชุดข้อมูลและหมวดหมู่ใหม่

```java
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// ลบซีรีย์และหมวดหมู่ที่สร้างตามค่าเริ่มต้น
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// เพิ่มซีรีย์ใหม่
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// การเพิ่มหมวดหมู่ใหม่
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## ขั้นตอนที่ 4: เติมข้อมูลชุดข้อมูล

เราจะเติมข้อมูลซีรีส์ทั้งซีรีส์ 1 และซีรีส์ 2

```java
// เริ่มต้นด้วยชุดแผนภูมิแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// มาดูแผนภูมิชุดที่สองกัน
series = chart.getChartData().getSeries().get_Item(1);
// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## ขั้นตอนที่ 5: ตั้งค่าสีเติมอัตโนมัติสำหรับซีรีส์

ตอนนี้เรามาตั้งค่าสีเติมอัตโนมัติให้กับชุดแผนภูมิกัน วิธีนี้จะทำให้ไลบรารีเลือกสีให้เรา

```java
// การตั้งค่าสีเติมอัตโนมัติสำหรับซีรีส์
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

สุดท้ายเราจะบันทึกการนำเสนอพร้อมแผนภูมิไปยังไฟล์ PowerPoint

```java
// บันทึกการนำเสนอด้วยแผนภูมิ
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับที่สมบูรณ์สำหรับการระบายสีแผนภูมิอัตโนมัติในสไลด์ Java

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
	// ตั้งค่าซีรีส์แรกให้แสดงค่า
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
	int defaultWorksheetIndex = 0;
	// การรับแผ่นงานข้อมูลแผนภูมิ
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// ลบซีรีย์และหมวดหมู่ที่สร้างตามค่าเริ่มต้น
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// เพิ่มซีรีย์ใหม่
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// การเพิ่มหมวดหมู่ใหม่
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// เริ่มต้นด้วยชุดแผนภูมิแรก
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// การตั้งค่าสีเติมอัตโนมัติสำหรับซีรีส์
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// มาดูแผนภูมิชุดที่สองกัน
	series = chart.getChartData().getSeries().get_Item(1);
	// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// การตั้งค่าสีเติมสำหรับซีรีส์
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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการสร้างงานนำเสนอ PowerPoint ด้วยแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java และตั้งค่าสีเติมอัตโนมัติสำหรับชุดแผนภูมิ สีอัตโนมัติสามารถเพิ่มความน่าสนใจให้กับแผนภูมิของคุณและทำให้การนำเสนอของคุณน่าสนใจยิ่งขึ้น คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมตามความต้องการเฉพาะของคุณได้

## คำถามที่พบบ่อย

### ฉันจะตั้งค่าสีเติมอัตโนมัติให้กับชุดแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการตั้งค่าสีเติมอัตโนมัติสำหรับชุดแผนภูมิใน Aspose.Slides สำหรับ Java ให้ใช้โค้ดต่อไปนี้:

```java
// การตั้งค่าสีเติมอัตโนมัติสำหรับซีรีส์
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

โค้ดนี้จะช่วยให้ไลบรารีเลือกสีให้กับชุดแผนภูมิได้โดยอัตโนมัติ

### ฉันสามารถปรับแต่งสีแผนภูมิได้หรือไม่หากจำเป็น?

ใช่ คุณสามารถปรับแต่งสีของแผนภูมิได้ตามต้องการ ในตัวอย่างที่ให้มา เราใช้สีเติมอัตโนมัติ แต่คุณสามารถตั้งค่าสีเฉพาะได้โดยแก้ไข `FillType` และ `SolidFillColor` คุณสมบัติของรูปแบบซีรีย์

### ฉันจะเพิ่มซีรีส์หรือหมวดหมู่เพิ่มเติมลงในแผนภูมิได้อย่างไร

หากต้องการเพิ่มชุดหรือหมวดหมู่เพิ่มเติมลงในแผนภูมิ ให้ใช้ `getSeries()` และ `getCategories()` วิธีการของแผนภูมิ `ChartData` วัตถุ คุณสามารถเพิ่มซีรีส์และหมวดหมู่ใหม่ได้โดยระบุข้อมูลและป้ายกำกับ

### สามารถจัดรูปแบบแผนภูมิและป้ายกำกับเพิ่มเติมได้หรือไม่

ใช่ คุณสามารถจัดรูปแบบแผนภูมิ ชุดข้อมูล และป้ายกำกับเพิ่มเติมตามต้องการได้ Aspose.Slides สำหรับ Java มีตัวเลือกการจัดรูปแบบแผนภูมิมากมาย รวมถึงแบบอักษร สี สไตล์ และอื่นๆ คุณสามารถศึกษารายละเอียดเพิ่มเติมเกี่ยวกับตัวเลือกการจัดรูปแบบได้ในเอกสารประกอบ

### ฉันสามารถหาข้อมูลเพิ่มเติมเกี่ยวกับการทำงานกับ Aspose.Slides สำหรับ Java ได้จากที่ใด

สำหรับข้อมูลเพิ่มเติมและเอกสารโดยละเอียดเกี่ยวกับ Aspose.Slides สำหรับ Java คุณสามารถเยี่ยมชมเอกสารอ้างอิงได้ [ที่นี่](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}