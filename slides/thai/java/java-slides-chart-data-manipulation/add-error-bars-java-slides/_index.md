---
"description": "เรียนรู้วิธีเพิ่มแถบข้อผิดพลาดในแผนภูมิ PowerPoint ใน Java โดยใช้ Aspose.Slides คำแนะนำทีละขั้นตอนพร้อมโค้ดต้นฉบับสำหรับการปรับแต่งแถบข้อผิดพลาด"
"linktitle": "เพิ่มแถบข้อผิดพลาดใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "เพิ่มแถบข้อผิดพลาดใน Java Slides"
"url": "/th/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# เพิ่มแถบข้อผิดพลาดใน Java Slides


## การแนะนำการเพิ่มแถบข้อผิดพลาดใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการเพิ่มแถบข้อผิดพลาดในแผนภูมิในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แถบข้อผิดพลาดให้ข้อมูลอันมีค่าเกี่ยวกับความแปรปรวนหรือความไม่แน่นอนของจุดข้อมูลในแผนภูมิ เราจะสร้างแผนภูมิฟองและเพิ่มแถบข้อผิดพลาดลงไป เริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จาก [เว็บไซต์อาโพส](https://downloads-aspose.com/slides/java).

## ขั้นตอนที่ 1: สร้างการนำเสนอที่ว่างเปล่า

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// การสร้างการนำเสนอแบบว่างเปล่า
Presentation presentation = new Presentation();
```

ในขั้นตอนนี้ เราจะสร้างการนำเสนอเปล่าที่เราจะเพิ่มแผนภูมิพร้อมแถบข้อผิดพลาด

## ขั้นตอนที่ 2: สร้างแผนภูมิฟองสบู่

```java
// การสร้างแผนภูมิฟองสบู่
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

ที่นี่เราสร้างแผนภูมิฟองและระบุตำแหน่งและมิติบนสไลด์

## ขั้นตอนที่ 3: การเพิ่มแถบข้อผิดพลาดและการตั้งค่ารูปแบบ

```java
// การเพิ่มแถบข้อผิดพลาดและการตั้งค่ารูปแบบ
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

ในขั้นตอนนี้ เราจะเพิ่มแถบข้อผิดพลาดลงในแผนภูมิและกำหนดรูปแบบ คุณสามารถปรับแต่งแถบข้อผิดพลาดได้โดยการเปลี่ยนแปลงค่า ประเภท และคุณสมบัติอื่นๆ

- `errBarX` แสดงแถบข้อผิดพลาดตามแนวแกน X
- `errBarY` แสดงแถบข้อผิดพลาดตามแกน Y
- เราทำให้แถบข้อผิดพลาดทั้ง X และ Y มองเห็นได้
- `setValueType` ระบุประเภทค่าสำหรับแถบข้อผิดพลาด (เช่น คงที่หรือเปอร์เซ็นต์)
- `setValue` ตั้งค่าสำหรับแถบข้อผิดพลาด
- `setType` กำหนดประเภทของแถบข้อผิดพลาด (เช่น บวกหรือลบ)
- เราตั้งค่าความกว้างของเส้นแถบแสดงข้อผิดพลาดโดยใช้ `getFormat()-getLine().setWidth(2)`.
- `setEndCap` ระบุว่าจะรวมฝาปิดไว้ในแถบข้อผิดพลาดหรือไม่

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

```java
// บันทึกการนำเสนอ
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

สุดท้าย เราบันทึกการนำเสนอพร้อมแถบข้อผิดพลาดที่เพิ่มเข้ามาไปยังตำแหน่งที่ระบุ

เสร็จเรียบร้อย! คุณได้เพิ่มแถบข้อผิดพลาดลงในแผนภูมิในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java สำเร็จแล้ว

## โค้ดต้นฉบับสมบูรณ์สำหรับการเพิ่มแถบข้อผิดพลาดใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// การสร้างการนำเสนอแบบว่างเปล่า
Presentation presentation = new Presentation();
try
{
	// การสร้างแผนภูมิฟองสบู่
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// การเพิ่มแถบข้อผิดพลาดและการตั้งค่ารูปแบบ
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// บันทึกการนำเสนอ
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้ศึกษาวิธีการปรับปรุงการนำเสนอ PowerPoint ของคุณโดยการเพิ่มแถบข้อผิดพลาดลงในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java แถบข้อผิดพลาดจะให้ข้อมูลเชิงลึกอันมีค่าเกี่ยวกับความแปรปรวนและความไม่แน่นอนของข้อมูล ทำให้การนำเสนอของคุณมีข้อมูลมากขึ้นและดูน่าสนใจยิ่งขึ้น

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของแถบข้อผิดพลาดเพิ่มเติมได้อย่างไร

คุณสามารถปรับแต่งแถบข้อผิดพลาดได้โดยการแก้ไขคุณสมบัติ เช่น รูปแบบของเส้น สี และความกว้าง ดังที่แสดงในขั้นตอนที่ 3

### ฉันสามารถเพิ่มแถบข้อผิดพลาดให้กับแผนภูมิประเภทต่างๆ ได้หรือไม่

ใช่ คุณสามารถเพิ่มแถบข้อผิดพลาดลงในแผนภูมิประเภทต่างๆ ที่รองรับโดย Aspose.Slides สำหรับ Java ได้ เพียงสร้างแผนภูมิประเภทที่ต้องการและทำตามขั้นตอนการปรับแต่งแถบข้อผิดพลาดเดียวกัน

### ฉันจะปรับตำแหน่งและขนาดของแผนภูมิบนสไลด์ได้อย่างไร

คุณสามารถควบคุมตำแหน่งและขนาดของแผนภูมิได้โดยการปรับพารามิเตอร์ใน `addChart` วิธีการดังที่แสดงในขั้นตอนที่ 2

### ฉันสามารถหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

คุณสามารถอ้างอิงได้ที่ [เอกสาร Aspose.Slides สำหรับ Java](https://reference.aspose.com/slides/java/) เพื่อทราบข้อมูลรายละเอียดการใช้งานห้องสมุด

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}