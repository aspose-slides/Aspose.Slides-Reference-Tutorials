---
"description": "เรียนรู้วิธีตั้งค่าความกว้างของช่องว่างใน Java Slides ด้วย Aspose.Slides สำหรับ Java ปรับปรุงภาพแผนภูมิสำหรับการนำเสนอ PowerPoint ของคุณ"
"linktitle": "ตั้งค่าความกว้างช่องว่างใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าความกว้างช่องว่างใน Java Slides"
"url": "/th/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าความกว้างช่องว่างใน Java Slides


## บทนำเกี่ยวกับการตั้งค่าความกว้างช่องว่างใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการตั้งค่าความกว้างของช่องว่างสำหรับแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java ความกว้างของช่องว่างจะกำหนดระยะห่างระหว่างคอลัมน์หรือแท่งในแผนภูมิ ช่วยให้คุณควบคุมลักษณะที่ปรากฏของแผนภูมิได้

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าได้ติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จากเว็บไซต์ Aspose [ที่นี่](https://releases-aspose.com/slides/java/).

## คำแนะนำทีละขั้นตอน

ปฏิบัติตามขั้นตอนเหล่านี้เพื่อตั้งค่าความกว้างช่องว่างในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java:

### 1. สร้างการนำเสนอแบบว่างเปล่า

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";

// การสร้างการนำเสนอแบบว่างเปล่า 
Presentation presentation = new Presentation();
```

### 2. เข้าถึงสไลด์แรก

```java
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. เพิ่มแผนภูมิที่มีข้อมูลเริ่มต้น

```java
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. ตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ

```java
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
```

### 5. รับสมุดงานข้อมูลแผนภูมิ

```java
// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. เพิ่มซีรีส์ลงในแผนภูมิ

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

### 8. เติมข้อมูลชุดข้อมูล

```java
// เติมข้อมูลชุด
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// การเติมจุดข้อมูลแบบอนุกรม
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. ตั้งค่าความกว้างช่องว่าง

```java
// ตั้งค่าค่าความกว้างช่องว่าง
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. บันทึกการนำเสนอ

```java
// บันทึกการนำเสนอด้วยแผนภูมิ
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับกำหนดความกว้างช่องว่างใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// การสร้างการนำเสนอแบบว่างเปล่า 
Presentation presentation = new Presentation();
// เข้าถึงสไลด์แรก
ISlide slide = presentation.getSlides().get_Item(0);
// เพิ่มแผนภูมิด้วยข้อมูลเริ่มต้น
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// การตั้งค่าดัชนีของแผ่นข้อมูลแผนภูมิ
int defaultWorksheetIndex = 0;
// การรับแผ่นงานข้อมูลแผนภูมิ
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// เพิ่มซีรี่ย์
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// เพิ่มหมวดหมู่
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// มาดูแผนภูมิชุดที่สองกัน
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// ขณะนี้กำลังเพิ่มข้อมูลซีรีส์
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// ตั้งค่าค่า GapWidth
series.getParentSeriesGroup().setGapWidth(50);
// บันทึกการนำเสนอด้วยแผนภูมิ
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีตั้งค่าความกว้างของช่องว่างสำหรับแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java การปรับความกว้างของช่องว่างช่วยให้คุณควบคุมระยะห่างระหว่างคอลัมน์หรือแท่งในแผนภูมิได้ ทำให้การแสดงภาพข้อมูลของคุณดีขึ้น

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนค่าความกว้างของช่องว่างได้อย่างไร?

หากต้องการเปลี่ยนความกว้างของช่องว่าง ให้ใช้ `setGapWidth` วิธีการบน `ParentSeriesGroup` ของชุดแผนภูมิ ในตัวอย่างที่ให้มา เราตั้งค่าความกว้างของช่องว่างเป็น 50 แต่คุณสามารถปรับค่านี้ให้เป็นระยะห่างที่คุณต้องการได้

### ฉันสามารถปรับแต่งคุณสมบัติแผนภูมิอื่น ๆ ได้หรือไม่

ใช่ Aspose.Slides สำหรับ Java มีความสามารถมากมายสำหรับการปรับแต่งแผนภูมิ คุณสามารถปรับเปลี่ยนคุณสมบัติแผนภูมิต่างๆ เช่น สี ป้ายกำกับ ชื่อเรื่อง และอื่นๆ อีกมากมาย ตรวจสอบข้อมูลโดยละเอียดเกี่ยวกับตัวเลือกการปรับแต่งแผนภูมิได้จากเอกสารอ้างอิง API

### ฉันสามารถหาทรัพยากรและเอกสารเพิ่มเติมได้ที่ไหน

คุณสามารถค้นหาเอกสารประกอบที่ครอบคลุมและแหล่งข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ [เว็บไซต์อาโพส](https://reference-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}