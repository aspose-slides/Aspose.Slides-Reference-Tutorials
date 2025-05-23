---
"description": "สร้างแผนภูมิแผนที่อันน่าทึ่งในงานนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนและซอร์สโค้ดสำหรับนักพัฒนา Java"
"linktitle": "แผนภูมิแผนที่ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิแผนที่ใน Java Slides"
"url": "/th/java/chart-elements/map-chart-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิแผนที่ใน Java Slides


## การแนะนำแผนภูมิแผนที่ใน Java สไลด์ที่ใช้ Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างแผนภูมิแผนที่ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แผนภูมิแผนที่เป็นวิธีที่ยอดเยี่ยมในการแสดงข้อมูลทางภูมิศาสตร์ในงานนำเสนอของคุณ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: ตั้งค่าโครงการของคุณ

ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าโครงการ Java ของคุณแล้ว และเพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในคลาสพาธของโครงการของคุณแล้ว

## ขั้นตอนที่ 2: สร้างการนำเสนอ PowerPoint

ก่อนอื่นมาสร้างการนำเสนอ PowerPoint ใหม่กันก่อน

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 3: เพิ่มแผนภูมิแผนที่

ตอนนี้เราจะเพิ่มแผนภูมิแผนที่ลงในการนำเสนอ

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## ขั้นตอนที่ 4: เพิ่มข้อมูลลงในแผนภูมิแผนที่

มาเพิ่มข้อมูลลงในแผนภูมิกันเถอะ เราจะสร้างชุดข้อมูลและเพิ่มจุดข้อมูลลงไป

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## ขั้นตอนที่ 5: เพิ่มหมวดหมู่

เราจำเป็นต้องเพิ่มหมวดหมู่ลงในแผนภูมิแผนที่เพื่อแสดงภูมิภาคทางภูมิศาสตร์ที่แตกต่างกัน

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## ขั้นตอนที่ 6: ปรับแต่งจุดข้อมูล

คุณสามารถปรับแต่งจุดข้อมูลแต่ละจุดได้ ในตัวอย่างนี้ เราจะเปลี่ยนสีและค่าของจุดข้อมูลเฉพาะ

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

สุดท้ายให้บันทึกการนำเสนอด้วยแผนภูมิแผนที่

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้สร้างแผนภูมิแผนที่ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แล้ว คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมและสำรวจฟีเจอร์อื่นๆ ที่ Aspose.Slides นำเสนอเพื่อปรับปรุงงานนำเสนอของคุณ

## โค้ดต้นฉบับสมบูรณ์สำหรับแผนภูมิแผนที่ในสไลด์ Java

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//สร้างแผนภูมิเปล่า
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//เพิ่มซีรีส์และจุดข้อมูลบางจุด
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//เพิ่มหมวดหมู่
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//การเปลี่ยนแปลงค่าจุดข้อมูล
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//ตั้งค่าลักษณะจุดข้อมูล
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราจะแนะนำขั้นตอนการสร้างแผนภูมิแผนที่ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แผนภูมิแผนที่เป็นวิธีที่มีประสิทธิภาพในการแสดงข้อมูลทางภูมิศาสตร์ ทำให้การนำเสนอของคุณน่าสนใจและให้ข้อมูลมากขึ้น มาสรุปขั้นตอนสำคัญๆ กัน:

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิแผนที่ได้อย่างไร?

คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแทนที่ `ChartType.Map` ด้วยประเภทแผนภูมิที่ต้องการเมื่อสร้างแผนภูมิในขั้นตอนที่ 3

### ฉันจะปรับแต่งลักษณะของแผนภูมิแผนที่ได้อย่างไร

คุณสามารถปรับแต่งลักษณะของแผนภูมิได้โดยการแก้ไขคุณสมบัติของ `dataPoint` วัตถุในขั้นตอนที่ 6 คุณสามารถเปลี่ยนสี ค่า และอื่นๆ ได้

### ฉันสามารถเพิ่มจุดข้อมูลและหมวดหมู่เพิ่มเติมได้หรือไม่

ใช่ คุณสามารถเพิ่มจุดข้อมูลและหมวดหมู่ได้มากเท่าที่ต้องการ เพียงใช้ `series.getDataPoints().addDataPointForMapSeries()` และ `chart.getChartData().getCategories().add()` วิธีการเพิ่มพวกมัน

### ฉันจะรวม Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ของฉันได้อย่างไร

ดาวน์โหลดห้องสมุดได้จาก [ที่นี่](https://releases.aspose.com/slides/java/) และเพิ่มลงใน classpath ของโปรเจ็กต์ของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}