---
"description": "สร้างแผนภูมิปกติใน Java Slides ด้วย Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนและซอร์สโค้ดสำหรับการสร้าง ปรับแต่ง และบันทึกแผนภูมิในงานนำเสนอ PowerPoint"
"linktitle": "แผนภูมิปกติใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิปกติใน Java Slides"
"url": "/th/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิปกติใน Java Slides


## การแนะนำแผนภูมิปกติใน Java Slides

ในบทช่วยสอนนี้ เราจะแนะนำขั้นตอนการสร้างแผนภูมิปกติใน Java Slides โดยใช้ Aspose.Slides for Java API เราจะใช้คำแนะนำทีละขั้นตอนพร้อมกับโค้ดต้นฉบับเพื่อสาธิตวิธีสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ในงานนำเสนอ PowerPoint

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

1. ติดตั้ง Aspose.Slides สำหรับ Java API แล้ว
2. การตั้งค่าสภาพแวดล้อมการพัฒนา Java
3. ความรู้พื้นฐานเกี่ยวกับการเขียนโปรแกรมภาษา Java

## ขั้นตอนที่ 1: การตั้งค่าโครงการ

ตรวจสอบว่าคุณมีไดเรกทอรีสำหรับโครงการของคุณแล้ว เรียกว่า "ไดเรกทอรีเอกสารของคุณ" ตามที่ระบุไว้ในโค้ด คุณสามารถแทนที่ด้วยเส้นทางไปยังไดเรกทอรีโครงการของคุณได้

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## ขั้นตอนที่ 2: การสร้างงานนำเสนอ

ตอนนี้เรามาสร้างการนำเสนอ PowerPoint และเข้าถึงสไลด์แรกกัน

```java
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
Presentation pres = new Presentation();
// เข้าถึงสไลด์แรก
ISlide sld = pres.getSlides().get_Item(0);
```

## ขั้นตอนที่ 3: การเพิ่มแผนภูมิ

เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์และตั้งชื่อ

```java
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// ตั้งค่าแผนภูมิชื่อ
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## ขั้นตอนที่ 4: การตั้งค่าข้อมูลแผนภูมิ

ต่อไปเราจะตั้งค่าข้อมูลแผนภูมิโดยการกำหนดชุดข้อมูลและหมวดหมู่

```java
// ตั้งค่าซีรีส์แรกให้แสดงค่า
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

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

## ขั้นตอนที่ 5: การเติมข้อมูลชุดข้อมูล

ตอนนี้ เรามาเพิ่มจุดข้อมูลลงในแผนภูมิกัน

```java
// เริ่มต้นด้วยชุดแผนภูมิแรก
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// การเติมข้อมูลชุด
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// การตั้งค่าสีเติมสำหรับซีรีส์
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// มาดูแผนภูมิชุดที่สองกัน
series = chart.getChartData().getSeries().get_Item(1);

// การเติมข้อมูลชุด
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// การตั้งค่าสีเติมสำหรับซีรีส์
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## ขั้นตอนที่ 6: การปรับแต่งฉลาก

มาปรับแต่งป้ายข้อมูลสำหรับชุดแผนภูมิกัน

```java
// ป้ายแรกจะแสดงชื่อหมวดหมู่
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// แสดงค่าสำหรับป้ายที่สามพร้อมชื่อชุดและตัวคั่น
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอพร้อมแผนภูมิไปยังไดเร็กทอรีโครงการของคุณ

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้สร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมตามความต้องการของคุณได้

## โค้ดต้นฉบับสมบูรณ์สำหรับแผนภูมิปกติใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างไดเร็กทอรีหากยังไม่มีอยู่
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// สร้างอินสแตนซ์คลาสการนำเสนอที่แสดงไฟล์ PPTX
Presentation pres = new Presentation();
// เข้าถึงสไลด์แรก
ISlide sld = pres.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// ตั้งค่าแผนภูมิชื่อ
// Chart.getChartTitle().getTextFrameForOverriding().setText("ตัวอย่างชื่อ");
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
// การตั้งค่าสีเติมสำหรับซีรีส์
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// มาดูแผนภูมิชุดที่สองกัน
series = chart.getChartData().getSeries().get_Item(1);
// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// การตั้งค่าสีเติมสำหรับซีรีส์
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// ป้ายแรกจะแสดงชื่อหมวดหมู่
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// แสดงค่าสำหรับป้ายที่สาม
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// บันทึกการนำเสนอด้วยแผนภูมิ
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างแผนภูมิปกติใน Java Slides โดยใช้ Aspose.Slides for Java API เราได้แนะนำขั้นตอนโดยละเอียดพร้อมโค้ดต้นฉบับเพื่อสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ในงานนำเสนอ PowerPoint

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร

หากต้องการเปลี่ยนประเภทแผนภูมิ ให้แก้ไข `ChartType` พารามิเตอร์เมื่อเพิ่มแผนภูมิโดยใช้ `sld.getShapes().addChart()`คุณสามารถเลือกจากประเภทแผนภูมิต่างๆ ที่มีอยู่ใน Aspose.Slides ได้

### ฉันสามารถเปลี่ยนสีของชุดแผนภูมิได้หรือไม่

ใช่ คุณสามารถเปลี่ยนสีของชุดแผนภูมิได้โดยการตั้งค่าสีเติมสำหรับแต่ละชุดโดยใช้ `series-getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### ฉันจะเพิ่มหมวดหมู่หรือซีรีส์เพิ่มเติมลงในแผนภูมิได้อย่างไร

คุณสามารถเพิ่มหมวดหมู่หรือชุดเพิ่มเติมลงในแผนภูมิได้โดยการเพิ่มจุดข้อมูลและป้ายกำกับใหม่โดยใช้ `chart.getChartData().getCategories().add()` และ `chart.getChartData().getSeries().add()` วิธีการ

### ฉันจะปรับแต่งชื่อแผนภูมิเพิ่มเติมได้อย่างไร

คุณสามารถปรับแต่งชื่อแผนภูมิเพิ่มเติมได้โดยการแก้ไขคุณสมบัติของ `chart.getChartTitle()` เช่น การจัดตำแหน่งข้อความ ขนาดตัวอักษร และสี

### ฉันจะบันทึกแผนภูมิเป็นรูปแบบไฟล์อื่นได้อย่างไร

หากต้องการบันทึกแผนภูมิเป็นรูปแบบไฟล์อื่น ให้เปลี่ยน `SaveFormat` พารามิเตอร์ใน `pres.save()` วิธีการให้เป็นรูปแบบที่ต้องการ (เช่น PDF, PNG, JPEG)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}