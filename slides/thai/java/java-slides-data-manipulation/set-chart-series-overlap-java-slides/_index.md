---
title: ตั้งค่าชุดแผนภูมิที่ทับซ้อนกันใน Java Slides
linktitle: ตั้งค่าชุดแผนภูมิที่ทับซ้อนกันใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: ชุดแผนภูมิหลักซ้อนทับกันใน Java Slides ด้วย Aspose.Slides สำหรับ Java เรียนรู้วิธีปรับแต่งภาพแผนภูมิเพื่อการนำเสนอที่น่าทึ่งทีละขั้นตอน
weight: 16
url: /th/java/data-manipulation/set-chart-series-overlap-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าชุดแผนภูมิที่ทับซ้อนกันใน Java Slides


## ข้อมูลเบื้องต้นเกี่ยวกับการตั้งค่าการทับซ้อนของชุดแผนภูมิใน Java Slides

ในคู่มือที่ครอบคลุมนี้ เราจะเจาะลึกโลกที่น่าทึ่งของการจัดการชุดแผนภูมิที่ทับซ้อนกันใน Java Slides โดยใช้ Aspose.Slides อันทรงพลังสำหรับ Java API ไม่ว่าคุณจะเป็นนักพัฒนาที่มีประสบการณ์หรือเพิ่งเริ่มต้น บทช่วยสอนทีละขั้นตอนนี้จะช่วยให้คุณมีความรู้และซอร์สโค้ดที่จำเป็นสำหรับการทำงานที่สำคัญนี้ให้เชี่ยวชาญ

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

- สภาพแวดล้อมการพัฒนาจาวา
- Aspose.Slides สำหรับไลบรารี Java
- สภาพแวดล้อมการพัฒนาแบบบูรณาการ (IDE) ที่คุณเลือก

ตอนนี้เรามีเครื่องมือพร้อมแล้ว เรามาดำเนินการตั้งค่าชุดแผนภูมิที่ทับซ้อนกันกัน

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก เราต้องสร้างงานนำเสนอโดยที่เราจะเพิ่มแผนภูมิของเรา คุณสามารถกำหนดเส้นทางไปยังไดเร็กทอรีเอกสารของคุณได้ดังนี้:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิ

เราจะเพิ่มแผนภูมิคอลัมน์แบบกลุ่มในการนำเสนอของเราโดยใช้โค้ดต่อไปนี้:

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## ขั้นตอนที่ 3: การปรับการทับซ้อนกันของซีรี่ส์

หากต้องการตั้งค่าการทับซ้อนของซีรีส์ เราจะตรวจสอบว่าปัจจุบันตั้งค่าเป็นศูนย์หรือไม่ จากนั้นจึงปรับเปลี่ยนตามความจำเป็น:

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
if (series.get_Item(0).getOverlap() == 0)
{
    // การตั้งค่าชุดการทับซ้อนกัน
    series.get_Item(0).getParentSeriesGroup().setOverlap((byte) -30);
}
```

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้ายนี้ เราจะบันทึกการนำเสนอที่แก้ไขแล้วของเราไปยังไดเร็กทอรีที่ระบุ:

```java
presentation.save(dataDir + "SetChartSeriesOverlap_out.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับชุดแผนภูมิชุดที่ทับซ้อนกันใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	// กำลังเพิ่มแผนภูมิ
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	if (series.get_Item(0).getOverlap() == 0)
	{
		// การตั้งค่าชุดการทับซ้อนกัน
		series.get_Item(0).getParentSeriesGroup().setOverlap((byte) -30);
	}
	// เขียนไฟล์การนำเสนอลงดิสก์
	presentation.save(dataDir + "SetChartSeriesOverlap_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

ยินดีด้วย! คุณได้เรียนรู้วิธีตั้งค่าชุดแผนภูมิที่ทับซ้อนกันใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java เรียบร้อยแล้ว นี่อาจเป็นทักษะที่มีคุณค่าเมื่อทำงานกับการนำเสนอ เนื่องจากช่วยให้คุณปรับแต่งแผนภูมิให้ตรงตามข้อกำหนดเฉพาะได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

 หากต้องการเปลี่ยนประเภทแผนภูมิ คุณสามารถใช้`ChartType` การแจงนับเมื่อเพิ่มแผนภูมิ เพียงแค่แทนที่`ChartType.ClusteredColumn` ด้วยประเภทกราฟที่ต้องการ เช่น`ChartType.Line` หรือ`ChartType.Pie`.

### มีตัวเลือกการปรับแต่งแผนภูมิอื่นๆ อะไรบ้าง?

Aspose.Slides สำหรับ Java นำเสนอตัวเลือกการปรับแต่งที่หลากหลายสำหรับแผนภูมิ คุณสามารถปรับเปลี่ยนชื่อแผนภูมิ ป้ายข้อมูล สี และอื่นๆ ได้ โปรดดูเอกสารประกอบสำหรับข้อมูลโดยละเอียด

### Aspose.Slides สำหรับ Java เหมาะสำหรับการนำเสนอระดับมืออาชีพหรือไม่

ใช่ Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพสำหรับการสร้างและจัดการงานนำเสนอ มีการใช้กันอย่างแพร่หลายในการตั้งค่าระดับมืออาชีพเพื่อสร้างสไลด์โชว์คุณภาพสูงพร้อมคุณสมบัติขั้นสูง

### ฉันสามารถสร้างงานนำเสนออัตโนมัติด้วย Aspose.Slides สำหรับ Java ได้หรือไม่

อย่างแน่นอน! Aspose.Slides สำหรับ Java มี API สำหรับการสร้างงานนำเสนอตั้งแต่เริ่มต้นหรือแก้ไขงานนำเสนอที่มีอยู่ คุณสามารถทำให้กระบวนการสร้างงานนำเสนอทั้งหมดเป็นแบบอัตโนมัติเพื่อประหยัดเวลาและความพยายาม

### ฉันจะค้นหาแหล่งข้อมูลเพิ่มเติมและตัวอย่างสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 สำหรับเอกสารและตัวอย่างที่ครอบคลุม โปรดไปที่หน้าอ้างอิง Aspose.Slides สำหรับ Java:[Aspose.Slides สำหรับการอ้างอิง Java API](https://reference.aspose.com/slides/java/)
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
