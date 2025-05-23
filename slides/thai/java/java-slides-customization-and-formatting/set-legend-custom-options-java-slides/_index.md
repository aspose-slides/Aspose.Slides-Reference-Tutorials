---
"description": "เรียนรู้วิธีตั้งค่าตัวเลือกคำอธิบายแบบกำหนดเองใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java ปรับแต่งตำแหน่งและขนาดของคำอธิบายในแผนภูมิ PowerPoint ของคุณ"
"linktitle": "ตั้งค่าตัวเลือกกำหนดเองของตำนานใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าตัวเลือกกำหนดเองของตำนานใน Java Slides"
"url": "/th/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าตัวเลือกกำหนดเองของตำนานใน Java Slides


## การแนะนำการตั้งค่าตัวเลือกกำหนดเองของตำนานใน Java Slides

ในบทช่วยสอนนี้ เราจะสาธิตวิธีปรับแต่งคุณสมบัติของคำอธิบายแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับเปลี่ยนตำแหน่ง ขนาด และคุณลักษณะอื่นๆ ของคำอธิบายแผนภูมิให้เหมาะกับความต้องการในการนำเสนอของคุณได้

## ข้อกำหนดเบื้องต้น

ก่อนที่คุณจะเริ่มต้น โปรดตรวจสอบให้แน่ใจว่าคุณมีสิ่งต่อไปนี้:

- ติดตั้ง Aspose.Slides สำหรับ Java API แล้ว
- การตั้งค่าสภาพแวดล้อมการพัฒนา Java

## ขั้นตอนที่ 1: นำเข้าคลาสที่จำเป็น:

```java
// นำเข้า Aspose.Slides สำหรับคลาส Java
import com.aspose.slides.*;
```

## ขั้นตอนที่ 2: ระบุเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ:

```java
String dataDir = "Your Document Directory";
```

## ขั้นตอนที่ 3: สร้างอินสแตนซ์ของ `Presentation` ระดับ:

```java
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 4: เพิ่มสไลด์ลงในการนำเสนอ:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## ขั้นตอนที่ 5: เพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## ขั้นตอนที่ 6. ตั้งค่าคุณสมบัติคำอธิบาย:

- กำหนดตำแหน่ง X ของคำอธิบาย (เทียบกับความกว้างของแผนภูมิ):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- ตั้งค่าตำแหน่ง Y ของคำอธิบาย (เทียบกับความสูงของแผนภูมิ):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- กำหนดความกว้างของคำอธิบาย (เทียบกับความกว้างของแผนภูมิ):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- ตั้งค่าความสูงของตำนาน (เทียบกับความสูงของแผนภูมิ):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## ขั้นตอนที่ 7: บันทึกการนำเสนอลงในดิสก์:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

เสร็จเรียบร้อย! คุณปรับแต่งคุณสมบัติคำอธิบายแผนภูมิในงานนำเสนอ PowerPoint ได้สำเร็จแล้วโดยใช้ Aspose.Slides สำหรับ Java

## โค้ดต้นฉบับสมบูรณ์สำหรับตัวเลือกกำหนดเองของชุดคำอธิบายใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
// สร้างอินสแตนซ์ของคลาสการนำเสนอ
Presentation presentation = new Presentation();
try
{
	// รับข้อมูลอ้างอิงของสไลด์
	ISlide slide = presentation.getSlides().get_Item(0);
	// เพิ่มแผนภูมิคอลัมน์แบบคลัสเตอร์บนสไลด์
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// ตั้งค่าคุณสมบัติตำนาน
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// เขียนการนำเสนอลงดิสก์
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## บทสรุป

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีปรับแต่งคุณสมบัติของคำอธิบายแผนภูมิในงานนำเสนอ PowerPoint โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับเปลี่ยนตำแหน่ง ขนาด และคุณลักษณะอื่นๆ ของคำอธิบายแผนภูมิเพื่อสร้างงานนำเสนอที่น่าสนใจและให้ข้อมูล

## คำถามที่พบบ่อย

## ฉันจะเปลี่ยนตำแหน่งตำนานได้อย่างไร?

หากต้องการเปลี่ยนตำแหน่งของตำนาน ให้ใช้ `setX` และ `setY` วิธีการของวัตถุตำนาน ค่าจะถูกระบุสัมพันธ์กับความกว้างและความสูงของแผนภูมิ

## ฉันจะปรับขนาดของตำนานได้อย่างไร

คุณสามารถปรับขนาดของตำนานได้โดยใช้ `setWidth` และ `setHeight` วิธีการของวัตถุตำนาน ค่าเหล่านี้ยังสัมพันธ์กับความกว้างและความสูงของแผนภูมิด้วย

## ฉันสามารถปรับแต่งคุณลักษณะตำนานอื่น ๆ ได้หรือไม่

ใช่ คุณสามารถปรับแต่งคุณลักษณะต่างๆ ของคำอธิบายได้ เช่น แบบอักษร ขอบ สีพื้นหลัง และอื่นๆ อีกมากมาย อ่านเอกสาร Aspose.Slides เพื่อดูข้อมูลโดยละเอียดเกี่ยวกับการปรับแต่งคำอธิบายเพิ่มเติม

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}