---
title: ตั้งค่าความกว้างของช่องว่างใน Java Slides
linktitle: ตั้งค่าความกว้างของช่องว่างใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่าความกว้างของช่องว่างใน Java Slides ด้วย Aspose.Slides สำหรับ Java ปรับปรุงภาพแผนภูมิสำหรับการนำเสนอ PowerPoint ของคุณ
type: docs
weight: 21
url: /th/java/data-manipulation/set-gap-width-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่าความกว้างของช่องว่างใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการตั้งค่าความกว้างของช่องว่างสำหรับแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ความกว้างของช่องว่างจะกำหนดระยะห่างระหว่างคอลัมน์หรือแท่งในแผนภูมิ ช่วยให้คุณสามารถควบคุมลักษณะที่ปรากฏของแผนภูมิได้

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose[ที่นี่](https://releases.aspose.com/slides/java/).

## คำแนะนำทีละขั้นตอน

ทำตามขั้นตอนเหล่านี้เพื่อตั้งค่าความกว้างของช่องว่างในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java:

### 1. สร้างงานนำเสนอเปล่า

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// การสร้างการนำเสนอที่ว่างเปล่า
Presentation presentation = new Presentation();
```

### 2. เข้าถึงสไลด์แรก

```java
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. เพิ่มแผนภูมิที่มีข้อมูลเริ่มต้น

```java
// เพิ่มแผนภูมิที่มีข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. ตั้งค่าดัชนีของเอกสารข้อมูลแผนภูมิ

```java
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
```

### 5. รับสมุดงานข้อมูลแผนภูมิ

```java
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. เพิ่มซีรี่ส์ลงในแผนภูมิ

```java
// เพิ่มซีรีส์ลงในแผนภูมิ
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. เพิ่มหมวดหมู่ลงในแผนภูมิ

```java
// เพิ่มหมวดหมู่ลงในแผนภูมิ
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. เติมข้อมูลซีรี่ส์

```java
// เติมข้อมูลชุดข้อมูล
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// การเติมจุดข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. ตั้งค่าความกว้างของช่องว่าง

```java
// ตั้งค่าความกว้างของช่องว่าง
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. บันทึกการนำเสนอ

```java
// บันทึกงานนำเสนอด้วยแผนภูมิ
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับกำหนดความกว้างของช่องว่างใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// กำลังสร้างการนำเสนอที่ว่างเปล่า
Presentation presentation = new Presentation();
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
// รับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// เพิ่มซีรีส์
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// เพิ่ม Catrgories
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// ใช้แผนภูมิชุดที่สอง
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
//กำลังเติมข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// ตั้งค่า GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// บันทึกการนำเสนอด้วยแผนภูมิ
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีตั้งค่าความกว้างของช่องว่างสำหรับแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การปรับความกว้างของช่องว่างช่วยให้คุณสามารถควบคุมระยะห่างระหว่างคอลัมน์หรือแท่งในแผนภูมิของคุณ ซึ่งช่วยปรับปรุงการแสดงข้อมูลของคุณเป็นภาพ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนค่าความกว้างของช่องว่างได้อย่างไร

 หากต้องการเปลี่ยนความกว้างของช่องว่าง ให้ใช้`setGapWidth` วิธีการบน`ParentSeriesGroup`ของซีรีย์แผนภูมิ ในตัวอย่างที่ให้ไว้ เราตั้งค่าความกว้างของช่องว่างเป็น 50 แต่คุณสามารถปรับค่านี้เป็นระยะห่างที่คุณต้องการได้

### ฉันสามารถปรับแต่งคุณสมบัติแผนภูมิอื่นๆ ได้หรือไม่

ใช่ Aspose.Slides สำหรับ Java มีความสามารถที่ครอบคลุมสำหรับการปรับแต่งแผนภูมิ คุณสามารถแก้ไขคุณสมบัติแผนภูมิต่างๆ ได้ เช่น สี ป้าย ชื่อ และอื่นๆ ตรวจสอบการอ้างอิง API สำหรับข้อมูลโดยละเอียดเกี่ยวกับตัวเลือกการปรับแต่งแผนภูมิ

### ฉันจะหาแหล่งข้อมูลเพิ่มเติมและเอกสารประกอบได้จากที่ไหน?

 คุณสามารถค้นหาเอกสารที่ครอบคลุมและแหล่งข้อมูลเพิ่มเติมได้ใน Aspose.Slides สำหรับ Java บน[เว็บไซต์กำหนด](https://reference.aspose.com/slides/java/).