---
"description": "เรียนรู้วิธีสร้างแผนภูมิฮิสโทแกรมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการแสดงภาพข้อมูล"
"linktitle": "แผนภูมิฮิสโทแกรมในสไลด์ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิฮิสโทแกรมในสไลด์ Java"
"url": "/th/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิฮิสโทแกรมในสไลด์ Java


## การแนะนำแผนภูมิฮิสโทแกรมใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณเกี่ยวกับขั้นตอนการสร้างแผนภูมิฮิสโทแกรมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides for Java API แผนภูมิฮิสโทแกรมใช้เพื่อแสดงการกระจายของข้อมูลในช่วงเวลาต่อเนื่อง

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าได้ติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จาก [เว็บไซต์อาโพส](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: เริ่มต้นโครงการของคุณ

สร้างโครงการ Java และรวมไลบรารี Aspose.Slides ลงในส่วนที่ต้องมีของโครงการของคุณ

## ขั้นตอนที่ 2: นำเข้าไลบรารีที่จำเป็น

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 3: โหลดงานนำเสนอที่มีอยู่

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

อย่าลืมเปลี่ยน `"Your Document Directory"` พร้อมเส้นทางจริงไปยังเอกสาร PowerPoint ของคุณ

## ขั้นตอนที่ 4: สร้างแผนภูมิฮิสโทแกรม

ตอนนี้เรามาสร้างแผนภูมิฮิสโทแกรมบนสไลด์ในงานนำเสนอกัน

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // เพิ่มจุดข้อมูลลงในชุดข้อมูล
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // ตั้งค่าประเภทการรวมแกนแนวนอนเป็นอัตโนมัติ
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // บันทึกการนำเสนอ
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

ในโค้ดนี้ ก่อนอื่นเราจะล้างหมวดหมู่และชุดข้อมูลที่มีอยู่ทั้งหมดออกจากแผนภูมิ จากนั้นจึงเพิ่มจุดข้อมูลลงในชุดข้อมูลโดยใช้ `getDataPoints().addDataPointForHistogramSeries` วิธีการ ในที่สุด เราตั้งค่าประเภทการรวมแกนแนวนอนเป็นอัตโนมัติ และบันทึกการนำเสนอ

## โค้ดต้นฉบับสมบูรณ์สำหรับแผนภูมิฮิสโทแกรมในสไลด์ Java

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้ศึกษาวิธีการสร้างแผนภูมิฮิสโทแกรมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides for Java API แผนภูมิฮิสโทแกรมเป็นเครื่องมือที่มีประโยชน์สำหรับการแสดงภาพการกระจายของข้อมูลในช่วงเวลาต่อเนื่อง และสามารถเป็นส่วนเสริมที่มีประสิทธิภาพสำหรับงานนำเสนอของคุณ โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับเนื้อหาทางสถิติหรือการวิเคราะห์

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร?

คุณสามารถดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java ได้จาก [ที่นี่](https://releases.aspose.com/slides/java/). ทำตามคำแนะนำการติดตั้งที่อยู่ในเว็บไซต์

### แผนภูมิฮิสโทแกรมใช้ทำอะไร?

แผนภูมิฮิสโทแกรมใช้เพื่อแสดงการกระจายของข้อมูลในช่วงเวลาต่อเนื่อง โดยทั่วไปจะใช้ในสถิติเพื่อแสดงการกระจายความถี่

### ฉันสามารถปรับแต่งลักษณะของแผนภูมิฮิสโทแกรมได้หรือไม่

ใช่ คุณสามารถปรับแต่งลักษณะของแผนภูมิ รวมถึงสี ป้ายกำกับ และแกน โดยใช้ Aspose.Slides API

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}