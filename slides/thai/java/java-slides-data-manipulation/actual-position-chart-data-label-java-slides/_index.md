---
title: รับตำแหน่งที่แท้จริงของป้ายกำกับข้อมูลแผนภูมิใน Java Slides
linktitle: รับตำแหน่งที่แท้จริงของป้ายกำกับข้อมูลแผนภูมิใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีรับตำแหน่งที่แท้จริงของป้ายกำกับข้อมูลแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ด
weight: 18
url: /th/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## ข้อมูลเบื้องต้นเกี่ยวกับการรับตำแหน่งที่แท้จริงของป้ายกำกับข้อมูลแผนภูมิใน Java Slides

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีดึงข้อมูลตำแหน่งจริงของป้ายกำกับข้อมูลแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java เราจะสร้างโปรแกรม Java ที่สร้างงานนำเสนอ PowerPoint ด้วยแผนภูมิ ปรับแต่งป้ายข้อมูล จากนั้นเพิ่มรูปร่างที่แสดงถึงตำแหน่งของป้ายข้อมูลเหล่านี้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides for Java ในโปรเจ็กต์ Java ของคุณแล้ว

## ขั้นตอนที่ 1: สร้างงานนำเสนอ PowerPoint

ขั้นแรก มาสร้างงานนำเสนอ PowerPoint ใหม่และเพิ่มแผนภูมิลงไป เราจะปรับแต่งป้ายกำกับข้อมูลของแผนภูมิในภายหลังในบทช่วยสอน

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## ขั้นตอนที่ 2: ปรับแต่งป้ายกำกับข้อมูล
ตอนนี้ มาปรับแต่งป้ายชื่อข้อมูลสำหรับชุดแผนภูมิกันดีกว่า เราจะกำหนดตำแหน่งและแสดงค่า

```java
try {
    // ... (รหัสก่อนหน้า)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (รหัสที่เหลืออยู่)
} finally {
    if (pres != null) pres.dispose();
}
```

## ขั้นตอนที่ 3: รับตำแหน่งที่แท้จริงของป้ายกำกับข้อมูล
ในขั้นตอนนี้ เราจะวนซ้ำจุดข้อมูลของชุดแผนภูมิและดึงข้อมูลตำแหน่งจริงของป้ายกำกับข้อมูลที่มีค่ามากกว่า 4 จากนั้นเราจะเพิ่มจุดไข่ปลาเพื่อแสดงตำแหน่งเหล่านี้

```java
try {
    // ... (รหัสก่อนหน้า)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (รหัสที่เหลืออยู่)
} finally {
    if (pres != null) pres.dispose();
}
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ
สุดท้าย ให้บันทึกงานนำเสนอที่สร้างขึ้นลงในไฟล์

```java
try {
    // ... (รหัสก่อนหน้า)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## กรอกซอร์สโค้ดเพื่อรับตำแหน่งที่แท้จริงของป้ายกำกับข้อมูลแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//ทำ
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีดึงข้อมูลตำแหน่งจริงของป้ายกำกับข้อมูลแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java ตอนนี้คุณสามารถใช้ความรู้นี้เพื่อปรับปรุงงานนำเสนอ PowerPoint ของคุณด้วยป้ายข้อมูลที่กำหนดเองและการแสดงตำแหน่งของพวกเขาด้วยภาพ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งป้ายกำกับข้อมูลในแผนภูมิได้อย่างไร

 หากต้องการปรับแต่งป้ายกำกับข้อมูลในแผนภูมิ คุณสามารถใช้`setDefaultDataLabelFormat` บนชุดแผนภูมิและตั้งค่าคุณสมบัติ เช่น ตำแหน่งและการมองเห็น ตัวอย่างเช่น:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### ฉันจะเพิ่มรูปร่างเพื่อแสดงตำแหน่งป้ายกำกับข้อมูลได้อย่างไร

 คุณสามารถวนซ้ำจุดข้อมูลของชุดแผนภูมิและใช้`getActualX`, `getActualY`, `getActualWidth` , และ`getActualHeight`วิธีการของฉลากข้อมูลเพื่อให้ได้ตำแหน่ง จากนั้นคุณสามารถเพิ่มรูปร่างโดยใช้`addAutoShape` วิธี. นี่คือตัวอย่าง:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### ฉันจะบันทึกงานนำเสนอที่สร้างขึ้นได้อย่างไร

 คุณสามารถบันทึกการนำเสนอที่สร้างขึ้นได้โดยใช้`save` วิธี. ระบุเส้นทางไฟล์ที่ต้องการและไฟล์`SaveFormat` เป็นพารามิเตอร์ ตัวอย่างเช่น:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
