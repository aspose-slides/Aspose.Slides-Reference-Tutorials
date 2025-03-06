---
title: แผนภูมิฮิสโตแกรมใน Java Slides
linktitle: แผนภูมิฮิสโตแกรมใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีการสร้างแผนภูมิฮิสโตแกรมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดสำหรับการแสดงข้อมูลเป็นภาพ
weight: 19
url: /th/java/chart-data-manipulation/histogram-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## รู้เบื้องต้นเกี่ยวกับแผนภูมิฮิสโตแกรมใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ เราจะแนะนำคุณตลอดขั้นตอนการสร้างแผนภูมิฮิสโตแกรมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java API แผนภูมิฮิสโตแกรมใช้เพื่อแสดงการกระจายข้อมูลในช่วงเวลาต่อเนื่องกัน

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งไลบรารี Aspose.Slides สำหรับ Java แล้ว คุณสามารถดาวน์โหลดได้จาก[เว็บไซต์กำหนด](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: เริ่มต้นโครงการของคุณ

สร้างโปรเจ็กต์ Java และรวมไลบรารี Aspose.Slides ในการขึ้นต่อกันของโปรเจ็กต์ของคุณ

## ขั้นตอนที่ 2: นำเข้าไลบรารีที่จำเป็น

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 3: โหลดงานนำเสนอที่มีอยู่

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Your Document Directory"` ด้วยเส้นทางจริงไปยังเอกสาร PowerPoint ของคุณ

## ขั้นตอนที่ 4: สร้างแผนภูมิฮิสโตแกรม

ตอนนี้ เรามาสร้างแผนภูมิฮิสโตแกรมบนสไลด์ในงานนำเสนอกันดีกว่า

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

 ในโค้ดนี้ ขั้นแรกเราจะล้างหมวดหมู่และซีรีส์ที่มีอยู่ออกจากแผนภูมิก่อน จากนั้นเราเพิ่มจุดข้อมูลให้กับซีรี่ส์โดยใช้`getDataPoints().addDataPointForHistogramSeries` วิธี. สุดท้าย เราตั้งค่าประเภทการรวมแกนนอนเป็นอัตโนมัติและบันทึกการนำเสนอ

## กรอกซอร์สโค้ดสำหรับแผนภูมิฮิสโตแกรมใน Java Slides

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

ในบทช่วยสอนนี้ เราได้สำรวจวิธีสร้างแผนภูมิฮิสโตแกรมในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java API แผนภูมิฮิสโตแกรมเป็นเครื่องมืออันทรงคุณค่าในการแสดงภาพการกระจายของข้อมูลในช่วงเวลาต่อเนื่องกัน และยังสามารถเป็นส่วนเสริมที่มีประสิทธิภาพในการนำเสนอของคุณ โดยเฉพาะอย่างยิ่งเมื่อต้องจัดการกับเนื้อหาทางสถิติหรือเชิงวิเคราะห์

## คำถามที่พบบ่อย

### ฉันจะติดตั้ง Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถดาวน์โหลดไลบรารี Aspose.Slides สำหรับ Java ได้จาก[ที่นี่](https://releases.aspose.com/slides/java/)- ทำตามคำแนะนำการติดตั้งที่ให้ไว้บนเว็บไซต์

### แผนภูมิฮิสโตแกรมมีไว้เพื่ออะไร?

แผนภูมิฮิสโตแกรมใช้เพื่อแสดงภาพการกระจายข้อมูลในช่วงเวลาต่อเนื่องกัน โดยทั่วไปจะใช้ในสถิติเพื่อแสดงการแจกแจงความถี่

### ฉันสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิฮิสโตแกรมได้หรือไม่

ใช่ คุณสามารถปรับแต่งลักษณะของแผนภูมิ รวมถึงสี ป้ายกำกับ และแกนได้โดยใช้ Aspose.Slides API
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
