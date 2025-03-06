---
title: รับค่าและมาตราส่วนหน่วยจากแกนใน Java Slides
linktitle: รับค่าและมาตราส่วนหน่วยจากแกนใน Java Slides
second_title: Aspose.Slides Java PowerPoint การประมวลผล API
description: เรียนรู้วิธีรับค่าและมาตราส่วนหน่วยจากแกนใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java ปรับปรุงความสามารถในการวิเคราะห์ข้อมูลของคุณ
weight: 20
url: /th/java/data-manipulation/get-values-unit-scale-axis-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## ข้อมูลเบื้องต้นเกี่ยวกับการรับค่าและมาตราส่วนหน่วยจากแกนใน Java Slides

ในบทช่วยสอนนี้ เราจะสำรวจวิธีดึงค่าและมาตราส่วนหน่วยจากแกนใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java API ไม่ว่าคุณจะทำงานในโครงการแสดงข้อมูลเป็นภาพหรือต้องการวิเคราะห์ข้อมูลแผนภูมิในแอปพลิเคชัน Java ของคุณ การทำความเข้าใจวิธีเข้าถึงค่าแกนถือเป็นสิ่งสำคัญ เราจะแนะนำคุณตลอดกระบวนการทีละขั้นตอน โดยให้ตัวอย่างโค้ดไปพร้อมกัน

## ข้อกำหนดเบื้องต้น

ก่อนที่เราจะเจาะลึกโค้ด ตรวจสอบให้แน่ใจว่าคุณมีข้อกำหนดเบื้องต้นต่อไปนี้:

1. สภาพแวดล้อมการพัฒนา Java: ตรวจสอบให้แน่ใจว่าคุณได้ติดตั้ง Java บนระบบของคุณและคุ้นเคยกับแนวคิดการเขียนโปรแกรม Java

2.  Aspose.Slides สำหรับ Java: ดาวน์โหลดและติดตั้งไลบรารี Aspose.Slides สำหรับ Java จากไฟล์[ลิ้งค์ดาวน์โหลด](https://releases.aspose.com/slides/java/).

## ขั้นตอนที่ 1: การสร้างงานนำเสนอ

ในการเริ่มต้น เรามาสร้างงานนำเสนอใหม่โดยใช้ Aspose.Slides สำหรับ Java:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 แทนที่`"Your Document Directory"` พร้อมเส้นทางไปยังไดเร็กทอรีที่คุณต้องการบันทึกงานนำเสนอ

## ขั้นตอนที่ 2: การเพิ่มแผนภูมิ

ต่อไป เราจะเพิ่มแผนภูมิลงในงานนำเสนอ ในตัวอย่างนี้ เราจะสร้างแผนภูมิพื้นที่:

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
chart.validateChartLayout();
```

เราได้เพิ่มแผนภูมิพื้นที่ลงในสไลด์แรกของงานนำเสนอ คุณสามารถปรับแต่งประเภทแผนภูมิและตำแหน่งได้ตามต้องการ

## ขั้นตอนที่ 3: การดึงค่าแกนตั้ง

ตอนนี้ เรามาดึงค่าจากแกนตั้งของแผนภูมิกันดีกว่า:

```java
double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
```

ตรงนี้ เราได้ค่าสูงสุดและต่ำสุดของแกนตั้ง ค่าเหล่านี้มีประโยชน์สำหรับงานวิเคราะห์ข้อมูลต่างๆ

## ขั้นตอนที่ 4: การดึงค่าแกนนอน

ในทำนองเดียวกัน เราสามารถดึงค่าจากแกนนอนได้:

```java
double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
```

 ที่`majorUnit` และ`minorUnit` ค่าแสดงถึงหน่วยหลักและหน่วยรองบนแกนนอนตามลำดับ

## ขั้นตอนที่ 5: บันทึกการนำเสนอ

เมื่อเราดึงค่าแกนแล้ว เราก็สามารถบันทึกการนำเสนอได้:

```java
pres.save(dataDir + "ChartValues.pptx", SaveFormat.Pptx);
```

รหัสนี้จะบันทึกงานนำเสนอด้วยค่าแกนที่ดึงมาลงในไฟล์ PowerPoint

## กรอกซอร์สโค้ดเพื่อรับค่าและมาตราส่วนหน่วยจากแกนใน Java Slides

```java
// เส้นทางไปยังไดเร็กทอรีเอกสาร
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
	chart.validateChartLayout();
	double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
	double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
	double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
	double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
	// กำลังบันทึกการนำเสนอ
	pres.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## บทสรุป

ในบทช่วยสอนนี้ เราได้สำรวจวิธีรับค่าและมาตราส่วนหน่วยจากแกนใน Java Slides โดยใช้ Aspose.Slides สำหรับ Java สิ่งนี้มีประโยชน์อย่างเหลือเชื่อเมื่อทำงานกับแผนภูมิและวิเคราะห์ข้อมูลภายในแอปพลิเคชัน Java ของคุณ Aspose.Slides for Java มีเครื่องมือที่คุณต้องการในการทำงานกับงานนำเสนอโดยทางโปรแกรม ช่วยให้คุณสามารถควบคุมข้อมูลแผนภูมิและอื่นๆ อีกมากมาย

## คำถามที่พบบ่อย

### ฉันจะปรับแต่งประเภทแผนภูมิใน Aspose.Slides สำหรับ Java ได้อย่างไร

 หากต้องการปรับแต่งประเภทแผนภูมิ เพียงแทนที่`ChartType.Area` ด้วยประเภทแผนภูมิที่ต้องการเมื่อเพิ่มแผนภูมิลงในงานนำเสนอของคุณ

### ฉันสามารถเปลี่ยนลักษณะที่ปรากฏของป้ายชื่อแกนแผนภูมิได้หรือไม่

ใช่ คุณสามารถปรับแต่งลักษณะที่ปรากฏของป้ายกำกับแกนแผนภูมิได้โดยใช้ Aspose.Slides สำหรับ Java โปรดดูเอกสารประกอบสำหรับคำแนะนำโดยละเอียด

### Aspose.Slides สำหรับ Java เข้ากันได้กับ Java เวอร์ชันล่าสุดหรือไม่

Aspose.Slides for Java ได้รับการอัปเดตเป็นประจำเพื่อรองรับ Java เวอร์ชันล่าสุด เพื่อให้มั่นใจว่าสามารถเข้ากันได้กับการพัฒนา Java ล่าสุด

### ฉันสามารถใช้ Aspose.Slides สำหรับ Java ในโครงการเชิงพาณิชย์ได้หรือไม่

ได้ คุณสามารถใช้ Aspose.Slides สำหรับ Java ในโครงการเชิงพาณิชย์ได้ มีตัวเลือกใบอนุญาตเพื่อให้เหมาะกับความต้องการของโครงการต่างๆ

### ฉันจะหาแหล่งข้อมูลเพิ่มเติมและเอกสารประกอบสำหรับ Aspose.Slides สำหรับ Java ได้ที่ไหน

 คุณสามารถค้นหาเอกสารที่ครอบคลุมและแหล่งข้อมูลเพิ่มเติมได้ที่[Aspose.Slides สำหรับเอกสาร Java](https://reference.aspose.com/slides/java/) เว็บไซต์.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
