---
title: รับความกว้างและความสูงจากพื้นที่แปลงแผนภูมิใน Java Slides
linktitle: รับความกว้างและความสูงจากพื้นที่แปลงแผนภูมิใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีดึงข้อมูลขนาดพื้นที่ลงจุดแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java พัฒนาทักษะการทำงานอัตโนมัติของ PowerPoint ของคุณ
weight: 21
url: /th/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# รับความกว้างและความสูงจากพื้นที่แปลงแผนภูมิใน Java Slides


## การแนะนำ

แผนภูมิเป็นวิธีที่มีประสิทธิภาพในการแสดงภาพข้อมูลในงานนำเสนอ PowerPoint บางครั้ง คุณอาจต้องทราบขนาดของพื้นที่การลงจุดของแผนภูมิด้วยเหตุผลหลายประการ เช่น การปรับขนาดหรือการเปลี่ยนตำแหน่งองค์ประกอบภายในแผนภูมิ คู่มือนี้จะสาธิตวิธีรับความกว้างและความสูงของพื้นที่ลงจุดโดยใช้ Java และ Aspose.Slides สำหรับ Java

## ข้อกำหนดเบื้องต้น

 ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้งและตั้งค่าไลบรารี Aspose.Slides สำหรับ Java ในโปรเจ็กต์ Java ของคุณแล้ว คุณสามารถดาวน์โหลดไลบรารีได้จากเว็บไซต์ Aspose[ที่นี่](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: การตั้งค่าสภาพแวดล้อม

ตรวจสอบให้แน่ใจว่าคุณได้เพิ่มไลบรารี Aspose.Slides สำหรับ Java ให้กับโปรเจ็กต์ Java ของคุณ คุณสามารถทำได้โดยการรวมไลบรารีไว้ในการขึ้นต่อกันของโปรเจ็กต์ของคุณ หรือโดยการเพิ่มไฟล์ JAR ด้วยตนเอง

## ขั้นตอนที่ 2: การสร้างงานนำเสนอ PowerPoint

เริ่มต้นด้วยการสร้างงานนำเสนอ PowerPoint และเพิ่มสไลด์ลงไป นี่จะทำหน้าที่เป็นคอนเทนเนอร์สำหรับแผนภูมิของเรา

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีเอกสารของคุณ

## ขั้นตอนที่ 3: การเพิ่มแผนภูมิ

ตอนนี้ เรามาเพิ่มแผนภูมิคอลัมน์แบบกลุ่มลงในสไลด์ เราจะตรวจสอบเค้าโครงแผนภูมิด้วย

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

รหัสนี้สร้างแผนภูมิคอลัมน์แบบคลัสเตอร์ที่ตำแหน่ง (100, 100) ด้วยขนาด (500, 350)

## ขั้นตอนที่ 4: รับขนาดพื้นที่แปลง

หากต้องการดึงข้อมูลความกว้างและความสูงของพื้นที่ลงจุดของแผนภูมิ เราสามารถใช้โค้ดต่อไปนี้:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 ทีนี้ตัวแปรต่างๆ`x`, `y`, `w` , และ`h` มีค่าตามลำดับสำหรับพิกัด X, พิกัด Y, ความกว้าง และความสูงของพื้นที่ลงจุด

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

สุดท้าย ให้บันทึกงานนำเสนอด้วยแผนภูมิ

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 ตรวจสอบให้แน่ใจว่าได้เปลี่ยน`"Chart_out.pptx"` ด้วยชื่อไฟล์เอาต์พุตที่คุณต้องการ

## กรอกซอร์สโค้ดเพื่อรับความกว้างและความสูงจากพื้นที่แปลงแผนภูมิใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// บันทึกการนำเสนอด้วยแผนภูมิ
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทความนี้ เราได้กล่าวถึงวิธีการรับความกว้างและความสูงของพื้นที่ลงจุดของแผนภูมิใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API ข้อมูลนี้อาจมีคุณค่าเมื่อคุณต้องการปรับเค้าโครงแผนภูมิของคุณแบบไดนามิกภายในงานนำเสนอ PowerPoint

## คำถามที่พบบ่อย

### ฉันจะเปลี่ยนประเภทแผนภูมิเป็นอย่างอื่นที่ไม่ใช่คอลัมน์แบบคลัสเตอร์ได้อย่างไร

 คุณสามารถเปลี่ยนประเภทแผนภูมิได้โดยการแทนที่`ChartType.ClusteredColumn` พร้อมระบุประเภทแผนภูมิที่ต้องการ เช่น`ChartType.Line` หรือ`ChartType.Pie`.

### ฉันสามารถแก้ไขคุณสมบัติอื่นๆ ของแผนภูมิได้หรือไม่

ได้ คุณสามารถแก้ไขคุณสมบัติต่างๆ ของแผนภูมิได้ เช่น ข้อมูล ป้ายกำกับ และการจัดรูปแบบ โดยใช้ Aspose.Slides สำหรับ Java API โปรดดูเอกสารประกอบสำหรับรายละเอียดเพิ่มเติม

### Aspose.Slides สำหรับ Java เหมาะสำหรับระบบอัตโนมัติ PowerPoint ระดับมืออาชีพหรือไม่

ใช่ Aspose.Slides สำหรับ Java เป็นไลบรารีที่มีประสิทธิภาพสำหรับงาน PowerPoint อัตโนมัติในแอปพลิเคชัน Java โดยมีคุณสมบัติที่ครอบคลุมสำหรับการทำงานกับงานนำเสนอ สไลด์ รูปร่าง แผนภูมิ และอื่นๆ

### ฉันจะเรียนรู้เพิ่มเติมเกี่ยวกับ Aspose.Slides สำหรับ Java ได้อย่างไร

 คุณสามารถค้นหาเอกสารและตัวอย่างที่ครอบคลุมได้ที่หน้าเอกสารประกอบของ Aspose.Slides สำหรับ Java[ที่นี่](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
