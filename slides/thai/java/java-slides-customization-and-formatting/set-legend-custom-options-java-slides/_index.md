---
title: ตั้งค่าตัวเลือกแบบกำหนดเองของ Legend ใน Java Slides
linktitle: ตั้งค่าตัวเลือกแบบกำหนดเองของ Legend ใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่าตัวเลือกคำอธิบายแบบกำหนดเองใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java กำหนดตำแหน่งและขนาดคำอธิบายแผนภูมิในแผนภูมิ PowerPoint ของคุณ
weight: 14
url: /th/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าตัวเลือกแบบกำหนดเองของ Legend ใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่าตัวเลือกแบบกำหนดเองของ Legend ใน Java Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีการปรับแต่งคุณสมบัติคำอธิบายแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถแก้ไขตำแหน่ง ขนาด และคุณลักษณะอื่นๆ ของคำอธิบายเพื่อให้เหมาะกับความต้องการในการนำเสนอของคุณได้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Slides สำหรับ Java API แล้ว
- ตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: นำเข้าคลาสที่จำเป็น:

```java
// นำเข้า Aspose.Slides สำหรับคลาส Java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: ระบุเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:

```java
String dataDir = "Your Document Directory";
```

##  ขั้นตอนที่ 3: สร้างอินสแตนซ์ของ`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 4: เพิ่มสไลด์ในงานนำเสนอ:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## ขั้นตอนที่ 5: เพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## ขั้นตอนที่ 6 ตั้งค่าคุณสมบัติคำอธิบาย:

- ตั้งค่าตำแหน่ง X ของคำอธิบายแผนภูมิ (สัมพันธ์กับความกว้างของแผนภูมิ):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- ตั้งค่าตำแหน่ง Y ของคำอธิบายแผนภูมิ (สัมพันธ์กับความสูงของแผนภูมิ):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- ตั้งค่าความกว้างของคำอธิบาย (สัมพันธ์กับความกว้างของแผนภูมิ):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- กำหนดความสูงของคำอธิบาย (สัมพันธ์กับความสูงของแผนภูมิ):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## ขั้นตอนที่ 7: บันทึกงานนำเสนอลงดิสก์:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

แค่นั้นแหละ! คุณได้ปรับแต่งคุณสมบัติคำอธิบายแผนภูมิในงานนำเสนอ PowerPoint เรียบร้อยแล้วโดยใช้ Aspose.Slides สำหรับ Java

## กรอกซอร์สโค้ดให้สมบูรณ์สำหรับตัวเลือก Set Legend Custom ใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
try
{
	// รับข้อมูลอ้างอิงของสไลด์
	ISlide slide = presentation.getSlides().get_Item(0);
	// เพิ่มแผนภูมิคอลัมน์แบบกลุ่มบนสไลด์
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// ตั้งค่าคุณสมบัติคำอธิบายแผนภูมิ
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// เขียนงานนำเสนอลงดิสก์
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีปรับแต่งคุณสมบัติคำอธิบายแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถแก้ไขตำแหน่ง ขนาด และคุณลักษณะอื่นๆ ของคำอธิบายแผนภูมิเพื่อสร้างการนำเสนอที่ดึงดูดสายตาและให้ข้อมูลได้

## คำถามที่พบบ่อย

## ฉันจะเปลี่ยนตำแหน่งของตำนานได้อย่างไร?

 หากต้องการเปลี่ยนตำแหน่งของคำอธิบาย ให้ใช้`setX` และ`setY` วิธีการของวัตถุตำนาน ค่าจะถูกระบุโดยสัมพันธ์กับความกว้างและความสูงของแผนภูมิ

## ฉันจะปรับขนาดของคำอธิบายได้อย่างไร

 คุณสามารถปรับขนาดของคำอธิบายได้โดยใช้`setWidth` และ`setHeight` วิธีการของวัตถุตำนาน ค่าเหล่านี้สัมพันธ์กับความกว้างและความสูงของแผนภูมิด้วย

## ฉันสามารถปรับแต่งคุณสมบัติคำอธิบายแผนภูมิอื่นๆ ได้หรือไม่

ใช่ คุณสามารถปรับแต่งคุณลักษณะต่างๆ ของคำอธิบายได้ เช่น รูปแบบแบบอักษร เส้นขอบ สีพื้นหลัง และอื่นๆ สำรวจเอกสารประกอบของ Aspose.Slides เพื่อดูข้อมูลโดยละเอียดเกี่ยวกับการปรับแต่งคำอธิบายเพิ่มเติม
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
