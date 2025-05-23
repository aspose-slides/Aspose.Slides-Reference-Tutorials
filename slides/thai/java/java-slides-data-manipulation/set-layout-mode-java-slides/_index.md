---
"description": "เรียนรู้วิธีตั้งค่าโหมดเค้าโครงสำหรับสไลด์ Java โดยใช้ Aspose.Slides ปรับแต่งตำแหน่งและขนาดของแผนภูมิในคู่มือทีละขั้นตอนพร้อมโค้ดต้นฉบับนี้"
"linktitle": "ตั้งค่าโหมดเค้าโครงใน Java Slides"
"second_title": "API การประมวลผล Java PowerPoint ของ Aspose.Slides"
"title": "ตั้งค่าโหมดเค้าโครงใน Java Slides"
"url": "/th/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# ตั้งค่าโหมดเค้าโครงใน Java Slides


## บทนำสู่การตั้งค่าโหมดเค้าโครงใน Java Slides

ในบทช่วยสอนนี้ เราจะเรียนรู้วิธีตั้งค่าโหมดเค้าโครงสำหรับแผนภูมิในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java โหมดเค้าโครงจะกำหนดตำแหน่งและขนาดของแผนภูมิภายในสไลด์

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเริ่ม ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จาก [ที่นี่](https://releases-aspose.com/slides/java/).

## ขั้นตอนที่ 1: สร้างงานนำเสนอ

ขั้นแรกเราต้องสร้างการนำเสนอใหม่

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## ขั้นตอนที่ 2: เพิ่มสไลด์และแผนภูมิ

ต่อไปเราจะเพิ่มสไลด์และแผนภูมิลงไป ในตัวอย่างนี้ เราจะสร้างแผนภูมิคอลัมน์แบบคลัสเตอร์

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## ขั้นตอนที่ 3: ตั้งค่าเค้าโครงแผนภูมิ

ต่อไปเรามาตั้งค่าเค้าโครงของแผนภูมิกัน เราจะปรับตำแหน่งและขนาดของแผนภูมิภายในสไลด์โดยใช้ `setX`- `setY`- `setWidth`- `setHeight` วิธีการ นอกจากนี้เราจะกำหนด `LayoutTargetType` เพื่อกำหนดโหมดเค้าโครง

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

ในตัวอย่างนี้ เราได้ตั้งค่าแผนภูมิเพื่อให้มีเป้าหมายเค้าโครงประเภทเป็น "ด้านใน" ซึ่งหมายความว่าแผนภูมิจะถูกวางตำแหน่งและมีขนาดสัมพันธ์กับพื้นที่ด้านในของสไลด์

## ขั้นตอนที่ 4: บันทึกการนำเสนอ

สุดท้ายเรามาบันทึกการนำเสนอโดยใช้การตั้งค่าเค้าโครงแผนภูมิกัน

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## โค้ดต้นฉบับสมบูรณ์สำหรับโหมดเค้าโครงชุดใน Java Slides

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

ในบทช่วยสอนนี้ เราได้เรียนรู้วิธีตั้งค่าโหมดเค้าโครงสำหรับแผนภูมิในสไลด์ Java โดยใช้ Aspose.Slides สำหรับ Java คุณสามารถปรับแต่งตำแหน่งและขนาดของแผนภูมิตามความต้องการเฉพาะของคุณได้โดยปรับค่าใน `setX`- `setY`- `setWidth`- `setHeight`, และ `setLayoutTargetType` วิธีการนี้ช่วยให้คุณควบคุมการวางแผนภูมิภายในสไลด์ของคุณได้

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนโหมดเค้าโครงสำหรับแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

หากต้องการเปลี่ยนโหมดเค้าโครงสำหรับแผนภูมิใน Aspose.Slides สำหรับ Java คุณสามารถใช้ `setLayoutTargetType` วิธีการบนพื้นที่พล็อตของแผนภูมิ คุณสามารถตั้งค่าให้เป็น `LayoutTargetType.Inner` หรือ `LayoutTargetType.Outer` ขึ้นอยู่กับเค้าโครงที่คุณต้องการ

### ฉันสามารถปรับแต่งตำแหน่งและขนาดของแผนภูมิภายในสไลด์ได้หรือไม่

ใช่ คุณสามารถปรับแต่งตำแหน่งและขนาดของแผนภูมิภายในสไลด์ได้โดยใช้ `setX`- `setY`- `setWidth`, และ `setHeight` วิธีการบนพื้นที่พล็อตของแผนภูมิ ปรับค่าเหล่านี้เพื่อวางตำแหน่งและขนาดของแผนภูมิตามความต้องการของคุณ

### ฉันสามารถหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ที่ไหน

คุณสามารถค้นหาข้อมูลเพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้ใน [เอกสารประกอบ](https://reference.aspose.com/slides/java/)มีข้อมูลอ้างอิงและตัวอย่าง API โดยละเอียดเพื่อช่วยให้คุณทำงานกับสไลด์และแผนภูมิได้อย่างมีประสิทธิภาพใน Java

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}