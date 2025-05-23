---
"description": "เรียนรู้วิธีเพิ่มสีลงในจุดข้อมูลในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java"
"linktitle": "เพิ่มสีให้กับจุดข้อมูลใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มสีให้กับจุดข้อมูลใน Java Slides"
"url": "/th/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มสีให้กับจุดข้อมูลใน Java Slides


## บทนำสู่การเพิ่มสีให้กับจุดข้อมูลใน Java Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการเพิ่มสีลงในจุดข้อมูลในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คำแนะนำทีละขั้นตอนนี้ประกอบด้วยตัวอย่างโค้ดต้นฉบับเพื่อช่วยให้คุณบรรลุภารกิจนี้ได้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นดังต่อไปนี้:

- สภาพแวดล้อมการพัฒนา Java
- Aspose.Slides สำหรับไลบรารี Java

## ขั้นตอนที่ 1: สร้างงานนำเสนอใหม่

ขั้นแรก เราจะสร้างงานนำเสนอใหม่โดยใช้ Aspose.Slides สำหรับ Java งานนำเสนอนี้จะทำหน้าที่เป็นคอนเทนเนอร์สำหรับแผนภูมิของเรา

```java
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิซันเบิร์สต์

ตอนนี้เรามาเพิ่มแผนภูมิ Sunburst ลงในงานนำเสนอกัน โดยระบุประเภท ตำแหน่ง และขนาดของแผนภูมิ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## ขั้นตอนที่ 3: การเข้าถึงจุดข้อมูล

ในการปรับเปลี่ยนจุดข้อมูลในแผนภูมิ เราจำเป็นต้องเข้าถึง `IChartDataPointCollection` วัตถุ.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## ขั้นตอนที่ 4: ปรับแต่งจุดข้อมูล

ในขั้นตอนนี้ เราจะกำหนดจุดข้อมูลเฉพาะเอง ที่นี่ เราจะเปลี่ยนสีของจุดข้อมูลและกำหนดค่าการตั้งค่าป้ายกำกับ

```java
// ปรับแต่งจุดข้อมูล 0
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

สุดท้ายให้บันทึกการนำเสนอด้วยแผนภูมิที่กำหนดเอง

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้เพิ่มสีให้กับจุดข้อมูลเฉพาะในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว

## โค้ดต้นฉบับสมบูรณ์สำหรับการเพิ่มสีให้กับจุดข้อมูลใน Java Slides

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
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//สิ่งที่ต้องทำ
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีเพิ่มสีให้กับจุดข้อมูลในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งแผนภูมิและการนำเสนอของคุณเพิ่มเติมตามความต้องการเฉพาะของคุณได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีของจุดข้อมูลอื่น ๆ ได้อย่างไร

หากต้องการเปลี่ยนสีของจุดข้อมูลอื่น คุณสามารถทำตามแนวทางเดียวกันได้ ดังที่แสดงในขั้นตอนที่ 4 เข้าถึงจุดข้อมูลที่คุณต้องการปรับแต่ง และแก้ไขการตั้งค่าสีและป้ายกำกับ

### ฉันสามารถปรับแต่งด้านอื่น ๆ ของแผนภูมิได้หรือไม่

ใช่ คุณสามารถปรับแต่งส่วนต่างๆ ของแผนภูมิได้ เช่น แบบอักษร ป้ายกำกับ ชื่อเรื่อง และอื่นๆ โปรดดูที่ [เอกสาร Aspose.Slides สำหรับ Java](https://reference.aspose.com/slides/java/) สำหรับตัวเลือกการปรับแต่งโดยละเอียด

### ฉันสามารถหาตัวอย่างและเอกสารเพิ่มเติมได้ที่ไหน

คุณสามารถค้นหาตัวอย่างเพิ่มเติมและเอกสารโดยละเอียดเกี่ยวกับการใช้ Aspose.Slides สำหรับ Java ได้ที่ [เอกสารประกอบ Aspose.Slides](https://reference.aspose.com/slides/java/) เว็บไซต์.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}