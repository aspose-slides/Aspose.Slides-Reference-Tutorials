---
"description": "เรียนรู้วิธีเพิ่มแถบข้อผิดพลาดแบบกำหนดเองลงในแผนภูมิ PowerPoint ใน Java Slides โดยใช้ Aspose.Slides คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการแสดงภาพข้อมูลที่แม่นยำ"
"linktitle": "เพิ่มข้อผิดพลาดแบบกำหนดเองใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มข้อผิดพลาดแบบกำหนดเองใน Java Slides"
"url": "/th/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มข้อผิดพลาดแบบกำหนดเองใน Java Slides


## การแนะนำการเพิ่มแถบข้อผิดพลาดแบบกำหนดเองใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีเพิ่มแถบข้อผิดพลาดแบบกำหนดเองลงในแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แถบข้อผิดพลาดมีประโยชน์สำหรับการแสดงความแปรปรวนหรือความไม่แน่นอนในจุดข้อมูลบนแผนภูมิ

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- Aspose.Slides สำหรับไลบรารี Java ได้รับการติดตั้งและกำหนดค่าในโปรเจ็กต์ของคุณแล้ว
- การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: สร้างการนำเสนอที่ว่างเปล่า

ขั้นแรก ให้สร้างการนำเสนอ PowerPoint ที่ว่างเปล่า

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// การสร้างการนำเสนอแบบว่างเปล่า
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิฟองสบู่

ต่อไปเราจะเพิ่มแผนภูมิฟองลงในการนำเสนอ

```java
// การสร้างแผนภูมิฟองสบู่
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## ขั้นตอนที่ 3: เพิ่มแถบข้อผิดพลาดที่กำหนดเอง

ตอนนี้ มาเพิ่มแถบข้อผิดพลาดแบบกำหนดเองให้กับชุดแผนภูมิกัน

```java
// การเพิ่มแถบข้อผิดพลาดแบบกำหนดเองและการตั้งค่ารูปแบบ
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## ขั้นตอนที่ 4: ตั้งค่าข้อมูลแถบข้อผิดพลาด

ในขั้นตอนนี้เราจะเข้าถึงจุดข้อมูลชุดแผนภูมิและตั้งค่าแถบข้อผิดพลาดแบบกำหนดเองสำหรับแต่ละจุด

```java
// การเข้าถึงจุดข้อมูลชุดแผนภูมิและการตั้งค่าแถบข้อผิดพลาดสำหรับจุดแต่ละจุด
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

สุดท้าย ให้บันทึกการนำเสนอด้วยแถบข้อผิดพลาดแบบกำหนดเอง

```java
// บันทึกการนำเสนอ
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

เสร็จเรียบร้อย! คุณได้เพิ่มแถบข้อผิดพลาดแบบกำหนดเองลงในแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว

## โค้ดต้นฉบับสมบูรณ์สำหรับการเพิ่มข้อผิดพลาดแบบกำหนดเองใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// การสร้างการนำเสนอแบบว่างเปล่า
Presentation presentation = new Presentation();
try
{
	// การสร้างแผนภูมิฟองสบู่
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// การเพิ่มแถบข้อผิดพลาดแบบกำหนดเองและการตั้งค่ารูปแบบ
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// การเข้าถึงจุดข้อมูลชุดแผนภูมิและการตั้งค่าแถบข้อผิดพลาดสำหรับจุดแต่ละจุด
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
	// บันทึกการนำเสนอ
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนที่ครอบคลุมนี้ คุณจะได้เรียนรู้วิธีปรับปรุงการนำเสนอ PowerPoint ของคุณโดยเพิ่มแถบข้อผิดพลาดแบบกำหนดเองลงในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java แถบข้อผิดพลาดจะให้ข้อมูลเชิงลึกอันมีค่าเกี่ยวกับความแปรปรวนและความไม่แน่นอนของข้อมูล ทำให้แผนภูมิของคุณมีข้อมูลมากขึ้นและดูน่าสนใจยิ่งขึ้น

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของแถบข้อผิดพลาดได้อย่างไร

คุณสามารถปรับแต่งลักษณะที่ปรากฏของแถบข้อผิดพลาดได้โดยการแก้ไขคุณสมบัติของ `IErrorBarsFormat` วัตถุ เช่น สไตล์เส้น สีเส้น และความกว้างของแถบแสดงข้อผิดพลาด

### ฉันสามารถเพิ่มแถบข้อผิดพลาดให้กับแผนภูมิประเภทอื่นได้หรือไม่

ใช่ คุณสามารถเพิ่มแถบข้อผิดพลาดให้กับแผนภูมิประเภทต่างๆ ที่ได้รับการรองรับโดย Aspose.Slides สำหรับ Java รวมถึงแผนภูมิแท่ง แผนภูมิเส้น และแผนภูมิกระจาย

### ฉันจะตั้งค่าแถบข้อผิดพลาดที่แตกต่างกันสำหรับจุดข้อมูลแต่ละจุดได้อย่างไร

คุณสามารถวนซ้ำผ่านจุดข้อมูลและตั้งค่าแถบข้อผิดพลาดแบบกำหนดเองสำหรับแต่ละจุดได้ ดังที่แสดงในโค้ดด้านบน

### สามารถซ่อนแถบข้อผิดพลาดสำหรับจุดข้อมูลที่เจาะจงได้หรือไม่

ใช่ คุณสามารถควบคุมการมองเห็นของแถบข้อผิดพลาดสำหรับจุดข้อมูลแต่ละจุดได้โดยการตั้งค่า `setVisible` ทรัพย์สินของ `IErrorBarsFormat` วัตถุ.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}