---
title: คำอธิบายขนาดตัวอักษรใน Java Slides
linktitle: คำอธิบายขนาดตัวอักษรใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ปรับปรุงการนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ Java เรียนรู้วิธีปรับแต่งขนาดตัวอักษรคำอธิบายและอื่นๆ ในคำแนะนำทีละขั้นตอนของเรา
type: docs
weight: 13
url: /th/java/chart-elements/font-size-legend-java-slides/
---

## รู้เบื้องต้นเกี่ยวกับคำอธิบายขนาดตัวอักษรใน Java Slides

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีกำหนดขนาดตัวอักษรของคำอธิบายแผนภูมิในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เราจะให้คำแนะนำทีละขั้นตอนและซอร์สโค้ดเพื่อให้บรรลุภารกิจนี้

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

ขั้นแรก นำเข้าคลาสที่จำเป็นและเริ่มต้นงานนำเสนอ PowerPoint ของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 แทนที่`"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์ PowerPoint ของคุณ

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

ต่อไป เราจะเพิ่มแผนภูมิลงในสไลด์และตั้งค่าขนาดตัวอักษรของคำอธิบายแผนภูมิ

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 ในโค้ดนี้ เราสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์บนสไลด์แรก และตั้งค่าขนาดแบบอักษรของข้อความคำอธิบายแผนภูมิเป็น 20 พอยต์ คุณสามารถปรับ`setFontHeight`ค่าเพื่อเปลี่ยนขนาดตัวอักษรตามต้องการ

## ขั้นตอนที่ 3: ปรับแต่งค่าแกน

ตอนนี้ เรามาปรับแต่งค่าแกนตั้งของแผนภูมิกัน

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

ที่นี่ เราตั้งค่าต่ำสุดและสูงสุดสำหรับแกนตั้ง คุณสามารถแก้ไขค่าได้ตามความต้องการข้อมูลของคุณ

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอที่แก้ไขแล้วเป็นไฟล์ใหม่

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

รหัสนี้จะบันทึกงานนำเสนอที่แก้ไขแล้วเป็น "output.pptx" ในไดเร็กทอรีที่ระบุ

## กรอกซอร์สโค้ดสำหรับคำอธิบายขนาดตัวอักษรใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

คุณได้กำหนดขนาดตัวอักษรของคำอธิบายแผนภูมิในสไลด์ Java PowerPoint ได้สำเร็จโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถสำรวจความสามารถของ Aspose.Slides เพิ่มเติมเพื่อสร้างงานนำเสนอเชิงโต้ตอบและดึงดูดสายตาได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนขนาดแบบอักษรของข้อความคำอธิบายแผนภูมิในแผนภูมิได้อย่างไร

เมื่อต้องการเปลี่ยนขนาดแบบอักษรของข้อความคำอธิบายแผนภูมิในแผนภูมิ คุณสามารถใช้โค้ดต่อไปนี้:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 ในโค้ดนี้ เราสร้างแผนภูมิและตั้งค่าขนาดแบบอักษรของข้อความคำอธิบายแผนภูมิเป็น 20 พอยต์ คุณสามารถปรับ`setFontHeight` ค่าเพื่อเปลี่ยนขนาดตัวอักษร

### ฉันสามารถปรับแต่งคุณสมบัติอื่นๆ ของคำอธิบายแผนภูมิในแผนภูมิได้หรือไม่

ใช่ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของคำอธิบายแผนภูมิในแผนภูมิได้โดยใช้ Aspose.Slides คุณสมบัติทั่วไปบางอย่างที่คุณปรับแต่งได้ ได้แก่ การจัดรูปแบบข้อความ ตำแหน่ง การมองเห็น และอื่นๆ ตัวอย่างเช่น หากต้องการเปลี่ยนตำแหน่งของคำอธิบาย คุณสามารถใช้:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

รหัสนี้กำหนดคำอธิบายให้ปรากฏที่ด้านล่างของแผนภูมิ สำรวจเอกสารประกอบของ Aspose.Slides เพื่อดูตัวเลือกการปรับแต่งเพิ่มเติม

### ฉันจะตั้งค่าต่ำสุดและสูงสุดสำหรับแกนตั้งในแผนภูมิได้อย่างไร

หากต้องการตั้งค่าต่ำสุดและสูงสุดสำหรับแกนตั้งในแผนภูมิ คุณสามารถใช้โค้ดต่อไปนี้:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

ที่นี่ เราปิดใช้งานการปรับขนาดแกนอัตโนมัติ และระบุค่าต่ำสุดและสูงสุดสำหรับแกนตั้ง ปรับค่าตามที่จำเป็นสำหรับข้อมูลแผนภูมิของคุณ

### ฉันจะหาข้อมูลและเอกสารประกอบเพิ่มเติมสำหรับ Aspose.Slides ได้ที่ไหน

 คุณสามารถค้นหาเอกสารที่ครอบคลุมและข้อมูลอ้างอิง API สำหรับ Aspose.Slides สำหรับ Java ได้บนเว็บไซต์เอกสารประกอบของ Aspose เยี่ยม[ที่นี่](https://reference.aspose.com/slides/java/) สำหรับข้อมูลรายละเอียดการใช้ห้องสมุด