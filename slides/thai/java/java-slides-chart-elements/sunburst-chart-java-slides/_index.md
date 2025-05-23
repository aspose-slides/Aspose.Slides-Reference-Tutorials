---
"description": "สร้างแผนภูมิ Sunburst ที่สวยงามใน Java Slides ด้วย Aspose.Slides เรียนรู้การสร้างแผนภูมิและการจัดการข้อมูลแบบทีละขั้นตอน"
"linktitle": "แผนภูมิ Sunburst ใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "แผนภูมิ Sunburst ใน Java Slides"
"url": "/th/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# แผนภูมิ Sunburst ใน Java Slides


## การแนะนำแผนภูมิ Sunburst ใน Java สไลด์ด้วย Aspose.Slides

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีสร้างแผนภูมิซันเบิร์สต์ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides for Java API แผนภูมิซันเบิร์สต์เป็นแผนภูมิเชิงรัศมีที่ใช้แสดงข้อมูลตามลำดับชั้น เราจะให้คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าได้ติดตั้งและกำหนดค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: นำเข้าไลบรารีที่จำเป็น

ขั้นแรก นำเข้าไลบรารีที่จำเป็นสำหรับการใช้งาน Aspose.Slides และสร้างแผนภูมิ Sunburst ในแอปพลิเคชัน Java ของคุณ

```java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: เริ่มต้นการนำเสนอ

เริ่มต้นการนำเสนอ PowerPoint และระบุไดเร็กทอรีที่จะบันทึกไฟล์การนำเสนอของคุณ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## ขั้นตอนที่ 3: สร้างแผนภูมิ Sunburst

สร้างแผนภูมิ Sunburst บนสไลด์ โดยระบุตำแหน่ง (X, Y) และขนาด (ความกว้าง ความสูง) ของแผนภูมิ

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## ขั้นตอนที่ 4: เตรียมข้อมูลแผนภูมิ

ล้างหมวดหมู่และชุดข้อมูลที่มีอยู่จากแผนภูมิ และสร้างเวิร์กบุ๊กข้อมูลสำหรับแผนภูมิ

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## ขั้นตอนที่ 5: กำหนดลำดับชั้นของแผนภูมิ

กำหนดโครงสร้างลำดับชั้นของแผนภูมิ Sunburst คุณสามารถเพิ่มกิ่งก้าน ลำต้น และใบเป็นหมวดหมู่ได้

```java
// สาขา 1
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// สาขา 2
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## ขั้นตอนที่ 6: เพิ่มข้อมูลลงในแผนภูมิ

เพิ่มจุดข้อมูลลงในชุดแผนภูมิ Sunburst

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกการนำเสนอด้วยแผนภูมิ Sunburst

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับแผนภูมิ Sunburst ใน Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
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
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการสร้างแผนภูมิ Sunburst ในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java API คุณได้เรียนรู้วิธีการเริ่มต้นงานนำเสนอ สร้างแผนภูมิ กำหนดลำดับชั้นของแผนภูมิ เพิ่มจุดข้อมูล และบันทึกงานนำเสนอแล้ว ตอนนี้คุณสามารถใช้ความรู้เหล่านี้เพื่อสร้างแผนภูมิ Sunburst แบบโต้ตอบและให้ข้อมูลในแอปพลิเคชัน Java ของคุณได้แล้ว

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งรูปลักษณ์ของแผนภูมิ Sunburst ได้อย่างไร

คุณสามารถปรับแต่งลักษณะของแผนภูมิ Sunburst ได้โดยการแก้ไขคุณสมบัติ เช่น สี ป้ายกำกับ และรูปแบบ โปรดดูเอกสาร Aspose.Slides เพื่อดูตัวเลือกการปรับแต่งโดยละเอียด

### ฉันสามารถเพิ่มจุดข้อมูลเพิ่มเติมลงในแผนภูมิได้หรือไม่

ใช่ คุณสามารถเพิ่มจุดข้อมูลเพิ่มเติมลงในแผนภูมิได้โดยใช้ `series.getDataPoints().addDataPointForSunburstSeries()` วิธีการสำหรับแต่ละจุดข้อมูลที่คุณต้องการรวมไว้

### ฉันจะเพิ่มคำอธิบายเครื่องมือลงในแผนภูมิ Sunburst ได้อย่างไร

หากต้องการเพิ่มคำอธิบายเครื่องมือลงในแผนภูมิ Sunburst คุณสามารถตั้งค่ารูปแบบป้ายข้อมูลเพื่อแสดงข้อมูลเพิ่มเติม เช่น ค่าหรือคำอธิบาย เมื่อวางเมาส์เหนือส่วนต่างๆ ของแผนภูมิ

### เป็นไปได้ไหมที่จะสร้างแผนภูมิ Sunburst แบบโต้ตอบพร้อมไฮเปอร์ลิงก์?

ใช่ คุณสามารถสร้างแผนภูมิ Sunburst แบบโต้ตอบที่มีไฮเปอร์ลิงก์ได้โดยการเพิ่มไฮเปอร์ลิงก์ไปยังองค์ประกอบหรือกลุ่มแผนภูมิเฉพาะ โปรดอ่านเอกสาร Aspose.Slides เพื่อดูรายละเอียดเกี่ยวกับการเพิ่มไฮเปอร์ลิงก์

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}