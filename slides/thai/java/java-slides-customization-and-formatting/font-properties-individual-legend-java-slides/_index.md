---
title: คุณสมบัติแบบอักษรสำหรับคำอธิบายแผนภูมิแต่ละรายการใน Java Slides
linktitle: คุณสมบัติแบบอักษรสำหรับคำอธิบายแผนภูมิแต่ละรายการใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ปรับปรุงงานนำเสนอ PowerPoint ด้วยสไตล์ฟอนต์ ขนาด และสีที่กำหนดเองสำหรับคำอธิบายแต่ละรายการใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java
type: docs
weight: 12
url: /th/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

## ข้อมูลเบื้องต้นเกี่ยวกับคุณสมบัติแบบอักษรสำหรับคำอธิบายเฉพาะบุคคลใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีตั้งค่าคุณสมบัติแบบอักษรสำหรับคำอธิบายแผนภูมิแต่ละรายการใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java ด้วยการกำหนดคุณสมบัติฟอนต์เอง คุณสามารถทำให้คำอธิบายแผนภูมิของคุณดูน่าดึงดูดและให้ข้อมูลมากขึ้นในงานนำเสนอ PowerPoint ของคุณ

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java เข้ากับโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/).

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอและเพิ่มแผนภูมิ

ขั้นแรก เริ่มต้นด้วยการเริ่มต้นงานนำเสนอ PowerPoint และเพิ่มแผนภูมิลงไป ในตัวอย่างนี้ เราจะใช้แผนภูมิคอลัมน์แบบกลุ่มเป็นภาพประกอบ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // รหัสที่เหลืออยู่ที่นี่
} finally {
    if (pres != null) pres.dispose();
}
```

 แทนที่`"Your Document Directory"` ด้วยไดเร็กทอรีจริงที่มีเอกสาร PowerPoint ของคุณอยู่

## ขั้นตอนที่ 2: ปรับแต่งคุณสมบัติแบบอักษรสำหรับ Legend

ตอนนี้ เรามาปรับแต่งคุณสมบัติแบบอักษรสำหรับรายการคำอธิบายแผนภูมิแต่ละรายการภายในแผนภูมิกัน ในตัวอย่างนี้ เรากำลังกำหนดเป้าหมายรายการคำอธิบายแผนภูมิที่สอง (ดัชนี 1) แต่คุณสามารถปรับดัชนีตามความต้องการเฉพาะของคุณได้

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

โค้ดแต่ละบรรทัดทำหน้าที่ดังนี้:

- `get_Item(1)` ดึงข้อมูลรายการคำอธิบายแผนภูมิที่สอง (ดัชนี 1) คุณสามารถเปลี่ยนดัชนีเพื่อกำหนดเป้าหมายรายการคำอธิบายแผนภูมิอื่นได้
- `setFontBold(NullableBool.True)` ตั้งค่าแบบอักษรให้เป็นตัวหนา
- `setFontHeight(20)` กำหนดขนาดตัวอักษรเป็น 20 พอยต์
- `setFontItalic(NullableBool.True)` ตั้งค่าแบบอักษรเป็นตัวเอียง
- `setFillType(FillType.Solid)` ระบุว่าข้อความรายการคำอธิบายควรมีการเติมแบบทึบ
- `getSolidFillColor().setColor(Color.BLUE)` ตั้งค่าสีเติมเป็นสีน้ำเงิน คุณสามารถแทนที่ได้`Color.BLUE` ด้วยสีที่คุณต้องการ

## ขั้นตอนที่ 3: บันทึกงานนำเสนอที่แก้ไข

สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์ใหม่เพื่อรักษาการเปลี่ยนแปลงของคุณ

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 แทนที่`"output.pptx"` ด้วยชื่อไฟล์เอาต์พุตที่คุณต้องการ

แค่นั้นแหละ! คุณได้ปรับแต่งคุณสมบัติแบบอักษรสำหรับรายการคำอธิบายแผนภูมิแต่ละรายการในงานนำเสนอ Java Slides สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java

## กรอกซอร์สโค้ดสำหรับคุณสมบัติแบบอักษรสำหรับคำอธิบายแผนภูมิแต่ละรายการใน Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีปรับแต่งคุณสมบัติแบบอักษรสำหรับคำอธิบายแผนภูมิแต่ละรายการใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java ด้วยการปรับสไตล์ฟอนต์ ขนาด และสี คุณสามารถเพิ่มความน่าดึงดูดทางสายตาและความชัดเจนของงานนำเสนอ PowerPoint ของคุณได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีตัวอักษรได้อย่างไร?

 หากต้องการเปลี่ยนสีตัวอักษร ให้ใช้`tf.getPortionFormat().getFontColor().setColor(yourColor)` แทนที่จะเปลี่ยนสีเติม แทนที่`yourColor` ด้วยสีตัวอักษรที่ต้องการ

### ฉันจะแก้ไขคุณสมบัติคำอธิบายแผนภูมิอื่นๆ ได้อย่างไร

คุณสามารถแก้ไขคุณสมบัติอื่นๆ ของคำอธิบายแผนภูมิได้ เช่น ตำแหน่ง ขนาด และรูปแบบ โปรดดูเอกสารประกอบ Aspose.Slides สำหรับ Java สำหรับข้อมูลโดยละเอียดเกี่ยวกับการทำงานกับคำอธิบายแผนภูมิ

### ฉันสามารถใช้การเปลี่ยนแปลงเหล่านี้กับรายการคำอธิบายหลายรายการได้หรือไม่

 ได้ คุณสามารถวนซ้ำรายการคำอธิบายแผนภูมิและใช้การเปลี่ยนแปลงเหล่านี้กับหลายรายการได้โดยการปรับดัชนี`get_Item(index)` และทำซ้ำรหัสปรับแต่ง

อย่าลืมทิ้งวัตถุการนำเสนอเมื่อคุณปล่อยทรัพยากรเสร็จแล้ว:

```java
if (pres != null) pres.dispose();
```