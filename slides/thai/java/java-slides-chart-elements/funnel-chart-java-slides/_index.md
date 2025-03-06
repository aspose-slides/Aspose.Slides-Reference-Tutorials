---
title: แผนภูมิช่องทางใน Java Slides
linktitle: แผนภูมิช่องทางใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: สำรวจ Aspose.Slides สำหรับ Java ด้วยบทช่วยสอนทีละขั้นตอน สร้างแผนภูมิกรวยที่น่าทึ่งและอื่นๆ อีกมากมาย
type: docs
weight: 14
url: /th/java/chart-elements/funnel-chart-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับแผนภูมิช่องทางใน Java Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีสร้างแผนภูมิกรวยโดยใช้ Aspose.Slides สำหรับ Java แผนภูมิกรวยมีประโยชน์ในการแสดงภาพกระบวนการตามลำดับโดยมีขั้นตอนที่แคบลงเรื่อยๆ เช่น การแปลงยอดขายหรือการได้มาซึ่งลูกค้า

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides ลงในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

ขั้นแรก มาเริ่มต้นการนำเสนอและเพิ่มสไลด์ในตำแหน่งที่เราจะวางแผนภูมิกรวยของเรา

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไดเร็กทอรีโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: สร้างแผนภูมิช่องทาง

ตอนนี้ เรามาสร้างแผนภูมิกรวยและกำหนดขนาดบนสไลด์กันดีกว่า

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Funnel, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

ในโค้ดด้านบน เราเพิ่มแผนภูมิกรวยลงในสไลด์แรกที่พิกัด (50, 50) โดยมีความกว้าง 500 และความสูง 400 พิกเซล

## ขั้นตอนที่ 3: กำหนดข้อมูลแผนภูมิ

ต่อไป เราจะกำหนดข้อมูลสำหรับแผนภูมิช่องทางของเรา เราจะกำหนดหมวดหมู่และซีรีส์สำหรับแผนภูมิ

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

ที่นี่ เราจะล้างข้อมูลที่มีอยู่ เพิ่มหมวดหมู่ (ในกรณีนี้คือขั้นตอนของช่องทาง) และตั้งค่าป้ายกำกับ

## ขั้นตอนที่ 4: เพิ่มจุดข้อมูล

ตอนนี้ เรามาเพิ่มจุดข้อมูลลงในชุดแผนภูมิกรวยของเรากัน

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Funnel);
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B1", 50));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B2", 100));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B3", 200));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B4", 300));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B5", 400));
    series.getDataPoints().addDataPointForFunnelSeries(wb.getCell(0, "B6", 500));
```

ในขั้นตอนนี้ เราสร้างชุดข้อมูลสำหรับแผนภูมิช่องทางของเรา และเพิ่มจุดข้อมูลที่แสดงถึงค่าในแต่ละขั้นตอนของช่องทาง

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้ายนี้ เราจะบันทึกงานนำเสนอด้วยแผนภูมิกรวยเป็นไฟล์ PowerPoint

```java
    pres.save(dataDir + "Funnel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Your Document Directory"` ด้วยตำแหน่งบันทึกที่คุณต้องการ

## กรอกซอร์สโค้ดสำหรับแผนภูมิช่องทางใน Java Slides

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

ในบทช่วยสอนนี้ เราได้แสดงวิธีสร้างแผนภูมิกรวยใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งแผนภูมิเพิ่มเติมได้โดยการปรับสี ป้ายชื่อ และคุณสมบัติอื่นๆ เพื่อให้เหมาะกับความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งรูปลักษณ์ของแผนภูมิช่องทางได้อย่างไร

คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิกรวยได้โดยการแก้ไขคุณสมบัติของแผนภูมิ ชุดข้อมูล และจุดข้อมูล โปรดดูเอกสารประกอบของ Aspose.Slides สำหรับตัวเลือกการปรับแต่งโดยละเอียด

### ฉันสามารถเพิ่มหมวดหมู่หรือจุดข้อมูลลงในแผนภูมิช่องทางได้หรือไม่

ได้ คุณสามารถเพิ่มหมวดหมู่และจุดข้อมูลลงในแผนภูมิช่องทางได้โดยขยายโค้ดในขั้นตอนที่ 3 และขั้นตอนที่ 4 ตามลำดับ

### เป็นไปได้ไหมที่จะเปลี่ยนประเภทแผนภูมิเป็นอย่างอื่นที่ไม่ใช่ช่องทาง

 ใช่ Aspose.Slides รองรับแผนภูมิประเภทต่างๆ คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแทนที่`ChartType.Funnel` ด้วยประเภทแผนภูมิที่ต้องการในขั้นตอนที่ 2

### ฉันจะจัดการกับข้อผิดพลาดหรือข้อยกเว้นขณะทำงานกับ Aspose.Slides ได้อย่างไร

คุณสามารถจัดการข้อผิดพลาดและข้อยกเว้นได้โดยใช้กลไกการจัดการข้อยกเว้น Java มาตรฐาน ตรวจสอบให้แน่ใจว่าคุณมีการจัดการข้อผิดพลาดที่เหมาะสมในโค้ดของคุณเพื่อจัดการกับสถานการณ์ที่ไม่คาดคิดได้อย่างสง่างาม

### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 คุณสามารถค้นหาตัวอย่างเพิ่มเติมและเอกสารประกอบโดยละเอียดเกี่ยวกับการใช้ Aspose.Slides สำหรับ Java ได้ใน[เอกสารประกอบ](https://docs.aspose.com/slides/java/).