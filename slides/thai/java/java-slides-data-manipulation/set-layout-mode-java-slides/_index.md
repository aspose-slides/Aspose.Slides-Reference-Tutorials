---
title: ตั้งค่าโหมดเค้าโครงใน Java Slides
linktitle: ตั้งค่าโหมดเค้าโครงใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีตั้งค่าโหมดเค้าโครงสำหรับสไลด์ Java โดยใช้ Aspose.Slides ปรับแต่งตำแหน่งและขนาดของแผนภูมิในคำแนะนำทีละขั้นตอนพร้อมซอร์สโค้ด
type: docs
weight: 23
url: /th/java/data-manipulation/set-layout-mode-java-slides/
---

## รู้เบื้องต้นเกี่ยวกับการตั้งค่าโหมดเค้าโครงใน Java Slides

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีตั้งค่าโหมดเค้าโครงสำหรับแผนภูมิในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java โหมดเค้าโครงจะกำหนดตำแหน่งและขนาดของแผนภูมิภายในสไลด์

## ข้อกำหนดเบื้องต้น

 ก่อนที่เราจะเริ่มต้น ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดห้องสมุดได้จาก[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรก เราต้องสร้างงานนำเสนอใหม่

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มสไลด์และแผนภูมิ

ต่อไปเราจะเพิ่มสไลด์และแผนภูมิลงไป ในตัวอย่างนี้ เราจะสร้างแผนภูมิคอลัมน์แบบกลุ่ม

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## ขั้นตอนที่ 3: ตั้งค่าเค้าโครงแผนภูมิ

 ตอนนี้ เรามาตั้งค่าเค้าโครงสำหรับแผนภูมิกันดีกว่า เราจะปรับตำแหน่งและขนาดของแผนภูมิภายในสไลด์โดยใช้`setX`, `setY`, `setWidth`, `setHeight` วิธีการ นอกจากนี้เราจะตั้งค่า`LayoutTargetType` เพื่อกำหนดโหมดเค้าโครง

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

ในตัวอย่างนี้ เราได้ตั้งค่าแผนภูมิให้มีประเภทเป้าหมายเค้าโครงเป็น "ด้านใน" ซึ่งหมายความว่าจะมีตำแหน่งและขนาดสัมพันธ์กับพื้นที่ด้านในของสไลด์

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้าย มาบันทึกงานนำเสนอด้วยการตั้งค่าเค้าโครงแผนภูมิกัน

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## กรอกซอร์สโค้ดสำหรับโหมดเค้าโครงการตั้งค่าใน Java Slides

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## บทสรุป

 ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าโหมดเค้าโครงสำหรับแผนภูมิในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งตำแหน่งและขนาดของแผนภูมิได้ตามความต้องการเฉพาะของคุณโดยการปรับค่าใน`setX`, `setY`, `setWidth`, `setHeight` , และ`setLayoutTargetType`วิธีการ ซึ่งช่วยให้คุณควบคุมตำแหน่งของแผนภูมิภายในสไลด์ของคุณได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนโหมดเค้าโครงสำหรับแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

 หากต้องการเปลี่ยนโหมดเค้าโครงสำหรับแผนภูมิใน Aspose.Slides สำหรับ Java คุณสามารถใช้`setLayoutTargetType` วิธีการบนพื้นที่ลงจุดของแผนภูมิ คุณสามารถตั้งค่าเป็นอย่างใดอย่างหนึ่ง`LayoutTargetType.Inner` หรือ`LayoutTargetType.Outer` ขึ้นอยู่กับเค้าโครงที่คุณต้องการ

### ฉันสามารถปรับแต่งตำแหน่งและขนาดของแผนภูมิภายในสไลด์ได้หรือไม่

 ใช่ คุณสามารถปรับแต่งตำแหน่งและขนาดของแผนภูมิภายในสไลด์ได้โดยใช้`setX`, `setY`, `setWidth` , และ`setHeight` วิธีการบนพื้นที่ลงจุดของแผนภูมิ ปรับค่าเหล่านี้เพื่อวางตำแหน่งและปรับขนาดแผนภูมิตามความต้องการของคุณ

### ฉันจะหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 คุณสามารถค้นหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ใน[เอกสารประกอบ](https://reference.aspose.com/slides/java/)- ประกอบด้วยการอ้างอิง API โดยละเอียดและตัวอย่างเพื่อช่วยให้คุณทำงานกับสไลด์และแผนภูมิใน Java ได้อย่างมีประสิทธิภาพ