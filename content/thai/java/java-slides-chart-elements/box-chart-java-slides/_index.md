---
title: แผนภูมิกล่องใน Java Slides
linktitle: แผนภูมิกล่องใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีสร้าง Box Charts ในงานนำเสนอ Java ด้วย Aspose.Slides มีคำแนะนำทีละขั้นตอนและซอร์สโค้ดเพื่อการแสดงภาพข้อมูลที่มีประสิทธิภาพ
type: docs
weight: 10
url: /th/java/chart-elements/box-chart-java-slides/
---

## รู้เบื้องต้นเกี่ยวกับแผนภูมิกล่องใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้าง Box Chart โดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกล่องมีประโยชน์ในการแสดงข้อมูลทางสถิติด้วยควอไทล์และค่าผิดปกติต่างๆ เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ดเพื่อช่วยคุณในการเริ่มต้น

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Aspose.Slides สำหรับไลบรารี Java ติดตั้งและกำหนดค่าแล้ว
- ตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

ในขั้นตอนนี้ เราเริ่มต้นวัตถุการนำเสนอโดยใช้เส้นทางไปยังไฟล์ PowerPoint ที่มีอยู่ ("test.pptx" ในตัวอย่างนี้)

## ขั้นตอนที่ 2: สร้างแผนภูมิกล่อง

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

ในขั้นตอนนี้ เราจะสร้างรูปร่าง Box Chart บนสไลด์แรกของงานนำเสนอ นอกจากนี้เรายังล้างหมวดหมู่และซีรีส์ที่มีอยู่ออกจากแผนภูมิด้วย

## ขั้นตอนที่ 3: กำหนดหมวดหมู่

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 ในขั้นตอนนี้ เรากำหนดหมวดหมู่สำหรับแผนภูมิกล่อง เราใช้`IChartDataWorkbook`เพื่อเพิ่มหมวดหมู่และติดป้ายกำกับให้เหมาะสม

## ขั้นตอนที่ 4: สร้างซีรี่ส์

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

ที่นี่ เราสร้างชุด BoxAndWhisker สำหรับแผนภูมิและกำหนดค่าตัวเลือกต่างๆ เช่น วิธีควอร์ไทล์ เส้นค่าเฉลี่ย เครื่องหมายเฉลี่ย จุดภายใน และจุดผิดปกติ

## ขั้นตอนที่ 5: เพิ่มจุดข้อมูล

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

ในขั้นตอนนี้ เราเพิ่มจุดข้อมูลลงในชุด BoxAndWhisker จุดข้อมูลเหล่านี้แสดงถึงข้อมูลทางสถิติสำหรับแผนภูมิ

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

สุดท้าย เราจะบันทึกงานนำเสนอด้วย Box Chart ลงในไฟล์ PowerPoint ใหม่ชื่อ "BoxAndWhisker.pptx"

ยินดีด้วย! คุณสร้างแผนภูมิกล่องโดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมได้โดยการปรับคุณสมบัติต่างๆ และเพิ่มจุดข้อมูลเพิ่มเติมตามต้องการ

## กรอกซอร์สโค้ดสำหรับแผนภูมิกล่องใน Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีสร้าง Box Chart โดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกล่องเป็นเครื่องมืออันทรงคุณค่าในการแสดงภาพข้อมูลทางสถิติ รวมถึงควอไทล์และค่าผิดปกติ เราได้ให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ดเพื่อช่วยคุณในการเริ่มต้นสร้าง Box Charts ในแอปพลิเคชัน Java ของคุณ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนรูปลักษณ์ของ Box Chart ได้อย่างไร?

คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิกล่องได้โดยการแก้ไขคุณสมบัติ เช่น ลักษณะของเส้น สี และแบบอักษร โปรดดูเอกสารประกอบ Aspose.Slides สำหรับ Java สำหรับรายละเอียดเกี่ยวกับการปรับแต่งแผนภูมิ

### ฉันสามารถเพิ่มชุดข้อมูลเพิ่มเติมลงใน Box Chart ได้หรือไม่

 ได้ คุณสามารถเพิ่มชุดข้อมูลหลายชุดลงในแผนภูมิกล่องได้โดยการสร้างเพิ่มเติม`IChartSeries` วัตถุและเพิ่มจุดข้อมูลลงไป

### QuartileMethodType.Exclusive หมายถึงอะไร

 ที่`QuartileMethodType.Exclusive` การตั้งค่าระบุว่าการคำนวณควอไทล์ควรทำโดยใช้วิธีพิเศษ คุณสามารถเลือกวิธีคำนวณควอไทล์ที่แตกต่างกันได้ ขึ้นอยู่กับข้อมูลและข้อกำหนดของคุณ