---
"description": "สร้างแผนภูมิแผนผังต้นไม้ใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการแสดงภาพข้อมูลแบบลำดับชั้น"
"linktitle": "แผนภูมิแผนที่ต้นไม้ในสไลด์ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิแผนที่ต้นไม้ในสไลด์ Java"
"url": "/th/java/chart-creation/tree-map-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิแผนที่ต้นไม้ในสไลด์ Java


## สไลด์แนะนำแผนภูมิต้นไม้ใน Java

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการสร้างแผนภูมิ Tree Map ในงานนำเสนอ PowerPoint โดยใช้ไลบรารี Aspose.Slides สำหรับ Java แผนภูมิ Tree Map เป็นวิธีที่มีประสิทธิภาพในการแสดงข้อมูลแบบลำดับชั้น

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว

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

    // สร้างสาขา 2
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

    // บันทึกการนำเสนอด้วยแผนภูมิแผนที่ต้นไม้
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## โค้ดต้นฉบับสมบูรณ์สำหรับแผนภูมิแผนที่ต้นไม้ในสไลด์ Java
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

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการสร้างแผนภูมิ Tree Map ในงานนำเสนอ PowerPoint โดยใช้ไลบรารี Aspose.Slides สำหรับ Java แผนภูมิ Tree Map เป็นเครื่องมือที่มีประโยชน์สำหรับการแสดงข้อมูลแบบลำดับชั้น ทำให้การนำเสนอของคุณมีข้อมูลและน่าสนใจมากขึ้น

## คำถามที่พบบ่อย

### ฉันจะเพิ่มข้อมูลลงในแผนภูมิแผนที่ต้นไม้ได้อย่างไร

หากต้องการเพิ่มข้อมูลลงในแผนภูมิแผนที่ต้นไม้ ให้ใช้ `series.getDataPoints().addDataPointForTreemapSeries()` วิธีการส่งค่าข้อมูลเป็นพารามิเตอร์

### ฉันจะปรับแต่งลักษณะของแผนภูมิแผนที่ต้นไม้ได้อย่างไร

คุณสามารถปรับแต่งลักษณะของแผนภูมิแผนที่ต้นไม้ได้โดยการแก้ไขคุณสมบัติต่างๆ ของ `chart` และ `series` วัตถุ เช่น สี ป้ายกำกับ และเค้าโครง

### ฉันสามารถสร้างแผนภูมิแผนที่ต้นไม้หลายรายการในงานนำเสนอเดียวได้หรือไม่

ใช่ คุณสามารถสร้างแผนภูมิ Tree Map หลายรายการในงานนำเสนอเดียวได้โดยทำตามขั้นตอนเดียวกันและระบุตำแหน่งสไลด์ที่แตกต่างกัน

### ฉันจะบันทึกการนำเสนอโดยใช้แผนภูมิแผนที่ต้นไม้ได้อย่างไร

ใช้ `pres.save()` วิธีการบันทึกการนำเสนอด้วยแผนภูมิแผนที่ต้นไม้ในรูปแบบที่ต้องการ (เช่น PPTX)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}