---
title: แผนภูมิหลายหมวดหมู่ใน Java Slides
linktitle: แผนภูมิหลายหมวดหมู่ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: สร้างแผนภูมิหลายหมวดหมู่ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อการแสดงภาพข้อมูลที่น่าประทับใจในการนำเสนอ
weight: 20
url: /th/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## ข้อมูลเบื้องต้นเกี่ยวกับแผนภูมิหลายหมวดหมู่ใน Java Slides พร้อม Aspose.Slides

ในบทช่วยสอนนี้ เราจะได้เรียนรู้วิธีสร้างแผนภูมิหลายหมวดหมู่ในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API คู่มือนี้จะให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ดเพื่อช่วยคุณสร้างแผนภูมิคอลัมน์แบบกลุ่มที่มีหมวดหมู่และซีรีส์หลายรายการ

## ข้อกำหนดเบื้องต้น
ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในสภาพแวดล้อมการพัฒนา Java ของคุณแล้ว

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม
ขั้นแรก นำเข้าคลาสที่จำเป็นและสร้างออบเจ็กต์การนำเสนอใหม่เพื่อทำงานกับสไลด์

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: การเพิ่มสไลด์และแผนภูมิ
จากนั้น สร้างสไลด์และเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงไป

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## ขั้นตอนที่ 3: การล้างข้อมูลที่มีอยู่
ล้างข้อมูลที่มีอยู่ออกจากแผนภูมิ

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## ขั้นตอนที่ 4: การตั้งค่าหมวดหมู่ข้อมูล
ตอนนี้ เรามาตั้งค่าหมวดหมู่ข้อมูลสำหรับแผนภูมิกันดีกว่า เราจะสร้างหลายประเภทและจัดกลุ่มไว้

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// เพิ่มหมวดหมู่และจัดกลุ่ม
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

## ขั้นตอนที่ 5: การเพิ่มซีรี่ส์
ตอนนี้ เรามาเพิ่มชุดข้อมูลลงในแผนภูมิพร้อมกับจุดข้อมูลกัน

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
สุดท้าย ให้บันทึกงานนำเสนอด้วยแผนภูมิ

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณได้สร้างแผนภูมิหลายหมวดหมู่ในสไลด์ Java โดยใช้ Aspose.Slides สำเร็จแล้ว คุณสามารถปรับแต่งแผนภูมินี้เพิ่มเติมเพื่อให้เหมาะกับความต้องการเฉพาะของคุณได้

## กรอกซอร์สโค้ดสำหรับแผนภูมิหลายหมวดหมู่ใน Java Slides

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
// กำลังเพิ่มซีรี่ส์
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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้างแผนภูมิหลายหมวดหมู่ในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java API เราอ่านคำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ที่มีหมวดหมู่และซีรีส์หลายรายการ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของแผนภูมิได้อย่างไร

คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิได้โดยการแก้ไขคุณสมบัติ เช่น สี แบบอักษร และสไตล์ โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับตัวเลือกการปรับแต่งโดยละเอียด

### ฉันสามารถเพิ่มซีรี่ส์เพิ่มเติมลงในแผนภูมิได้หรือไม่

ได้ คุณสามารถเพิ่มซีรี่ส์เพิ่มเติมลงในแผนภูมิได้โดยทำตามขั้นตอนที่คล้ายกันดังที่แสดงในขั้นตอนที่ 5

### ฉันจะเปลี่ยนประเภทแผนภูมิได้อย่างไร?

 หากต้องการเปลี่ยนประเภทแผนภูมิ ให้แทนที่`ChartType.ClusteredColumn` ด้วยประเภทแผนภูมิที่ต้องการเมื่อเพิ่มแผนภูมิในขั้นตอนที่ 2

### ฉันจะเพิ่มชื่อลงในแผนภูมิได้อย่างไร

 คุณสามารถเพิ่มชื่อลงในแผนภูมิได้โดยใช้`ch.getChartTitle().getTextFrame().setText("Chart Title");` วิธี.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
