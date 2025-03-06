---
title: แผนภูมิแผนที่ต้นไม้ใน Java Slides
linktitle: แผนภูมิแผนที่ต้นไม้ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: สร้างแผนภูมิแผนที่ต้นไม้ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดสำหรับการแสดงข้อมูลแบบลำดับชั้น
weight: 13
url: /th/java/chart-creation/tree-map-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## รู้เบื้องต้นเกี่ยวกับแผนภูมิแผนที่ต้นไม้ใน Java Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการสร้างแผนภูมิแผนผังต้นไม้ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับไลบรารี Java แผนภูมิแผนที่ต้นไม้เป็นวิธีที่มีประสิทธิภาพในการแสดงภาพข้อมูลแบบลำดับชั้น

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides for Java ในโปรเจ็กต์ Java ของคุณแล้ว

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: โหลดงานนำเสนอ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ขั้นตอนที่ 3: สร้างแผนภูมิแผนที่ต้นไม้

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    // สร้างสาขา 1
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // สร้างสาขาที่ 2
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // เพิ่มจุดข้อมูล
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
    series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);

    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));

    series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);

    // บันทึกงานนำเสนอด้วยแผนภูมิแผนผังต้นไม้
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## กรอกซอร์สโค้ดสำหรับแผนภูมิแผนที่ต้นไม้ใน Java Slides
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//สาขา 1
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//สาขา 2
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
	series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
	pres.save("Treemap.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีสร้างแผนภูมิแผนผังต้นไม้ในงานนำเสนอ PowerPoint โดยใช้ไลบรารี Aspose.Slides สำหรับ Java แผนภูมิแผนผังต้นไม้เป็นเครื่องมืออันทรงคุณค่าในการแสดงภาพข้อมูลแบบลำดับชั้น ทำให้การนำเสนอของคุณมีข้อมูลและมีส่วนร่วมมากขึ้น

## คำถามที่พบบ่อย

### ฉันจะเพิ่มข้อมูลลงในแผนภูมิแผนผังต้นไม้ได้อย่างไร

 หากต้องการเพิ่มข้อมูลลงในแผนภูมิแผนผังต้นไม้ ให้ใช้`series.getDataPoints().addDataPointForTreemapSeries()` วิธีการส่งผ่านค่าข้อมูลเป็นพารามิเตอร์

### ฉันจะปรับแต่งรูปลักษณ์ของแผนภูมิ Tree Map ได้อย่างไร

 คุณสามารถปรับแต่งลักษณะที่ปรากฏของแผนภูมิแผนผังต้นไม้ได้โดยการแก้ไขคุณสมบัติต่างๆ ของ`chart` และ`series`วัตถุ เช่น สี ป้ายกำกับ และเค้าโครง

### ฉันสามารถสร้างแผนภูมิแผนผังต้นไม้หลายแผนภูมิในการนำเสนอครั้งเดียวได้หรือไม่

ได้ คุณสามารถสร้างแผนภูมิแผนผังต้นไม้ได้หลายแผนภูมิในการนำเสนอครั้งเดียวโดยทำตามขั้นตอนเดียวกันและระบุตำแหน่งสไลด์ที่แตกต่างกัน

### ฉันจะบันทึกงานนำเสนอด้วยแผนภูมิแผนผังต้นไม้ได้อย่างไร

 ใช้`pres.save()` วิธีการบันทึกการนำเสนอด้วยแผนภูมิ Tree Map ในรูปแบบที่ต้องการ (เช่น PPTX)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
