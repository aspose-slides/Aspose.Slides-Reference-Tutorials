---
"description": "เรียนรู้วิธีสร้าง Box Charts ในงานนำเสนอ Java ด้วย Aspose.Slides พร้อมคำแนะนำทีละขั้นตอนและโค้ดต้นฉบับสำหรับการแสดงภาพข้อมูลอย่างมีประสิทธิภาพ"
"linktitle": "แผนภูมิกล่องใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิกล่องใน Java Slides"
"url": "/th/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิกล่องใน Java Slides


## บทนำสู่ Box Chart ใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างแผนภูมิกล่องโดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกล่องมีประโยชน์สำหรับการแสดงภาพข้อมูลสถิติที่มีค่าควอร์ไทล์และค่าผิดปกติต่างๆ เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับโค้ดต้นฉบับเพื่อช่วยคุณเริ่มต้นใช้งาน

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้งและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java แล้ว
- การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

ในขั้นตอนนี้ เราจะเริ่มต้นวัตถุการนำเสนอโดยใช้เส้นทางไปยังไฟล์ PowerPoint ที่มีอยู่ ("test.pptx" ในตัวอย่างนี้)

## ขั้นตอนที่ 2: สร้างแผนภูมิกล่อง

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

ในขั้นตอนนี้ เราจะสร้างรูปร่างแผนภูมิกล่องบนสไลด์แรกของการนำเสนอ นอกจากนี้ เรายังล้างหมวดหมู่และชุดที่มีอยู่ทั้งหมดออกจากแผนภูมิด้วย

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

ในขั้นตอนนี้ เราจะกำหนดหมวดหมู่สำหรับแผนภูมิกล่อง เราใช้ `IChartDataWorkbook` เพื่อเพิ่มหมวดหมู่และจัดป้ายกำกับให้เหมาะสม

## ขั้นตอนที่ 4: สร้างซีรีส์

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

ที่นี่ เราสร้างชุด BoxAndWhisker สำหรับแผนภูมิและกำหนดค่าตัวเลือกต่างๆ เช่น วิธีควอร์ไทล์ เส้นค่ากลาง เครื่องหมายค่ากลาง จุดด้านใน และจุดค่าผิดปกติ

## ขั้นตอนที่ 5: เพิ่มจุดข้อมูล

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

ในขั้นตอนนี้ เราจะเพิ่มจุดข้อมูลลงในซีรีส์ BoxAndWhisker จุดข้อมูลเหล่านี้แสดงถึงข้อมูลทางสถิติสำหรับแผนภูมิ

## ขั้นตอนที่ 6: บันทึกการนำเสนอ

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

ในที่สุด เราบันทึกการนำเสนอด้วย Box Chart ลงในไฟล์ PowerPoint ใหม่ชื่อ "BoxAndWhisker.pptx"

ขอแสดงความยินดี! คุณได้สร้างแผนภูมิกล่องโดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมได้โดยปรับคุณสมบัติต่างๆ และเพิ่มจุดข้อมูลเพิ่มเติมตามต้องการ

## โค้ดต้นฉบับสมบูรณ์สำหรับ Box Chart ใน Java Slides

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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีการสร้างแผนภูมิกล่องโดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกล่องเป็นเครื่องมือที่มีประโยชน์สำหรับการแสดงภาพข้อมูลทางสถิติ รวมถึงควอร์ไทล์และค่าผิดปกติ เราได้จัดทำคู่มือทีละขั้นตอนพร้อมโค้ดต้นฉบับเพื่อช่วยให้คุณเริ่มต้นสร้างแผนภูมิกล่องในแอปพลิเคชัน Java ของคุณได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนรูปลักษณ์ของ Box Chart ได้อย่างไร?

คุณสามารถปรับแต่งลักษณะของแผนภูมิกล่องได้โดยการแก้ไขคุณสมบัติ เช่น สไตล์เส้น สี และแบบอักษร ดูเอกสาร Aspose.Slides สำหรับ Java เพื่อดูรายละเอียดเกี่ยวกับการปรับแต่งแผนภูมิ

### ฉันสามารถเพิ่มชุดข้อมูลเพิ่มเติมลงในแผนภูมิกล่องได้หรือไม่

ใช่ คุณสามารถเพิ่มชุดข้อมูลหลายชุดลงในแผนภูมิกล่องได้โดยการสร้างเพิ่มเติม `IChartSeries` วัตถุและการเพิ่มจุดข้อมูลลงไป

### QuartileMethodType.Exclusive หมายถึงอะไร

การ `QuartileMethodType.Exclusive` การตั้งค่าระบุว่าการคำนวณควอร์ไทล์ควรทำโดยใช้เมธอดพิเศษ คุณสามารถเลือกวิธีคำนวณควอร์ไทล์ที่แตกต่างกันได้ขึ้นอยู่กับข้อมูลและความต้องการของคุณ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}