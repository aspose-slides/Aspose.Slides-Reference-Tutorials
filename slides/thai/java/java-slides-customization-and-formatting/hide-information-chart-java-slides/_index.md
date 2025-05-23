---
"description": "เรียนรู้วิธีซ่อนองค์ประกอบแผนภูมิใน Java Slides ด้วย Aspose.Slides สำหรับ Java ปรับแต่งการนำเสนอเพื่อความชัดเจนและความสวยงามด้วยคำแนะนำทีละขั้นตอนและโค้ดต้นฉบับ"
"linktitle": "ซ่อนข้อมูลจากแผนภูมิใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ซ่อนข้อมูลจากแผนภูมิใน Java Slides"
"url": "/th/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ซ่อนข้อมูลจากแผนภูมิใน Java Slides


## บทนำการซ่อนข้อมูลจากแผนภูมิใน Java Slides

ในบทช่วยสอนนี้ เราจะมาดูวิธีการซ่อนองค์ประกอบต่างๆ จากแผนภูมิใน Java Slides โดยใช้ Aspose.Slides for Java API คุณสามารถใช้โค้ดนี้เพื่อปรับแต่งแผนภูมิตามความจำเป็นสำหรับการนำเสนอของคุณ

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ลงในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 2: สร้างงานนำเสนอใหม่

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 3: การเพิ่มแผนภูมิลงในสไลด์

เราจะเพิ่มแผนภูมิเส้นพร้อมเครื่องหมายลงในสไลด์และดำเนินการซ่อนองค์ประกอบต่างๆ ของแผนภูมิ

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

หากต้องการซ่อนแกนค่า (แกนแนวตั้ง) ให้ใช้โค้ดดังต่อไปนี้:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## ขั้นตอนที่ 6: ซ่อนแกนหมวดหมู่

หากต้องการซ่อนแกนหมวดหมู่ (แกนแนวนอน) ให้ใช้รหัสนี้:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## ขั้นตอนที่ 7: ซ่อนคำอธิบาย

คุณสามารถซ่อนตำนานของแผนภูมิได้ดังนี้:

```java
chart.setLegend(false);
```

## ขั้นตอนที่ 8: ซ่อนเส้นกริดหลัก

หากต้องการซ่อนเส้นกริดหลักของแกนแนวนอน คุณสามารถใช้โค้ดดังต่อไปนี้:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## ขั้นตอนที่ 9: ลบซีรีส์

หากคุณต้องการลบซีรีส์ทั้งหมดออกจากแผนภูมิ คุณสามารถใช้ลูปดังนี้:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## ขั้นตอนที่ 10: ปรับแต่งชุดแผนภูมิ

คุณสามารถปรับแต่งชุดแผนภูมิได้ตามต้องการ ในตัวอย่างนี้ เราจะเปลี่ยนรูปแบบเครื่องหมาย ตำแหน่งป้ายข้อมูล ขนาดเครื่องหมาย สีเส้น และรูปแบบเส้นประ:

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

สุดท้ายให้บันทึกการนำเสนอลงในไฟล์:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้ซ่อนองค์ประกอบต่างๆ จากแผนภูมิใน Java Slides สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งแผนภูมิและการนำเสนอของคุณเพิ่มเติมตามความต้องการเฉพาะของคุณได้

## โค้ดต้นฉบับสมบูรณ์สำหรับการซ่อนข้อมูลจากแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//ซ่อนชื่อแผนภูมิ
	chart.setTitle(false);
	///แกนซ่อนค่า
	chart.getAxes().getVerticalAxis().setVisible(false);
	//หมวดหมู่ ทัศนวิสัยของแกน
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
	//การตั้งค่าสีเส้นซีรีย์
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

ในคู่มือทีละขั้นตอนนี้ เราได้อธิบายวิธีการซ่อนองค์ประกอบต่างๆ จากแผนภูมิใน Java Slides โดยใช้ Aspose.Slides for Java API ซึ่งอาจมีประโยชน์อย่างยิ่งเมื่อคุณต้องการปรับแต่งแผนภูมิสำหรับการนำเสนอและทำให้ดูน่าสนใจยิ่งขึ้นหรือเหมาะกับความต้องการเฉพาะของคุณ

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏขององค์ประกอบแผนภูมิเพิ่มเติมได้อย่างไร

คุณสามารถปรับแต่งคุณสมบัติต่างๆ ขององค์ประกอบแผนภูมิ เช่น สีเส้น สีเติม สไตล์เครื่องหมาย และอื่นๆ ได้โดยการเข้าถึงคุณสมบัติที่เกี่ยวข้องของชุดแผนภูมิ เครื่องหมาย ป้าย และรูปแบบ

### ฉันสามารถซ่อนจุดข้อมูลที่เจาะจงในแผนภูมิได้หรือไม่

ใช่ คุณสามารถซ่อนจุดข้อมูลเฉพาะได้โดยการจัดการข้อมูลในชุดแผนภูมิ คุณสามารถลบจุดข้อมูลหรือตั้งค่าเป็นค่าว่างเพื่อซ่อนจุดข้อมูลเหล่านั้นได้

### ฉันจะเพิ่มซีรีส์เพิ่มเติมลงในแผนภูมิได้อย่างไร

คุณสามารถเพิ่มซีรีส์เพิ่มเติมลงในแผนภูมิได้โดยใช้ `IChartData.getSeries().add` วิธีการและการระบุจุดข้อมูลสำหรับชุดใหม่

### เป็นไปได้หรือไม่ที่จะเปลี่ยนประเภทแผนภูมิแบบไดนามิก?

ใช่ คุณสามารถเปลี่ยนประเภทแผนภูมิแบบไดนามิกได้โดยการสร้างแผนภูมิใหม่ตามประเภทที่ต้องการและคัดลอกข้อมูลจากแผนภูมิเก่าไปยังแผนภูมิใหม่

### ฉันจะเปลี่ยนชื่อแผนภูมิและป้ายแกนโดยโปรแกรมได้อย่างไร

คุณสามารถตั้งชื่อเรื่องและป้ายกำกับของแผนภูมิและแกนได้โดยการเข้าถึงคุณสมบัติที่เกี่ยวข้องและตั้งค่าข้อความและการจัดรูปแบบที่ต้องการ

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}