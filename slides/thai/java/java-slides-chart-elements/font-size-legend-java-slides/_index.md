---
"description": "ปรับปรุงการนำเสนอ PowerPoint ด้วย Aspose.Slides สำหรับ Java เรียนรู้วิธีปรับแต่งขนาดแบบอักษรของคำอธิบายและอื่นๆ ในคู่มือทีละขั้นตอนของเรา"
"linktitle": "คำอธิบายขนาดตัวอักษรใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "คำอธิบายขนาดตัวอักษรใน Java Slides"
"url": "/th/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# คำอธิบายขนาดตัวอักษรใน Java Slides


## บทนำเกี่ยวกับคำอธิบายขนาดตัวอักษรในสไลด์ Java

ในบทช่วยสอนนี้ คุณจะได้เรียนรู้วิธีปรับขนาดแบบอักษรของคำอธิบายในสไลด์ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java เราจะให้คำแนะนำทีละขั้นตอนและโค้ดต้นฉบับเพื่อบรรลุภารกิจนี้

## ข้อกำหนดเบื้องต้น

ก่อนเริ่มต้น โปรดตรวจสอบว่าได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: เริ่มต้นการนำเสนอ

ขั้นแรก นำเข้าคลาสที่จำเป็นและเริ่มต้นการนำเสนอ PowerPoint ของคุณ

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

แทนที่ `"Your Document Directory"` พร้อมเส้นทางจริงไปยังไฟล์ PowerPoint ของคุณ

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

ต่อไปเราจะเพิ่มแผนภูมิลงในสไลด์และกำหนดขนาดฟอนต์ของคำอธิบาย

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

ในโค้ดนี้ เราสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์บนสไลด์แรก และตั้งค่าขนาดฟอนต์ของข้อความคำอธิบายเป็น 20 พอยต์ คุณสามารถปรับขนาดได้ `setFontHeight` ค่าที่จะเปลี่ยนขนาดตัวอักษรตามต้องการ

## ขั้นตอนที่ 3: ปรับแต่งค่าแกน

ตอนนี้ มาปรับแต่งค่าแกนตั้งของแผนภูมิกัน

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

ที่นี่ เราตั้งค่าค่าต่ำสุดและสูงสุดสำหรับแกนแนวตั้ง คุณสามารถปรับเปลี่ยนค่าได้ตามความต้องการข้อมูลของคุณ

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้ายให้บันทึกงานนำเสนอที่แก้ไขแล้วลงในไฟล์ใหม่

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

รหัสนี้จะบันทึกงานนำเสนอที่แก้ไขเป็น "output.pptx" ในไดเร็กทอรีที่ระบุ

## โค้ดต้นฉบับสมบูรณ์สำหรับคำอธิบายขนาดตัวอักษรใน Java Slides

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

คุณได้ปรับขนาดตัวอักษรของคำอธิบายในสไลด์ Java PowerPoint สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java คุณสามารถสำรวจความสามารถของ Aspose.Slides เพิ่มเติมเพื่อสร้างการนำเสนอแบบโต้ตอบและดึงดูดสายตาได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนขนาดตัวอักษรของข้อความคำอธิบายในแผนภูมิได้อย่างไร

หากต้องการปรับขนาดตัวอักษรของข้อความคำอธิบายในแผนภูมิ คุณสามารถใช้โค้ดดังต่อไปนี้:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

ในโค้ดนี้ เราสร้างแผนภูมิและตั้งค่าขนาดตัวอักษรของข้อความคำอธิบายเป็น 20 พอยต์ คุณสามารถปรับขนาดได้ `setFontHeight` ค่าที่จะเปลี่ยนขนาดตัวอักษร

### ฉันสามารถปรับแต่งคุณสมบัติอื่น ๆ ของตำนานในแผนภูมิได้หรือไม่

ใช่ คุณสามารถปรับแต่งคุณสมบัติต่างๆ ของคำอธิบายแผนภูมิในแผนภูมิได้โดยใช้ Aspose.Slides คุณสมบัติทั่วไปบางอย่างที่คุณปรับแต่งได้ ได้แก่ การจัดรูปแบบข้อความ ตำแหน่ง การมองเห็น และอื่นๆ ตัวอย่างเช่น หากต้องการเปลี่ยนตำแหน่งของคำอธิบายแผนภูมิ คุณสามารถใช้:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

โค้ดนี้จะตั้งค่าคำอธิบายให้ปรากฏที่ด้านล่างของแผนภูมิ สำรวจเอกสาร Aspose.Slides เพื่อดูตัวเลือกการปรับแต่งเพิ่มเติม

### ฉันจะตั้งค่าต่ำสุดและสูงสุดสำหรับแกนตั้งในแผนภูมิได้อย่างไร

หากต้องการตั้งค่าต่ำสุดและสูงสุดสำหรับแกนตั้งในแผนภูมิ คุณสามารถใช้โค้ดดังต่อไปนี้:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

ที่นี่ เราจะปิดใช้งานการปรับขนาดแกนอัตโนมัติ และระบุค่าต่ำสุดและสูงสุดสำหรับแกนแนวตั้ง ปรับค่าตามต้องการสำหรับข้อมูลแผนภูมิของคุณ

### ฉันสามารถหาข้อมูลและเอกสารเพิ่มเติมสำหรับ Aspose.Slides ได้จากที่ใด

คุณสามารถค้นหาเอกสารประกอบฉบับสมบูรณ์และเอกสารอ้างอิง API สำหรับ Aspose.Slides สำหรับ Java ได้ที่เว็บไซต์เอกสารประกอบของ Aspose เข้าไปที่ [ที่นี่](https://reference.aspose.com/slides/java/) เพื่อทราบข้อมูลรายละเอียดการใช้งานห้องสมุด

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}