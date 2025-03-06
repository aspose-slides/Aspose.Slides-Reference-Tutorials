---
title: เพิ่มข้อผิดพลาดที่กำหนดเองใน Java Slides
linktitle: เพิ่มข้อผิดพลาดที่กำหนดเองใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มแถบข้อผิดพลาดที่กำหนดเองลงในแผนภูมิ PowerPoint ใน Java Slides โดยใช้ Aspose.Slides คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดเพื่อการแสดงภาพข้อมูลที่แม่นยำ
weight: 11
url: /th/java/chart-data-manipulation/add-custom-error-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## ข้อมูลเบื้องต้นเกี่ยวกับการเพิ่มแถบข้อผิดพลาดที่กำหนดเองใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีเพิ่มแถบข้อผิดพลาดแบบกำหนดเองลงในแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แถบข้อผิดพลาดมีประโยชน์สำหรับการแสดงความแปรปรวนหรือความไม่แน่นอนของจุดข้อมูลบนแผนภูมิ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Aspose.Slides สำหรับไลบรารี Java ที่ติดตั้งและกำหนดค่าในโปรเจ็กต์ของคุณ
- ตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: สร้างงานนำเสนอเปล่า

ขั้นแรก สร้างงานนำเสนอ PowerPoint เปล่า

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// กำลังสร้างการนำเสนอที่ว่างเปล่า
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิฟอง

ต่อไป เราจะเพิ่มแผนภูมิฟองให้กับงานนำเสนอ

```java
// การสร้างแผนภูมิฟอง
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## ขั้นตอนที่ 3: เพิ่มแถบข้อผิดพลาดที่กำหนดเอง

ตอนนี้ มาเพิ่มแถบข้อผิดพลาดแบบกำหนดเองลงในชุดแผนภูมิกัน

```java
// การเพิ่มแถบข้อผิดพลาดที่กำหนดเองและการตั้งค่ารูปแบบ
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## ขั้นตอนที่ 4: ตั้งค่าข้อมูลแถบข้อผิดพลาด

ในขั้นตอนนี้ เราจะเข้าถึงจุดข้อมูลชุดแผนภูมิและตั้งค่าแถบข้อผิดพลาดที่กำหนดเองสำหรับแต่ละจุด

```java
// การเข้าถึงจุดข้อมูลชุดแผนภูมิและการตั้งค่าแถบข้อผิดพลาดสำหรับแต่ละจุด
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// การตั้งค่าแถบข้อผิดพลาดสำหรับจุดชุดแผนภูมิ
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอด้วยแถบข้อผิดพลาดแบบกำหนดเอง

```java
// กำลังบันทึกการนำเสนอ
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

แค่นั้นแหละ! คุณได้เพิ่มแถบข้อผิดพลาดแบบกำหนดเองลงในแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว

## กรอกซอร์สโค้ดให้สมบูรณ์เพื่อเพิ่มข้อผิดพลาดที่กำหนดเองใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// กำลังสร้างการนำเสนอที่ว่างเปล่า
Presentation presentation = new Presentation();
try
{
	// การสร้างแผนภูมิฟอง
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// การเพิ่มแถบข้อผิดพลาดที่กำหนดเองและการตั้งค่ารูปแบบ
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// การเข้าถึงจุดข้อมูลชุดแผนภูมิและการตั้งค่าแถบข้อผิดพลาดสำหรับแต่ละจุด
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// การตั้งค่าแถบข้อผิดพลาดสำหรับจุดชุดแผนภูมิ
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// กำลังบันทึกการนำเสนอ
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนที่ครอบคลุมนี้ คุณได้เรียนรู้วิธีปรับปรุงงานนำเสนอ PowerPoint ของคุณโดยการเพิ่มแถบข้อผิดพลาดที่กำหนดเองลงในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java แถบข้อผิดพลาดให้ข้อมูลเชิงลึกอันมีค่าเกี่ยวกับความแปรปรวนของข้อมูลและความไม่แน่นอน ทำให้แผนภูมิของคุณมีข้อมูลมากขึ้นและดึงดูดสายตามากขึ้น

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของแถบข้อผิดพลาดได้อย่างไร

 คุณสามารถปรับแต่งลักษณะที่ปรากฏของแถบข้อผิดพลาดได้โดยการแก้ไขคุณสมบัติของ`IErrorBarsFormat` วัตถุ เช่น ลักษณะของเส้น สีของเส้น และความกว้างของแถบข้อผิดพลาด

### ฉันสามารถเพิ่มแถบข้อผิดพลาดให้กับแผนภูมิประเภทอื่นได้หรือไม่

ได้ คุณสามารถเพิ่มแถบข้อผิดพลาดลงในแผนภูมิประเภทต่างๆ ที่ Aspose.Slides สำหรับ Java รองรับ รวมถึงแผนภูมิแท่ง แผนภูมิเส้น และแผนภูมิกระจาย

### ฉันจะตั้งค่าแถบข้อผิดพลาดที่แตกต่างกันสำหรับแต่ละจุดข้อมูลได้อย่างไร

คุณสามารถวนซ้ำจุดข้อมูลและตั้งค่าแถบข้อผิดพลาดแบบกำหนดเองสำหรับแต่ละจุดได้ ดังที่แสดงในโค้ดด้านบน

### เป็นไปได้ไหมที่จะซ่อนแถบข้อผิดพลาดสำหรับจุดข้อมูลเฉพาะ

 ได้ คุณสามารถควบคุมการมองเห็นแถบข้อผิดพลาดสำหรับจุดข้อมูลแต่ละจุดได้โดยการตั้งค่า`setVisible` ทรัพย์สินของ`IErrorBarsFormat` วัตถุ.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
