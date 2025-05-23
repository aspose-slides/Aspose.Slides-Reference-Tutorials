---
"description": "สำรวจ Aspose.Slides สำหรับ Java พร้อมบทช่วยสอนแบบทีละขั้นตอน สร้างแผนภูมิกรวยที่สวยงามและอื่น ๆ อีกมากมาย"
"linktitle": "แผนภูมิกรวยใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิกรวยใน Java Slides"
"url": "/th/java/chart-elements/funnel-chart-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิกรวยใน Java Slides


## บทนำสู่ Funnel Chart ใน Java Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีสร้างแผนภูมิกรวยโดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกรวยมีประโยชน์สำหรับการแสดงภาพกระบวนการตามลำดับที่มีขั้นตอนที่ค่อยๆ แคบลง เช่น การแปลงยอดขายหรือการรับลูกค้า

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides ลงในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

ขั้นแรกให้เริ่มต้นการนำเสนอและเพิ่มสไลด์ลงไปเพื่อวางแผนภูมิกรวย

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

อย่าลืมเปลี่ยน `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีโครงการของคุณ

## ขั้นตอนที่ 2: สร้างแผนภูมิกรวย

ตอนนี้เรามาสร้างแผนภูมิกรวยและตั้งค่ามิติบนสไลด์กัน

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

ในโค้ดด้านบน เราเพิ่มแผนภูมิกรวยลงในสไลด์แรกที่พิกัด (50, 50) โดยมีความกว้าง 500 และความสูง 400 พิกเซล

## ขั้นตอนที่ 3: กำหนดข้อมูลแผนภูมิ

ต่อไปเราจะกำหนดข้อมูลสำหรับแผนภูมิกรวยของเรา เราจะกำหนดหมวดหมู่และชุดข้อมูลสำหรับแผนภูมิ

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
```

ที่นี่ เราจะล้างข้อมูลที่มีอยู่ทั้งหมด เพิ่มหมวดหมู่ (ในกรณีนี้คือขั้นตอนของช่องทาง) และตั้งค่าป้ายกำกับของหมวดหมู่เหล่านั้น

## ขั้นตอนที่ 4: เพิ่มจุดข้อมูล

ตอนนี้เรามาเพิ่มจุดข้อมูลลงในชุดแผนภูมิกรวยกัน

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

ในขั้นตอนนี้ เราจะสร้างชุดข้อมูลสำหรับแผนภูมิกรวย และเพิ่มจุดข้อมูลที่แสดงค่าในแต่ละขั้นตอนของกรวย

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้าย เราบันทึกการนำเสนอพร้อมแผนภูมิกรวยลงในไฟล์ PowerPoint

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

อย่าลืมเปลี่ยน `"Your Document Directory"` ตามตำแหน่งที่คุณต้องการบันทึก

## โค้ดต้นฉบับสมบูรณ์สำหรับ Funnel Chart ใน Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 4"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 5"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 6"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
	series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
	pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราจะแสดงให้คุณเห็นถึงวิธีการสร้างแผนภูมิกรวยใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมได้โดยปรับสี ป้ายกำกับ และคุณสมบัติอื่นๆ ให้เหมาะกับความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะของแผนภูมิกรวยได้อย่างไร

คุณสามารถปรับแต่งลักษณะของแผนภูมิกรวยได้โดยการแก้ไขคุณสมบัติของแผนภูมิ ชุดข้อมูล และจุดข้อมูล โปรดดูเอกสาร Aspose.Slides เพื่อดูตัวเลือกการปรับแต่งโดยละเอียด

### ฉันสามารถเพิ่มหมวดหมู่หรือจุดข้อมูลเพิ่มเติมลงในแผนภูมิกรวยได้หรือไม่

ใช่ คุณสามารถเพิ่มหมวดหมู่และจุดข้อมูลเพิ่มเติมลงในแผนภูมิกรวยได้โดยขยายโค้ดในขั้นตอนที่ 3 และขั้นตอนที่ 4 ตามลำดับ

### เป็นไปได้ไหมที่จะเปลี่ยนประเภทของแผนภูมิเป็นอย่างอื่นนอกจากรูปกรวย?

ใช่ Aspose.Slides รองรับแผนภูมิประเภทต่างๆ คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแทนที่ `ChartType.Funnel` ด้วยประเภทแผนภูมิที่ต้องการในขั้นตอนที่ 2

### ฉันจะจัดการข้อผิดพลาดหรือข้อยกเว้นขณะทำงานกับ Aspose.Slides ได้อย่างไร

คุณสามารถจัดการข้อผิดพลาดและข้อยกเว้นโดยใช้กลไกการจัดการข้อยกเว้นมาตรฐานของ Java ตรวจสอบให้แน่ใจว่าคุณมีการจัดการข้อผิดพลาดที่เหมาะสมในโค้ดของคุณเพื่อจัดการกับสถานการณ์ที่ไม่คาดคิดได้อย่างเหมาะสม

### ฉันสามารถหาตัวอย่างและเอกสารเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน

คุณสามารถค้นหาตัวอย่างเพิ่มเติมและเอกสารโดยละเอียดเกี่ยวกับการใช้ Aspose.Slides สำหรับ Java ได้ใน [เอกสารประกอบ](https://docs-aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}