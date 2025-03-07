---
title: การตั้งค่าแกนตำแหน่งใน Java Slides
linktitle: การตั้งค่าแกนตำแหน่งใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ปรับปรุงแผนภูมิของคุณด้วย Aspose.Slides สำหรับ Java เรียนรู้วิธีการตั้งค่าแกนตำแหน่งในสไลด์ Java สร้างงานนำเสนอที่น่าทึ่ง และปรับแต่งเค้าโครงแผนภูมิได้อย่างง่ายดาย
weight: 16
url: /th/java/customization-and-formatting/setting-position-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# การตั้งค่าแกนตำแหน่งใน Java Slides


## รู้เบื้องต้นเกี่ยวกับการตั้งค่าแกนตำแหน่งใน Aspose.Slides สำหรับ Java

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีตั้งค่าแกนตำแหน่งในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java การวางตำแหน่งแกนจะมีประโยชน์เมื่อคุณต้องการปรับแต่งรูปลักษณ์และเค้าโครงของแผนภูมิของคุณ เราจะสร้างแผนภูมิคอลัมน์แบบกลุ่มและปรับตำแหน่งของแกนนอนระหว่างหมวดหมู่

## ข้อกำหนดเบื้องต้น

 ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: การสร้างงานนำเสนอ

ขั้นแรก มาสร้างงานนำเสนอใหม่เพื่อใช้งาน:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Your Document Directory"` ด้วยเส้นทางจริงไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิ

ต่อไป เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์ เราระบุประเภทแผนภูมิ ตำแหน่ง (พิกัด x, y) และขนาด (ความกว้างและความสูง) ของแผนภูมิ:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

ที่นี่ เราได้เพิ่มแผนภูมิคอลัมน์แบบกลุ่มที่ตำแหน่ง (50, 50) โดยมีความกว้าง 450 และความสูง 300 คุณสามารถปรับค่าเหล่านี้ได้ตามต้องการ

## ขั้นตอนที่ 3: การตั้งค่าแกนตำแหน่ง

หากต้องการตั้งค่าแกนตำแหน่งระหว่างหมวดหมู่ คุณสามารถใช้โค้ดต่อไปนี้:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

รหัสนี้จะตั้งค่าแกนนอนเพื่อแสดงระหว่างหมวดหมู่ ซึ่งอาจมีประโยชน์สำหรับเค้าโครงแผนภูมิบางรูปแบบ

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้ายนี้ มาบันทึกงานนำเสนอด้วยแผนภูมิกัน:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 แทนที่`"AsposeClusteredColumnChart.pptx"` ด้วยชื่อไฟล์ที่คุณต้องการ

แค่นั้นแหละ! คุณสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์สำเร็จแล้วและตั้งค่าแกนตำแหน่งระหว่างหมวดหมู่โดยใช้ Aspose.Slides สำหรับ Java

## กรอกซอร์สโค้ดให้สมบูรณ์
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีตั้งค่าแกนตำแหน่งในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java ด้วยการทำตามขั้นตอนที่ระบุไว้ในคู่มือนี้ คุณได้เรียนรู้วิธีสร้างแผนภูมิคอลัมน์แบบกลุ่มและปรับแต่งลักษณะที่ปรากฏโดยการวางตำแหน่งแกนนอนระหว่างหมวดหมู่ Aspose.Slides สำหรับ Java มีคุณสมบัติอันทรงพลังสำหรับการทำงานกับแผนภูมิและการนำเสนอ ทำให้เป็นเครื่องมืออันมีค่าสำหรับนักพัฒนา Java

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งแผนภูมิเพิ่มเติมได้อย่างไร

คุณสามารถปรับแต่งแง่มุมต่างๆ ของแผนภูมิได้ รวมถึงชุดข้อมูล ชื่อแผนภูมิ คำอธิบาย และอื่นๆ อ้างถึง[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/) สำหรับคำแนะนำโดยละเอียดและตัวอย่าง

### ฉันสามารถเปลี่ยนประเภทแผนภูมิได้หรือไม่?

 ใช่ คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแก้ไข`ChartType` พารามิเตอร์เมื่อเพิ่มแผนภูมิ Aspose.Slides สำหรับ Java รองรับแผนภูมิหลายประเภท เช่น แผนภูมิแท่ง แผนภูมิเส้น และอื่นๆ

### ฉันจะหาตัวอย่างและเอกสารประกอบเพิ่มเติมได้ที่ไหน

 คุณสามารถค้นหาเอกสารประกอบที่ครอบคลุมและตัวอย่างเพิ่มเติมได้ที่[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/) หน้าหนังสือ.

อย่าลืมกำจัดวัตถุการนำเสนอเมื่อคุณทำเสร็จแล้วเพื่อปล่อยทรัพยากรระบบ:

```java
if (pres != null) pres.dispose();
```

เพียงเท่านี้สำหรับบทช่วยสอนนี้ คุณได้เรียนรู้วิธีการตั้งค่าแกนตำแหน่งในแผนภูมิโดยใช้ Aspose.Slides สำหรับ Java
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
