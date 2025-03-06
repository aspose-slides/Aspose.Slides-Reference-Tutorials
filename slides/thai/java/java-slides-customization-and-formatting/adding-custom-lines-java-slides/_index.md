---
title: การเพิ่มบรรทัดที่กำหนดเองใน Java Slides
linktitle: การเพิ่มบรรทัดที่กำหนดเองใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ปรับปรุง Java Slides ของคุณด้วยบรรทัดที่กำหนดเอง คำแนะนำทีละขั้นตอนโดยใช้ Aspose.Slides สำหรับ Java เรียนรู้วิธีการเพิ่มและปรับแต่งเส้นในการนำเสนอเพื่อให้ได้ภาพที่มีประสิทธิภาพ
weight: 10
url: /th/java/customization-and-formatting/adding-custom-lines-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การเพิ่มบรรทัดที่กำหนดเองใน Java Slides


## รู้เบื้องต้นเกี่ยวกับการเพิ่มบรรทัดที่กำหนดเองใน Java Slides

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีเพิ่มบรรทัดที่กำหนดเองลงในสไลด์ Java ของคุณโดยใช้ Aspose.Slides สำหรับ Java เส้นที่กำหนดเองสามารถใช้เพื่อเสริมการแสดงภาพสไลด์ของคุณและเน้นเนื้อหาเฉพาะได้ เราจะให้คำแนะนำทีละขั้นตอนพร้อมกับซอร์สโค้ดเพื่อให้บรรลุเป้าหมายนี้ มาเริ่มกันเลย!

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดห้องสมุดได้จากเว็บไซต์:[Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

ขั้นแรก คุณต้องสร้างงานนำเสนอใหม่ ในตัวอย่างนี้ เราจะสร้างงานนำเสนอเปล่า

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

ต่อไป เราจะเพิ่มแผนภูมิลงในสไลด์ ในตัวอย่างนี้ เรากำลังเพิ่มแผนภูมิคอลัมน์แบบกลุ่ม คุณสามารถเลือกประเภทแผนภูมิที่เหมาะกับความต้องการของคุณได้

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## ขั้นตอนที่ 3: เพิ่มบรรทัดที่กำหนดเอง

 ตอนนี้ มาเพิ่มเส้นที่กำหนดเองลงในแผนภูมิกัน เราจะสร้าง`IAutoShape` ประเภท`ShapeType.Line` และวางไว้ภายในแผนภูมิ

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## ขั้นตอนที่ 4: ปรับแต่งเส้น

คุณสามารถปรับแต่งลักษณะที่ปรากฏของเส้นได้โดยการตั้งค่าคุณสมบัติของเส้น ในตัวอย่างนี้ เรากำลังตั้งค่าสีของเส้นเป็นสีแดง

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้าย บันทึกงานนำเสนอไปยังตำแหน่งที่คุณต้องการ

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับการเพิ่มบรรทัดที่กำหนดเองใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ยินดีด้วย! คุณได้เพิ่มบรรทัดที่กำหนดเองลงในสไลด์ Java ของคุณสำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งคุณสมบัติของเส้นเพิ่มเติมเพื่อให้ได้เอฟเฟกต์ภาพที่คุณต้องการ

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีเส้นได้อย่างไร?

หากต้องการเปลี่ยนสีเส้น ให้ใช้โค้ดต่อไปนี้:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

 แทนที่`YOUR_COLOR` ด้วยสีที่ต้องการ

### ฉันสามารถเพิ่มเส้นแบบกำหนดเองให้กับรูปร่างอื่นได้หรือไม่

 ได้ คุณสามารถเพิ่มเส้นแบบกำหนดเองให้กับรูปร่างต่างๆ ได้ ไม่ใช่แค่แผนภูมิเท่านั้น เพียงสร้าง`IAutoShape` และปรับแต่งตามความต้องการของคุณ

### ฉันจะเปลี่ยนความหนาของเส้นได้อย่างไร?

 คุณสามารถเปลี่ยนความหนาของเส้นได้โดยการตั้งค่า`Width` คุณสมบัติของรูปแบบเส้น ตัวอย่างเช่น:
```java
shape.getLineFormat().setWidth(2); // ตั้งค่าความหนาของเส้นเป็น 2 จุด
```

### เป็นไปได้ไหมที่จะเพิ่มหลายบรรทัดลงในสไลด์?

ได้ คุณสามารถเพิ่มหลายบรรทัดลงในสไลด์ได้โดยทำซ้ำขั้นตอนที่กล่าวถึงในบทช่วยสอนนี้ แต่ละบรรทัดสามารถปรับแต่งได้อย่างอิสระ
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
