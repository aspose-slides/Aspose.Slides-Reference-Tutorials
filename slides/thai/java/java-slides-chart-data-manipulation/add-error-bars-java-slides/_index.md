---
title: เพิ่มแถบข้อผิดพลาดใน Java Slides
linktitle: เพิ่มแถบข้อผิดพลาดใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีเพิ่มแถบข้อผิดพลาดลงในแผนภูมิ PowerPoint ใน Java โดยใช้ Aspose.Slides คำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ดสำหรับปรับแต่งแถบข้อผิดพลาด
type: docs
weight: 13
url: /th/java/chart-data-manipulation/add-error-bars-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับการเพิ่มแถบข้อผิดพลาดใน Java Slides โดยใช้ Aspose.Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการเพิ่มแถบข้อผิดพลาดลงในแผนภูมิในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java แถบข้อผิดพลาดให้ข้อมูลที่มีคุณค่าเกี่ยวกับความแปรปรวนหรือความไม่แน่นอนของจุดข้อมูลในแผนภูมิ เราจะสร้างแผนภูมิฟองและเพิ่มแถบข้อผิดพลาดลงไป มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดห้องสมุดได้จาก[เว็บไซต์กำหนด](https://downloads.aspose.com/slides/java).

## ขั้นตอนที่ 1: สร้างงานนำเสนอเปล่า

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// กำลังสร้างการนำเสนอที่ว่างเปล่า
Presentation presentation = new Presentation();
```

ในขั้นตอนนี้ เราสร้างงานนำเสนอเปล่าโดยเราจะเพิ่มแผนภูมิที่มีแถบข้อผิดพลาด

## ขั้นตอนที่ 2: สร้างแผนภูมิฟอง

```java
// การสร้างแผนภูมิฟอง
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

ที่นี่ เราสร้างแผนภูมิฟองและระบุตำแหน่งและขนาดบนสไลด์

## ขั้นตอนที่ 3: การเพิ่มแถบข้อผิดพลาดและรูปแบบการตั้งค่า

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

ในขั้นตอนนี้ เราจะเพิ่มแถบค่าคลาดเคลื่อนลงในแผนภูมิและตั้งค่ารูปแบบของแถบค่าคลาดเคลื่อน คุณสามารถปรับแต่งแถบข้อผิดพลาดได้โดยการเปลี่ยนค่า ประเภท และคุณสมบัติอื่นๆ

- `errBarX` แสดงถึงแถบค่าคลาดเคลื่อนตามแนวแกน X
- `errBarY` แสดงถึงแถบค่าคลาดเคลื่อนตามแนวแกน Y
- เราทำให้ทั้งแถบข้อผิดพลาด X และ Y มองเห็นได้
- `setValueType` ระบุประเภทของค่าสำหรับแถบข้อผิดพลาด (เช่น คงที่หรือเปอร์เซ็นต์)
- `setValue` ตั้งค่าสำหรับแถบข้อผิดพลาด
- `setType` กำหนดประเภทของแถบข้อผิดพลาด (เช่น บวกหรือลบ)
-  เรากำหนดความกว้างของเส้นแถบข้อผิดพลาดโดยใช้`getFormat().getLine().setWidth(2)`.
- `setEndCap`ระบุว่าจะรวมตัวพิมพ์ใหญ่บนแถบข้อผิดพลาดหรือไม่

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

```java
// กำลังบันทึกการนำเสนอ
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

สุดท้าย เราจะบันทึกงานนำเสนอพร้อมกับแถบข้อผิดพลาดที่เพิ่มไปยังตำแหน่งที่ระบุ

แค่นั้นแหละ! คุณได้เพิ่มแถบข้อผิดพลาดลงในแผนภูมิในสไลด์ PowerPoint เรียบร้อยแล้วโดยใช้ Aspose.Slides สำหรับ Java

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับการเพิ่มแถบข้อผิดพลาดใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// กำลังสร้างการนำเสนอที่ว่างเปล่า
Presentation presentation = new Presentation();
try
{
	// การสร้างแผนภูมิฟอง
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
	// กำลังบันทึกการนำเสนอ
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีปรับปรุงงานนำเสนอ PowerPoint ของคุณโดยการเพิ่มแถบข้อผิดพลาดลงในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java แถบข้อผิดพลาดให้ข้อมูลเชิงลึกที่มีคุณค่าเกี่ยวกับความแปรปรวนของข้อมูลและความไม่แน่นอน ทำให้การนำเสนอของคุณมีข้อมูลมากขึ้นและดึงดูดสายตา

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งลักษณะที่ปรากฏของแถบข้อผิดพลาดเพิ่มเติมได้อย่างไร

คุณสามารถปรับแต่งแถบข้อผิดพลาดได้โดยแก้ไขคุณสมบัติ เช่น ลักษณะของเส้น สี และความกว้าง ดังแสดงในขั้นตอนที่ 3

### ฉันสามารถเพิ่มแถบข้อผิดพลาดให้กับแผนภูมิประเภทต่างๆ ได้หรือไม่

ได้ คุณสามารถเพิ่มแถบข้อผิดพลาดลงในแผนภูมิประเภทต่างๆ ที่ Aspose.Slides สำหรับ Java รองรับได้ เพียงสร้างประเภทแผนภูมิที่ต้องการแล้วทำตามขั้นตอนการปรับแต่งแถบข้อผิดพลาดเดียวกัน

### ฉันจะปรับตำแหน่งและขนาดของแผนภูมิบนสไลด์ได้อย่างไร

 คุณสามารถควบคุมตำแหน่งและขนาดของแผนภูมิได้โดยการปรับพารามิเตอร์ใน`addChart` วิธีการดังแสดงในขั้นตอนที่ 2

### ฉันจะหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 คุณสามารถอ้างถึง[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/) สำหรับข้อมูลรายละเอียดการใช้ห้องสมุด