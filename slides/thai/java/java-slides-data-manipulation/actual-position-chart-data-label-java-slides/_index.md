---
"description": "เรียนรู้วิธีรับตำแหน่งจริงของป้ายข้อมูลแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับ"
"linktitle": "รับตำแหน่งจริงของป้ายข้อมูลแผนภูมิใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "รับตำแหน่งจริงของป้ายข้อมูลแผนภูมิใน Java Slides"
"url": "/th/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# รับตำแหน่งจริงของป้ายข้อมูลแผนภูมิใน Java Slides


## บทนำสู่การรับตำแหน่งจริงของป้ายข้อมูลแผนภูมิใน Java Slides

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีดึงตำแหน่งจริงของป้ายข้อมูลแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java เราจะสร้างโปรแกรม Java ที่สร้างการนำเสนอ PowerPoint ด้วยแผนภูมิ ปรับแต่งป้ายข้อมูล และเพิ่มรูปร่างที่แสดงตำแหน่งของป้ายข้อมูลเหล่านี้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว

## ขั้นตอนที่ 1: สร้างการนำเสนอ PowerPoint

ขั้นแรก ให้สร้างงานนำเสนอ PowerPoint ใหม่และเพิ่มแผนภูมิลงไป เราจะปรับแต่งป้ายข้อมูลของแผนภูมิในภายหลังในบทช่วยสอนนี้

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

## ขั้นตอนที่ 2: ปรับแต่งป้ายข้อมูล
ตอนนี้เรามาปรับแต่งป้ายข้อมูลสำหรับชุดแผนภูมิกัน เราจะกำหนดตำแหน่งและแสดงค่าต่างๆ

```java
try {
    // ... (โค้ดก่อนหน้า)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (รหัสที่เหลืออยู่)
} finally {
    if (pres != null) pres.dispose();
}
```

## ขั้นตอนที่ 3: รับตำแหน่งจริงของป้ายข้อมูล
ในขั้นตอนนี้ เราจะวนซ้ำผ่านจุดข้อมูลของชุดแผนภูมิ และดึงตำแหน่งจริงของป้ายข้อมูลซึ่งมีค่ามากกว่า 4 จากนั้นเราจะเพิ่มวงรีเพื่อแสดงตำแหน่งเหล่านี้

```java
try {
    // ... (โค้ดก่อนหน้า)
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
สุดท้ายให้บันทึกการนำเสนอที่สร้างขึ้นลงในไฟล์

```java
try {
    // ... (โค้ดก่อนหน้า)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## โค้ดต้นฉบับที่สมบูรณ์สำหรับรับตำแหน่งจริงของป้ายข้อมูลแผนภูมิใน Java Slides

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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//สิ่งที่ต้องทำ
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

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีการดึงตำแหน่งจริงของป้ายข้อมูลแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java ตอนนี้คุณสามารถใช้ความรู้เหล่านี้เพื่อปรับปรุงการนำเสนอ PowerPoint ของคุณด้วยป้ายข้อมูลที่กำหนดเองและการแสดงภาพตำแหน่งของป้ายข้อมูลเหล่านั้น

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งป้ายข้อมูลในแผนภูมิได้อย่างไร

หากต้องการปรับแต่งป้ายข้อมูลในแผนภูมิ คุณสามารถใช้ `setDefaultDataLabelFormat` วิธีการบนชุดแผนภูมิและตั้งค่าคุณสมบัติเช่นตำแหน่งและการมองเห็น ตัวอย่างเช่น:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### ฉันจะเพิ่มรูปร่างเพื่อแสดงตำแหน่งป้ายข้อมูลได้อย่างไร

คุณสามารถทำซ้ำผ่านจุดข้อมูลของชุดแผนภูมิและใช้ `getActualX`- `getActualY`- `getActualWidth`, และ `getActualHeight` วิธีการของป้ายข้อมูลเพื่อรับตำแหน่ง จากนั้นคุณสามารถเพิ่มรูปร่างโดยใช้ `addAutoShape` วิธีการ นี่คือตัวอย่าง:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### ฉันสามารถบันทึกการนำเสนอที่สร้างขึ้นได้อย่างไร

คุณสามารถบันทึกการนำเสนอที่สร้างขึ้นได้โดยใช้ `save` วิธีการ ระบุเส้นทางไฟล์ที่ต้องการและ `SaveFormat` เป็นพารามิเตอร์ เช่น:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}