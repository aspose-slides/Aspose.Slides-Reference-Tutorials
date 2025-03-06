---
title: คุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides
linktitle: คุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ปรับปรุงคุณสมบัติแบบอักษรของแผนภูมิใน Java Slides ด้วย Aspose.Slides สำหรับ Java ปรับแต่งขนาดตัวอักษร สไตล์ และสีเพื่อการนำเสนอที่น่าประทับใจ
weight: 11
url: /th/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## รู้เบื้องต้นเกี่ยวกับคุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides

คู่มือนี้จะอธิบายการตั้งค่าคุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides คุณสามารถกำหนดขนาดแบบอักษรและลักษณะของข้อความในแผนภูมิได้เองเพื่อเพิ่มความสวยงามให้กับงานนำเสนอของคุณ

## ข้อกำหนดเบื้องต้น

 ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้รวม Aspose.Slides สำหรับ Java API เข้ากับโปรเจ็กต์ของคุณแล้ว หากคุณยังไม่มี คุณสามารถดาวน์โหลดได้จาก[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก สร้างงานนำเสนอใหม่โดยใช้โค้ดต่อไปนี้:

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มแผนภูมิ

ตอนนี้ เรามาเพิ่มแผนภูมิคอลัมน์แบบกลุ่มในงานนำเสนอของคุณ:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

ที่นี่ เรากำลังเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์แรกที่พิกัด (100, 100) โดยมีความกว้าง 500 หน่วยและความสูง 400 หน่วย

## ขั้นตอนที่ 3: ปรับแต่งคุณสมบัติแบบอักษร

ต่อไป เราจะปรับแต่งคุณสมบัติแบบอักษรของแผนภูมิ ในตัวอย่างนี้ เรากำลังตั้งค่าขนาดแบบอักษรเป็น 20 สำหรับข้อความในแผนภูมิทั้งหมด:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

รหัสนี้กำหนดขนาดตัวอักษรเป็น 20 พอยต์สำหรับข้อความทั้งหมดภายในแผนภูมิ

## ขั้นตอนที่ 4: แสดงป้ายกำกับข้อมูล

คุณยังสามารถแสดงป้ายกำกับข้อมูลบนแผนภูมิโดยใช้โค้ดต่อไปนี้:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

บรรทัดโค้ดนี้เปิดใช้งานป้ายกำกับข้อมูลสำหรับชุดแรกในแผนภูมิ โดยแสดงค่าในคอลัมน์แผนภูมิ

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้าย บันทึกงานนำเสนอด้วยคุณสมบัติแบบอักษรของแผนภูมิที่คุณกำหนดเอง:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

รหัสนี้จะบันทึกงานนำเสนอไปยังไดเร็กทอรีที่ระบุด้วยชื่อไฟล์ "FontPropertiesForChart.pptx"

## กรอกซอร์สโค้ดสำหรับคุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ คุณได้เรียนรู้วิธีปรับแต่งคุณสมบัติแบบอักษรสำหรับแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถใช้เทคนิคเหล่านี้เพื่อปรับปรุงรูปลักษณ์ของแผนภูมิและการนำเสนอของคุณได้ สำรวจตัวเลือกเพิ่มเติมใน[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/).

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนสีตัวอักษรได้อย่างไร?

 หากต้องการเปลี่ยนสีแบบอักษรสำหรับข้อความในแผนภูมิ ให้ใช้`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , แทนที่`Color.RED` ด้วยสีที่ต้องการ

### ฉันสามารถเปลี่ยนรูปแบบตัวอักษร (ตัวหนา ตัวเอียง ฯลฯ) ได้หรือไม่

 ใช่ คุณสามารถเปลี่ยนรูปแบบตัวอักษรได้ ใช้`chart.getTextFormat().getPortionFormat().setFontBold(true);` เพื่อให้ตัวอักษรเป็นตัวหนา ในทำนองเดียวกันคุณสามารถใช้`setFontItalic(true)` เพื่อทำให้มันเป็นตัวเอียง

### ฉันจะปรับแต่งคุณสมบัติแบบอักษรสำหรับองค์ประกอบแผนภูมิเฉพาะได้อย่างไร

หากต้องการปรับแต่งคุณสมบัติแบบอักษรสำหรับองค์ประกอบแผนภูมิเฉพาะ เช่น ป้ายแกนหรือข้อความคำอธิบาย คุณสามารถเข้าถึงองค์ประกอบเหล่านั้นและตั้งค่าคุณสมบัติแบบอักษรโดยใช้วิธีการที่คล้ายกันดังที่แสดงไว้ด้านบน
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
