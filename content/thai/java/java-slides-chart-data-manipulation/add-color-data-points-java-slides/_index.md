---
title: เพิ่มสีให้กับจุดข้อมูลใน Java Slides
linktitle: เพิ่มสีให้กับจุดข้อมูลใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มสีให้กับจุดข้อมูลในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java
type: docs
weight: 10
url: /th/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการเพิ่มสีให้กับจุดข้อมูลใน Java Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการเพิ่มสีให้กับจุดข้อมูลในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้มีตัวอย่างซอร์สโค้ดเพื่อช่วยให้คุณบรรลุงานนี้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- สภาพแวดล้อมการพัฒนาจาวา
- Aspose.Slides สำหรับไลบรารี Java

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

ขั้นแรก เราจะสร้างงานนำเสนอใหม่โดยใช้ Aspose.Slides สำหรับ Java การนำเสนอนี้จะทำหน้าที่เป็นคอนเทนเนอร์สำหรับแผนภูมิของเรา

```java
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิซันเบิร์สต์

ตอนนี้ เรามาเพิ่มแผนภูมิ Sunburst ให้กับงานนำเสนอกันดีกว่า เราระบุประเภทแผนภูมิ ตำแหน่ง และขนาด

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## ขั้นตอนที่ 3: เข้าถึงจุดข้อมูล

 หากต้องการแก้ไขจุดข้อมูลในแผนภูมิ เราจำเป็นต้องเข้าถึง`IChartDataPointCollection` วัตถุ.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## ขั้นตอนที่ 4: ปรับแต่งจุดข้อมูล

ในขั้นตอนนี้ เราจะปรับแต่งจุดข้อมูลเฉพาะ ที่นี่ เรากำลังเปลี่ยนสีของจุดข้อมูลและกำหนดการตั้งค่าป้ายกำกับ

```java
//ปรับแต่งจุดข้อมูล 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// ปรับแต่งจุดข้อมูล 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้าย บันทึกงานนำเสนอด้วยแผนภูมิแบบกำหนดเอง

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณได้เพิ่มสีให้กับจุดข้อมูลเฉพาะในสไลด์ Java สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java

## กรอกซอร์สโค้ดเพื่อเพิ่มสีให้กับจุดข้อมูลใน Java Slides

```java
Presentation pres = new Presentation();
try
{
	// เส้นทางไปยังไดเร็กทอรีเอกสาร
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//ทำ
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีเพิ่มสีให้กับจุดข้อมูลในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งแผนภูมิและการนำเสนอเพิ่มเติมได้ตามความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีของจุดข้อมูลอื่นๆ ได้อย่างไร

หากต้องการเปลี่ยนสีของจุดข้อมูลอื่นๆ คุณสามารถปฏิบัติตามแนวทางที่คล้ายกันดังที่แสดงในขั้นตอนที่ 4 เข้าถึงจุดข้อมูลที่คุณต้องการปรับแต่งและแก้ไขการตั้งค่าสีและป้ายกำกับ

### ฉันสามารถปรับแต่งด้านอื่นๆ ของแผนภูมิได้หรือไม่

 ใช่ คุณสามารถปรับแต่งแง่มุมต่างๆ ของแผนภูมิได้ รวมถึงแบบอักษร ป้ายกำกับ ชื่อ และอื่นๆ อีกมากมาย อ้างถึง[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/) สำหรับตัวเลือกการปรับแต่งโดยละเอียด

### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน

คุณสามารถค้นหาตัวอย่างเพิ่มเติมและเอกสารประกอบโดยละเอียดเกี่ยวกับการใช้ Aspose.Slides สำหรับ Java ได้บน[เอกสาร Aspose.Slides](https://reference.aspose.com/slides/java/) เว็บไซต์.