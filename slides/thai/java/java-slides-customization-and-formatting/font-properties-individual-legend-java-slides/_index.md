---
"description": "ปรับปรุงการนำเสนอ PowerPoint ด้วยรูปแบบอักษร ขนาด และสีที่กำหนดเองสำหรับคำอธิบายแต่ละรายการใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java"
"linktitle": "คุณสมบัติแบบอักษรสำหรับคำอธิบายแต่ละรายการในสไลด์ Java"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "คุณสมบัติแบบอักษรสำหรับคำอธิบายแต่ละรายการในสไลด์ Java"
"url": "/th/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# คุณสมบัติแบบอักษรสำหรับคำอธิบายแต่ละรายการในสไลด์ Java


## บทนำเกี่ยวกับคุณสมบัติแบบอักษรสำหรับคำอธิบายแต่ละรายการในสไลด์ Java

ในบทช่วยสอนนี้ เราจะมาดูวิธีการตั้งค่าคุณสมบัติแบบอักษรสำหรับคำอธิบายแต่ละรายการใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java การปรับแต่งคุณสมบัติแบบอักษรจะทำให้คำอธิบายของคุณดูน่าสนใจและให้ข้อมูลในงานนำเสนอ PowerPoint มากขึ้น

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้รวมไลบรารี Aspose.Slides สำหรับ Java ไว้ในโปรเจ็กต์ของคุณแล้ว คุณสามารถดาวน์โหลดได้จาก [เอกสาร Aspose.Slides สำหรับ Java](https://reference-aspose.com/slides/java/).

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอและเพิ่มแผนภูมิ

ขั้นแรก เราจะเริ่มต้นด้วยการสร้างงานนำเสนอ PowerPoint และเพิ่มแผนภูมิเข้าไป ในตัวอย่างนี้ เราจะใช้แผนภูมิคอลัมน์แบบคลัสเตอร์เป็นภาพประกอบ

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // ส่วนที่เหลือของรหัสอยู่ที่นี่
} finally {
    if (pres != null) pres.dispose();
}
```

แทนที่ `"Your Document Directory"` พร้อมไดเร็กทอรีจริงที่เอกสาร PowerPoint ของคุณตั้งอยู่

## ขั้นตอนที่ 2: ปรับแต่งคุณสมบัติแบบอักษรสำหรับคำอธิบาย

ตอนนี้ มาปรับแต่งคุณสมบัติของแบบอักษรสำหรับรายการคำอธิบายแต่ละรายการภายในแผนภูมิกัน ในตัวอย่างนี้ เรากำหนดเป้าหมายที่รายการคำอธิบายรายการที่สอง (ดัชนี 1) แต่คุณสามารถปรับแต่งดัชนีตามความต้องการเฉพาะของคุณได้

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

นี่คือสิ่งที่แต่ละบรรทัดของโค้ดทำ:

- `get_Item(1)` ดึงรายการตำนานที่สอง (ดัชนี 1) คุณสามารถเปลี่ยนดัชนีเพื่อกำหนดเป้าหมายรายการตำนานอื่นได้
- `setFontBold(NullableBool.True)` ตั้งค่าแบบอักษรเป็นตัวหนา
- `setFontHeight(20)` กำหนดขนาดตัวอักษรเป็น 20 จุด
- `setFontItalic(NullableBool.True)` ตั้งค่าแบบอักษรเป็นตัวเอียง
- `setFillType(FillType.Solid)` ระบุว่าข้อความรายการคำอธิบายจะต้องมีการเติมแบบทึบ
- `getSolidFillColor().setColor(Color.BLUE)` ตั้งค่าสีเติมเป็นสีน้ำเงิน คุณสามารถแทนที่ `Color.BLUE` ด้วยสีที่คุณต้องการ

## ขั้นตอนที่ 3: บันทึกการนำเสนอที่แก้ไขแล้ว

สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วไปยังไฟล์ใหม่เพื่อเก็บรักษาการเปลี่ยนแปลงของคุณ

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

แทนที่ `"output.pptx"` พร้อมชื่อไฟล์เอาท์พุตที่คุณต้องการ

เสร็จเรียบร้อย! คุณปรับแต่งคุณสมบัติของแบบอักษรสำหรับรายการคำอธิบายแต่ละรายการในงานนำเสนอ Java Slides ได้สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java

## โค้ดต้นฉบับที่สมบูรณ์สำหรับคุณสมบัติแบบอักษรสำหรับคำอธิบายแต่ละรายการในสไลด์ Java

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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีปรับแต่งคุณสมบัติของแบบอักษรสำหรับแต่ละคำอธิบายประกอบใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับปรุงความสวยงามและความชัดเจนของงานนำเสนอ PowerPoint ได้โดยการปรับรูปแบบ ขนาด และสีของแบบอักษร

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีตัวอักษรได้อย่างไร?

หากต้องการเปลี่ยนสีตัวอักษร ให้ใช้ `tf.getPortionFormat().getFontColor().setColor(yourColor)` แทนที่จะเปลี่ยนสีเติม แทนที่ `yourColor` ด้วยสีตัวอักษรที่ต้องการ

### ฉันจะปรับเปลี่ยนคุณสมบัติของตำนานอื่น ๆ ได้อย่างไร

คุณสามารถปรับเปลี่ยนคุณสมบัติอื่นๆ ของคำอธิบายได้ เช่น ตำแหน่ง ขนาด และรูปแบบ โปรดดูข้อมูลโดยละเอียดเกี่ยวกับการทำงานกับคำอธิบายในเอกสาร Aspose.Slides for Java

### ฉันสามารถใช้การเปลี่ยนแปลงเหล่านี้กับรายการตำนานหลายรายการได้หรือไม่

ใช่ คุณสามารถวนซ้ำผ่านรายการตำนานและนำการเปลี่ยนแปลงเหล่านี้ไปใช้กับรายการหลายรายการได้โดยการปรับดัชนีใน `get_Item(index)` และทำการทำซ้ำรหัสปรับแต่ง

อย่าลืมกำจัดวัตถุการนำเสนอเมื่อคุณดำเนินการเสร็จสิ้นเพื่อปล่อยทรัพยากร:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}