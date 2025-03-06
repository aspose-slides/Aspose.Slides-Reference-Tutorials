---
title: ซ่อนข้อมูลจากแผนภูมิใน Java Slides
linktitle: ซ่อนข้อมูลจากแผนภูมิใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีซ่อนองค์ประกอบแผนภูมิใน Java Slides ด้วย Aspose.Slides สำหรับ Java ปรับแต่งการนำเสนอเพื่อความชัดเจนและความสวยงามด้วยคำแนะนำทีละขั้นตอนและซอร์สโค้ด
weight: 13
url: /th/java/customization-and-formatting/hide-information-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## รู้เบื้องต้นเกี่ยวกับการซ่อนข้อมูลจากแผนภูมิใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีซ่อนองค์ประกอบต่างๆ จากแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API คุณสามารถใช้โค้ดนี้เพื่อปรับแต่งแผนภูมิตามที่จำเป็นสำหรับการนำเสนอของคุณได้

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

 ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ในโครงการของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 2: สร้างงานนำเสนอใหม่

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 3: การเพิ่มแผนภูมิลงในสไลด์

เราจะเพิ่มแผนภูมิเส้นพร้อมเครื่องหมายลงในสไลด์ จากนั้นจึงดำเนินการซ่อนองค์ประกอบต่างๆ ของแผนภูมิ

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## ขั้นตอนที่ 4: ซ่อนชื่อแผนภูมิ

คุณสามารถซ่อนชื่อแผนภูมิได้ดังนี้:

```java
chart.setTitle(false);
```

## ขั้นตอนที่ 5: ซ่อนแกนค่า

หากต้องการซ่อนแกนค่า (แกนแนวตั้ง) ให้ใช้รหัสต่อไปนี้:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## ขั้นตอนที่ 6: ซ่อนแกนหมวดหมู่

หากต้องการซ่อนแกนประเภท (แกนนอน) ให้ใช้รหัสนี้:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## ขั้นตอนที่ 7: ซ่อนตำนาน

คุณสามารถซ่อนคำอธิบายแผนภูมิได้ดังนี้:

```java
chart.setLegend(false);
```

## ขั้นตอนที่ 8: ซ่อนเส้นกริดหลัก

หากต้องการซ่อนเส้นตารางหลักของแกนนอน คุณสามารถใช้โค้ดต่อไปนี้:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## ขั้นตอนที่ 9: ลบซีรี่ส์

หากคุณต้องการลบซีรี่ส์ทั้งหมดออกจากแผนภูมิ คุณสามารถใช้การวนซ้ำดังนี้:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## ขั้นตอนที่ 10: ปรับแต่งชุดแผนภูมิ

คุณสามารถปรับแต่งชุดแผนภูมิได้ตามต้องการ ในตัวอย่างนี้ เราเปลี่ยนสไตล์มาร์กเกอร์ ตำแหน่งป้ายข้อมูล ขนาดมาร์กเกอร์ สีของเส้น และสไตล์เส้นประ:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## ขั้นตอนที่ 11: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอลงในไฟล์:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณได้ซ่อนองค์ประกอบต่างๆ จากแผนภูมิใน Java Slides ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งแผนภูมิและการนำเสนอของคุณเพิ่มเติมได้ตามความต้องการเฉพาะของคุณ

## กรอกซอร์สโค้ดเพื่อซ่อนข้อมูลจากแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//การซ่อนชื่อแผนภูมิ
	chart.setTitle(false);
	///ซ่อนแกนค่า
	chart.getAxes().getVerticalAxis().setVisible(false);
	//การมองเห็นแกนหมวดหมู่
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//ซ่อนตำนาน
	chart.setLegend(false);
	//การซ่อน MajorGridLines
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//การตั้งค่าสีของเส้นอนุกรม
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## บทสรุป

ในคำแนะนำทีละขั้นตอนนี้ เราได้สำรวจวิธีซ่อนองค์ประกอบต่างๆ จากแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API สิ่งนี้มีประโยชน์อย่างเหลือเชื่อเมื่อคุณต้องการปรับแต่งแผนภูมิสำหรับการนำเสนอและทำให้ดูน่าดึงดูดยิ่งขึ้นหรือปรับให้เหมาะกับความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏขององค์ประกอบแผนภูมิเพิ่มเติมได้อย่างไร

คุณสามารถปรับแต่งคุณสมบัติต่างๆ ขององค์ประกอบแผนภูมิ เช่น สีเส้น สีเติม สไตล์มาร์กเกอร์ และอื่นๆ ได้โดยการเข้าถึงคุณสมบัติที่เกี่ยวข้องของชุดแผนภูมิ มาร์กเกอร์ ป้ายกำกับ และรูปแบบ

### ฉันสามารถซ่อนจุดข้อมูลเฉพาะในแผนภูมิได้หรือไม่

ได้ คุณสามารถซ่อนจุดข้อมูลเฉพาะได้โดยการจัดการข้อมูลในชุดแผนภูมิ คุณสามารถลบจุดข้อมูลหรือตั้งค่าเป็น null เพื่อซ่อนได้

### ฉันจะเพิ่มซีรี่ส์เพิ่มเติมลงในแผนภูมิได้อย่างไร

 คุณสามารถเพิ่มซีรี่ส์เพิ่มเติมลงในแผนภูมิได้โดยใช้`IChartData.getSeries().add` วิธีการและการระบุจุดข้อมูลสำหรับซีรี่ส์ใหม่

### เป็นไปได้ไหมที่จะเปลี่ยนประเภทแผนภูมิแบบไดนามิก?

ได้ คุณสามารถเปลี่ยนประเภทแผนภูมิแบบไดนามิกได้โดยการสร้างแผนภูมิใหม่ในประเภทที่ต้องการและคัดลอกข้อมูลจากแผนภูมิเก่าไปยังแผนภูมิใหม่

### ฉันจะเปลี่ยนชื่อแผนภูมิและป้ายกำกับแกนโดยทางโปรแกรมได้อย่างไร

คุณสามารถตั้งชื่อและป้ายกำกับของแผนภูมิและแกนได้โดยเข้าไปที่คุณสมบัติที่เกี่ยวข้องและตั้งค่าข้อความและการจัดรูปแบบที่ต้องการ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
