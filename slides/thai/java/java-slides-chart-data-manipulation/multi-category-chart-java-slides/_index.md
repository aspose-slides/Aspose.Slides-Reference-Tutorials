---
"description": "สร้างแผนภูมิหลายหมวดหมู่ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการแสดงภาพข้อมูลที่น่าประทับใจในงานนำเสนอ"
"linktitle": "แผนภูมิหลายหมวดหมู่ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิหลายหมวดหมู่ใน Java Slides"
"url": "/th/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิหลายหมวดหมู่ใน Java Slides


## การแนะนำแผนภูมิหลายหมวดหมู่ใน Java สไลด์ด้วย Aspose.Slides

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีสร้างแผนภูมิหลายหมวดหมู่ในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API คู่มือนี้จะให้คำแนะนำทีละขั้นตอนพร้อมกับโค้ดต้นฉบับเพื่อช่วยคุณสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ที่มีหมวดหมู่และชุดต่างๆ

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในสภาพแวดล้อมการพัฒนา Java ของคุณแล้ว

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ขั้นแรก นำเข้าคลาสที่จำเป็น และสร้างอ็อบเจ็กต์การนำเสนอใหม่เพื่อทำงานกับสไลด์

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: การเพิ่มสไลด์และแผนภูมิ
ขั้นตอนต่อไป ให้สร้างสไลด์และเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงไป

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## ขั้นตอนที่ 3: การล้างข้อมูลที่มีอยู่
ล้างข้อมูลที่มีอยู่ใดๆ ออกจากแผนภูมิ

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## ขั้นตอนที่ 4: การตั้งค่าหมวดหมู่ข้อมูล
ตอนนี้เรามาตั้งค่าหมวดหมู่ข้อมูลสำหรับแผนภูมิกัน เราจะสร้างหมวดหมู่ต่างๆ และจัดกลุ่มพวกมัน

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// เพิ่มหมวดหมู่และจัดกลุ่มไว้
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## ขั้นตอนที่ 5: การเพิ่มซีรีส์
ตอนนี้ มาเพิ่มชุดข้อมูลลงในแผนภูมิพร้อมกับจุดข้อมูลกัน

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## ขั้นตอนที่ 6: บันทึกการนำเสนอ
สุดท้ายให้บันทึกการนำเสนอด้วยแผนภูมิ

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้สร้างแผนภูมิหลายหมวดหมู่ในสไลด์ Java สำเร็จแล้วโดยใช้ Aspose.Slides คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมเพื่อให้เหมาะกับความต้องการเฉพาะของคุณได้

## โค้ดต้นฉบับสมบูรณ์สำหรับแผนภูมิหลายหมวดหมู่ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
//            การเพิ่มซีรีย์
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// บันทึกการนำเสนอด้วยแผนภูมิ
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการสร้างแผนภูมิหลายหมวดหมู่ในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API เราได้อ่านคำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับเพื่อสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ที่มีหมวดหมู่และชุดต่างๆ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะแผนภูมิได้อย่างไร

คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิได้โดยการแก้ไขคุณสมบัติต่างๆ เช่น สี แบบอักษร และรูปแบบ โปรดดูเอกสาร Aspose.Slides เพื่อดูตัวเลือกการปรับแต่งโดยละเอียด

### ฉันสามารถเพิ่มซีรีส์เพิ่มเติมลงในแผนภูมิได้หรือไม่

ใช่ คุณสามารถเพิ่มซีรีส์เพิ่มเติมลงในแผนภูมิได้โดยทำตามขั้นตอนเดียวกันตามที่แสดงในขั้นตอนที่ 5

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

หากต้องการเปลี่ยนประเภทแผนภูมิ ให้แทนที่ `ChartType.ClusteredColumn` ด้วยประเภทแผนภูมิที่ต้องการเมื่อเพิ่มแผนภูมิในขั้นตอนที่ 2

### ฉันจะเพิ่มชื่อเรื่องลงในแผนภูมิได้อย่างไร

คุณสามารถเพิ่มชื่อเรื่องให้กับแผนภูมิได้โดยใช้ `ch.getChartTitle().getTextFrame().setText("Chart Title");` วิธี.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}